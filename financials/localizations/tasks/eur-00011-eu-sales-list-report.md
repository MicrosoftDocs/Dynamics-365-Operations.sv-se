--- 
title: "Generera en rapport med lista över försäljning inom EU"
description: "Den här proceduren går igenom hur du kan skapa en EU-försäljningslisterapport."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 10e7399b058695fb1c1b0db8c696c926619c995a
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="generate-an-eu-sales-list-report"></a>Generera en rapport med lista över försäljning inom EU

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren går igenom hur du kan skapa en EU-försäljningslisterapport. Detta inkluderar överföring av transaktioner för inomeuropeisk handel till EU-försäljningslistan och körning av rapporten. Proceduren innehåller även generering av en transaktion för inomeuropeisk handel för demonstration. Mer information om rapportering av EU-säljlista, inklusive nödvändiga krav, finns i hjälpen till Dynamics 365 for Finance and Operations.

Den här proceduren gäller för alla europeiska länder/regioner. Proceduren skapades med hjälp av demonstrationsföretaget DEMF och därför används Tyskland som exempelursprungsland. Proceduren använder också Portugal som exempel på ett EU-land. Innan du kan slutföra proceduren, måste du konfigurera rapporteringen av EU-försäljningslistan.

Proceduren är avsedd för kamrerer.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Skapa en inomeuropeisk försäljningstransaktion för demonstration
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. Skriv PRT-001 i fältet Kundkonto.
4. Klicka på OK.
5. Skriv "D0001" i fältet Artikelnummer.
6. Expandera avsnittet Radinformation.
7. Klicka på fliken Inställningar.
8. Skriv FULL i fältet Artikelmomsgrupp.
9. Klicka på Lägg till rad.
10. Skriv "D0003" i fältet Artikelnummer.
11. Skriv RED i fältet Artikelmomsgrupp.
12. Klicka på Spara.
13. Klicka på Faktura i åtgärdsfönstret.
14. Klicka på Faktura.
15. Expandera avsnittet Parametrar.
16. Välj Alla i fältet Kvantitet.
17. Expandera avsnittet Inställningar.
18. Ange datumet 01-11-2016 i fältet Fakturadatum.
19. Klicka på OK.
20. Klicka på OK.

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Överför transaktioner för inomeuropeisk handel till listan över försäljning inom EU
1. Gå till Moms > Deklarationer > Utländsk handel > Lista över försäljning inom EU.
2. Klicka på Överför.
3. Välj Ja i fältet Artikel om du vill överföra artikeltransaktioner.
4. Välj Ja i fältet Tjänst om du vill överföra tjänsttransaktioner.
    * Du kan även ange ytterligare filter för transaktioner i inomeuropeisk handel du vill överföra.  
5. Klicka på Överför.
    * Kontrollera att den inomeuropeiska försäljningstransaktionen överförs till EU-försäljningslistan.  

## <a name="generate-the-eu-sales-list-report"></a>Generera rapport med lista över försäljning inom EU
1. Klicka på Rapportering.
2. Markera Varje månad i fältet Rapporteringsperiod.
3. Ange datumet 01-01-2016 i fältet Från datum.
4. Välj Ja i fältet Generera fil.
5. Välj Ja i fältet Generera rapport.
6. Skriv EUSalesList (EU-försäljningslista) i fältet Filnamn.
7. Skriv EUSalesList (EU-försäljningslista) i fältet Rapportfilnamn.
8. Skriv 123 i fältet Registrerings-ID för EU-försäljningslista.
    * Det här fältet är bara tillgängligt för Tyskland.  
    * Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill ta med i rapporten.  
9. Klicka på OK.
    * Kontrollera att popup-fönster visas du vill bekräfta att filen och kontrollrapporten hämtas.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>Markera rader i EU-försäljningslistan som rapporterade
1. Klicka på Markera.
2. Klicka på Markera som rapporterad.
3. Välj raden för fältet Fakturadatum i listan.
4. Skriv 01/01/2016..01/31/2016 i fältet Kriterier.
5. Välj raden för fältet Rapporteringsstatus i listan.
6. Markera Inkluderat i fältet Kriterier.
    * Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill markera som rapporterade.  
7. Klicka på OK.
8. Välj Rapportet i fältet för val.

## <a name="mark-eu-sales-list-lines-as-closed"></a>Markera rader i EU-försäljningslistan som stängda
1. Klicka på Markera.
2. Klicka på Markera som stängd.
3. Markera raden för fältet Fakturadatum i listan.
4. Skriv 01/01/2016..01/31/2016 i fältet Kriterier.
5. Markera raden för fältet Rapporteringsstatus i listan.
6. Markera Rapporterat i fältet Kriterier.
    * Du kan även ange ytterligare filter för transaktioner för inomeuropeisk handel du vill markera som stängda.  
7. Klicka på OK.
8. Välj Stängt i fältet för val.

