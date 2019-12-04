---
title: Bädda in Power Apps-appar i Dynamics 365 - Core HR
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830219"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="64de9-103">Bädda in Power Apps-appar i Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="64de9-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="64de9-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="64de9-104">**Issue**</span></span>

<span data-ttu-id="64de9-105">**Power Apps** menyalternativ har försvunnit från modulen **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="64de9-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="64de9-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="64de9-106">**Cause**</span></span>

<span data-ttu-id="64de9-107">Designen för användargränssnittet (UI) har ändrats och Microsoft Power Apps ingår nu i standardanpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="64de9-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="64de9-108">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="64de9-108">**Resolution**</span></span>

<span data-ttu-id="64de9-109">Sättet som Power Apps bäddas in har ändrats.</span><span class="sxs-lookup"><span data-stu-id="64de9-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="64de9-110">Power Apps läggs nu till i anpassningsmodellen.</span><span class="sxs-lookup"><span data-stu-id="64de9-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="64de9-111">Du kan lägga till Power Apps för nästan alla sidor i Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="64de9-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="64de9-112">För detaljerad information om hur du bäddar in en Power Apps i Talent finns i [Bädda in Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="64de9-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="64de9-113">Alla Power Apps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.</span><span class="sxs-lookup"><span data-stu-id="64de9-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="64de9-114">Knappen **Power Apps** är i det övre högra hörnet på nästan varje sida i Talent.</span><span class="sxs-lookup"><span data-stu-id="64de9-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="64de9-115">Du kan använda den här knappen för att infoga en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="64de9-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="64de9-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="64de9-116">Here is an example.</span></span>

1. <span data-ttu-id="64de9-117">Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="64de9-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="64de9-118">Välj knappen **Power Apps** och välj sedan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="64de9-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Power Apps-knapp](media/png.png)

3. <span data-ttu-id="64de9-120">Fyll i fälten i dialogrutan **Infoga en PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="64de9-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Infoga en PowerApp-dialogruta](media/insert-powerapp.png)

<span data-ttu-id="64de9-122">Följ alternativt dessa steg.</span><span class="sxs-lookup"><span data-stu-id="64de9-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="64de9-123">På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj **Anpassa detta formulär**.</span><span class="sxs-lookup"><span data-stu-id="64de9-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    <span data-ttu-id="64de9-125">Verktygsfält för anpassning visas.</span><span class="sxs-lookup"><span data-stu-id="64de9-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="64de9-126">I verktygsfältet, välj **Infoga \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="64de9-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Infoga en Power Apps-app med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
