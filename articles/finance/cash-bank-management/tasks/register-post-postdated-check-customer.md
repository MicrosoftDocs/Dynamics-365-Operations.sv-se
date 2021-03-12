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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d14b0622f4fbad87ddf019307910d4d4e316888a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995300"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="d6b85-103">Registrera och bokför en efterdaterad check för en kund</span><span class="sxs-lookup"><span data-stu-id="d6b85-103">Register and post a postdated check for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6b85-104">Du kan registrera information om en efterdaterad check som tas emot från en kund.</span><span class="sxs-lookup"><span data-stu-id="d6b85-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="d6b85-105">Du kan även bokföra den efterdaterade checken och generera ekonomiska transaktioner.</span><span class="sxs-lookup"><span data-stu-id="d6b85-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="d6b85-106">Slutför följande uppgifter innan du registrerar och bokför en efterdaterad check som tas emot från en kund:   \* Ställ in efterdaterade checkar på sidan Kassa- och bankhantering \* Ställ in ett betalsätt för efterdaterade checkar   Rollen för den här proceduren är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="d6b85-106">Complete the following tasks before you register and post a postdated check received from a customer:   \* Set up postdated check in the Cash and bank management page \* Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="d6b85-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d6b85-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="d6b85-108">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="d6b85-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="d6b85-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d6b85-109">Click New.</span></span>
3. <span data-ttu-id="d6b85-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d6b85-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d6b85-111">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="d6b85-111">Click Lines.</span></span>
5. <span data-ttu-id="d6b85-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d6b85-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d6b85-113">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="d6b85-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="d6b85-114">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="d6b85-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="d6b85-115">Ange det specificerade beloppet på den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="d6b85-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="d6b85-116">Klicka på fliken Betalning.</span><span class="sxs-lookup"><span data-stu-id="d6b85-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="d6b85-117">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="d6b85-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="d6b85-118">Välj betalsättet för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="d6b85-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="d6b85-119">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="d6b85-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="d6b85-120">I fältet Förfallodatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="d6b85-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="d6b85-121">Ange det datum då den efterdaterade checken förfaller till betalning.</span><span class="sxs-lookup"><span data-stu-id="d6b85-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="d6b85-122">I fältet Utfärdande bankkontor, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d6b85-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="d6b85-123">Ange bankinformationen för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="d6b85-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="d6b85-124">I fältet Checknummer, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d6b85-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="d6b85-125">I fältet Namn på utfärdande bank, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d6b85-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="d6b85-126">Ange bankinformationen för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="d6b85-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="d6b85-127">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="d6b85-127">Click Post.</span></span>
16. <span data-ttu-id="d6b85-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d6b85-128">Close the page.</span></span>

