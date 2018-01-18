--- 
title: " Betalningskonfigurationer för Retail-utdrag"
description: "I den här proceduren visas konfigurationer för betalningsmetoder för butik som påverkar hur detaljhandelsutdrag skapas och bokförs."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 2a14efbeb03718b5d14571aded60eefe284b0022
ms.contentlocale: sv-se
ms.lasthandoff: 01/18/2018

---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="aac3a-103"> Betalningskonfigurationer för Retail-utdrag</span><span class="sxs-lookup"><span data-stu-id="aac3a-103">Payment configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="aac3a-104">I den här proceduren visas konfigurationer för betalningsmetoder för butik som påverkar hur detaljhandelsutdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="aac3a-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="aac3a-105">I den här registreringen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="aac3a-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="aac3a-106">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="aac3a-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="aac3a-107">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="aac3a-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="aac3a-108">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="aac3a-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="aac3a-109">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aac3a-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="aac3a-110">Klicka på Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="aac3a-110">Click Payment methods.</span></span>
6. <span data-ttu-id="aac3a-111">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="aac3a-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="aac3a-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="aac3a-112">Click Edit.</span></span>
    * <span data-ttu-id="aac3a-113">Välj om de belopp som har tagits emot för denna betalningsmetod ska bokföras på ett huvudbokskonto eller bankkonto.</span><span class="sxs-lookup"><span data-stu-id="aac3a-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="aac3a-114">Välj det konto som de belopp som tas emot för den här betalningsmetoden ska bokföras till.</span><span class="sxs-lookup"><span data-stu-id="aac3a-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="aac3a-115">Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det belopp som beräknas för betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="aac3a-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="aac3a-116">I det här fältet kan du ange ett konto att styra när avvikelsebeloppet ska bokföras på ett annat differenskonto.</span><span class="sxs-lookup"><span data-stu-id="aac3a-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="aac3a-117">Du kan använda det här alternativet för att spåra stora differenser.</span><span class="sxs-lookup"><span data-stu-id="aac3a-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="aac3a-118">Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det beräknade beloppet, när de överskrider det värde som har definierats i fältet Högsta avvikelsebelopp.</span><span class="sxs-lookup"><span data-stu-id="aac3a-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="aac3a-119">Välj Ja om du vill bokföra de belopp som sätts in på bank på ett separat konto.</span><span class="sxs-lookup"><span data-stu-id="aac3a-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="aac3a-120">I det här fältet kan du välja om de belopp som sätts in på bank ska bokföras på ett huvudbokskonto eller ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="aac3a-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="aac3a-121">Välj det konto du vill bokföra de belopp som sätts in på bank på.</span><span class="sxs-lookup"><span data-stu-id="aac3a-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="aac3a-122">Välj den banktransaktionstyp som ska användas när du bokför belopp som sätts in på bank på bankkontot.</span><span class="sxs-lookup"><span data-stu-id="aac3a-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="aac3a-123">Välj Ja om du vill bokföra de belopp som lämnats i kassaskåp på ett separat konto.</span><span class="sxs-lookup"><span data-stu-id="aac3a-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="aac3a-124">I det här fältet kan du välja om de belopp som lämnats i kassaskåp ska bokföras på huvudbokskontot eller bankkontot.</span><span class="sxs-lookup"><span data-stu-id="aac3a-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="aac3a-125">Välj det konto du vill bokföra de belopp som lämnats i kassaskåp på.</span><span class="sxs-lookup"><span data-stu-id="aac3a-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="aac3a-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aac3a-126">Click Save.</span></span>


