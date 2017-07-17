---
title: "Innehållspaket för ekonomiska resultat för Power BI"
description: "Det här avsnittet beskriver Power BI-innehåll för finansiellt resultat. Det beskriver instrumentpanelen och de rapporter som är inkluderade, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet."
author: kweekley
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b20f526d20d357750777d0f9bda26e4d9d55b335
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Innehållspaket för ekonomiska resultat för Power BI
<a id="financial-performance-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehåll för **finansiellt resultat**. Det beskriver instrumentpanelen och de rapporter som är inkluderade, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet.

## Åtkomst till Power BI-innehåll
<a id="accessing-the-power-bi-content" class="xliff"></a>

Du kan använda **ekonomiska resultat** Power BI från Microsoft Dynamics Lifecycle Services (LCS) och PowerBI.com.

### Tillgänglig från LCS
<a id="available-from-lcs" class="xliff"></a>
Det Power BI-innehåll för **ekonomiska resultat** som är tillgängligt från LCS stödjer följande versioner:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, juli 2017 uppdatering
- Microsoft Dynamics 365 for Operations version 1611 

Du hittar  Power BI-innehållet i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

### Från PowerBI.com
<a id="available-from-powerbicom" class="xliff"></a>
Power BI-innehållet för **exkomnomiska resultat** som finns på PowerBI.com stöder Microsoft Dynamics 7.0 AX, versioner 7.0 och 7.0.1. Mer information om hur du ansluter och laddar dina Dynamics AX, se [Åtkomst till Power BI-innehåll från PowerBI.com](power-bi-home-page.md).

## Huvudkontoinställningar
<a id="main-account-setup" class="xliff"></a>
Konfigurationen av huvudkonton är viktig eftersom organisationer vill att skuld- och intäktsbelopp ska anges som positiva belopp i rapporter. Huvudkontotypen måste anges som **Skuld** eller **Intäkt** för att huvudkontona ska anges som positiva belopp. När dessa kontotyper används, kommer rapporteringen via Power BI att vända på tecknen och ange beloppen som positiva.

## Instrumentpanelen och rapporterna som ingår i Power BI-innehåll
<a id="dashboard-and-reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
Instrumentpanelen innehåller summerade datarutor baserade på underliggande rapporter. Varje ruta innehåller sammanfattad information för innevarande år för alla företag i en organisation. Här följer några exempel på paneler:

- Kontant
- Totala intäkter i år
- Totala utgifter i år
- Nettoinkomst i år
- Snabbkvot
- Totala utgifter i år efter kontokategori
- Aktuell kvot
- Skuld till totala tillgångar
- Verkliga mot prognosticerade intäkter
- Fakturerade intäkter i år
- Kvot för verksamhetsutgifter i år
- Vinstmarginal i år
- Verkliga mot budgeterade utgifter – Alla företag

Var och en av dessa paneler backas upp av en underliggande rapport. Dessa rapporter innehåller både diagram och register som innehåller mer information. Följande register beskriver rapporterna.

| Rapport                      | Information som rapporten innehåller |
|-----------------------------|--------------------------------------|
| Kassaanalys               | Kassa efter juridisk person, kassa per kvartal, kassa totalt och kassa efter konto<blockquote>[!NOTE]<br>Informationen kassa per kvartal innehåller inga ingående saldon i totalsumman för det första kvartalet. Summan av nya transaktioner som bokförs under varje kvartal visas.</blockquote> |
| Aktuell kvotanalys      | Aktuell kvot per juridisk person, aktuell kvot per kvartal och saldon för omsättningstillgångar och kortfristiga skulder |
| Snabb kvotanalys        | Snabbkvot per juridisk person, snabbkvot per kvartal och saldon för kassa, kundreskontra och kortfristiga skulder |
| Kostnadsanalys för sålda varor | Kostnad för sålda varor (COGS) efter juridisk person, kostnad för sålda varor i år och förra året per kvartal, kostnaden för sålda varor till försäljning per juridisk person, total kostnad för sålda varor samt kostnad för sålda varor till försäljningprocentsatsen |
| Analys av arbetande kapital    | Arbetande kapital efter juridisk person, arbetande kapital per kvartal, omsättningstillgångar, kortfristiga skulder och totalt arbetande kapital |
| Tillgångs- och skuldanalys     | Avkastning på totala tillgångar och skuld till totala tillgångar efter juridisk person, skuld till totala tillgångar och avkastning på totala tillgångar (kvartal till dags dato), tillgångar och skulder |
| Analys av vinstmarginal      | Verklig vinstmarginal och budgetvinstmarginal efter juridisk person, vinstmarkering efter kvartal, vinstmarginalprocentsats och vinstmarginal |
| Analys av nettoinkomst         | Verkliga och budgeterade nettointäkter efter juridisk person, nettointäkter i år och förra året, samt utgifter till nettoinkomstprocentsatsen |
| Intäktsanalys           | Verkliga intäkter och budgetintäkter före ränta och moms (EBIT) efter juridisk person, EBIT i år och förra året, utgifter till intäktsprocentsatsen, samt verkliga och budgeterade utgifter till intäkt |
| Intäktsanalys            | Totala intäkter, verkliga och budgeterade totala intäkter efter juridisk person, totala intäkter i år och förra året, budgetkostnadsavvikelse efter juridisk person och totala intäkter under denna period och den sista perioden |
| Utgiftsanalys            | Totala utgifter, faktiska utgifter i jämförelse med totala budgeterade utgifter efter juridisk person, faktiska och budgeterade totala utgifter efter kvartal, totala utgifter efter kontokategori och kvot för verksamhetsutgifter |
| Fakturerad intäktsanalys     | Total kundreskontra, totala kundreskontra efter juridisk person, totala kundreskontra efter kvartal och saldon för kundreskontra-konton<blockquote>[!NOTE]<br>Informationen innehåller inga ingående saldon för redovisningskonton för kundreskontra. Den visar summan av nya transaktioner som bokförs under kundreskontra.</blockquote> |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## Förstå datamodellen och enheterna
<a id="understanding-the-data-model-and-entities" class="xliff"></a>
Följande enheter användes till grund för Power BI-innehållspaket för **ekonomiska resultat**

**Enheter för aggregerade data**

- **GeneralLedgerActivities** - Denna enhet sammanställer redovisningssaldon efter kontokategori.
- **BudgetActivities** - Denna enhet sammanställer budgetsaldon efter kontokategori.

**Dataenheter**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Redovisningar
- ChartofAccounts

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehåll. Som standard kommer innehållspaketet med data för de senaste tre åren och ett framtida år. Om du vill ta med ytterligare beräkningar i dina rapporter och din instrumentpanel, kan du ändra arbetsboken [Microsoft Excel-arbetsboken](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Denna arbetsbok är den standarddatamodell som använts för att skapa innehållet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

