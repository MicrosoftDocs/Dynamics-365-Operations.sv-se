---
title: Skapa ett kreditlimitavtal för en garanti
description: Denna uppgift skapar ett bankkreditlimitavtal för att bearbeta en garanti.
author: ShylaThompson
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
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb2fe6bfebcc0cc302d623a34fd994a57cbea1c8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842071"
---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="f73f9-103">Skapa ett kreditlimitavtal för en garanti</span><span class="sxs-lookup"><span data-stu-id="f73f9-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f73f9-104">Denna uppgift skapar ett bankkreditlimitavtal för att bearbeta en garanti.</span><span class="sxs-lookup"><span data-stu-id="f73f9-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="f73f9-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f73f9-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="f73f9-106">Skapa bankkreditlimitavtalet</span><span class="sxs-lookup"><span data-stu-id="f73f9-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="f73f9-107">Gå till Kassa- och bankhantering > Garanti > Avtal för bankkreditlimit.</span><span class="sxs-lookup"><span data-stu-id="f73f9-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="f73f9-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f73f9-108">Click New.</span></span>
3. <span data-ttu-id="f73f9-109">I fältet Avtalsnummer, ange bankavtalsnumret för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f73f9-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="f73f9-110">I fältet Bankkonto, välj vilket bankkontonummer som garantin är öppen för.</span><span class="sxs-lookup"><span data-stu-id="f73f9-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="f73f9-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f73f9-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f73f9-112">Ange datum och tid i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="f73f9-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="f73f9-113">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="f73f9-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="f73f9-114">Växla utökningen av avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="f73f9-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="f73f9-115">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="f73f9-115">Click Add line.</span></span>
10. <span data-ttu-id="f73f9-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i Kreditlimittyp.</span><span class="sxs-lookup"><span data-stu-id="f73f9-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f73f9-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f73f9-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="f73f9-118">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f73f9-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="f73f9-119">I fältet Gräns, ange beloppet som har förhandlats med banken.</span><span class="sxs-lookup"><span data-stu-id="f73f9-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="f73f9-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f73f9-120">Click Save.</span></span>
15. <span data-ttu-id="f73f9-121">Växla utökningen av avsnittet Garanti.</span><span class="sxs-lookup"><span data-stu-id="f73f9-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="f73f9-122">Välj ett alternativ i fältet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="f73f9-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="f73f9-123">Ange beräkningsmetod och procentsatsdetaljerna för kassamarginal, utfärdandeprovision, tilläggsprovision, öka värdeprovision eller minska värdeprovision, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="f73f9-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="f73f9-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f73f9-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="f73f9-125">Utöka kreditlimitavtalet</span><span class="sxs-lookup"><span data-stu-id="f73f9-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="f73f9-126">Klicka på Utöka om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f73f9-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="f73f9-127">Skriv ett värde i fältet Nytt avtal.</span><span class="sxs-lookup"><span data-stu-id="f73f9-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="f73f9-128">I fältet Slutdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="f73f9-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="f73f9-129">Klicka på Utöka.</span><span class="sxs-lookup"><span data-stu-id="f73f9-129">Click Extend.</span></span>
5. <span data-ttu-id="f73f9-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f73f9-130">Click Save.</span></span>
6. <span data-ttu-id="f73f9-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73f9-131">Close the page.</span></span>

