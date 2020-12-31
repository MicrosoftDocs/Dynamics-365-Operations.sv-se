---
title: Skapa ett kreditlimitavtal för en garanti
description: Denna uppgift skapar ett bankkreditlimitavtal för att bearbeta en garanti.
author: panolte
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 165552cade2a38d9605240ab6a8ff423585786ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447993"
---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="01a7c-103">Skapa ett kreditlimitavtal för en garanti</span><span class="sxs-lookup"><span data-stu-id="01a7c-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01a7c-104">Denna uppgift skapar ett bankkreditlimitavtal för att bearbeta en garanti.</span><span class="sxs-lookup"><span data-stu-id="01a7c-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="01a7c-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="01a7c-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="01a7c-106">Skapa bankkreditlimitavtalet</span><span class="sxs-lookup"><span data-stu-id="01a7c-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="01a7c-107">Gå till Kassa- och bankhantering > Garanti > Avtal för bankkreditlimit.</span><span class="sxs-lookup"><span data-stu-id="01a7c-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="01a7c-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="01a7c-108">Click New.</span></span>
3. <span data-ttu-id="01a7c-109">I fältet Avtalsnummer, ange bankavtalsnumret för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="01a7c-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="01a7c-110">I fältet Bankkonto, välj vilket bankkontonummer som garantin är öppen för.</span><span class="sxs-lookup"><span data-stu-id="01a7c-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="01a7c-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="01a7c-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="01a7c-112">Ange datum och tid i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="01a7c-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="01a7c-113">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="01a7c-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="01a7c-114">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="01a7c-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="01a7c-115">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="01a7c-115">Click Add line.</span></span>
10. <span data-ttu-id="01a7c-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i Kreditlimittyp.</span><span class="sxs-lookup"><span data-stu-id="01a7c-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="01a7c-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="01a7c-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="01a7c-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="01a7c-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="01a7c-119">I fältet Gräns, ange beloppet som har förhandlats med banken.</span><span class="sxs-lookup"><span data-stu-id="01a7c-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="01a7c-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="01a7c-120">Click Save.</span></span>
15. <span data-ttu-id="01a7c-121">Växla utökningen av avsnittet Garanti.</span><span class="sxs-lookup"><span data-stu-id="01a7c-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="01a7c-122">Välj ett alternativ i fältet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="01a7c-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="01a7c-123">Ange beräkningsmetod och procentsatsdetaljerna för kassamarginal, utfärdandeprovision, tilläggsprovision, öka värdeprovision eller minska värdeprovision, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="01a7c-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="01a7c-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="01a7c-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="01a7c-125">Utöka kreditlimitavtalet</span><span class="sxs-lookup"><span data-stu-id="01a7c-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="01a7c-126">Klicka på Utöka om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="01a7c-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="01a7c-127">Skriv ett värde i fältet Nytt avtal.</span><span class="sxs-lookup"><span data-stu-id="01a7c-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="01a7c-128">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="01a7c-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="01a7c-129">Klicka på Utöka.</span><span class="sxs-lookup"><span data-stu-id="01a7c-129">Click Extend.</span></span>
5. <span data-ttu-id="01a7c-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="01a7c-130">Click Save.</span></span>
6. <span data-ttu-id="01a7c-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="01a7c-131">Close the page.</span></span>

