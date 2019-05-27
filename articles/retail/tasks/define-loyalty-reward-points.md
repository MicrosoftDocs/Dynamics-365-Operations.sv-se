---
title: " Definiera förmånsbelöningspoäng"
description: Den här proceduren går igenom hur du definierar lojalitetsbelöningspoäng.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85ae26123d41fa74d32b102ddb7f021e9846a676
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564327"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="54167-103"> Definiera förmånsbelöningspoäng</span><span class="sxs-lookup"><span data-stu-id="54167-103">Define loyalty reward points</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="54167-104">Den här proceduren går igenom hur du definierar lojalitetsbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="54167-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="54167-105">Du bör ställa in lojalitetsbelöningspoäng innan du ställer in ett bonusprogram.</span><span class="sxs-lookup"><span data-stu-id="54167-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="54167-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="54167-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="54167-107">Gå till butik och handel > kunder > lojalitet > Lojalitet extrapoäng.</span><span class="sxs-lookup"><span data-stu-id="54167-107">Go to Retail and commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="54167-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="54167-108">Click New.</span></span>
3. <span data-ttu-id="54167-109">Skriv ett värde i fältet Belöningspoäng-ID.</span><span class="sxs-lookup"><span data-stu-id="54167-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="54167-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="54167-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="54167-111">Välj ett alternativ i fältet Belöningspoängtyp.</span><span class="sxs-lookup"><span data-stu-id="54167-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="54167-112">Välj Kvantitet om du vill belöningspoängen ska avrundas till närmaste heltal.</span><span class="sxs-lookup"><span data-stu-id="54167-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="54167-113">Välj om du vill att extrapoäng ska avrundas enligt valuta avrundningsregler.</span><span class="sxs-lookup"><span data-stu-id="54167-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="54167-114">Om du väljer Kvantitet, hoppa över nästa steg i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="54167-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="54167-115">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="54167-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="54167-116">För belöningspoäng av beloppstyp kommer alla utfärdade poäng ha den valda valutan.</span><span class="sxs-lookup"><span data-stu-id="54167-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="54167-117">För belöningspoäng av kvantitetstyp Det här fältet inte tillämpa-överhoppet det här steget.</span><span class="sxs-lookup"><span data-stu-id="54167-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="54167-118">Markera eller avmarkera kryssrutan Kan lösas in.</span><span class="sxs-lookup"><span data-stu-id="54167-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="54167-119">Ange ett nummer i fältet Rangordning av inlösen.</span><span class="sxs-lookup"><span data-stu-id="54167-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="54167-120">Rangordning av inlösen används när två eller fler inlösbara belöningspoäng kan användas för att betala för produkter.</span><span class="sxs-lookup"><span data-stu-id="54167-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="54167-121">Om de två belöningspoängen har samma belopp att lösa in rankningen, visas den, som behöver nedre antal poäng, användas.</span><span class="sxs-lookup"><span data-stu-id="54167-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="54167-122">Ange ett nummer i fältet Värde för utgångstid.</span><span class="sxs-lookup"><span data-stu-id="54167-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="54167-123">Belöningspoängen ska upphöra det angivna antalet dagar, månader eller år efter att poängen har utfärdas.</span><span class="sxs-lookup"><span data-stu-id="54167-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="54167-124">Värdet 0 innebär att lojalitetsbelöningspoängen aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="54167-124">A value of ‘0’ means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="54167-125">Välj ett alternativ i fältet Enhet för utgångstid.</span><span class="sxs-lookup"><span data-stu-id="54167-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="54167-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="54167-126">Click Save.</span></span>

