---
title: Spara uppgiftsguider i LCS och spela upp dem igen
description: Det här avsnittet beskriver hur du sparar uppgiftsguider till Microsoft Dynamics Lifecycle Services (LCS) och sedan spelar upp dem igen.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a18bb14ba8c3c926065c97b0ee26c38ee86ded2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053285"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="0d280-103">Spara uppgiftsguider i LCS och spela upp dem igen</span><span class="sxs-lookup"><span data-stu-id="0d280-103">Save task guides to LCS and replay them</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0d280-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="0d280-104">**Environment details**</span></span> 

<span data-ttu-id="0d280-105">Microsoft Dynamics 365 Human Resources som distribuerades via Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="0d280-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="0d280-106">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="0d280-106">**Issue**</span></span>

<span data-ttu-id="0d280-107">Kunden vill spara nya uppgiftsinspelningar till LCS-projektet och sedan spela upp de sparade uppgiftsguiderna.</span><span class="sxs-lookup"><span data-stu-id="0d280-107">The customer wants to save new task recordings to the LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="0d280-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="0d280-108">**Resolution**</span></span>

<span data-ttu-id="0d280-109">Följ dessa steg om du vill spara en uppgiftsinspelning till LCS.</span><span class="sxs-lookup"><span data-stu-id="0d280-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="0d280-110">Logga in på LCS och välj projektet.</span><span class="sxs-lookup"><span data-stu-id="0d280-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="0d280-111">Välj panelen **Affärsprocessmodelleraren**.</span><span class="sxs-lookup"><span data-stu-id="0d280-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="0d280-112">Visa sidan i den "uppdaterade BPM-miljön."</span><span class="sxs-lookup"><span data-stu-id="0d280-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="0d280-113">Välj ett bibliotek och välj **kopiera**.</span><span class="sxs-lookup"><span data-stu-id="0d280-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="0d280-114">Ange ett namn för modellen Affärsprocessmodelleraren (BPM).</span><span class="sxs-lookup"><span data-stu-id="0d280-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="0d280-115">Logga in på Personal från LCS.</span><span class="sxs-lookup"><span data-stu-id="0d280-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="0d280-116">I fältet **Sök**, ange **Hjälp**.</span><span class="sxs-lookup"><span data-stu-id="0d280-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="0d280-117">Hjälp för Lifecycle Services är öppen.</span><span class="sxs-lookup"><span data-stu-id="0d280-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="0d280-118">Välj knappen **Uppdatera** för Hjälpkonfiguration för Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="0d280-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="0d280-119">Ditt nya BPM-biblioteket bör visas och det ska vara aktivt.</span><span class="sxs-lookup"><span data-stu-id="0d280-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="0d280-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0d280-120">Close the page.</span></span>
10. <span data-ttu-id="0d280-121">Skapa en uppgiftsinspelning.</span><span class="sxs-lookup"><span data-stu-id="0d280-121">Create a task recording.</span></span>
11. <span data-ttu-id="0d280-122">När du är klar, välj **Spara till Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="0d280-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Spara till Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="0d280-124">Välj BPM-bibliotek och nod att spara uppgiftsinspelningen till.</span><span class="sxs-lookup"><span data-stu-id="0d280-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="0d280-125">Följ dessa steg för att spela upp en uppgiftsguide från LCS.</span><span class="sxs-lookup"><span data-stu-id="0d280-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="0d280-126">Starta Uppgiftsinspelare.</span><span class="sxs-lookup"><span data-stu-id="0d280-126">Start Task recorder.</span></span>
2. <span data-ttu-id="0d280-127">Välj **Öppna från LCS**.</span><span class="sxs-lookup"><span data-stu-id="0d280-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="0d280-128">Markera biblioteket och BPM-noden som har den sparade uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="0d280-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="0d280-129">Öppna uppgiftsguiden.</span><span class="sxs-lookup"><span data-stu-id="0d280-129">Open the task guide.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]