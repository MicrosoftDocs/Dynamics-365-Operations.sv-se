---
title: Säkerhetsdiagnos för uppgiftsinspelningar
description: I det här avsnittet finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: fada3abb9362426c7c9ec33f5d25552edf3ef630
ms.sourcegitcommit: 71fec2553158c332ce4d4bfcedc2c1ab58c1a1a5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340685"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="77d38-103">Säkerhetsdiagnos för uppgiftsinspelningar</span><span class="sxs-lookup"><span data-stu-id="77d38-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="77d38-104">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="77d38-104">Before you begin</span></span>

<span data-ttu-id="77d38-105">I det här avsnittet finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning.</span><span class="sxs-lookup"><span data-stu-id="77d38-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="77d38-106">Innan du slutför stegen i det här avsnittet måste du ha en uppgiftsinspelning av affärsprocessen som du vill analysera.</span><span class="sxs-lookup"><span data-stu-id="77d38-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="77d38-107">Information om hur du spelar in affärsprocesser finns i [resurser för uppgiftsinspelare](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="77d38-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="77d38-108">Hantera säkerhet för en uppgiftsinspelning</span><span class="sxs-lookup"><span data-stu-id="77d38-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="77d38-109">Gå till **Systemadministration** > **Säkerhet** > **Diagnostik för säkerhet för uppgiftsinspelning**.</span><span class="sxs-lookup"><span data-stu-id="77d38-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="77d38-110">Öppna uppgiftsinspelningen från dess plats.</span><span class="sxs-lookup"><span data-stu-id="77d38-110">Open the task recording from its location.</span></span> <span data-ttu-id="77d38-111">Välj **Öppna från den här datorn** eller **Öppna från Lifecycle Services** och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="77d38-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="77d38-112">Då öppnas sidan **Uppgifter om säkerhetsmeny** med en lista över de säkerhetsobjekt som krävs för processen.</span><span class="sxs-lookup"><span data-stu-id="77d38-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="77d38-113">Menyalternativen **Åtgärd** och **Utdata** finns inte med i listan.</span><span class="sxs-lookup"><span data-stu-id="77d38-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="77d38-114">Välj användare i fältet **Användar-ID**.</span><span class="sxs-lookup"><span data-stu-id="77d38-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="77d38-115">Om användaren inte har behörighet för vissa menyalternativ uppdateras fältet **Saknade behörigheter** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="77d38-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Sidan med uppgifter om säkerhetsmeny](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="77d38-117">Välj **Lägg till referens** för att visa en lista över de säkerhetsobjekt, inklusive roller, uppgifter och behörigheter som ger den saknade behörigheten.</span><span class="sxs-lookup"><span data-stu-id="77d38-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="77d38-118">Välj ett säkerhetsobjekt i listan:</span><span class="sxs-lookup"><span data-stu-id="77d38-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="77d38-119">Om **Roll** har valts väljer du **Lägg till roll till användare**.</span><span class="sxs-lookup"><span data-stu-id="77d38-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="77d38-120">Då öppnas sidan **Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="77d38-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="77d38-121">Mer information finns på sidan [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="77d38-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="77d38-122">Om **Uppdrag** är valt väljer du **Lägg till uppgift i roll**, väljer de roller som uppgiften ska läggas till i och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="77d38-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="77d38-123">Om **Privilegium** är valt väljer du **Lägg till privilegium i uppgifter**, väljer de roller som privilegium ska läggas till i och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="77d38-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
