---
title: Bädda in Power Apps-appar i Dynamics 365 Human Resources
description: Det här avsnittet beskriver hur du löser problemet där Microsoft Power Apps menyalternativ har försvunnit från modulen Systemadministration.
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017883"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="1c4bf-103">Bädda in Power Apps-appar i Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="1c4bf-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="1c4bf-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="1c4bf-104">**Issue**</span></span>

<span data-ttu-id="1c4bf-105">**Power Apps** menyalternativ har försvunnit från modulen **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="1c4bf-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="1c4bf-106">**Cause**</span></span>

<span data-ttu-id="1c4bf-107">Designen för användargränssnittet (UI) har ändrats och Microsoft Power Apps ingår nu i standardanpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="1c4bf-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="1c4bf-108">**Resolution**</span></span>

<span data-ttu-id="1c4bf-109">Sättet som Power Apps bäddas in har ändrats.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="1c4bf-110">Power Apps läggs nu till i anpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="1c4bf-111">Du kan lägga till Power Apps för nästan alla sidor i Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="1c4bf-112">För detaljerad information om hur du bäddar in en Power Apps i Talent finns i [Bädda in Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="1c4bf-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="1c4bf-113">Alla Power Apps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="1c4bf-114">Knappen **Power Apps** är i det övre högra hörnet på nästan varje sida i Talent.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="1c4bf-115">Du kan använda den här knappen för att infoga appar.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="1c4bf-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="1c4bf-116">Here is an example.</span></span>

1. <span data-ttu-id="1c4bf-117">Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="1c4bf-118">Markera **Power Apps**-knappen och välj sedan **Lägg till en app från Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Power Apps-knapp](media/png.png)

3. <span data-ttu-id="1c4bf-120">Slutför fälten i dialogrutan **Lägg till en app från Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Dialogrutan lägg till en app från Power Apps](media/insert-powerapp.png)

<span data-ttu-id="1c4bf-122">Följ alternativt dessa steg.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="1c4bf-123">På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj sidan **Anpassa detta formulär**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    <span data-ttu-id="1c4bf-125">Verktygsfält för anpassning visas.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="1c4bf-126">På verktygsfältet, välj **Lägg till en app från Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="1c4bf-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Lägg till en app från Power Apps med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
