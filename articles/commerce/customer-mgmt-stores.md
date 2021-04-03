---
title: Kundhantering i butiker
description: Det här avsnittet förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8a1b360ba6a2d32e38e101f25f108094a00190c8
ms.sourcegitcommit: 8a14eac1c27f10c2b1b02ac9ad82339f5e127602
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "5555057"
---
# <a name="customer-management-in-stores"></a>Kundhantering i butiker

[!include [banner](includes/banner.md)]

Det här avsnittet förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.

Det är viktigt att butikspersonalen kan skapa och redigera kundposter i kassan. På så sätt kan de samla in uppdateringar av kundinformationen som t.ex. e-postadress, telefonnummer och adress. Den här informationen är användbar i andra system, till exempel marknadsföring, eftersom effektiviteten hos dessa system beror på hur korrekta kunddata är.

Säljare kan utlösa arbetsflödet för kundskapande från två kassastartpunkter. De kan välja en knapp som är mappad till operationen **Lägga till kund** och de kan välja **Skapa kund** i appfältet på sökresultatsidan. I båda fall visas dialogrutan **Ny kund** där säljföretag kan ange nödvändiga kunduppgifter, såsom kundens namn, e-postadress, telefonnummer, adress och all ytterligare information som är relevant för verksamheten. Att ytterligare information kan fångas in med hjälp av de kundattribut som är associerade med kunden. Mer information om kundattribut finns i [Kundattribut](dev-itpro/customer-attributes.md).

Säljare kan också samla in sekundära e-postadresser och telefonnummer. De kan också fånga in kundens önskemål om att ta emot marknadsföringsinformation via någon av de sekundära e-postadresserna eller telefonnummer. För att aktivera denna funktion måste återförsäljare aktivera funktionen **Samla in flera e-postmeddelanden och telefonnummer och godkännande för marknadsföring på dessa kontakter** i arbetsytan **Funktionshantering** i Commerce-administration (**Systemadministration \> Arbetsytor \> Funktionshantering**).

## <a name="default-customer-properties"></a>Standardkundegenskaper

Detaljhandlare kan använda sidan **Alla butiker** i Commerce-administration (**Retail och Commerce \> Kanaler \> Butiker**) för att associera en standardkund till varje butik. I Commerce kopieras sedan de egenskaper som har definierats för standardkunden till alla nya kundposter som skapas. Till exempel visar dialogrutan **Skapa kund** egenskaper som ärvs från standardkunden som är associerad med butiken. Dessa egenskaper omfattar kundtyp, kundgrupp, kvittoinställning, valuta och språk. Eventuella anknytningar (gruppering av kunder) ärvs också från standardkunden. Ekonomiska dimensioner ärvs dock från den kundgrupp som associeras med standardkunden, inte från standardkunden.

Säljare kan fånga in flera adresser för en kund. Kundens namn och telefonnummer ärvs från den kontaktinformation som är kopplad till varje adress. Snabbflikarna **Adresser** för en kundpost innehåller ett fält för **Syfte** som säljarna kan redigera. Om kundtypen är **Person** är standardvärdet **Start**. Om kundtypen är **Organisation** är standardvärdet **Företag**. Andra värden som det här fältet stöder **Start**, **Kontor** och **Brevlåda**. Värdet i fältet **Land** för en adress ärvs från den primära adressen som anges på sidan **Driftenhet** i Commerce-administration i **Organisationsadministration \> Organisationer \> Driftenheter**.

## <a name="sync-customers-and-async-customers"></a>Synkrona och asynkrona kunder

I Commerce finns det två sätt att skapa kunder: Synkron (eller Synk) och Asynkron (eller Asynk). Kunder skapas som standard synkront. Med andra ord skapas de i Commerce-administration i realtid. Synkroniseringsläget för kunder är fördelaktigt eftersom nya kunder kan sökas omedelbart över kanaler. Den har emellertid även ett problem. Eftersom det genererar [Commerce Data Exchange: realtidstjänst](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) anropar till Commerce-administration kan prestanda påverkas om många samtidiga kundsamtal görs.

Om alternativet **Skapa kund i asynkront läge** anges till **Ja** i butikens funktionsprofil (**Retail och Commerce \> Kanalinställning \> Inställning av online-butik \> Funktionsprofiler**), realtidssamtal används inte för att skapa kundposter i kanaldatabasen. Asynkront kundgenereringsläge påverkar inte prestandan i Commerce-administration. En tillfällig, global unik identifierare (GUID) tilldelas varje ny asynkron kundpost och används som kundkonto-ID. Denna GUID inte visas för kassaanvändare. I stället visas **väntande synkronisering** som kundkonto-ID. Även om denna konfiguration tvingar kunder att skapas asynkront, observera att redigeringar till kundposter alltid görs synkront.

### <a name="convert-async-customers-to-sync-customers"></a>Konvertera asynkrona kunder till synkrona kunder

Om du vill konvertera asynkrona kunder till synkrona kunder måste du först köra P-jobbet för att skicka asynkrona kunderna till Commerce-administration. Kör sedan jobbet **Synkronisera kunder och affärspartners från asynkrona läge** för att skapa kundkonto-ID. Kör slutligen **1010** jobbet om du vill synkronisera de nya kundkonto-ID till kanalerna.

### <a name="async-customer-limitations"></a>Asynkrona kundbegränsningar

Asynkrona kundfunktionen har för närvarande följande begränsningar:

- Asynkrona kundposter kan inte redigeras om inte kunden har skapats i Commerce-administration och det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.
- Anknytningar kan inte associeras med asynkrona kunder. Därför ärver inte nya asynkrona kunder anknytningar från standardkunden.
- Förmånskort kan inte utfärdas till asynkrona kunder såvida inte det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.
- Sekundära e-postadresser och telefonnummer kan inte fångas in för asynkrona kunder.

### <a name="customer-creation-in-pos-offline-mode"></a>Kundskapa i kassa offlineläge

Om kassan är offline medan läget för asynkron kundgenerering är aktiverat, skapas nya kundposter asynkront. Om kassan är offline medan läget för asynkron kundgenerering är inaktiverat, växlar systemet automatiskt till läget för asynkron kundgenerering. Med andra ord kan kundposter skapas asynkront även om asynkront kundskapande är inaktiverat. Därför måste kommersiella administratörer för Commerce-administration skapa och schemalägga ett återkommande batchjobb för P-jobbet, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och jobbet **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce-administration.

> [!NOTE]
> Om alternativet **Filtrera delade kunddatatabeller** anger **Ja** på sidan **Commerce kanalschema** (**Retail och Commerce \> administration inställning \> Commerce schemaläggare \> Kanaldatabasgrupp**), kundposter skapas inte i kassa offline-läge. Mer information finns i [Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
