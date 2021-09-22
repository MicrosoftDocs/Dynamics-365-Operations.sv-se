---
title: Kundhantering i butiker
description: Det här avsnittet förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 09caa7fa8f10d1afc44bb9343550bc633b8ec99a
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472235"
---
# <a name="customer-management-in-stores"></a>Kundhantering i butiker

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.

Det är viktigt att butikspersonalen kan skapa och redigera kundposter i kassan. På så sätt kan de samla in uppdateringar av kundinformationen som t.ex. e-postadress, telefonnummer och adress. Den här informationen är användbar i andra system, till exempel marknadsföring, eftersom effektiviteten hos dessa system beror på hur korrekta kunddata är.

Säljare kan utlösa arbetsflödet för kundskapande från två kassastartpunkter. De kan välja en knapp som är mappad till operationen **Lägga till kund** och de kan välja **Skapa kund** i appfältet på sökresultatsidan. I båda fall visas dialogrutan **Ny kund** där säljföretag kan ange nödvändiga kunduppgifter, såsom kundens namn, e-postadress, telefonnummer, adress och all ytterligare information som är relevant för verksamheten. Att ytterligare information kan fångas in med hjälp av de kundattribut som är associerade med kunden. Mer information om kundattribut finns i [Kundattribut](dev-itpro/customer-attributes.md).

Säljare kan också samla in sekundära e-postadresser och telefonnummer. De kan också fånga in kundens önskemål om att ta emot marknadsföringsinformation via någon av de sekundära e-postadresserna eller telefonnummer. För att aktivera denna funktion måste återförsäljare aktivera funktionen **Samla in flera e-postmeddelanden och telefonnummer och godkännande för marknadsföring på dessa kontakter** i arbetsytan **Funktionshantering** i Commerce-administration (**Systemadministration \> Arbetsytor \> Funktionshantering**).

## <a name="default-customer-properties"></a>Standardkundegenskaper

Detaljhandlare kan använda sidan **Alla butiker** i Commerce-administration (**Retail och Commerce \> Kanaler \> Butiker**) för att associera en standardkund till varje butik. I Commerce kopieras sedan de egenskaper som har definierats för standardkunden till alla nya kundposter som skapas. Till exempel visar dialogrutan **Skapa kund** egenskaper som ärvs från standardkunden som är associerad med butiken. Dessa egenskaper omfattar **kundtyp**, **kundgrupp**, **kvittoalternativ**, **kvittomeddelande**, **valuta** och **språk**. Eventuella **anknytningar** (gruppering av kunder) ärvs också från standardkunden. **Ekonomiska dimensioner** ärvs dock från den kundgrupp som associeras med standardkunden, inte från standardkunden.

> [!NOTE]
> Värdet via e-postkvittot kopieras från standardkunden bara om **kvitto-e-post-ID** inte anges för de nya kunderna. Detta innebär att om kvitto-e-post-ID finns på standardkunden får alla kunder som skapats från e-handelsplatsen samma kvitto-e-post-ID eftersom det inte finns något användargränssnitt för att samla in kvitto-e-post-ID från kunden. Vi rekommenderar att du håller fältet **e-postkvitto** tomt för standardkunden i butiken och bara använder det om du har en affärsprocess som beror på att det finns en e-postadress med kvitto. 

Säljare kan fånga in flera adresser för en kund. Kundens namn och telefonnummer ärvs från den kontaktinformation som är kopplad till varje adress. Snabbflikarna **Adresser** för en kundpost innehåller ett fält för **Syfte** som säljarna kan redigera. Om kundtypen är **Person** är standardvärdet **Start**. Om kundtypen är **Organisation** är standardvärdet **Företag**. Andra värden som det här fältet stöder **Start**, **Kontor** och **Brevlåda**. Värdet i fältet **Land** för en adress ärvs från den primära adressen som anges på sidan **Driftenhet** i Commerce-administration i **Organisationsadministration \> Organisationer \> Driftenheter**.

## <a name="sync-customers-and-async-customers"></a>Synkrona och asynkrona kunder

