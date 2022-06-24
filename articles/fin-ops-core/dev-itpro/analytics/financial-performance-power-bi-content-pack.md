---
title: Innehållspaket för ekonomiska resultat för PowerBI.com
description: Den här artikeln beskriver PowerBI.com-lösning för finansiellt resultat.
author: kweekley
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcbe41d113ee41734020546388851afb7fc27bbf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910427"
---
# <a name="financial-performance-powerbicom-solution"></a>Innehållspaket för ekonomiska resultat för PowerBI.com

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Den här PowerBI.com lösningen är föråldrad som dokumenteras i [borttagna eller inaktuella funktioner för Finance and Operations](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Den här artikeln beskriver PowerBI.com-lösning för **finansiellt resultat**. Det beskriver instrumentpanelen och de rapporter som är inkluderade, samt ger dig information om den datamodell och de enheter som användes för att skapa lösningen.

## <a name="main-account-setup"></a>Huvudkontoinställningar
Konfigurationen av huvudkonton är viktig eftersom organisationer vill att skuld- och intäktsbelopp ska anges som positiva belopp i rapporter. Huvudkontotypen måste anges som **Skuld** eller **Intäkt** för att huvudkontona ska anges som positiva belopp. När dessa kontotyper används, kommer rapporteringen via Power BI att vända tecknen och ange beloppen som positiva.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>Instrumentpanelen och rapporterna som ingår i PowerBI.com-lösning
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
| Kassaanalys               | Kassa efter juridisk person, kassa per kvartal, kassa totalt och kassa efter konto<blockquote>[!NOTE] Informationen kassa per kvartal innehåller inga ingående saldon i totalsumman för det första kvartalet. Summan av nya transaktioner som bokförs under varje kvartal visas.</blockquote> |
| Aktuell kvotanalys      | Aktuell kvot per juridisk person, aktuell kvot per kvartal och saldon för omsättningstillgångar och kortfristiga skulder |
| Snabb kvotanalys        | Snabbkvot per juridisk person, snabbkvot per kvartal och saldon för kassa, kundreskontra och kortfristiga skulder |
| Kostnadsanalys för sålda varor | Kostnad för sålda varor (COGS) efter juridisk person, kostnad för sålda varor i år och förra året per kvartal, kostnaden för sålda varor till försäljning per juridisk person, total kostnad för sålda varor samt kostnad för sålda varor till försäljningprocentsatsen |
| Analys av arbetande kapital    | Arbetande kapital efter juridisk person, arbetande kapital per kvartal, omsättningstillgångar, kortfristiga skulder och totalt arbetande kapital |
| Tillgångs- och skuldanalys     | Avkastning på totala tillgångar och skuld till totala tillgångar efter juridisk person, skuld till totala tillgångar och avkastning på totala tillgångar (kvartal till dags dato), tillgångar och skulder |
| Analys av vinstmarginal      | Verklig vinstmarginal och budgetvinstmarginal efter juridisk person, vinstmarkering efter kvartal, vinstmarginalprocentsats och vinstmarginal |
| Analys av nettoinkomst         | Verkliga och budgeterade nettointäkter efter juridisk person, nettointäkter i år och förra året, samt utgifter till nettoinkomstprocentsatsen |
| Intäktsanalys           | Verkliga intäkter och budgetintäkter före ränta och skatt (EBIT) efter juridisk person, EBIT i år och förra året, utgifter till intäktsprocentsatsen, samt verkliga och budgeterade utgifter till intäkt |
| Intäktsanalys            | Totala intäkter, verkliga och budgeterade totala intäkter efter juridisk person, totala intäkter i år och förra året, budgetkostnadsavvikelse efter juridisk person och totala intäkter under denna period och den sista perioden |
| Utgiftsanalys            | Totala utgifter, faktiska utgifter i jämförelse med totala budgeterade utgifter efter juridisk person, faktiska och budgeterade totala utgifter efter kvartal, totala utgifter efter kontokategori och kvot för verksamhetsutgifter |
| Fakturerad intäktsanalys     | Total kundreskontra, totala kundreskontra efter juridisk person, totala kundreskontra efter kvartal och saldon för kundreskontra-konton<blockquote>[!NOTE] Informationen innehåller inga ingående saldon för redovisningskonton för kundreskontra. Den visar summan av nya transaktioner som bokförs under kundreskontra.</blockquote> |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande enheter användes till grund för PowerBI.com-lösningen för **ekonomiska resultat**

**Enheter för aggregerade data**

- **GeneralLedgerActivities** - Denna enhet sammanställer redovisningssaldon efter kontokategori.
- **BudgetActivities** - Denna enhet sammanställer budgetsaldon efter kontokategori.

**Dataenheter**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Redovisningar
- ChartofAccounts

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehåll. Som standard kommer innehållspaketet med data för de senaste tre åren och ett framtida år. Om du vill ta med ytterligare beräkningar i dina rapporter och din instrumentpanel, kan du ändra arbetsboken i [Microsoft Excel](/dynamics/s-e/). Denna arbetsbok är den standarddatamodell som använts för att skapa innehållet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]