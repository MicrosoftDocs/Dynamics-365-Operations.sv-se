---
title: EUR-00011 Konfigurera rapportering av EU-säljlista
description: Den här uppgiften vägleder dig genom en översikt över förutsättningarna som krävs för rapportering av EU-säljlista.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b44d439bf1e991380fb7273a70e1f69f807c8b25
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175080"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 Konfigurera rapportering av EU-säljlista

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften vägleder dig genom en översikt över förutsättningarna som krävs för rapportering av EU-säljlista. Mer information om rapportering av EU-säljlista, inklusive nödvändiga krav, finns i hjälpen.

Den här uppgiften gäller för alla europeiska länder/regioner. Guiden skapades med hjälp av demodataföretaget DEMF och därför används Tyskland som exempelursprungsland. Guiden använder också Portugal som exempel på ett EU-land.

Dessa uppgifter är avsedda för systemadministratörer.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Importera konfigurationer för elektronisk rapportering för rapportering av EU-säljlista
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Ställ in aktiv.
3. Klicka på Databaser.
4. Klicka på Öppna.
5. Klicka på Alternativ i åtgärdsfönstret.
6. Klicka på Avancerat filter/sortering.
7. Klicka på Lägg till.
8. Välj Konfigurationsnamn i fältet Fält.
9. Skriv EU-säljlista (DE) i fältet Kriterier.
10. Klicka på OK.
11. Klicka på Importera.
12. Klicka på Ja.
13. Klicka på Alternativ i åtgärdsfönstret.
14. Klicka på Avancerat filter/sortering.
15. Klicka på Återställ.
16. Klicka på Lägg till.
17. Välj Konfigurationsnamn i fältet Fält.
18. Skriv Rapport över EU-försäljningslista efter rader i fältet Kriterier.
19. Klicka på OK.
20. Klicka på Importera.
21. Klicka på Ja.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Ställ in momskoder för rapportering av EU-säljlista
1. Gå till Skatt > Indirekta skatter > Moms > Momskoder.
2. Använd snabbfiltret för att filtrera på fältet Moms med värdet VAT19.
3. Expandera avsnittet Rapportinställningar.
    * Kontrollera att Exkluderad är inställt på Nej.  
    * Du kan behöva låsa upp uppgiftsguiden för att ändra den här inställningen.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Ställ in momsgrupper för rapportering av EU-säljlista
1. Gå till Skatt > Indirekta skatter > Moms > Momsgrupper.
2. Använd snabbfiltret för att filtrera på fältet Momsgrupp med värdet AR-DOM.
3. Klicka på Redigera.
4. Expandera avsnittet Inställningar.
5. Välj den första raden i listan.
6. Markera kryssrutan Momsbefrielse.
7. Välj den andra raden i listan.
8. Markera kryssrutan Momsbefrielse.
9. Välj den tredje raden i listan.
10. Markera kryssrutan Momsbefrielse.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Ställ in artikelmomsgrupper för rapportering av EU-säljlista
1. Gå till Skatt > Indirekta skatter > Moms > Artikelmomsgrupper.
2. Använd snabbfiltret för att filtrera på fältet Artikelmomsgrupp med värdet FULL.
    * Kontrollera att Rapporteringstyp är inställt på Artikel.  
    * Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.  
3. Använd snabbfiltret för att filtrera på fältet Artikelmomsgrupp med värdet RED.
    * Kontrollera att Rapporteringstyp är inställt på Tjänst.  
    * Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Ställ in land-/regionsparametrar för rapportering av EU-säljlista
1. Gå till Moms > Inställningar > Moms > Parametrar för land/region.
2. Klicka på Ny.
3. Skriv PRT i fältet Land/region.
4. Skriv PT i fältet Moms.

## <a name="create-tax-exempt-numbers"></a>Skapa momsregistreringsnummer
1. Gå till Moms > Inställningar > Moms > Momsregistreringsnummer.
2. Klicka på Ny.
3. Skriv PRT i fältet Land/region.
4. Skriv PT12345 i fältet Momsregistreringsnummer.

## <a name="set-up-eu-sales-list-reporting-parameters"></a>Ställ in parametrar för rapportering av EU-säljlista
1. Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.
2. Klicka på fliken Lista över försäljning inom EU.
3. Välj Ja i fältet Överför inköp.
4. Expandera avsnittet Avrundningsregler.
5. Ange Avrundningsregel till 0,1.
6. Välj Ja i fältet Använd lägsta värde.
7. Ange 2 i fältet Antal decimaler.
8. Expandera avsnittet Elektronisk rapportering.
9. Välj EU-försäljningslista (DE) i fältet Mappning av filformat.
10. I fältet Mappning av rapportformat väljer du Rapport över EU-försäljningslista.
11. Klicka på fliken Egenskaper för land/region.
    * Kontrollera att fältet Lands-/regiontyp är inställt på Inrikes för land/region DEU.  
    * Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.  
12. Klicka på Ny.
13. Skriv PRT i fältet Land/region.
14. Skriv PT i fältet Intrastat-kod.
15. Välj EU i fältet Lands-/regiontyp.
16. Klicka på fliken Nummersekvenser.
    * Kontrollera att en nummerseriekod ställts in för referensen Lista över försäljning inom EU.  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Skapa en kund för rapportering av EU-säljlista för demonstrationsändamål
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Klicka på Ny.
3. Skriv PRT-001 i fältet Kundkonto.
4. Skriv En kund från Portugal i fältet Namn.
5. Välj 10 i fältet Kundgrupp.
6. Välj AR-DOM i gruppen Momsgrupp.
7. Välj PT12345 i fältet Momsregistreringsnummer.
8. Skriv PRT i fältet Land/region.
9. Klicka på Spara.