> [VIKTIGT] När kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Oavsett om du väljer synkron eller asynkron kundgenerering måste Commerce headquarters-administratörer därför skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartner från asynkront läge** (kallades tidigare jobbet **Synkronisera kunder och affärspartner från asynkront läge**) och **1010**-jobbet, så att alla asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

I Commerce finns det två sätt att skapa kunder: Synkron (eller Synk) och Asynkron (eller Asynk). Kunder skapas som standard synkront. Med andra ord skapas de i Commerce-administration i realtid. Synkroniseringsläget för kunder är fördelaktigt eftersom nya kunder kan sökas omedelbart över kanaler. Den har emellertid även ett problem. Eftersom det genererar [Commerce Data Exchange: realtidstjänst](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) anropar till Commerce-administration kan prestanda påverkas om många samtidiga kundsamtal görs.

Om alternativet **Skapa kund i asynkront läge** anges till **Ja** i butikens funktionsprofil (**Retail och Commerce \> Kanalinställning \> Inställning av online-butik \> Funktionsprofiler**), realtidssamtal används inte för att skapa kundposter i kanaldatabasen. Asynkront kundgenereringsläge påverkar inte prestandan i Commerce-administration. En tillfällig, global unik identifierare (GUID) tilldelas varje ny asynkron kundpost och används som kundkonto-ID. Denna GUID inte visas för kassaanvändare. I stället visas **väntande synkronisering** som kundkonto-ID. 

### <a name="convert-async-customers-to-sync-customers"></a>Konvertera asynkrona kunder till synkrona kunder

Om du vill konvertera asynkrona kunder till synkrona kunder måste du först köra **P-jobbet** för att skicka asynkrona kunderna till Commerce headquarters. Kör sedan jobbet **Synkronisera kunder och affärspartner från asynkront läge** (kallades tidigare **Synkronisera kunder och affärspartner från asynkront läge**) för att skapa kundkonto-ID:n. Kör slutligen **1010** jobbet om du vill synkronisera de nya kundkonto-ID till kanalerna.

### <a name="async-customer-limitations"></a>Asynkrona kundbegränsningar

Asynkrona kundfunktionen har för närvarande följande begränsningar:

- Asynkrona kundposter kan inte redigeras om inte kunden har skapats i Commerce-administration och det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen. Därför kan adressen inte sparas för en asynkron kund förrän den kunden har synkroniserats med Commerce Headquarters eftersom tillägget av en kundadress är internt implementerat som en redigeringsåtgärd i kundprofilen. Men om funktionen **Aktivera asynkron generering av kundadresser** har aktiverats kan kundadresser sparas även för asynkrona kunder.
- Anknytningar kan inte associeras med asynkrona kunder. Därför ärver inte nya asynkrona kunder anknytningar från standardkunden.
- Förmånskort kan inte utfärdas till asynkrona kunder såvida inte det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.
- Sekundära e-postadresser och telefonnummer kan inte fångas in för asynkrona kunder.

Vissa av de tidigare nämnda begränsningarna kan få dig att välja alternativet Synkron kund för ditt företag, men Commerce-teamet arbetar för att göra funktionerna för asynkron kund mer lika funktionerna för synkron kund. Exempelvis från och med Commerce version 10.0.22 kommer nya funktionen **Aktivera asynkron generering av kundadresser** som du kan aktivera i arbetsytan **Funktionshantering** asynkront och som sparar nyligen skapade kundadresser för både synkrona och asynkrona kunder. För att spara dessa adresser i kundprofilen i Commerce headquarters måste du schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och jobbet **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Kundskapa i kassa offlineläge

När kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Därför, som nämndes tidigare, måste Commerce headquarters-administratörer skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

> [!NOTE]
> Om alternativet **Filtrera delade kunddatatabeller** anger **Ja** på sidan **Commerce kanalschema** (**Retail och Commerce \> administration inställning \> Commerce schemaläggare \> Kanaldatabasgrupp**), kundposter skapas inte i kassa offline-läge. Mer information finns i [Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
