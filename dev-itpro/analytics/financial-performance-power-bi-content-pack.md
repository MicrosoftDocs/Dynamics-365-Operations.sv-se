---
title: "Innehållspaket för ekonomiska resultat för Power BI"
description: "Denna artikel förklarar innehållspaketet Microsoft Dynamics 365 for Operations Financial Performance för Microsoft Power BI. Det beskriver instrumentpanelen och de rapporter som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Innehållspaket för ekonomiska resultat för Power BI

[!include[banner](../includes/banner.md)]


Denna artikel förklarar innehållspaketet Microsoft Dynamics 365 for Operations Financial Performance för Microsoft Power BI. Det beskriver instrumentpanelen och de rapporter som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
--------------------------

Det finns två versioner av ekonomiska innehållspaket. En version är tillgänglig från Microsoft Dynamics Lifecycle Services (LCS), och den andra är tillgänglig från PowerBI.com.

-   **Versionen som är tillgänglig från LCS:** Innehållspaketet för ekonomiska resultat från LCS stöder Microsoft Dynamics 365 for Operations version 1611. Du hittar innehållspaketet i det delade resursbiblioteket i LCS. Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).
-   **Versionen som är tillgänglig från PowerBI.com:** Innehållspaketet för ekonomiska resultat från PowerBI.com stöder Microsoft Dynamics 7.0 AX, versioner 7.0 och 7.0.1. Mer information om hur du ansluter och laddar dina Microsoft Dynamics 365 for Operations-data, se [Åtkomst till Power BI-innehåll från PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Huvudkontoinställningar
Konfigurationen av huvudkonton i Dynamics 365 for Operations är viktig eftersom organisationer vill att skuld- och intäktsbelopp ska anges som positiva belopp i rapporter. Huvudkontotypen måste anges som **Skuld** eller **Intäkt** för att huvudkontona ska anges som positiva belopp. När dessa kontotyper används, kommer rapporteringen via Microsoft Power BI att vända på tecknen och ange beloppen som positiva.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Instrumentpanelen och rapporterna som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Dynamics 365 for Operations-data kommer instrumentpanelen och rapporterna att visa dina ekonomiska data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Instrumentpanelen innehåller summerade datarutor baserade på underliggande rapporter. Varje ruta innehåller sammanfattad information för innevarande år för alla företag i en organisation. Här följer några exempel på paneler:

-   Kontant
-   Totala intäkter i år
-   Totala utgifter i år
-   Nettoinkomst i år
-   Snabbkvot
-   Totala utgifter i år efter kontokategori
-   Aktuell kvot
-   Skuld till totala tillgångar
-   Verkliga mot prognosticerade intäkter
-   Fakturerade intäkter i år
-   Kvot för verksamhetsutgifter i år
-   Vinstmarginal i år
-   Verkliga mot budgeterade utgifter – Alla företag

Var och en av dessa paneler backas upp av en underliggande rapport. Dessa rapporter innehåller både diagram och register som innehåller mer information. Följande register beskriver rapporterna.

| Rapport                      | Information som rapporten innehåller                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kassaanalys               | Kontanter per juridisk person, kontanter per kvartal, totala kontanter och kontanter per konto **Obs!:** Rapporten **Kontanter per kvartal** omfattar inte ingående saldon i summan för det första kvartalet. Summan av nya transaktioner som bokförs under varje kvartal visas.                                                                                |
| Aktuell kvotanalys      | Aktuell kvot per juridisk person, aktuell kvot per kvartal och saldon för omsättningstillgångar och kortfristiga skulder                                                                                                                                                                                                                              |
| Snabb kvotanalys        | Snabbkvot per juridisk person, snabbkvot per kvartal och saldon för kassa, kundreskontra och kortfristiga skulder                                                                                                                                                                                                                      |
| Kostnadsanalys för sålda varor | Kostnad för sålda varor (COGS) efter juridisk person, kostnad för sålda varor i år och förra året per kvartal, kostnaden för sålda varor till försäljning per juridisk person, total kostnad för sålda varor samt kostnad för sålda varor till försäljningprocentsatsen                                                                                                                                                                                   |
| Analys av arbetande kapital    | Arbetande kapital efter juridisk person, arbetande kapital per kvartal, omsättningstillgångar, kortfristiga skulder och totalt arbetande kapital                                                                                                                                                                                                                   |
| Tillgångs- och skuldanalys     | Avkastning på totala tillgångar och skuld till totala tillgångar efter juridisk person, skuld till totala tillgångar och avkastning på totala tillgångar (kvartal till dags dato), tillgångar och skulder                                                                                                                                                                                     |
| Analys av vinstmarginal      | Verklig vinstmarginal och budgetvinstmarginal efter juridisk person, vinstmarkering efter kvartal, vinstmarginalprocentsats och vinstmarginal                                                                                                                                                                                                                       |
| Analys av nettoinkomst         | Verkliga och budgeterade nettointäkter efter juridisk person, nettointäkter i år och förra året, samt utgifter till nettoinkomstprocentsatsen                                                                                                                                                                                                                       |
| Intäktsanalys           | Verkliga intäkter och budgetintäkter före ränta och moms (EBIT) efter juridisk person, EBIT i år och förra året, utgifter till intäktsprocentsatsen, samt verkliga och budgeterade utgifter till intäkt                                                                                                                                                          |
| Intäktsanalys            | Totala intäkter, verkliga och budgeterade totala intäkter efter juridisk person, totala intäkter i år och förra året, budgetkostnadsavvikelse efter juridisk person och totala intäkter under denna period och den sista perioden                                                                                                                                                 |
| Utgiftsanalys            | Totala utgifter, faktiska utgifter i jämförelse med totala budgeterade utgifter efter juridisk person, faktiska och budgeterade totala utgifter efter kvartal, totala utgifter efter kontokategori och kvot för verksamhetsutgifter                                                                                                                                                                 |
| Fakturerad intäktsanalys     | Summa för kundreskontra, summa för kundreskontra per juridisk person, summa för kundreskontra per kvartal och saldon för konton för kundreskontra **Obs!** Rapporterna inkluderar inte ingående saldon för redovisningskonton för kundreskontra. De visar summan av nya transaktioner som bokförs under kundreskontra. |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Den data som fylls i på instrumentpanelen och rapporterna i innehållspaketet för ekonomiskt resultat är Dynamics 365 for Operations-data. Följande enheter användes till grund för innehållspaketet: **Aggregerade dataposter**

-   **GeneralLedgerActivities** - Denna enhet sammanställer redovisningssaldon efter kontokategori.
-   **BudgetActivities** - Denna enhet sammanställer budgetsaldon efter kontokategori.

**Dataenheter**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Redovisningar
-   ChartofAccounts

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehållspaketet. Som standard kommer innehållspaketet med data för de senaste tre åren och ett framtida år. Om du vill ta med ytterligare beräkningar i dina rapporter och din instrumentpanel, kan du ändra arbetsboken [Microsoft Excel-arbetsboken](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Denna arbetsbok är den standarddatamodell som använts för att skapa innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)





