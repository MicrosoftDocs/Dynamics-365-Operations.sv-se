---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.29 (oktober 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d12932f35b3b451577d38948f60bc3a73c10e2a0
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714844"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10029-october-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.29 (oktober 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.29. Den här versionen har ett versionsnummer för 10.0.1326 på följande schema:

- **Förhandsversion av versionen:** Augusti 2022
- **Allmän tillgänglighet för versionen (självuppdatering):** September 2022
- **Allmän tillgänglighet för versionen (automatisk uppdatering):** Oktober 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Lager och logistik | [Allokera och reservera WMS-artiklar i Lagersynlighet](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Kommer snart | Aktiverad som standard |
| Lager och logistik | [Förinläsning av strömlinjeformade lagerlistor](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | [Använda appen Inventory Visibility](../inventory/inventory-visibility-power-platform.md) | Aktiveras via tjänstekonfiguration |
| Tillverka mot order-automation | [Tillverka mot order-automation](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Tillverka mot order-automation](../master-planning/make-to-order-supply-automation.md) | Funktionshantering:<br>*Tillverka mot order-automation* |
| Planering | [Visa och använd detaljerad inblick för DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Planeringsöversikt för efterfrågebaserade materialbehov](../master-planning/planning-optimization/ddmrp-overview.md) | Funktionshantering:<br>*(Förhandsversion) DDMRP för Planeringsoptimering* |
| Produktionskontroll | [Göra färdiga varor fysiskt tillgängliga före bokföring i journaler](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Göra färdiga varor fysiskt tillgängliga före bokföring i journaler](../production-control/deferred-posting.md) | Funktionshantering:<br>*(Förhandsversion) Göra färdiga varor fysiskt tillgängliga före bokföring i journaler* |
| Warehouse management | [Söka efter relevanta data i Warehouse Mobile App](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Fråga data med hjälp av omvägar Warehouse Management-mobilappen](../warehousing/warehouse-app-data-inquiry.md) | Funktionshantering:<br>*Dataförfrågansflöde i Warehouse Management-appen* |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Kostnadshantering | Optimering av samprodukt som väntar på prisberäkning | Funktionen löser en konflikt som ibland kan uppstå när samproduktpriser beräknas med hjälp av flera trådar. Det gör att systemet ser till att varje artikelpris för samprodukt beräknas bara en gång. Resultatet av den beräkningen används sedan som indata för alla andra beräkningar. Om ett väntande pris redan finns används det priset. |
| Huvudplanering | Grupptransaktioner i Planeringsoptimering | Den här funktionen kan hjälpa till att reducera antalet planerade order som genereras för att leverera en enskild försäljningsorderrad när du använder Planeringsoptimering. När den här funktionen är aktiverad grupperar Planeringsoptimering alla lagertransaktioner för en orderrad i ett enda behov för hela kvantiteten. (Det här beteendet matchar det inbyggda motorbeteendet för planering.) Tillgång och efterfrågan grupperas separat. Därför hjälper funktionen till att minska transaktionsvolymen när du har delat upp transaktioner och när du använder dimensioner (till exempel batchnummer eller serienummer) som inte är disponeringsdimensioner. |
| Anskaffning och källa | Spärra leverantör för inköpsorder | Med hjälp av den här funktionen kan du vänta med en leverantör för inköpsorder. Den lägger till en ny spärrtyp *inköpsordertyp* som markerar en leverantör som innehar inköpsorder. Du kan inte skapa nya inköpsorder för leverantörer som är innehar för inköpsorder, men du kan fortfarande fortsätta med eventuella öppna fakturor eller betalningar för dessa leverantörer. |
| Försäljning och marknadsföring | Beräkna radens nettobelopp vid import | Den här funktionen låter dig styra om systemet ska räkna om radsummor när du importerar data genom entiteten *Försäljningsorderrader*, *Försäljningsoffertrader* eller *Returorderrader* genom att använda OData eller dubbelriktad skrivning. Det har bara effekt när du också har policyer för utvärdering av handelsavtal som begränsar förändringar på området **Nettobelopp** för försäljningsorderrader, försäljningsoffertrader och/eller returorderrader. Den lägger till en inställning som heter **Beräkna radens nettobelopp** till sidan **Kundreskontra > Inställningar > Parametrar för kundreskontra**. När den här inställningen ställs in på *Ja*, omberäknas alltid radbelopp när det behövs (och ignorerar eventuell handelsavtalsutvärderingspolicy för radens nettobelopp). När inställningen är inställd på *Nej* kommer systemet aldrig automatiskt att beräkna radens nettobelopp, även när inkommande ändringar av radens pris, kvantitet och/eller rabatt skulle innebära att radens nettobelopp bör räknas om. Den här funktionen aktiveras som standard och ställer in **Beräkna rad nettobelopp** till *Ja*. Inställningen *Nej* matchar systembeteendet före version 10.0.23 och tillhandahålls huvudsakligen för att stödja äldre integrationsscenarier.<br><br>Mer information finns i [Omberäkna radens nettobelopp när du importerar försäljningsorder, offerter och returer](../sales-marketing/calc-line-net-amounts-import.md). |
| Försäljning och marknadsföring | Beräkna försäljningssummor med hjälp av flera trådar | Med den här funktionen förbättras prestandan genom att systemet kan använda parallell bearbetning när försäljningssummor beräknas i en batch. Funktionen lägger till ett nytt **Antal trådar** i dialogrutan **Beräkna försäljningssummor**. Om du väljer att köra beräkningen i en batch kan du använda det här fältet för att ange det maximala antalet trådar. Om du ställer in värdet till *0* (noll) eller *1*, används en enda tråd. Värden över 1 aktiverar flertrådskörning. |
| Försäljning och marknadsföring | Uppdatera priser och rabatter som angetts manuellt koncerninternt | Den här funktionen ger stöd för manuella ändringsprinciper för koncerninterna order. Den innehåller stöd för överföring av manuella ändringsprinciper mellan koncerninterna försäljnings- och inköpsorder. Tidigare har manuella ändringsprinciper bara stöd för icke-koncerninterna order. När den här funktionen har aktiverats ges du möjlighet att uppdatera priser och rabatter när du har sparat ändringarna i en koncernintern order. Med det här alternativet kan du välja om du vill använda de nya pris- och rabattuppgifterna på den koncerninterna ordern eller lämna ordern oförändrad. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktioner som lagts till för denna version, enligt vad som beskrivs i de föregående avsnitten. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Huvudplanering, CTP | [Beräkna leveransdatum för försäljningsorder med hjälp av CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Huvudplanering, DDMRP | [Planeringsöversikt för efterfrågebaserade materialbehov](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Aktivera funktionen DDMRP i systemet](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Lagerplacering](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Buffertprofil och nivåer](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Efterfrågedriven planering](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Visuell och samarbetsinriktad körning](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Warehouse management | [Packa behållare för leverans](../warehousing/packing-containers.md)<br>[Förpackningsarbete för att packa utgående behållare och bearbeta försändelser](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Funktionstillstånd ändras i den här versionen

Följande tabell listar funktioner som blev obligatoriska eller aktiverade som standard i version 10.0.29. Alla dessa funktioner aktiveras automatiskt för ditt system så snart du uppdaterar till version 10.0.29. Obligatoriska funktioner kan inte stängas av, men funktioner som är på som standard kan fortfarande stängas av med [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tabellen visar även funktioner som tidigare var offentliga, men som har ändrats till att bli allmänt tillgängliga i version 10.0.29. Den här ändringen indikerar att funktionerna nu rekommenderas för användning i produktionsmiljöer. Dessa funktioner är avstängda som standard om inget annat anges. Därför måste du använda [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera dem om du vill använda dem.

| Modul | Funktionsnamn | Nytt funktionstillstånd |
| --- | --- | --- |
| Tillgångshantering | [Funktionen för Tillgångshantering för körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Kostnadshantering | [Ändra etiketten för annullering i stängning och justering till Återförd](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Obligatoriskt |
| Kostnadshantering | Rensa information om strukturlisteberäkning mellan korsvis kostnadsredovisningsversioner | Obligatoriskt |
| Kostnadshantering | [Jämför artikelprislager](../cost-management/compare-item-price.md) | Obligatoriskt |
| Kostnadshantering | [Kostnadsberäkningsnivå](../cost-management/cost-calculation-level.md) | På som standard |
| Kostnadshantering | Aktivera användardefinierat batchnummerkonfiguration för återföring av lagerstängning | På som standard |
| Kostnadshantering | [Information om lagerstängningsförlopp](whats-new-scm-10-0-21.md) | På som standard |
| Kostnadshantering | [Lagring av lagervärderapport](../cost-management/inventory-value-report-storage.md) | Obligatoriskt |
| Kostnadshantering | Lagervärderapport, datarensning | Obligatoriskt |
| Kostnadshantering | Glidande medelvärde, reservkostnadssekvens | Obligatoriskt |
| Kostnadshantering | Visa lagerstängningslogg i rutnät | Obligatoriskt |
| Kostnadshantering | Visa artiklar med inte helt kvittade transaktioner i sammanfattningsformat | Obligatoriskt |
| Hantering av lager och lagerstyrning | Tillåt tomma batchattributvärden | Obligatoriskt |
| Hantering av lager och lagerstyrning | Öka radnummer för orderrader i lageröverföring automatiskt | Obligatoriskt |
| Hantering av lager och lagerstyrning | Skapa överföringsorder från försäljningsrad | Obligatoriskt |
| Hantering av lager och lagerstyrning | Inaktivera radfält för lagerjournaler i arbetsflöde | Obligatoriskt |
| Hantering av lager och lagerstyrning | Aktivera varningsfunktionen för parametrar för lagerkvalitetshantering | Obligatoriskt |
| Hantering av lager och lagerstyrning | (Kina) Exkludera fysiska inleverans- och utleveranskostnader från månatlig genomsnittlig kostnad | På som standard |
| Hantering av lager och lagerstyrning | [Godkännandearbetsflöde för lagerjournal](../inventory/inventory-journal-workflow.md) | Obligatoriskt |
| Hantering av lager och lagerstyrning | [Lagring av lagerbehållningsrapport](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Obligatoriskt |
| Hantering av lager och lagerstyrning | [Sparade vyer för lagerhantering](saved-views-scm.md) | Obligatoriskt |
| Hantering av lager och lagerstyrning | Annullering av överföringsorder | Obligatoriskt |
| Hantering av lager och lagerstyrning | Med måttenhet och enhetskvantitet i lagerjournaler | Obligatoriskt |
| Hantering av lager och lagerstyrning | Lås upp lagerjournal | Obligatoriskt |
| Tillverkning | [Automatisk plockning av lagerställeaktiverade material för automatiskt bokförda plocklistor](whats-new-scm-10-0-23.md) | Allmänt tillgängligt |
| Tillverkning | Aktivera visning av lagerdimensioner i materiallistan för produktionsflödesoperationer | Obligatoriskt |
| Tillverkning | [Aktivera för att ange batch- och löpnummer vid rapportering som färdigt från jobbkortenheten](../production-control/report-finished-job-device.md) | På som standard |
| Tillverkning | Förbättrad produktionsplockning av kvantitet för faktisk/nominell vikt | På som standard |
| Tillverkning | [Jobbsökning för produktionsgolvets körningsgränssnitt](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Tillverkning | [Integrering med tillverkningskörningssystem](../production-control/mes-integration.md) | På som standard |
| Tillverkning | [Vyn Min dag i körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-configure.md) | På som standard |
| Tillverkning | [Kontroll av materialtillgänglighet på begäran för tillverkningsorder](whats-new-scm-10-0-24.md) | På som standard |
| Tillverkning | [Åsidosätta standardproduktionsreservation](../production-control/override-default-reservation-principle.md) | Obligatoriskt |
| Tillverkning | [Registrera materialförbrukning i körningsgränssnittet för produktionsgolv (icke-WMS)](../production-control/production-floor-execution-configure.md) | Allmänt tillgängligt |
| Tillverkning | [Rapportera artiklar med faktisk/nominell vikt från körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-configure.md) | Allmänt tillgängligt |
| Tillverkning | [Rapport om sam- och biprodukter från produktionsgolvets körningsgränssnitt](../production-control/production-floor-execution-configure.md) | På som standard |
| Tillverkning | [Rapportera planeringsartiklar i körningsgränssnittet för produktionsgolvet](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | På som standard |
| Tillverkning | [Sparade vyer för produktionskontroll](saved-views-scm.md) | Obligatoriskt |
| Tillverkning | [Visa fullständiga löpnummer, batch- och ID-nummer i gränssnittet för produktionsgolvkörning](../production-control/production-floor-execution-configure.md) | Obligatoriskt |
| Tillverkning | [Validera råmaterialets utgång mot planerat förbrukningsdatum](whats-new-scm-10-0-23.md) | På som standard |
| Huvudplanering | [Automatisk bekräftelse för Planeringsoptimering](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoriskt |
| Huvudplanering | [Batchbar bekräftelse och konsolidering för planerade bulk- och paketbatchorder](whats-new-scm-10-0-20.md) | På som standard |
| Huvudplanering | [Inkludera artiklar med behållning när förbearbetningsfilter har aktiverats](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | På som standard |
| Huvudplanering | [Planering av oändlig kapacitet för Planeringsoptimering](../master-planning/planning-optimization/infinite-capacity-planning.md) | På som standard |
| Huvudplanering | [Marginaler för planeringsoptimering](../master-planning/planning-optimization/safety-margins.md) | Obligatoriskt |
| Huvudplanering | [Negativa dagar för Planeringsoptimering](../master-planning/planning-optimization/delay-tolerance.md) | Obligatoriskt |
| Huvudplanering | [Parallell auktorisering av justerad efterfrågeprognos](whats-new-scm-10-0-20.md) | Obligatoriskt |
| Huvudplanering | [Bekräfta planerad order med filtrering](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoriskt |
| Huvudplanering | [Planerade produktionsorder för planeringsoptimering](../master-planning/planning-optimization/production-planning.md) | Obligatoriskt |
| Huvudplanering | [Inköpshandelsavtal för planeringsoptimering](../master-planning/planning-optimization/purchase-trade-agreement.md) | Obligatoriskt |
| Huvudplanering | [Sparade vyer för planerade order](saved-views-scm.md) | Obligatoriskt |
| Anskaffning och källa | Till- och från-avgifter på inköpsorder | Obligatoriskt |
| Anskaffning och källa | Inaktivera återställningsknappen för inköpsrekvisitionsdistribution | På som standard |
| Anskaffning och källa | [Aktivera återställning av anskaffningsrelaterade arbetsflöden](whats-new-scm-10-0-20.md) | På som standard |
| Anskaffning och källa | [Begränsa antalet inköpsorderrader per batchuppgift](whats-new-scm-10-0-27.md) | På som standard |
| Anskaffning och källa | [Sammanfoga ekonomiska dimensioner från providern med aktiv dimensionslänk för ekonomisk dimension på inköpsordern](whats-new-scm-10-0-25.md) | Obligatoriskt |
| Anskaffning och källa | [Bokför registrerade kvantiteter av produkter i lager och rester av produkter som inte finns i lager för inleveranser och leverantörsfakturor](whats-new-scm-10-0-26.md) | Allmänt tillgängligt |
| Anskaffning och källa | [Förhindra överkonsumering av huvudbudgetreservationer när flera inköpsrekvisitioner finns i arbetsflöde](whats-new-scm-10-0-21.md) | På som standard |
| Anskaffning och källa | [Ansvarig part för inköpsavtal](../procurement/purchase-agreements.md) | Obligatoriskt |
| Anskaffning och källa | [Sparade vyer för inköpsorder](saved-views-scm.md) | Obligatoriskt |
| Produktinformationshantering | Förbearbetning av strukturlisterapport för att undvika tidsgräns | Obligatoriskt |
| Produktinformationshantering | Använd ekonomiska dimensioner separat som standard vid användning av artikelmallar | Obligatoriskt |
| Produktinformationshantering | Aktivera produktdimensionsgrupper för artikelmallar | Obligatoriskt |
| Produktinformationshantering | Förbättringar av entiteten artikel-streckkod | Obligatoriskt |
| Produktinformationshantering | Generera om produktvarianter baserat på nomenklatur | Obligatoriskt |
| Produktinformationshantering | [Sparade vyer för frisläppta produkter](saved-views-scm.md) | Obligatoriskt |
| Produktinformationshantering | [Förbättringar av sidan med variantförslag](../pim/tasks/create-predefined-product-variants.md) | Obligatoriskt |
| Försäljning och marknadsföring | [Allokering av avgifter på en försäljningsorder](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Obligatoriskt |
| Försäljning och marknadsföring | Rensa försäljningsorderns uppdateringshistorik | Obligatoriskt |
| Försäljning och marknadsföring | [Rensa försäljningsuppdateringshistorik grundat på ålder](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Obligatoriskt |
| Försäljning och marknadsföring | [Optimering av kontaktpersons datatabellsexport](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Obligatoriskt |
| Försäljning och marknadsföring | Kopiera totalrabattgrupp för försäljningskreditfaktura | Obligatoriskt |
| Försäljning och marknadsföring | [Aktivera uppslag av dokumentintroduktion för försäljningsoffert och dokumentslutsatsfält](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Obligatoriskt |
| Försäljning och marknadsföring | [Förbättra rapportresultat för de 100 främsta kunderna](whats-new-scm-10-0-23.md) | Obligatoriskt |
| Försäljning och marknadsföring | Inkludera väntande poster i historikrensningsuppgifter | Obligatoriskt |
| Försäljning och marknadsföring | Begränsa antalet försäljningsorderrader per batchuppgift | På som standard |
| Försäljning och marknadsföring | [Begränsa antalet försäljningsorder som går att välja för bokföring](whats-new-scm-10-0-21.md) | Obligatoriskt |
| Försäljning och marknadsföring | Beräkna om uppskattat kundsaldo | Obligatoriskt |
| Försäljning och marknadsföring | [Registrering av försäljningsreturorderrad med decimalprecision med och utan faktisk/nominell vikt](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Obligatoriskt |
| Försäljning och marknadsföring | [Sparade vyer för försäljning och marknadsföring](saved-views-scm.md) | Obligatoriskt |
| Försäljning och marknadsföring | [Bekräftelse av försäljningsorder med ett klick](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Obligatoriskt |
| Transporthantering | Tillåt avmatchning av fraktsedlar från fraktfakturarader utan en bokförd leverantörsfakturajournal | På som standard |
| Transporthantering | [Gör det möjligt att skapa en leverantörsfakturajournal när en fraktsedel kastas](whats-new-scm-10-0-20.md) | På som standard |
| Transporthantering | [Leverans av små paket](../warehousing/small-parcel-shipping.md) | Obligatoriskt |
| Transporthantering | [Dokument för USMCA-ursprungsintyg](../transportation/usmca-certification-of-origin.md) | På som standard |
| Warehouse management | [Ytterligare platszoner](../warehousing/additional-location-zones.md) | Obligatoriskt |
| Warehouse management | [Avbryt arbete](../warehousing/cancel-warehouse-work.md) | Obligatoriskt |
| Warehouse management | [Konsolidera leverans](../warehousing/configure-shipment-consolidation-policies.md) | Obligatoriskt |
| Warehouse management | [Skapa och bearbeta överföringsorder från lagerställeappen](../warehousing/create-transfer-order-from-warehouse-app.md) | Obligatoriskt |
| Warehouse management | Mallar för direktleverans med platsdirektiv | På som standard |
| Warehouse management | [Avkoda platsarbete från ASN:er](whats-new-scm-10-0-21.md) | Obligatoriskt |
| Warehouse management | [Uppskjutna put-åtgärder](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoriskt |
| Warehouse management | Uppskjuten – behållare | På som standard |
| Warehouse management | Uppskjuten placeringsbearbetning – aktivera för granskningsmallfunktionen där utlösarhändelsen anges till Tidigare | Obligatoriskt |
| Warehouse management | [Inaktivera förväntade inleveranser från kvalitetsorder som ger exempel på blockerat lager](../inventory/inventory-blocking.md) | På som standard |
| Warehouse management | Aktivera snabbvalidering för lagerställets mobila enheter | Obligatoriskt |
| Warehouse management | [Utökad parser för GS1-streckkoder](../warehousing/gs1-barcodes.md) | Allmänt tillgängligt |
| Warehouse management | [Flexibelt orderutfäst registreringsskyltsreservation](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoriskt |
| Warehouse management | [Flexibel dimensionsreservation på lagerställenivå](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoriskt |
| Warehouse management | [Utnyttjande av artikelns konsolideringsplats](../warehousing/item-consolidation-location-utilization.md) | På som standard |
| Warehouse management | Inleveranshistorik för ID-nummer | På som standard |
| Warehouse management | [Manuell leveranskonsolidering](../warehousing/consolidate-shipments-manual-workbench.md) | På som standard |
| Warehouse management | [Manuell plockningstjänst för överföringsrad för admin eller liknande betrodda användare](whats-new-scm-10-0-28.md) | Allmänt tillgängligt |
| Warehouse management | [Materialhanteringsutrustningens gränssnitt](../warehousing/mhax.md) | Obligatoriskt |
| Warehouse management | [Nya sidor för lastplaneringsworkbench](whats-new-scm-10-0-24.md) | Allmänt tillgängligt |
| Warehouse management | [Visualisering av utgående arbetsbelastning](../warehousing/outbound-workload-visualization.md) | Obligatoriskt |
| Warehouse management | [Planerad direktleverans](../warehousing/planned-cross-docking.md) | Obligatoriskt |
| Warehouse management | [Bearbeta lagerställeapphändelser](../warehousing/warehouse-app-events.md) | Obligatoriskt |
| Warehouse management | Frågeförbättring för arbetsmallen Plats för samprodukt och biprodukt | Obligatoriskt |
| Warehouse management | [Avrunda kvantiteter neråt till närmaste försäljningsenhet vid frisläpp till lagerställe](whats-new-scm-10-0-19.md) | Obligatoriskt |
| Warehouse management | [Sparad vy för workbench vid lastplanering](saved-views-scm.md) | Obligatoriskt |
| Warehouse management | [Sparad vy för sidan Information om arbete](saved-views-scm.md) | Obligatoriskt |
| Warehouse management | [Sparad vy för påfyllnadsbearbetning](saved-views-scm.md) | Obligatoriskt |
| Warehouse management | [Sparade vyer för lastbearbetning](saved-views-scm.md) | Obligatoriskt |
| Warehouse management | [Sparade vyer för leveransbearbetning](saved-views-scm.md) | Obligatoriskt |
| Warehouse management | [Skanna GS1-streckkoder](../warehousing/gs1-barcodes.md) | Allmänt tillgängligt |
| Warehouse management | Information om etikett för leveranspåfyllnad | Obligatoriskt |
| Warehouse management | [Blandade enheter i fack](whats-new-scm-10-0-21.md) | Obligatoriskt |
| Warehouse management | [Använd snabbare API för behållare som stängs/öppnas igen på förpackningsstationen](whats-new-scm-10-0-21.md) | På som standard |
| Warehouse management | [Validera mallar valda för lagerpåfyllnadsjobb](whats-new-scm-10-0-20.md) | På som standard |
| Warehouse management | [Erbjudna fält i lagerställeapp](../warehousing/warehouse-app-promoted-fields.md) | Obligatoriskt |
| Warehouse management | [Steginstruktioner för lagerställeapp](../warehousing/mobile-app-titles-instructions.md) | Obligatoriskt |
| Warehouse management | [Lagerställets platsstatus](../warehousing/warehouse-location-status.md) | Obligatoriskt |
| Warehouse management | [Omvägar för lagerstyrningsappen Warehouse Management](../warehousing/warehouse-app-detours.md) | På som standard |
| Warehouse management | [Information om påfyllnadsbatchjobb](../warehousing/wave-processing.md) | Obligatoriskt |
| Warehouse management | [Meddelanden för påfyllnadskörning](../warehousing/wave-execution-notifications.md) | Obligatoriskt |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.29 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.29 av Ekonomi och Drift-appar (oktober 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i version 10.0.29 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022](/dynamics365-release-plan/2022wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
