---
title: Vad är nytt och ändrat i Dynamics 365 Supply Chain Management (10.0.25 april 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: af344d3771583a99851c070e3735258ac964b5d7
ms.sourcegitcommit: 78576abe5c7cbab1bb69d26c999b038e8c24873a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954508"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10025-april-2022"></a>Vad är nytt och ändrat i Dynamics 365 Supply Chain Management (10.0.25 april 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management-version 10.0.25. Den här versionen har ett versionsnummer för 10.0.1149 och är tillgänglig enligt följande:

- **Förhandsversion:** februari 2022
- **Allmän tillgänglighet för frisläppning (självuppdatering):** mars 2022
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** april 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel i syfte att inkludera funktioner som kommit med i versionen efter det att denna artikel publicerades första gången.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Lager&nbsp;och&nbsp;logistik | [Förbättringar av farliga material](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Kommer snart | Funktionshantering:<br>*Förbättringar av farliga material* |
| Lager&nbsp;och&nbsp;logistik | [Förpackningsstationer för packningsarbete](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | Kommer snart | Funktionshantering:<br>*Förpackningsstationer för packningsarbete* |
| Lager&nbsp;och&nbsp;logistik | [Skanna streckkoder på lagerstället med standarder för GS1-format](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [GS1-streckkoder och QR-koder](../warehousing/gs1-barcodes.md) | Funktionshantering:<br>*Skanna GS1-streckkoder* |
| Tillverkning | [Materialförbrukning och reservationer i körningsgränssnittet för produktionsgolv](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Hur arbetare använder körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-use.md) | Funktionshantering:<br>*(Förhandsversion) Registrera materialförbrukning i körningsgränssnittet för produktionsgolv (inte WMS)*<br><br>Och/eller:<br><br>Funktionshantering:<br>*(Förhandsversion) Registrera materialförbrukning i körningsgränssnittet för produktionsgolvet (WMS-aktiverat)* |
| Tillverkning | [Registrera materialförbrukning skalningsenheter](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [Arbetsbelastningar för tillverkningskörning för moln- och kantskalenheter](../cloud-edge/cloud-edge-workload-manufacturing.md) | Funktionshantering:<br>*Registrera materialförbrukning i mobilappen på en skalenhet* |
| Planering | [Centralunderhåll för Planeringsoptimering](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [Kalendrar och huvudplanering](../master-planning/supply-chain-calendars-master-planning.md) | Aktiverad som standard |
| Planering | [Förslag till Planeringsoptimering för att optimera befintligt leverans](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Åtgärdsmeddelanden](../master-planning/action-messages.md) | Aktiverad som standard |
| Planering | Förenklade planerade order | [Förenklade planerade order](../master-planning/planning-optimization/planned-orders-simplified.md ) | Funktionshantering:<br>*Förenklade planerade order* |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Hantering av lager och lagerstyrning | (Polen) Tillåt att flera fakturor för enskilda administrativa dokument länkas till en inköpsorderrad i ett enskilt administrativt dokument | Med den här funktionen kan du dela inköpsorderrader och länka dem till ett enda administrativt dokument (SAD) när dessa inköpsorderrader bokfördes för flera olika fakturor (som för olika försändelser). |
| Anskaffning och källa | Konsolidera flera inköpsrekvisitioner till en enda inköpsorder efter redovisningsdatum | Med den här funktionen kan flera inköpsrekvisitioner konsolideras till en enda inköpsorder om de olika inköpsrekvisitionerna har olika redovisningsdatum. Regler för inköpspolicy för inköpsordergenerering och efterfrågekonsolidering kan ställas in för att automatisera beslutet att gruppera rekvisitionsrader efter redovisningsdatum på inköpsordernivå. Konsolidering av inköpsorder per redovisningsdatum stöds inte om budgetkontroll aktiveras eftersom redovisningsdatumet används för budgetreservationer och inteckning. Därför bör den behållas under övergången från inköpsrekvisition till inköpsorder. |
| Anskaffning och källa | Visa äldre standardfältinställningar för svar på anbudsförfrågan | Den här funktionen återinför de äldre standardinställningarna för svarsfält för anbudsförfrågningar (RFQ), som tidigare togs bort från användargränssnittet. De här inställningarna har ingen funktion i rutan men de kan anpassas efter behov. Aktivera den här funktionen om organisationen redan har lagt till funktioner för standardinställningarna för anbudsförfrågans svarsfält eller planerar att göra det. När den här funktionen är aktiverad kan du öppna inställningarna genom att gå till sidan **Anskaffnings- och inköpparametrar**, öppna fliken **Anbudsförfrågan** och välj **Standardsvarsfält för anbudsförfrågan**. |
| Anskaffning och källa | Sammanfoga ekonomiska dimensioner från providern med aktiv dimensionslänk för ekonomisk dimension på inköpsordern | Med den här funktionen kan du slå samman ekonomiska dimensioner från leverantörer med aktiva dimensionslänk ekonomiska dimensioner efter godkännande av inköpsrekvisition om du skapar en länk mellan en ekonomisk dimension och platsinventeringsdimensionen. Regler för inköpspolicy för inköpsorderskapande och efterfrågekonsolidering kan ställas in så att de styr beslutet att koppla ekonomiska dimensioner från leverantörer till den aktiva dimensionslänkens ekonomiska dimension på inköpsorderrubriknivå. |
| Produktionskontroll | (Ryssland) Aktivera standardplatsinställningar för produktionsrecept/strukturlista och automatisk GTD-reservation/-förbrukning i produktion | Funktionen möjliggör ytterligare alternativ för produktion från importerade råvaror (endast rysk lokalisering):<ul><li>Möjlighet att konfigurera den automatiska standardplatsen för produktionsformler och stycklistor på både resursgrupper och lager.</li><li>Automatisk reservation av råmaterial genom dimensionen *GTD-nummer* på WMS-aktiverade lager enligt icke-WMS reservationsalgoritmen. Detta gäller i de fall en arbetspolicy för *Råmaterialhämtning* finns med **Arbetsskapande metod** inställt på *Aldrig* och inställningen av lager, plats och artikelnummer matchar lagertransaktionerna för produktionsordern (batch).</li><li>Automatisk förbrukning av råmaterial per dimensionen *GTD-nummer* vid bokföring av plocklista, enligt den anskaffade reservationen som beskrivs tidigare.</li></ul> |
| Lagerstyrning | (Förhandsversion) Skalenhetsstöd för inkommande och utgående lagerorder | Den här funktionen gör att systemet skapar utgående lagerställeorder under processen frisläppning till lagerställe, och att man skapar inkommande lagerställeorder när överföringsorder bokförs som levererade. Systemet synkroniserar sedan varje inkommande eller utgående lagerställeorder till den vågsenhet som ansvarar för att skeppa eller ta emot ordern. Observera att dina arbetsbelastningar för lagerstyrning måste uppgraderas när du har aktiverat funktionen. För mer information, se [Arbetsbelastningar för hantering av distributionslager för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Den här funktionen *Avkoda platsarbete från ASN:er ASNs* och kommer att möjliggöra möjligheten att ta emot överföringsorder med hjälp av inleveransprocess för ID-nummer i Lagerstyrning-mobilappen. |

## <a name="feature-state-changes-in-this-release"></a>Funktionstillstånd ändras i den här versionen

Följande tabell listar funktioner som blev obligatoriska eller aktiverade som standard från och med 10.0.25. Alla dessa funktioner aktiveras automatiskt för ditt system så snart du uppdaterar till 10.0.25. Obligatoriska funktioner kan inte stängas av, men funktioner som är på som standard kan fortfarande stängas av med [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tabellen visar även funktioner som tidigare var offentliga, men som har ändrats till att bli allmänt tillgängliga i 10.0.25, vilket innebär att de nu rekommenderas att användas i produktionsmiljöer. Dessa funktioner är inaktiverade som standard om inget annat anges, så du måste använda [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera dem om du vill använda dem.

| Modul | Funktionsnamn | Funktionens tillstånd |
| --- | --- | --- |
| Tillgångshantering | [Tillämpa regler för gruppering av arbetsorder medan en underhållsplan körs](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Allmänt tillgängligt |
| Tillgångshantering | [Räknarbaserade underhållsförbättringar](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Allmänt tillgängligt |
| Kostnadshantering | [Kostnadsberäkningsnivå](../cost-management/cost-calculation-level.md) | Allmänt tillgängligt |
| Kostnadshantering | Aktivera användardefinierat batchnummerkonfiguration för återföring av lagerstängning | Allmänt tillgängligt |
| Kostnadshantering | [Information om lagerstängningsförlopp](whats-new-scm-10-0-21.md) | Allmänt tillgängligt |
| Kostnadshantering | [Alternativ för att använda ekonomiska standarddimensioner som standard för omvärdering av standardkostnad för lager](../cost-management/manage-standard-cost-updates.md) | Allmänt tillgängligt |
| Kostnadshantering | Lagervärderapport, datarensning | På som standard |
| Kostnadshantering | [Lagring av lagervärderapport](../cost-management/inventory-value-report-storage.md) | På som standard |
| Kostnadshantering | Visa lagerstängningslogg i rutnät | På som standard |
| Konstruktionsändringshantering | [Aktivera ändringshantering för befintliga produkter](../engineering-change-management/change-management-existing-products.md) | På som standard |
| Konstruktionsändringshantering | [Konstruktionsändringshantering](../engineering-change-management/product-engineering-overview.md) | På som standard |
| Konstruktionsändringshantering | [Konstruktionsmeddelanden för produktion](../engineering-change-management/engineering-change-management.md) | På som standard |
| Konstruktionsändringshantering | [Förbättrat attributarv för konstruktionsändringshantering](../engineering-change-management/engineering-attributes-and-search.md) | På som standard |
| Konstruktionsändringshantering | [Hantera formeländringar och deras ingredienser](../engineering-change-management/manage-formula-changes.md) | På som standard |
| Konstruktionsändringshantering | [Kontroller av produktberedskap](../engineering-change-management/product-readiness.md) | På som standard |
| Konstruktionsändringshantering | [Variantgenerering för tekniska produkter](../engineering-change-management/engineering-variants.md) | På som standard |
| Hantering av lager och lagerstyrning | Navigera till strukturlisteversion från strukturlisterader | Obligatoriskt |
| Huvudplanering | [Batchbar bekräftelse och konsolidering för planerade bulk- och paketbatchorder](whats-new-scm-10-0-20.md) | Allmänt tillgängligt |
| Huvudplanering | Resursplanering med underhåll | Allmänt tillgängligt |
| Huvudplanering | Aktivera inställningsguidefunktionerna i masterplanen | Obligatoriskt |
| Huvudplanering | [Prognosmodellval på Detaljer för efterfrågeprognos](../master-planning/manual-adjustments-baseline-forecast.md) | Obligatoriskt |
| Huvudplanering | [Visualisering av huvudplaneringsförlopp](../master-planning/tasks/monitor-master-planning-run.md) | Obligatoriskt |
| Huvudplanering | [Parallell bekräftelse av planerade order](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoriskt |
| Huvudplanering | [Bekräfta planerad order med filtrering](../master-planning/planning-optimization/planned-order-firming.md) | På som standard |
| Huvudplanering | [Sparade vyer för planerade order](saved-views-scm.md) | På som standard |
| Anskaffning och källa | Inaktivera återställningsknappen för inköpsrekvisitionsdistribution | Allmänt tillgängligt |
| Anskaffning och källa | [Aktivera återställning av anskaffningsrelaterade arbetsflöden](whats-new-scm-10-0-20.md) | Allmänt tillgängligt |
| Anskaffning och källa | Möjlighet att bekräfta godkända inköpsorder från leverantörssamarbete i batch | Obligatoriskt |
| Anskaffning och källa | Inköpsavtal status stängd | Obligatoriskt |
| Anskaffning och källa | Lägga till rader i inköpsorder som är associerade med ett inköpsavtal | På som standard |
| Anskaffning och källa | Lägg till fältet Beställd kvantitet på sidan Bokför produktinleverans | På som standard |
| Anskaffning och källa | [Tillåt leverantörer att ansöka om anskaffningskategorier via leverantörssamarbete](../procurement/category-requests-from-vendors.md) | På som standard |
| Anskaffning och källa | Till- och från-avgifter på inköpsorder | På som standard |
| Anskaffning och källa | Inställning av avgift med plats och lagerställe | På som standard |
| Anskaffning och källa | Aktivera beräkning av inköpsavgift baserat på årstariff | På som standard |
| Anskaffning och källa | [Ansvarig part för inköpsavtal](../procurement/purchase-agreements.md) | På som standard |
| Anskaffning och källa | [Sparade vyer för inköpsorder](saved-views-scm.md) | På som standard |
| Produktinformationshantering | [Strikt validering av standardkvantiteter för order](../production-control/default-order-settings.md) | Obligatoriskt |
| Produktinformationshantering | Förbearbetning av strukturlisterapport för att undvika tidsgräns | På som standard |
| Produktinformationshantering | Använd ekonomiska dimensioner separat som standard vid användning av artikelmallar | På som standard |
| Produktinformationshantering | Aktivera produktdimensionsgrupper för artikelmallar | På som standard |
| Produktinformationshantering | Generera om produktvarianter baserat på nomenklatur | På som standard |
| Produktinformationshantering | [Förbättringar av sidan med variantförslag](../pim/tasks/create-predefined-product-variants.md) | På som standard |
| Produktionskontroll | Förbättrad produktionsplockning av kvantitet för faktisk/nominell vikt | Allmänt tillgängligt |
| Produktionskontroll | Den nya knappen Stoppa rast har lagts till på sidan Jobbkortterminal | Obligatoriskt |
| Produktionskontroll | [Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Produktionskontroll | Aktivera delvis inleverans av underleverantörsartiklar och korrigera ett problem med beräkning av kassation för strukturlisterader av typen Leverantör | Obligatoriskt |
| Produktionskontroll | [Funktion för att låsa jobbkortsenhet och jobbkortsterminal för att anpassas till språk](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Produktionskontroll | Förbättringar av dialogrutorna Godkänn jobb och Överför jobb | Obligatoriskt |
| Produktionskontroll | [ID-nummer för rapportering som färdig har lagts till på jobbkortenheten](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Produktionskontroll | [Skriv ut etikett från jobbkortenhet](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Produktionskontroll | [Produktionsgolvskörning](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Produktionskontroll | [Funktionen för Tillgångshantering för körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-configure.md) | På som standard |
| Produktionskontroll | [Jobbsökning för produktionsgolvets körningsgränssnitt](../production-control/production-floor-execution-configure.md) | På som standard |
| Produktionskontroll | [Åsidosätta standardproduktionsreservation](../production-control/override-default-reservation-principle.md) | På som standard |
| Produktionskontroll | [Visa fullständiga serienummer, batch- och ID-nummer i gränssnittet för produktionsgolvkörning](whats-new-scm-10-0-21.md) | På som standard |
| Försäljning och marknadsföring | [Prestandaförbättringar för försäljningsorderinformation](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Allmänt tillgängligt |
| Försäljning och marknadsföring | Prestandaförbättringar för försäljningsoffertinformation | Allmänt tillgängligt |
| Försäljning och marknadsföring | Dataexportpolicy som refereras i försäljningsorder | Obligatoriskt |
| Försäljning och marknadsföring | [Raderingspolicy för försäljningsorder till inköpsorderrad](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Obligatoriskt |
| Försäljning och marknadsföring | [Dataexportpolicy som refereras i försäljningsoffert](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Obligatoriskt |
| Försäljning och marknadsföring | [Optimering av kontaktpersons datatabellsexport](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | På som standard |
| Försäljning och marknadsföring | Aktivera uppslag av dokumentintroduktion för försäljningsoffert och dokumentslutsatsfält | På som standard |
| Försäljning och marknadsföring | [Förbättra rapportresultat för de 100 främsta kunderna](whats-new-scm-10-0-23.md) | På som standard |
| Försäljning och marknadsföring | Beräkna om uppskattat kundsaldo | På som standard |
| Försäljning och marknadsföring | [Registrering av försäljningsreturorderrad med decimalprecision med och utan faktisk/nominell vikt](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | På som standard |
| Försäljning och marknadsföring | [Sparade vyer för försäljning och marknadsföring](saved-views-scm.md) | På som standard |
| Försäljning och marknadsföring | Bekräftelse av försäljningsorder med ett klick | På som standard |
| Lagerstyrning | [Mallar för direktleverans med platsdirektiv](../warehousing/planned-cross-docking.md) | Allmänt tillgängligt |
| Lagerstyrning | [Inaktivera förväntade inleveranser från kvalitetsorder som ger exempel på blockerat lager](../inventory/inventory-blocking.md) | Allmänt tillgängligt |
| Lagerstyrning | Inleveranshistorik för ID-nummer | Allmänt tillgängligt |
| Lagerstyrning | [Materialhanteringsutrustningens gränssnitt](../warehousing/mhax.md) | Allmänt tillgängligt |
| Lagerstyrning | [Avrunda kvantiteter neråt till närmaste försäljningsenhet vid frisläpp till lagerställe](whats-new-scm-10-0-19.md) | Allmänt tillgängligt |
| Lagerstyrning | Stöd för skalningsenhet för arbetslistor för distributionslagerapp | Allmänt tillgängligt |
| Lagerstyrning | Information om etikett för leveranspåfyllnad | Allmänt tillgängligt |
| Lagerstyrning | [Använd snabbare API för behållare som stängs/öppnas igen på förpackningsstationen](whats-new-scm-10-0-21.md) | Allmänt tillgängligt |
| Lagerstyrning | [Validera mallar valda för lagerpåfyllnadsjobb](whats-new-scm-10-0-20.md) | Allmänt tillgängligt |
| Lagerstyrning | Tillåt lagerpåfyllnadsmall att använda befintligt omedelbart lagerpåfyllnadsarbete (mellan enheter) | Obligatoriskt |
| Lagerstyrning | Automatisk tilldelning av GUID när användaren skapar något i WHS | Obligatoriskt |
| Lagerstyrning | Inhämta produktvarianter och spårningsdimensioner i lagerstyrningsappen under mottagande av lastartikel | Obligatoriskt |
| Lagerstyrning | [Ändra lagerstatus för artiklar som styrs av spårningsdimensioner](../inventory/inventory-statuses.md) | Obligatoriskt |
| Lagerstyrning | [Ändra arbetspool för arbete](../warehousing/change-work-pool-on-work.md) | Obligatoriskt |
| Lagerstyrning | [Klusterposition full](../warehousing/cluster-position-full.md) | Obligatoriskt |
| Lagerstyrning | [Funktionen för klusterplats](../warehousing/putaway-clusters.md) | Obligatoriskt |
| Lagerstyrning | [Bekräfta och överföra](../warehousing/confirm-and-transfer.md) | Obligatoriskt |
| Lagerstyrning | [Bekräfta utgående leveranser från batchjobb](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Obligatoriskt |
| Lagerstyrning | [Kontrollera om en sammanfattningssida för inleverans ska visas på mobila enheter](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoriskt |
| Lagerstyrning | [Uppskjuten bearbetning av manuell åtgärd för lagerrörelse](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoriskt |
| Lagerstyrning | Tillåt inte att skapa laster som inte uppfyller kraven i mallen för påfyllnadslastuppbyggnad | Obligatoriskt |
| Lagerstyrning | [Förbättrad layout för ID-nummeretikett](../warehousing/document-routing-layout-for-license-plates.md) | Obligatoriskt |
| Lagerstyrning | [Utvärdera alla åtgärder för platsdirektiv för flera SKU:er](/troubleshoot/dynamics-365/supply-chain/warehousing/evaluate-multiple-location-directive-actions) | Obligatoriskt |
| Lagerstyrning | Dölj fältet Totalt värde på sidorna Alla beläggningar och Beläggningsinformation | Obligatoriskt |
| Lagerstyrning | ID-nummeretikettens byggkonfiguration | Obligatoriskt |
| Lagerstyrning | Manuell korrigering av lastrad för administratör eller andra betrodda användare | Obligatoriskt |
| Lagerstyrning | [Placering för plats-ID-nummer](../warehousing/location-license-plate-positioning.md) | Obligatoriskt |
| Lagerstyrning | [Blandning av produktstorlekar på plats](../warehousing/location-product-dimension-mixing.md) | Obligatoriskt |
| Lagerstyrning | Gör fältet med lagerstatus för mobilenhetslagerrörelse redigerbart | Obligatoriskt |
| Lagerstyrning | Manuell plockningstjänst för försäljningsrad för admin eller liknande betrodda användare | Obligatoriskt |
| Lagerstyrning | [Förhindra att levererade ID-nummer för överföringsorder används på i andra distributionslager än måldistributionslagret](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoriskt |
| Lagerstyrning | Prompt för att lösa tvetydiga plats/ID-nummernamn | Obligatoriskt |
| Lagerstyrning | [Kvalitetskontroll](../warehousing/quality-check.md) | Obligatoriskt |
| Lagerstyrning | [Användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen](../warehousing/install-configure-warehouse-management-app.md) | Obligatoriskt |
| Lagerstyrning | [Ytterligare platszoner](../warehousing/additional-location-zones.md) | På som standard |
| Lagerstyrning | [Skapa och bearbeta överföringsorder från lagerställeappen](../warehousing/create-transfer-order-from-warehouse-app.md) | På som standard |
| Lagerstyrning | Aktivera snabbvalidering för lagerställets mobila enheter | På som standard |
| Lagerstyrning | [Maximal körningstid för jobbet Rensning av behållningsposter för lagerstyrning](../warehousing/onhand-cleanup.md) | På som standard |
| Lagerstyrning | [Visualisering av utgående arbetsbelastning](../warehousing/outbound-workload-visualization.md) | På som standard |
| Lagerstyrning | [Bearbeta lagerställeapphändelser](../warehousing/warehouse-app-events.md) | På som standard |
| Lagerstyrning | [Sparad vy för workbench vid lastplanering](saved-views-scm.md) | På som standard |
| Lagerstyrning | [Sparad vy för sidan Information om arbete](saved-views-scm.md) | På som standard |
| Lagerstyrning | [Sparad vy för påfyllnadsbearbetning](saved-views-scm.md) | På som standard |
| Lagerstyrning | [Sparade vyer för lastbearbetning](saved-views-scm.md) | På som standard |
| Lagerstyrning | [Sparade vyer för leveransbearbetning](saved-views-scm.md) | På som standard |
| Lagerstyrning | [Information om påfyllnadsbatchjobb](../warehousing/wave-processing.md) | På som standard |
| Lagerstyrning | [Meddelanden för påfyllnadskörning](../warehousing/wave-execution-notifications.md) | På som standard |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.25 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.25 av appar för ekonomi och drift (april 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.25 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022](/dynamics365-release-plan/2022wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
