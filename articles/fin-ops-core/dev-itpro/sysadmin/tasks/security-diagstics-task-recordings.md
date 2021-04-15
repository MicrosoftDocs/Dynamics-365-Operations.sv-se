---
title: Säkerhetsdiagnos för uppgiftsinspelningar
description: I det här avsnittet finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: cb4d544d8d74ad10432901381253f84ec9331ae7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745775"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="c4a42-103">Säkerhetsdiagnos för uppgiftsinspelningar</span><span class="sxs-lookup"><span data-stu-id="c4a42-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="c4a42-104">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c4a42-104">Before you begin</span></span>

<span data-ttu-id="c4a42-105">I det här avsnittet finns information om hur du analyserar och hanterar krav på säkerhetsbehörighet baserat på en uppgiftsinspelning.</span><span class="sxs-lookup"><span data-stu-id="c4a42-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="c4a42-106">Innan du slutför stegen i det här avsnittet måste du ha en uppgiftsinspelning av affärsprocessen som du vill analysera.</span><span class="sxs-lookup"><span data-stu-id="c4a42-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="c4a42-107">Information om hur du spelar in affärsprocesser finns i [resurser för uppgiftsinspelare](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="c4a42-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="c4a42-108">Hantera säkerhet för en uppgiftsinspelning</span><span class="sxs-lookup"><span data-stu-id="c4a42-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="c4a42-109">Gå till **Systemadministration** > **Säkerhet** > **Diagnostik för säkerhet för uppgiftsinspelning**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="c4a42-110">Öppna uppgiftsinspelningen från dess plats.</span><span class="sxs-lookup"><span data-stu-id="c4a42-110">Open the task recording from its location.</span></span> <span data-ttu-id="c4a42-111">Välj **Öppna från den här datorn** eller **Öppna från Lifecycle Services** och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="c4a42-112">Då öppnas sidan **Uppgifter om säkerhetsmeny** med en lista över de säkerhetsobjekt som krävs för processen.</span><span class="sxs-lookup"><span data-stu-id="c4a42-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="c4a42-113">Menyalternativen **Åtgärd** och **Utdata** finns inte med i listan.</span><span class="sxs-lookup"><span data-stu-id="c4a42-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="c4a42-114">Välj användare i fältet **Användar-ID**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="c4a42-115">Om användaren inte har behörighet för vissa menyalternativ uppdateras fältet **Saknade behörigheter** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Sidan med uppgifter om säkerhetsmeny](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="c4a42-117">Välj **Lägg till referens** för att visa en lista över de säkerhetsobjekt, inklusive roller, uppgifter och behörigheter som ger den saknade behörigheten.</span><span class="sxs-lookup"><span data-stu-id="c4a42-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="c4a42-118">Välj ett säkerhetsobjekt i listan:</span><span class="sxs-lookup"><span data-stu-id="c4a42-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="c4a42-119">Om **Roll** har valts väljer du **Lägg till roll till användare**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="c4a42-120">Då öppnas sidan **Tilldela användare till roller**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="c4a42-121">Mer information finns på sidan [Tilldela användare till säkerhetsroller](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c4a42-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="c4a42-122">Om **Uppdrag** är valt väljer du **Lägg till uppgift i roll**, väljer de roller som uppgiften ska läggas till i och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="c4a42-123">Om **Privilegium** är valt väljer du **Lägg till privilegium i uppgifter**, väljer de roller som privilegium ska läggas till i och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]