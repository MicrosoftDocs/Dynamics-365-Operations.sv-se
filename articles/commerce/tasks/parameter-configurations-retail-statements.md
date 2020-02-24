---
title: Konfigurera parametrar som berör butiksutdrag
description: I det här avsnittet visas konfigurationer för handelsparametrarna som påverkar hur utdrag skapas och bokförs.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024054"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="f075e-103">Konfigurera parametrar som berör butiksutdrag</span><span class="sxs-lookup"><span data-stu-id="f075e-103">Configure parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f075e-104">I det här avsnittet visas konfigurationer för handelsparametrarna som påverkar hur utdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="f075e-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="f075e-105">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="f075e-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="f075e-106">I Navigeringsfönstret, gå till **Moduler > Butik och handel > Administrationsinställning > Parametrar > Handelsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="f075e-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="f075e-107">Välj fliken **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="f075e-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="f075e-108">Välj **Ja** om du vill bokföra de tidsbegränsade rabattbeloppen specifikt.</span><span class="sxs-lookup"><span data-stu-id="f075e-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="f075e-109">Välj **Standard** för att använda standardkonton eller välj **Periodisk** om du vill ange vilket konto som ska användas för respektive tidsbegränsad rabatt.</span><span class="sxs-lookup"><span data-stu-id="f075e-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="f075e-110">Välj **Sammanfattning** om lagerraderna ska sammansättas när det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="f075e-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="f075e-111">Välj **Ja** om fakturor och betalningar automatiskt ska kvittas som en del av utdragbokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f075e-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="f075e-112">Välj **Ja** om transaktioner från lämning av pengar i kassaskåp ska sammansättas.</span><span class="sxs-lookup"><span data-stu-id="f075e-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="f075e-113">Välj **Ja** om transaktioner från bankinsättningar ska sammansättas.</span><span class="sxs-lookup"><span data-stu-id="f075e-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="f075e-114">Välj **Ja** för att aktivera sammansättning för utdragsbokföring.</span><span class="sxs-lookup"><span data-stu-id="f075e-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="f075e-115">Välj **Ja** när du skapar och bearbetar order parallellt när utdrag bokförs.</span><span class="sxs-lookup"><span data-stu-id="f075e-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="f075e-116">Ange det högsta antal order som ska bearbetas i varje batchjobbuppgift.</span><span class="sxs-lookup"><span data-stu-id="f075e-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="f075e-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f075e-117">Select **Save**.</span></span>

