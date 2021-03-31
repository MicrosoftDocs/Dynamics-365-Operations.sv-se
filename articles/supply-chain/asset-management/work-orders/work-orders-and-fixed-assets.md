---
title: Arbetsorder och anläggningstillgångar
description: Det här avsnittet innehåller förklaringar av arbetsorder och anläggningstillgångar i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 678bfae5d0b4ea469a91fc89306be40c39cb082d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223444"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="5799c-103">Arbetsorder och anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="5799c-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="5799c-104">I Tillgångshantering kan tillgångar relateras till anläggningstillgångar och du kan skapa arbetsorder för dessa tillgångar.</span><span class="sxs-lookup"><span data-stu-id="5799c-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="5799c-105">Om du använder den här funktionen kan du få en fullständig översikt över anläggningstillgångar, relaterade investeringsprojekt och de kostnader som registrerats för investeringsprojekt i modulen **Projekthantering och redovisning** och moduler i **Anläggningstillgångar** i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5799c-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="5799c-106">Fältet **Anläggningstillgångsnummer** på arbetsorderns jobbprojekt anges endast om **investering** väljs som projekttyp för arbetsorders jobbprojekt.</span><span class="sxs-lookup"><span data-stu-id="5799c-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="5799c-107">I bilden nedan visas relationen mellan ett investeringsprojekt i **projektlednings- och redovisningsmodulen** och ett jobbprojekt för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="5799c-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Figur 1](media/24-work-orders.png)

<span data-ttu-id="5799c-109">Följande procedur beskriver relationen mellan tillgångar, arbetsorder, jobbprojekt för arbetsorder och anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="5799c-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="5799c-110">Du skapar en tillgång som du kopplar till en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="5799c-110">You create an asset that you relate to a fixed asset.</span></span>

![Figur 2](media/25-work-orders.png)

2. <span data-ttu-id="5799c-112">När du ställer in arbetsordertyper på sidan **Arbetsorderordertyper** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Arbetsordertyper**) skapar du en arbetsordertyp för hantering av investeringar.</span><span class="sxs-lookup"><span data-stu-id="5799c-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="5799c-113">Se även [Arbetsordertyper](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="5799c-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figur 3](media/26-work-orders.png)

3. <span data-ttu-id="5799c-115">När du ställer in projektgrupper för arbetsorder i fliken **Projektgrupp** på sidan **Projektinställningar för arbetsorder** (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projktinställningar**) skapas en relation mellan arbetsordertypen som används för investeringar och projektgruppen som skapas för investeringar på sidan **Projektgrupper** i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Inställningar** > **Bokföring** > **Projektgrupper**).</span><span class="sxs-lookup"><span data-stu-id="5799c-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figur 4](media/27-work-orders.png)

4. <span data-ttu-id="5799c-117">När du skapar en arbetsorder som är relaterad till en anläggningstillgång väljer du den arbetsordertyp som brukar användas för att hantera investeringar, t.ex. **investeringar**.</span><span class="sxs-lookup"><span data-stu-id="5799c-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="5799c-118">När arbetsordern skapas visas den relaterade arbetsordertypen på sidan **Alla arbetsorder.**</span><span class="sxs-lookup"><span data-stu-id="5799c-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Figur 5](media/28-work-orders.png)

6. <span data-ttu-id="5799c-120">När arbetsordern skapas kommer projektet som är relaterat till arbetsordern på sidan **Alla projekt** skapas i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Projekt** > **Alla projekt**).</span><span class="sxs-lookup"><span data-stu-id="5799c-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="5799c-121">För att visa projektrelaterad information, välj länken i fältet **Projekt-ID** på fliken **Allmänt** på snabbfliken **Raddetaljer** i detaljvyn för sidan **Alla arbetsorder** i modulen **Tillgångshantering** (**Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder**).</span><span class="sxs-lookup"><span data-stu-id="5799c-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Figur 6](media/29-work-orders.png)

7. <span data-ttu-id="5799c-123">Om du vill visa en översikt över de projekt som är kopplade till en anläggningstillgång **anläggningstillgångar** > **anläggningstillgångar** > **anläggningstillgångar** och sedan i fältet **anläggningstillgångsnummer**, välj länken för anläggningstillgången för att öppna detaljvyn.</span><span class="sxs-lookup"><span data-stu-id="5799c-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="5799c-124">Expandera fönstret **relaterad information** till höger på sidan och välj snabbfliken **associerade projekt**.</span><span class="sxs-lookup"><span data-stu-id="5799c-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]