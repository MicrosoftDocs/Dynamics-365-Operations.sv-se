---
title: " Betalningskonfigurationer för Retail-utdrag"
description: I den här proceduren visas konfigurationer för betalningsmetoder för handel som påverkar hur handelsutdrag skapas och bokförs.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 390ccdfde3f9bb93770d456af7532a42e81955a1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415870"
---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="7eea9-103"> Betalningskonfigurationer för Retail-utdrag</span><span class="sxs-lookup"><span data-stu-id="7eea9-103">Payment configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7eea9-104">I den här proceduren visas konfigurationer för betalningsmetoder för handel som påverkar hur handelsutdrag skapas och bokförs.</span><span class="sxs-lookup"><span data-stu-id="7eea9-104">This procedure demonstrates configurations for Commerce store payment methods, which affect how statements get created and posted.</span></span>

<span data-ttu-id="7eea9-105">I den här registreringen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="7eea9-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="7eea9-106">Gå till Butik och handel > Kanaler > Butiker >Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="7eea9-106">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="7eea9-107">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7eea9-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7eea9-108">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7eea9-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7eea9-109">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7eea9-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="7eea9-110">Klicka på Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="7eea9-110">Click Payment methods.</span></span>
6. <span data-ttu-id="7eea9-111">Utöka eller komprimera avsnittet Bokföring.</span><span class="sxs-lookup"><span data-stu-id="7eea9-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="7eea9-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="7eea9-112">Click Edit.</span></span>
    * <span data-ttu-id="7eea9-113">Välj om de belopp som har tagits emot för denna betalningsmetod ska bokföras på ett huvudbokskonto eller bankkonto.</span><span class="sxs-lookup"><span data-stu-id="7eea9-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="7eea9-114">Välj det konto som de belopp som tas emot för den här betalningsmetoden ska bokföras till.</span><span class="sxs-lookup"><span data-stu-id="7eea9-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="7eea9-115">Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det belopp som beräknas för betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="7eea9-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="7eea9-116">I det här fältet kan du ange ett konto att styra när avvikelsebeloppet ska bokföras på ett annat differenskonto.</span><span class="sxs-lookup"><span data-stu-id="7eea9-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="7eea9-117">Du kan använda det här alternativet för att spåra stora differenser.</span><span class="sxs-lookup"><span data-stu-id="7eea9-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="7eea9-118">Välj ett konto för att bokföra möjliga differenser mellan det inlevererade totala transaktionsbeloppet och det beräknade beloppet, när de överskrider det värde som har definierats i fältet Högsta avvikelsebelopp.</span><span class="sxs-lookup"><span data-stu-id="7eea9-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="7eea9-119">Välj Ja om du vill bokföra de belopp som sätts in på bank på ett separat konto.</span><span class="sxs-lookup"><span data-stu-id="7eea9-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="7eea9-120">I det här fältet kan du välja om de belopp som sätts in på bank ska bokföras på ett huvudbokskonto eller ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="7eea9-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="7eea9-121">Välj det konto du vill bokföra de belopp som sätts in på bank på.</span><span class="sxs-lookup"><span data-stu-id="7eea9-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="7eea9-122">Välj den banktransaktionstyp som ska användas när du bokför belopp som sätts in på bank på bankkontot.</span><span class="sxs-lookup"><span data-stu-id="7eea9-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="7eea9-123">Välj Ja om du vill bokföra de belopp som lämnats i kassaskåp på ett separat konto.</span><span class="sxs-lookup"><span data-stu-id="7eea9-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="7eea9-124">I det här fältet kan du välja om de belopp som lämnats i kassaskåp ska bokföras på huvudbokskontot eller bankkontot.</span><span class="sxs-lookup"><span data-stu-id="7eea9-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="7eea9-125">Välj det konto du vill bokföra de belopp som lämnats i kassaskåp på.</span><span class="sxs-lookup"><span data-stu-id="7eea9-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="7eea9-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7eea9-126">Click Save.</span></span>

