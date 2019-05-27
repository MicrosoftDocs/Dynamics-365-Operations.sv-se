---
title: Registrera och bokför en efterdaterad check för en kund
description: Du kan registrera information om en efterdaterad check som tas emot från en kund.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 131e4f364c62d03b95fb4b77f472828b9483d5e1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566097"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="8c23b-103">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="8c23b-103">Register and post a postdated check for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c23b-104">Du kan registrera information om en efterdaterad check som tas emot från en kund.</span><span class="sxs-lookup"><span data-stu-id="8c23b-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="8c23b-105">Du kan även bokföra den efterdaterade checken och generera ekonomiska transaktioner.</span><span class="sxs-lookup"><span data-stu-id="8c23b-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="8c23b-106">Slutför följande uppgifter innan du registrerar och bokför en efterdaterad check som tas emot från en kund:   • Ställ in efterdaterade checkar på sidan Kassa- och bankhantering • Ställ in en betalningsmetod för efterdaterade checkar   Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="8c23b-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="8c23b-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="8c23b-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="8c23b-108">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="8c23b-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="8c23b-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8c23b-109">Click New.</span></span>
3. <span data-ttu-id="8c23b-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8c23b-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8c23b-111">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="8c23b-111">Click Lines.</span></span>
5. <span data-ttu-id="8c23b-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8c23b-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="8c23b-113">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="8c23b-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="8c23b-114">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="8c23b-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="8c23b-115">Ange det specificerade beloppet på den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="8c23b-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="8c23b-116">Klicka på fliken Betalning.</span><span class="sxs-lookup"><span data-stu-id="8c23b-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="8c23b-117">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="8c23b-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="8c23b-118">Välj betalningsmetoden för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="8c23b-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="8c23b-119">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="8c23b-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="8c23b-120">I fältet Förfallodatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="8c23b-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="8c23b-121">Ange det datum då den efterdaterade checken förfaller till betalning.</span><span class="sxs-lookup"><span data-stu-id="8c23b-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="8c23b-122">I fältet Utfärdande bankkontor, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="8c23b-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="8c23b-123">Ange bankinformationen för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="8c23b-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="8c23b-124">I fältet Checknummer, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="8c23b-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="8c23b-125">I fältet Namn på utfärdande bank, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="8c23b-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="8c23b-126">Ange bankinformationen för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="8c23b-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="8c23b-127">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="8c23b-127">Click Post.</span></span>
16. <span data-ttu-id="8c23b-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8c23b-128">Close the page.</span></span>

