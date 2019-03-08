---
title: Bädda in appar för PowerApps i Core HR
description: Det här avsnittet beskriver hur du löser problemet där PowerApps menyalternativ har försvunnit från modulen Systemadministration.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306293"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="a2ce0-103">Bädda in appar för PowerApps i Core HR</span><span class="sxs-lookup"><span data-stu-id="a2ce0-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a2ce0-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-104">**Issue**</span></span>

<span data-ttu-id="a2ce0-105">**PowerApps** menyalternativ har försvunnit från modulen **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a2ce0-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-106">**Cause**</span></span>

<span data-ttu-id="a2ce0-107">Designen för användargränssnittet (UI) har ändrats och Microsoft PowerApps ingår nu i standardanpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a2ce0-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-108">**Resolution**</span></span>

<span data-ttu-id="a2ce0-109">Sättet som PowerApps-appar bäddas in har ändrats.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="a2ce0-110">PowerApps-appar läggs nu till i anpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="a2ce0-111">Du kan lägga till PowerApps-appar för nästan alla sidor i Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="a2ce0-112">För detaljerad information om hur du bäddar in en PowerApps-app i Talent finns i [Bädda in PowerApps-appar](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a2ce0-113">Alla PowerApps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a2ce0-114">Knappen **PowerApps** är i det övre högra hörnet på nästan varje sida i Talent.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a2ce0-115">Du kan använda den här knappen för att infoga en PowerApps-app.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="a2ce0-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a2ce0-116">Here is an example.</span></span>

1. <span data-ttu-id="a2ce0-117">Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a2ce0-118">Välj knappen **PowerApps** och välj sedan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Knappen PowerApps](media/png.png)

3. <span data-ttu-id="a2ce0-120">Fyll i fälten i dialogrutan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Infoga en PowerApp-dialogruta](media/insert-powerapp.png)

<span data-ttu-id="a2ce0-122">Följ alternativt dessa steg.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a2ce0-123">På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj **Anpassa detta formulär**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    <span data-ttu-id="a2ce0-125">Verktygsfält för anpassning visas.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a2ce0-126">I verktygsfältet, välj **Infoga \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Infoga enn PowerApps-app med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
