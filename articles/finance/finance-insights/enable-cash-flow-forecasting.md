---
title: Aktivera kassaflödesprognoser (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222568"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="8927d-103">Aktivera kassaflödesprognoser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8927d-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8927d-104">I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.</span><span class="sxs-lookup"><span data-stu-id="8927d-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="8927d-105">Om du vill använda betalningsförutsägelser i kassaflödet måste du ställa in funktionen Prediktioner av kundbetalning enligt beskrivningen i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="8927d-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="8927d-106">Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön.</span><span class="sxs-lookup"><span data-stu-id="8927d-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="8927d-107">Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön.</span><span class="sxs-lookup"><span data-stu-id="8927d-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="8927d-108">(Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="8927d-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="8927d-109">Hoppa över det här steget om du använder version 10.0.20 eller senare, eller om du använder en Service Fabric-distribution.</span><span class="sxs-lookup"><span data-stu-id="8927d-109">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="8927d-110">Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig.</span><span class="sxs-lookup"><span data-stu-id="8927d-110">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="8927d-111">Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="8927d-111">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="8927d-112">Öppna arbetsytan **Funktionshantering** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="8927d-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="8927d-113">Välj **Sök efter uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="8927d-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="8927d-114">Aktivera följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="8927d-114">Turn on the following features:</span></span>

        - <span data-ttu-id="8927d-115">Ny rutnätskontroll</span><span class="sxs-lookup"><span data-stu-id="8927d-115">New grid control</span></span>
        - <span data-ttu-id="8927d-116">Gruppering i rutnät (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8927d-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="8927d-117">Kundbetalningsförutsägelser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8927d-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="8927d-118">Kassaflödesprognoser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8927d-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="8927d-119">Gå till **Kassa- och bankhantering \> Kassaflödesprognosinställningar** och lägg till likviditetskontona som ska inkluderas i prognoserna.</span><span class="sxs-lookup"><span data-stu-id="8927d-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8927d-120">Om likviditetskonton inte har konfigurerats kan kassaflödet inte genereras.</span><span class="sxs-lookup"><span data-stu-id="8927d-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="8927d-121">Gå till **Kassa- och bankhantering \> Konfigurera \> Finance-insikter (förhandsversion) \> Kassaflödesprognoser (förhandsversion)** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="8927d-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="8927d-122">På fliken **Kassaflödesprognos** väljer du **Aktivera funktion**.</span><span class="sxs-lookup"><span data-stu-id="8927d-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="8927d-123">Välj **Skapa förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="8927d-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="8927d-124">Mer information om funktionen för kassaflödesprognoser finns i [Kassaflödesprognoser](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="8927d-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
