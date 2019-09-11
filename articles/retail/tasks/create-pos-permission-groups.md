---
title: Skapa kassabehörighetsgrupper
description: Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914841"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="bca91-103">Skapa kassabehörighetsgrupper</span><span class="sxs-lookup"><span data-stu-id="bca91-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bca91-104">Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="bca91-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="bca91-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT.</span><span class="sxs-lookup"><span data-stu-id="bca91-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="bca91-106">Den här uppgiften är avsedd för rollen Driftchef (butik).</span><span class="sxs-lookup"><span data-stu-id="bca91-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="bca91-107">I navigeringsfönstret, gå till **Moduler > Butik > Medarbetare > Behörighetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="bca91-107">In the navigation pane, go to **Modules > Retail > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="bca91-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bca91-108">Select **New**.</span></span>
3. <span data-ttu-id="bca91-109">Skriv ett värde i fältet **ID för kassabehörighetsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="bca91-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="bca91-110">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="bca91-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="bca91-111">Välj **Ja** i fältet **Visa stämpelklocksregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="bca91-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="bca91-112">Nu kan du aktivera eller avaktivera olika behörigheter för din kassabehörighetgrupp.</span><span class="sxs-lookup"><span data-stu-id="bca91-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="bca91-113">För en del behörigheter kan du ange ett värde som ska användas för att bedöma om kassaanvändaren kan utföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bca91-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="bca91-114">Den här uppgiftsguiden aktiverar några behörigheter som kan tilldelas en kassör.</span><span class="sxs-lookup"><span data-stu-id="bca91-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="bca91-115">Välj **Ja** i fältet **Tillåt att skapa order**.</span><span class="sxs-lookup"><span data-stu-id="bca91-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="bca91-116">Välj **Ja** i fältet **Tillåt att redigera order**.</span><span class="sxs-lookup"><span data-stu-id="bca91-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="bca91-117">Välj **Ja** i fältet **Tillåt att hämta order**.</span><span class="sxs-lookup"><span data-stu-id="bca91-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="bca91-118">Välj **Ja** i fältet **Tillåt att lösenordet ändras**.</span><span class="sxs-lookup"><span data-stu-id="bca91-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="bca91-119">Välj **Ja** i fältet **Tillåt hemlig stängning**.</span><span class="sxs-lookup"><span data-stu-id="bca91-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="bca91-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bca91-120">Select **Save**.</span></span> <span data-ttu-id="bca91-121">När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="bca91-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span> 
12. <span data-ttu-id="bca91-122">I navigeringsfönstret, gå till **Moduler > Personal > Jobb > Jobb**.</span><span class="sxs-lookup"><span data-stu-id="bca91-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="bca91-123">Nu tilldelar vi kassabehörighetgruppen till ett jobb.</span><span class="sxs-lookup"><span data-stu-id="bca91-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="bca91-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bca91-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="bca91-125">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="bca91-125">Select **Edit**.</span></span>
15. <span data-ttu-id="bca91-126">Expandera avsnittet **Jobbklassificering**.</span><span class="sxs-lookup"><span data-stu-id="bca91-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="bca91-127">I fältet Kassabehörighetsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bca91-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="bca91-128">Alla arbetare i befattningar för det här jobbet ska använda den här kassabehörighetsgruppens inställningar, om inte arbetarnas kassabehörigheter har åsidosatts på deras befattningsnivå.</span><span class="sxs-lookup"><span data-stu-id="bca91-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="bca91-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bca91-129">Select **Save**.</span></span> <span data-ttu-id="bca91-130">När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="bca91-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  

