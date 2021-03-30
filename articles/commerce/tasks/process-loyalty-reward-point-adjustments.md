---
title: " Bearbeta justeringar av förmånsbelöningspoäng"
description: Den här proceduren visar hur du söker efter information om lojalitetskort och justerar förmånsbelöningspoäng.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fca59651065d20e79a47b49a4eb3b4def7cac674
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232820"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="ed114-103"> Bearbeta justeringar av förmånsbelöningspoäng</span><span class="sxs-lookup"><span data-stu-id="ed114-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed114-104">Den här proceduren visar hur du söker efter information om lojalitetskort och justerar förmånsbelöningspoäng.</span><span class="sxs-lookup"><span data-stu-id="ed114-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="ed114-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="ed114-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="ed114-106">Denna uppgift är avsedd för rollen driftchef (handel) eller kundtjänstchef.</span><span class="sxs-lookup"><span data-stu-id="ed114-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="ed114-107">Gå till förmånskort.</span><span class="sxs-lookup"><span data-stu-id="ed114-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="ed114-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ed114-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ed114-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ed114-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ed114-110">Klicka på Korttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ed114-110">Click Card transactions.</span></span>
    * <span data-ttu-id="ed114-111">På den här sidan kan du visa alla förmånstransaktionerna för det valda förmånskortet.</span><span class="sxs-lookup"><span data-stu-id="ed114-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="ed114-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ed114-112">Close the page.</span></span>
6. <span data-ttu-id="ed114-113">Klicka på Kortjusteringar.</span><span class="sxs-lookup"><span data-stu-id="ed114-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="ed114-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ed114-114">Click New.</span></span>
8. <span data-ttu-id="ed114-115">I fältet Belöningspoäng, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ed114-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="ed114-116">I fältet Belopp eller kvantitet, ange ett nummer.</span><span class="sxs-lookup"><span data-stu-id="ed114-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="ed114-117">Du kan lägga till eller ta bort poäng från förmånskort genom att använda positiva eller negativa belopp.</span><span class="sxs-lookup"><span data-stu-id="ed114-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="ed114-118">I fältet Bonusprogram, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="ed114-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="ed114-119">Ange ett värde i fältet Kommentar.</span><span class="sxs-lookup"><span data-stu-id="ed114-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="ed114-120">Klicka på Bokföringsjustering.</span><span class="sxs-lookup"><span data-stu-id="ed114-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="ed114-121">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="ed114-121">Click Yes.</span></span>
14. <span data-ttu-id="ed114-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ed114-122">Close the page.</span></span>
    * <span data-ttu-id="ed114-123">Normalt vid den här punkten kan du uppdatera sidan för att se resultatet av belöningspoängjusteringen på fliken Belöningssammanfattning. Men om du kör detta som en uppgiftsguide, uppdatera inte nu eftersom uppgiftsguiden stoppas om du gör det.</span><span class="sxs-lookup"><span data-stu-id="ed114-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="ed114-124">Klicka på Korttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ed114-124">Click Card transactions.</span></span>
16. <span data-ttu-id="ed114-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ed114-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]