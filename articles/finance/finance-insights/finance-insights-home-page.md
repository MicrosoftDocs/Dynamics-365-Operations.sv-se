---
title: Finance insights – startsida (förhandsversion)
description: Finance insights ger konfigurerbara och utökningsbara modeller för att hjälpa dig att noggrant och effektivt förutsäga företagets kassaflöde, när du ska få betalning för utestående kundfordringar och skapa ett budgetförslag som kan påskynda budgetprocessen. Alla dessa funktioner baseras på intelligenta maskininlärningsmodeller.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8c9d5b9857e978eb5e591f4d854d687f33b438025e81fe2c827ab7ecdb2be4e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768829"
---
# <a name="finance-insights-home-page-preview"></a>Finance insights – startsida (förhandsversion)

[!include [banner](../includes/banner.md)]

Finance insights ger konfigurerbara och utökningsbara modeller för att hjälpa dig att noggrant och effektivt förutsäga företagets kassaflöde, när du ska få betalning för utestående kundfordringar och skapa ett budgetförslag som kan påskynda budgetprocessen. Alla dessa funktioner baseras på intelligenta maskininlärningsmodeller. När dessa nya funktioner kombineras med automatisering i leverantörsbetalningar och -samlingar, tillhandahåller de ett omfattande och intelligent system som driver beslutsfattande och hjälper dig att vidta åtgärder för att effektivt svara på aktuella och förväntade affärsutmaningar.

> [!NOTE]
> Förhandsversionen av Finance Insights finns tillgänglig för distribution i USA, Kanada, Storbritannien, Europa, Asien och stillahavsområdet, Australien och Nya Zeeland. Microsoft lägger stegvis till support för fler regioner. Om du vill aktivera Finance Insights för produktionsmiljöer måste du först aktivera funktionerna för [Exportera till Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) i produktionsmiljön.

