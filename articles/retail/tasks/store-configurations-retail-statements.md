---
title: " Butikskonfigurationer för Retail-utdrag"
description: Den här proceduren går igenom konfigurationer för den butik som påverkar hur butiksutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 9fddeb8434d916df1613d61da88110dec8fb4465
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "354723"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="eca4b-103"> Butikskonfigurationer för Retail-utdrag</span><span class="sxs-lookup"><span data-stu-id="eca4b-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="eca4b-104">Den här proceduren går igenom konfigurationer för den butik som påverkar hur butiksutdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="eca4b-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="eca4b-105">Ekonomiska dimensioner för butiker hanteras i en annan procedur.</span><span class="sxs-lookup"><span data-stu-id="eca4b-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="eca4b-106">I den här proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="eca4b-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="eca4b-107">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="eca4b-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="eca4b-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="eca4b-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="eca4b-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="eca4b-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="eca4b-110">Inställningarna i avsnittet Utdrag/avstämning påverkar skapandet av utdrag, validering och bokföringen för butiken.</span><span class="sxs-lookup"><span data-stu-id="eca4b-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="eca4b-111">Öppna avsnittet Utdrag/avstämning.</span><span class="sxs-lookup"><span data-stu-id="eca4b-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="eca4b-112">Välj den metod du vill använda för att gruppera utdragsraderna efter.</span><span class="sxs-lookup"><span data-stu-id="eca4b-112">Select the method you want to use to to group the statement lines by.</span></span>  
    * <span data-ttu-id="eca4b-113">Välj Ja om det ska finnas bara ett utdrag per dag när du skapar utdrag från batchjobbet för skapande av utdrag.</span><span class="sxs-lookup"><span data-stu-id="eca4b-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="eca4b-114">Fältet Beräkning av kassaavstämning anger om kassaavstämningar ska läggas till tillsammans, eller om den sista ska användas.</span><span class="sxs-lookup"><span data-stu-id="eca4b-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="eca4b-115">Välj huvudbokskontot för bokföring av avrundningsdifferenser.</span><span class="sxs-lookup"><span data-stu-id="eca4b-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="eca4b-116">I fältet Högsta avrundningsbelopp kan du ange den största tillåtna avrundningsdifferensen.</span><span class="sxs-lookup"><span data-stu-id="eca4b-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="eca4b-117">I fältet Bokföring kan du ange den högsta totala tillåtna bokföringsdifferensen för ett utdrag.</span><span class="sxs-lookup"><span data-stu-id="eca4b-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="eca4b-118">I fältet Skift kan du ange den högsta totala tillåtna differensen i ett skift i ett utdrag.</span><span class="sxs-lookup"><span data-stu-id="eca4b-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="eca4b-119">I fältet Transaktion kan du ange den högsta totala tillåtna differensen på en utdragsrad.</span><span class="sxs-lookup"><span data-stu-id="eca4b-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="eca4b-120">I fältet Stängningsmetod kan du definiera om transaktioner som ska inkluderas i ett utdrag ska ingå i ett stängt skift eller om de kan vara transaktioner inom det angivna datum/tidintervallet.</span><span class="sxs-lookup"><span data-stu-id="eca4b-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="eca4b-121">I fältet Slut på vardagen kan du ange en tidpunkt om transaktioner som inträffar efter midnatt borde ha bokförts föregående dag.</span><span class="sxs-lookup"><span data-stu-id="eca4b-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="eca4b-122">Välj Ja om transaktioner som inträffar efter midnatt borde ha bokförs som en del av föregående dag.</span><span class="sxs-lookup"><span data-stu-id="eca4b-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="eca4b-123">Välj Ja för att få utdrag skapade för varje definierad utdragsmetod.</span><span class="sxs-lookup"><span data-stu-id="eca4b-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="eca4b-124">Det kan vara praktiskt om resultatet för bokföringen behöver förbättras för butiker med höga transaktionsvolymer, eftersom den skapar flera mindre utdrag som kan bearbetas parallellt.</span><span class="sxs-lookup"><span data-stu-id="eca4b-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="eca4b-125">I fältet Standardkund kan du välja kundkontot som ska användas för försäljning till kunder som gör köp direkt i butiken.</span><span class="sxs-lookup"><span data-stu-id="eca4b-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  

