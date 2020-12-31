---
title: Skapa en räntekod med ett intervall
description: Räntekoder kan ställas in för att beräkna olika räntebelopp baserat på ett värdeintervall.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c0c5b20ff6fff2bc62daca68c46e949a38df8d92
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447900"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="b1ab0-103">Skapa en räntekod med ett intervall</span><span class="sxs-lookup"><span data-stu-id="b1ab0-103">Create an interest code with a range</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="b1ab0-104">Räntekoder kan ställas in för att beräkna olika räntebelopp baserat på ett värdeintervall.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="b1ab0-105">I den här proceduren visas hur du lägger till en räntekod och lägger till ett intervall i den.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="b1ab0-106">Gå till Kredit och inkasso > Ränta > Ställ in räntekoder.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="b1ab0-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-107">Click New.</span></span>
3. <span data-ttu-id="b1ab0-108">I fältet Räntekod, ange räntekodens namn.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="b1ab0-109">I fältet Beskrivning anger du en beskrivning av räntekoden.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="b1ab0-110">Välj Månad.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-110">Select Month.</span></span>
6. <span data-ttu-id="b1ab0-111">Expandera avsnittet Earnings.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="b1ab0-112">Expandera avsnittet Earnings by currency.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="b1ab0-113">I fältet Redovisningsbokföringskonto, ange önskade värden.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="b1ab0-114">I fältet Ränta per intervall, välj Månader.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="b1ab0-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-115">Click Add.</span></span>
11. <span data-ttu-id="b1ab0-116">I fältet Beskrivning anger du en beskrivning för valutan och intervallet.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="b1ab0-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-117">Click Save.</span></span>
13. <span data-ttu-id="b1ab0-118">Klicka på Intervall.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-118">Click Ranges.</span></span>
14. <span data-ttu-id="b1ab0-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-119">Click New.</span></span>
15. <span data-ttu-id="b1ab0-120">Ange Från-värdet 0 och ange sedan ränteprocenten per månad som ska användas för att beräkna räntan.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="b1ab0-121">I vårt exempel är den 1,5.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="b1ab0-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-122">Click New.</span></span>
17. <span data-ttu-id="b1ab0-123">Ange nästa Från-värde till 4, vilket är den första månaden du beräknar ett nytt räntebelopp.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="b1ab0-124">Ange den ränteprocent per månad som ska användas för att beräkna räntan från och med månad 4.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="b1ab0-125">Välj 2.0 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="b1ab0-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-126">Click New.</span></span>
20. <span data-ttu-id="b1ab0-127">Ange nästa Från-värde till 7, vilket är den nästa månad du beräknar ett nytt räntebelopp.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="b1ab0-128">Ange den ränteprocent per månad som ska användas för att beräkna räntan från och med månad 7.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="b1ab0-129">Välj 2.5 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="b1ab0-130">Avsluta inställningarna genom att klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="b1ab0-130">Click Close to complete the setup.</span></span>