> [!NOTE]
> Den här funktionen ges som en uppsättning förhandsgranskningsfunktioner. Som en förhandsgranskning bör du inte använda de resulterande maskininlärningsmodellerna för att påverka dina affärsbeslut eller budgeteringsförslag. Din användning av den här funktionen regleras [extra användningsvillkor](https://go.microsoft.com/fwlink/?linkid=2105274).

## <a name="prerequisites"></a>Förutsättningar

I det här avsnittet beskrivs kraven för att använda Finance insights. När det är möjligt tillhandahålls länkar till källor med ytterligare information.

### <a name="legal-requirements"></a>Lagkrav

Om du vill ansöka om att använda förhandsversionen av programmet fyller du i [Avtal för förhandsversion av Finance insights för Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Systemkrav

En nivå-2-miljö (multibox) krävs för att förhandsgranska Finance insights. Mer bakgrundsinformation om miljöer finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Versionskrav

Det här dokumentet gäller för version 10.0.11 av Finance and Operations-appar (Platform update 35) och senare versioner.

### <a name="historical-data-requirements"></a>Historiska datakrav

Minst ett års kundfakturor krävs för att korrekt träna den maskininlärningsmodell som används för funktionen Prediktioner av kundbetalning.

### <a name="role-and-permission-requirements"></a>Roll- och behörighetskrav

Ändringar görs i Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps och Azure. Korrekta behörigheter krävs i alla dessa miljöer. Nedan följer några exempel på de ändringar som görs:

- En ny miljö kommer att skapas i Microsoft Power Platform.
- Ett lagringskonto, nyckelvalv och program kommer att skapas i Azure.
- Administratören av Active Directory-klientorganisationen måste auktorisera AI Builder-programmet för åtkomst till datasjön.
- Funktionen aktiveras i Dynamics 365.

Om du är bekant med processen för att skapa och hantera resurser i Azure, Microsoft Dataverse och LCS kommer det vara till hjälp när du slutför processen.

## <a name="configure-finance-insights"></a>Konfigurera Finance insights

Du måste slutföra vissa konfigurationssteg innan du kan använda Finance insights. Mer information om hur du konfigurerar Finance insights finns i:
  - För versioner upp till 10.0.19: [Konfiguration för Finance insights (förhandsversion) – versioner upp till 10.0.19](configure-for-fin-insites.md).
  - För version 10.0.20 och senare: [Konfiguration för Finance insights (förhandsversion) – versioner 10.0.20 och senare](configure-for-fin-insites-PubPrvw.md).

## <a name="create-a-data-integrator-project"></a>Skapa ett projekt för dataintegrerare

Du måste skapa ett projekt för dataintegrerare så att data som skapas i maskininlärningsmodellen kan flöda in Dynamics 365 Finance. Information om hur du skapar ett sådant projekt finns i [Skapa ett projekt för dataintegrerare](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Aktivera funktioner för Finance insights

När du har slutfört konfigurationsstegen och konfigurerat demodata måste du aktivera och ställa in varje funktion som du vill använda: kundbetalningsförutsägelser, kassaflödesprognoser och budgetförslag.

### <a name="enable-customer-payment-predictions"></a>Aktivera prediktioner av kundbetalning
Om du använder demodata för att testa kundbetalningsförutsägelser måste du kanske importera ytterligare demodata för att kunna skapa din AI-modell. 

Om du vill aktivera kundbetalningsförutsägelser måste du utföra en uppsättning steg för att bygga en maskininlärningsmodell som använder organisationens data för att generera förutsägelser om när det är sannolikt att kunder betalar utestående fakturor, och när specifika fakturor sannolikt kommer att betalas. Mer information och de olika stegen finns i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Aktivera kassaflödesprognoser
Om du vill aktivera kassaflödesprognoser måste du utföra en uppsättning steg för att bygga en maskininlärningsmodell som använder organisationens data för att generera kassaflödesprognoser. Mer information och de olika stegen finns i [Aktivera kassaflödesprognoser](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Aktivera budgetförslag

I funktionen Budgetförslag används en maskininlärningsmodell tillsammans med din organisations historiska data för att generera ett budgetförslag. Det genererade förslaget kan hjälpa dig att påbörja en budgetprocess som är effektivare än en manuell process. Mer information om hur du aktiverar den här funktionen finns i [Aktivera budgetförslag](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Använda Finance insights-funktioner

### <a name="using-customer-payment-predictions"></a>Använda prediktioner av kundbetalning

Den intelligenta kassaflödesprognosen skapas ovanpå den befintliga funktionen för kassaflödesprognos i Dynamics 365 Finance. Information om hur du granskar den befintliga funktionen finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md).

- Mer information om hur kundbetalningsförutsägelser kan tillhandahålla den information som behövs för att proaktivt vara inkassoaktiviteter finns i [Använda prediktioner av kundbetalning](use-customer-payment-predictions.md).
- Mer information som kan hjälpa dig att utvärdera förutsägelsemodellens effektivitet när du har börjat använda funktionen finns i [Utvärdera den första förutsägelsemodellen för kundbetalning](evaluate-payment-prediction.md).
- Mer information som kan hjälpa dig att justera de data som används för att bygga förutsägelsen och därigenom förbättra dess effektivitet finns i [Förbättra prediktionsmodellen](improve-model.md).

Mer information om resultaten av AI-förutsägelsemodeller finns i [Resultat av maskininlärningsmodeller](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Använda kassaflödesprognoser

Med hjälp av funktionen för kassaflödesprognos kan du få en mer exakt uppskattning av din kassaposition. 

- Mer information om de nya funktionerna i kassaflödesprognoser finns i [Kassaflödesprognos](cash-flow-forecast-intro.md).
- Mer information om hur du importerar externa data som ska inkluderas i kassaflödesprognosen finns i [Använda externa data i kassaflödesprognoser](external-data-in-cash-flow.md). 
- Information om hur du använder en AI-modell för att förutsäga kassaflöden för kortfristiga perioder finns i [Kassaplacering](cash-position.md).
- Information om hur du sparar kassaflödespositioner och kassaflödesprognoser som ögonblicksbilder och för att jämföra en ögonblicksbild med verkliga värden finns i [Översikt över ögonblicksbilder](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Använda budgetförslag

Information om hur du påskyndar skapandet av en budget finns i [Budgetförslag](budget-proposals.md). 

## <a name="feedback-and-support"></a>Feedback och support

Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
