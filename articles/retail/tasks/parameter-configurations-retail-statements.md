---
title: " Parameterkonfigurationer för Retail-utdrag"
description: I den här proceduren visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 6dacd2b80ca0d51d81d2bdf5bc2636b47da621ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "352630"
---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="8a13a-103"> Parameterkonfigurationer för Retail-utdrag</span><span class="sxs-lookup"><span data-stu-id="8a13a-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8a13a-104">I den här proceduren visas konfigurationer för detaljhandelsparametrarna som påverkar hur detaljhandelsutdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="8a13a-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="8a13a-105">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="8a13a-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="8a13a-106">Gå till Butik och handel > Administrationsinställning > Parametrar > Butiksparametrar.</span><span class="sxs-lookup"><span data-stu-id="8a13a-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="8a13a-107">Klicka på fliken Bokföring.</span><span class="sxs-lookup"><span data-stu-id="8a13a-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="8a13a-108">Välj Ja om du vill bokföra de tidsbegränsade rabattbeloppen specifikt.</span><span class="sxs-lookup"><span data-stu-id="8a13a-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="8a13a-109">Välj Standard för att använda standardkonton eller välj Periodisk om du vill ange vilket konto som ska användas för respektive tidsbegränsad rabatt.</span><span class="sxs-lookup"><span data-stu-id="8a13a-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="8a13a-110">Välj Sammanfattning om lagerraderna ska sammansättas när det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="8a13a-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="8a13a-111">Välj Ja om fakturor och betalningar automatiskt ska kvittas som en del av utdragbokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8a13a-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="8a13a-112">Välj Ja om transaktioner från lämning av pengar i kassaskåp ska sammansättas.</span><span class="sxs-lookup"><span data-stu-id="8a13a-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="8a13a-113">Välj Ja om transaktioner från bankinsättningar ska sammansättas.</span><span class="sxs-lookup"><span data-stu-id="8a13a-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="8a13a-114">Välj Ja för att aktivera sammansättning för utdragsbokföring.</span><span class="sxs-lookup"><span data-stu-id="8a13a-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="8a13a-115">Välj Ja när du skapar och bearbetar order parallellt när utdrag bokförs.</span><span class="sxs-lookup"><span data-stu-id="8a13a-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="8a13a-116">Ange det högsta antal order som ska bearbetas i varje batchjobbuppgift.</span><span class="sxs-lookup"><span data-stu-id="8a13a-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="8a13a-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8a13a-117">Click Save.</span></span>

