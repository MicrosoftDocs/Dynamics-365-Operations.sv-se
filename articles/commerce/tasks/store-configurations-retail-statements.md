---
title: " Butikskonfigurationer för Retail-utdrag"
description: Den här proceduren går igenom konfigurationer för den butik som påverkar hur handelsutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e255c58997ed1c0ad5614b15867f14714a8bcfc8
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "4415985"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="a18bb-103"> Butikskonfigurationer för Retail-utdrag</span><span class="sxs-lookup"><span data-stu-id="a18bb-103">Store configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a18bb-104">Den här proceduren går igenom konfigurationer för den butik som påverkar hur handelsutdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="a18bb-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="a18bb-105">Ekonomiska dimensioner för butiker hanteras i en annan procedur.</span><span class="sxs-lookup"><span data-stu-id="a18bb-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="a18bb-106">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="a18bb-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="a18bb-107">I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Kanaler > Butiker > Alla butiker**.</span><span class="sxs-lookup"><span data-stu-id="a18bb-107">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="a18bb-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a18bb-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a18bb-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a18bb-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a18bb-110">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="a18bb-110">Click **Edit**.</span></span>
5. <span data-ttu-id="a18bb-111">Inställningarna på snabbfliken **Utdrag/avstämning** påverkar skapandet av utdrag, validering och bokföringen för butiken.</span><span class="sxs-lookup"><span data-stu-id="a18bb-111">The settings in the **Statement/closing** FastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="a18bb-112">Expandera snabbfliken **Utdrag/avstämning**.</span><span class="sxs-lookup"><span data-stu-id="a18bb-112">Expand the **Statement/closing** FastTab.</span></span>  
6. <span data-ttu-id="a18bb-113">I fältet **Utdragsmetod** väljer du den metod du vill använda för att gruppera utdragsrader.</span><span class="sxs-lookup"><span data-stu-id="a18bb-113">In the **Statement method** field, select the method you want to use to group the statement lines by.</span></span>  
7. <span data-ttu-id="a18bb-114">Välj Ja i **Ett utdrag per dag** om det ska finnas bara ett utdrag per dag när du skapar utdrag från batchjobbet för skapande av utdrag.</span><span class="sxs-lookup"><span data-stu-id="a18bb-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="a18bb-115">Fältet **Beräkning av kassaavstämning** anger om kassaavstämningar ska läggas till tillsammans, eller om den sista ska användas.</span><span class="sxs-lookup"><span data-stu-id="a18bb-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="a18bb-116">I fältet **Avrundning** välj huvudbokskontot för bokföring av avrundningsdifferenser.</span><span class="sxs-lookup"><span data-stu-id="a18bb-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="a18bb-117">I fältet **Högsta avrundningsbelopp** kan du ange den största tillåtna avrundningsdifferensen.</span><span class="sxs-lookup"><span data-stu-id="a18bb-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="a18bb-118">I fältet **Bokföring** kan du ange den högsta totala tillåtna bokföringsdifferensen för ett utdrag.</span><span class="sxs-lookup"><span data-stu-id="a18bb-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="a18bb-119">I fältet **Skift** kan du ange den högsta totala tillåtna differensen i ett skift i ett utdrag.</span><span class="sxs-lookup"><span data-stu-id="a18bb-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="a18bb-120">I fältet **Transaktion** kan du ange den högsta totala tillåtna differensen på en utdragsrad.</span><span class="sxs-lookup"><span data-stu-id="a18bb-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="a18bb-121">I fältet **Stängningsmetod** kan du definiera om transaktioner som ska inkluderas i ett utdrag ska ingå i ett stängt skift eller om de kan vara transaktioner inom det angivna datum/tidintervallet.</span><span class="sxs-lookup"><span data-stu-id="a18bb-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="a18bb-122">I fältet **Slut på vardagen** kan du ange en tidpunkt om transaktioner som inträffar efter midnatt borde ha bokförts föregående dag.</span><span class="sxs-lookup"><span data-stu-id="a18bb-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="a18bb-123">Välj Ja i **Bokför som vardag** om transaktioner som inträffar efter midnatt borde ha bokförs som en del av föregående dag.</span><span class="sxs-lookup"><span data-stu-id="a18bb-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="a18bb-124">Välj Ja i **Metoden dela efter utdrag** för att få utdrag skapade för varje definierad utdragsmetod.</span><span class="sxs-lookup"><span data-stu-id="a18bb-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="a18bb-125">Denna åtgärd kan vara praktiskt om resultatet för bokföringen behöver förbättras för butiker med höga transaktionsvolymer, eftersom den skapar flera mindre utdrag som kan bearbetas parallellt.</span><span class="sxs-lookup"><span data-stu-id="a18bb-125">This action can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="a18bb-126">I snabbfliken **Standardkund** på snabbfliken **Allmänt** kan du välja kundkontot som ska användas för försäljning till kunder som gör köp direkt i butiken.</span><span class="sxs-lookup"><span data-stu-id="a18bb-126">In the **General** FastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

