---
title: Bädda in PowerApps-appar i Dynamics 365 - Core HR
description: Det här avsnittet beskriver hur du löser problemet där PowerApps menyalternativ har försvunnit från modulen Systemadministration.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008440"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="866be-103">Bädda in appar för PowerApps i Core HR</span><span class="sxs-lookup"><span data-stu-id="866be-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="866be-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="866be-104">**Issue**</span></span>

<span data-ttu-id="866be-105">**PowerApps** menyalternativ har försvunnit från modulen **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="866be-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="866be-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="866be-106">**Cause**</span></span>

<span data-ttu-id="866be-107">Designen för användargränssnittet (UI) har ändrats och Microsoft PowerApps ingår nu i standardanpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="866be-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="866be-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="866be-108">**Resolution**</span></span>

<span data-ttu-id="866be-109">Sättet som PowerApps-appar bäddas in har ändrats.</span><span class="sxs-lookup"><span data-stu-id="866be-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="866be-110">PowerApps-appar läggs nu till i anpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="866be-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="866be-111">Du kan lägga till PowerApps-appar för nästan alla sidor i Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="866be-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="866be-112">För detaljerad information om hur du bäddar in en PowerApps-app i Talent finns i [Bädda in PowerApps-appar](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="866be-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="866be-113">Alla PowerApps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="866be-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="866be-114">Knappen **PowerApps** är i det övre högra hörnet på nästan varje sida i Talent.</span><span class="sxs-lookup"><span data-stu-id="866be-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="866be-115">Du kan använda den här knappen för att infoga en PowerApps-app.</span><span class="sxs-lookup"><span data-stu-id="866be-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="866be-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="866be-116">Here is an example.</span></span>

1. <span data-ttu-id="866be-117">Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="866be-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="866be-118">Välj knappen **PowerApps** och välj sedan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="866be-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![PowerApps-knapp](media/png.png)

3. <span data-ttu-id="866be-120">Fyll i fälten i dialogrutan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="866be-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Infoga en PowerApp-dialogruta](media/insert-powerapp.png)

<span data-ttu-id="866be-122">Följ alternativt dessa steg.</span><span class="sxs-lookup"><span data-stu-id="866be-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="866be-123">På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj **Anpassa detta formulär**.</span><span class="sxs-lookup"><span data-stu-id="866be-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    <span data-ttu-id="866be-125">Verktygsfält för anpassning visas.</span><span class="sxs-lookup"><span data-stu-id="866be-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="866be-126">I verktygsfältet, välj **Infoga \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="866be-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Infoga en PowerApps-app med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
