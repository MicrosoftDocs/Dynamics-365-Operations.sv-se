---
title: Aktivera kassaflödesprognoser (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f7c06eaeb79c1a2aa319cfa3d2ad8255bf716cd0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818738"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="194c2-103">Aktivera kassaflödesprognoser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="194c2-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="194c2-104">I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.</span><span class="sxs-lookup"><span data-stu-id="194c2-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="194c2-105">Om du vill använda betalningsförutsägelser i kassaflödet måste du ställa in funktionen Prediktioner av kundbetalning enligt beskrivningen i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="194c2-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="194c2-106">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="194c2-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="194c2-107">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="194c2-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="194c2-108">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="194c2-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="194c2-109">Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="194c2-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="194c2-110">Teamet för Finance-insikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="194c2-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="194c2-111">Om funktionerna inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera dem, kontaktar du <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="194c2-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="194c2-112">Öppna arbetsytan **Funktionshantering** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="194c2-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="194c2-113">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="194c2-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="194c2-114">Aktivera följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="194c2-114">Turn on the following features:</span></span>

        - <span data-ttu-id="194c2-115">Ny rutnätskontroll</span><span class="sxs-lookup"><span data-stu-id="194c2-115">New grid control</span></span>
        - <span data-ttu-id="194c2-116">Gruppering i rutnät (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="194c2-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="194c2-117">Kundbetalningsförutsägelser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="194c2-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="194c2-118">Kassaflödesprognoser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="194c2-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="194c2-119">Gå till **Kassa- och bankhantering \> Kassaflödesprognosinställningar** och lägg till likviditetskontona som ska inkluderas i prognoserna.</span><span class="sxs-lookup"><span data-stu-id="194c2-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="194c2-120">Om likviditetskonton inte har konfigurerats kan kassaflödet inte genereras.</span><span class="sxs-lookup"><span data-stu-id="194c2-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="194c2-121">Gå till **Kassa- och bankhantering \> Konfigurera \> Finance-insikter (förhandsversion) \> Kassaflödesprognoser (förhandsversion)** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="194c2-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="194c2-122">På fliken **Kassaflödesprognos** väljer du **Aktivera funktion**.</span><span class="sxs-lookup"><span data-stu-id="194c2-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="194c2-123">Välj **Skapa förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="194c2-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="194c2-124">Mer information om funktionen för kassaflödesprognoser finns i [Kassaflödesprognoser](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="194c2-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="194c2-125">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="194c2-125">Privacy notice</span></span>

<span data-ttu-id="194c2-126">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="194c2-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]