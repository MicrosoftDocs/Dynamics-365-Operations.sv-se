---
title: Kundhantering i butiker
description: Denna artikel förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 2928aa5c4e62611b54799fbe7c1bba25fe186bcd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282252"
---
# <a name="customer-management-in-stores"></a>Kundhantering i butiker

[!include [banner](includes/banner.md)]

Denna artikel förklarar hur återförsäljare kan aktivera kundhanteringsfunktioner vid kassan (POS) i Microsoft Dynamics 365 Commerce.

Det är viktigt att butikspersonalen kan skapa och redigera kundposter i kassan. På så sätt kan de samla in uppdateringar av kundinformationen som t.ex. e-postadress, telefonnummer och adress. Den här informationen är användbar i andra system, till exempel marknadsföring, eftersom effektiviteten hos dessa system beror på hur korrekta kunddata är.

Säljare kan utlösa arbetsflödet för kundskapande från två kassastartpunkter. De kan välja en knapp som är mappad till åtgärden **Lägga till kund** och de kan välja **Skapa kund** i appfältet på sökresultatsidan. I båda fall visas dialogrutan **Ny kund** där säljföretag kan ange nödvändiga kunduppgifter, såsom kundens namn, e-postadress, telefonnummer, adress och all ytterligare information som är relevant för verksamheten. Att ytterligare information kan fångas in med hjälp av de kundattribut som är associerade med kunden. Mer information om kundattribut finns i [Kundattribut](dev-itpro/customer-attributes.md).

Säljare kan också samla in sekundära e-postadresser och telefonnummer. De kan också fånga in kundens önskemål om att ta emot marknadsföringsinformation via någon av de sekundära e-postadresserna eller telefonnummer. För att aktivera denna funktion måste återförsäljare aktivera funktionen **Samla in flera e-postmeddelanden och telefonnummer och godkännande för marknadsföring på dessa kontakter** i arbetsytan **Funktionshantering** i Commerce headquarters (**Systemadministration \> Arbetsytor \> Funktionshantering**).

## <a name="default-customer-properties"></a>Standardkundegenskaper

Detaljhandlare kan använda sidan **Alla butiker** i Commerce headquarters (**Retail och Commerce \> Kanaler \> Butiker**) för att associera en standardkund till varje butik. I Commerce kopieras sedan de egenskaper som har definierats för standardkunden till alla nya kundposter som skapas. Till exempel visar dialogrutan **Skapa kund** egenskaper som ärvs från standardkunden som är associerad med butiken. Dessa egenskaper omfattar **kundtyp**, **kundgrupp**, **kvittoalternativ**, **kvittomeddelande**, **valuta** och **språk**. Eventuella **anknytningar** (gruppering av kunder) ärvs också från standardkunden. **Ekonomiska dimensioner** ärvs dock från den kundgrupp som associeras med standardkunden, inte från standardkunden.

> [!NOTE]
> Värdet via e-postkvittot kopieras från standardkunden bara om **kvitto-e-post-ID** inte anges för de nya kunderna. Detta innebär att om kvitto-e-post-ID finns på standardkunden får alla kunder som skapats från näthandelsplatsen samma kvitto-e-post-ID eftersom det inte finns något användargränssnitt för att samla in kvitto-e-post-ID från kunden. Vi rekommenderar att du håller fältet **e-postkvitto** tomt för standardkunden i butiken och bara använder det om du har en affärsprocess som beror på att det finns en e-postadress med kvitto. 

Säljare kan fånga in flera adresser för en kund. Kundens namn och telefonnummer ärvs från den kontaktinformation som är kopplad till varje adress. Snabbflikarna **Adresser** för en kundpost innehåller ett fält för **Syfte** som säljarna kan redigera. Om kundtypen är **Person** är standardvärdet **Start**. Om kundtypen är **Organisation** är standardvärdet **Företag**. Andra värden som det här fältet stöder **Start**, **Kontor** och **Brevlåda**. Värdet i fältet **Land** för en adress ärvs från den primära adressen som anges på sidan **Driftenhet** i Commerce headquarters i **Organisationsadministration \> Organisationer \> Driftenheter**.



## <a name="additional-resources"></a>Ytterligare resurser

[Skapningsläge asynkron kund](async-customer-mode.md)

[Konvertera asynkrona kunder till synkrona kunder](convert-async-to-sync.md)

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
