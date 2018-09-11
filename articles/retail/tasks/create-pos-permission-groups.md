--- 
title: " Skapa kassabehörighetsgrupper"
description: "I den här proceduren visas hur du skapar en kassabehörighetsgrupp."
author: scott-tucker
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c5bb77b0cc4d81e2cceb8c17760fe0b84d2c575d
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="00c31-103"> Skapa kassabehörighetsgrupper</span><span class="sxs-lookup"><span data-stu-id="00c31-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="00c31-104">I den här proceduren visas hur du skapar en kassabehörighetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00c31-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="00c31-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="00c31-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="00c31-106">Den här uppgiften är avsedd för rollen Driftchef (butik).</span><span class="sxs-lookup"><span data-stu-id="00c31-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="00c31-107">Gå till Behörighetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="00c31-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="00c31-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00c31-108">Click New.</span></span>
3. <span data-ttu-id="00c31-109">Skriv ett värde i fältet ID för kassabehörighetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00c31-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="00c31-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="00c31-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="00c31-111">Välj Ja i fältet Visa stämpelklocksregistreringar.</span><span class="sxs-lookup"><span data-stu-id="00c31-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="00c31-112">Nu kan du aktivera eller avaktivera olika behörigheter för din kassabehörighetgrupp.</span><span class="sxs-lookup"><span data-stu-id="00c31-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="00c31-113">För en del behörigheter kan du ange ett värde som ska användas för att bedöma om kassaanvändaren kan utföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="00c31-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="00c31-114">Den här uppgiftsguiden aktiverar några behörigheter som kan tilldelas en kassör.</span><span class="sxs-lookup"><span data-stu-id="00c31-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="00c31-115">Välj Ja i fältet Tillåt att skapa order.</span><span class="sxs-lookup"><span data-stu-id="00c31-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="00c31-116">Välj Ja i fältet Tillåt att redigera order.</span><span class="sxs-lookup"><span data-stu-id="00c31-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="00c31-117">Välj Ja i fältet Tillåt att hämta order.</span><span class="sxs-lookup"><span data-stu-id="00c31-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="00c31-118">Välj Ja i fältet Tillåt att lösenordet ändras.</span><span class="sxs-lookup"><span data-stu-id="00c31-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="00c31-119">Välj Ja i fältet Tillåt hemlig stängning.</span><span class="sxs-lookup"><span data-stu-id="00c31-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="00c31-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="00c31-120">Click Save.</span></span>
    * <span data-ttu-id="00c31-121">När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="00c31-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="00c31-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00c31-122">Close the page.</span></span>
13. <span data-ttu-id="00c31-123">Gå till Jobb.</span><span class="sxs-lookup"><span data-stu-id="00c31-123">Go to Jobs.</span></span>
    * <span data-ttu-id="00c31-124">Nu tilldelar vi kassabehörighetgruppen till ett jobb.</span><span class="sxs-lookup"><span data-stu-id="00c31-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="00c31-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="00c31-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="00c31-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="00c31-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="00c31-127">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="00c31-127">Click Edit.</span></span>
17. <span data-ttu-id="00c31-128">Expandera avsnittet Jobbklassificering.</span><span class="sxs-lookup"><span data-stu-id="00c31-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="00c31-129">I fältet Kassabehörighetsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="00c31-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="00c31-130">Alla arbetare i befattningar för det här jobbet ska använda den här kassabehörighetsgruppens inställningar, om inte arbetarnas kassabehörigheter har åsidosatts på deras befattningsnivå.</span><span class="sxs-lookup"><span data-stu-id="00c31-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="00c31-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="00c31-131">Click Save.</span></span>
    * <span data-ttu-id="00c31-132">När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="00c31-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


