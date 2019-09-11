---
title: Arbetsorder och anläggningstillgångar
description: Det här avsnittet innehåller förklaringar av arbetsorder och anläggningstillgångar i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875897"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="88255-103">Arbetsorder och anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="88255-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="88255-104">I Tillgångshantering kan tillgångar relateras till anläggningstillgångar och du kan skapa arbetsorder för dessa tillgångar.</span><span class="sxs-lookup"><span data-stu-id="88255-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="88255-105">Om du använder den här funktionen kan du få en fullständig översikt över anläggningstillgångar, relaterade investeringsprojekt och de kostnader som registrerats för investeringsprojekt i modulen **Projekthantering och redovisning** och modulen **Anläggningstillgångar** i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="88255-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="88255-106">Fältet **Anläggningstillgångsnummer** fylls bara i på arbetsorderns jobbprojekt om typen "investering" väljs som projekttyp för arbetsorders jobbprojekt.</span><span class="sxs-lookup"><span data-stu-id="88255-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Figur 1](media/24-work-orders.png)

<span data-ttu-id="88255-108">Följande procedur beskriver relationen mellan tillgångar, arbetsorder, jobbprojekt för arbetsorder och anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="88255-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="88255-109">Du skapar en tillgång som du kopplar till en anläggningstill gång, som du ser i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="88255-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Figur 2](media/25-work-orders.png)

2. <span data-ttu-id="88255-111">När du ställer in arbetsordertyper (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Arbetsordertyper**) skapar du en arbetsordertyp för hantering av investeringar.</span><span class="sxs-lookup"><span data-stu-id="88255-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="88255-112">Se även [Arbetsordertyper](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="88255-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figur 3](media/26-work-orders.png)

3. <span data-ttu-id="88255-114">När du ställer in projektgrupper för arbetsorder (**Tillgångshantering** > **Inställningar** > **Arbetsorder** > **Projektinställning** > **Projektgrupp**-länk), skapas en relation mellan arbetsordertypen som används för investeringar och projektetgruppen som skapas för investeringar i modulen **Projekthantering och redovisning** (**Projekthantering och redovisning** > **Inställningar** > **Bokför** > **Projektgrupper**).</span><span class="sxs-lookup"><span data-stu-id="88255-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figur 4](media/27-work-orders.png)

4. <span data-ttu-id="88255-116">När du skapar en arbetsorder som hör till ett anläggningstillgångsobjekt väljer du den arbetsordertyp som används för att hantera investeringar, t. ex. "investeringar".</span><span class="sxs-lookup"><span data-stu-id="88255-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="88255-117">När arbetsordern skapas visas den relaterade arbetsordertypen i **Alla arbetsorder.**</span><span class="sxs-lookup"><span data-stu-id="88255-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Figur 5](media/28-work-orders.png)

6. <span data-ttu-id="88255-119">När arbetsordern skapas, skapas projektet som hör till arbetsordern i **Projekthantering och redovisning** > **Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="88255-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="88255-120">Du kan se projektrelaterad information genom att klicka på **Projekt-ID**-länken på arbetsordern (i **Tillgångshantering**, öppna arbetsordern i informationsvyn > snabbfliken **Radinformation** > fliken **Allmänt**  > fältet **Projekt-ID**).</span><span class="sxs-lookup"><span data-stu-id="88255-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Figur 6](media/29-work-orders.png)

7. <span data-ttu-id="88255-122">I **Anläggningstillgångar** visas en översikt över de projekt som är kopplade till en anläggningstillgång (**Anläggningstillgångar** > **Anläggningstillgångar** > **Anläggningstillgångar** > klicka på anläggningstillgången i fältet **Anläggningstillgångens nummer** > visa innehållet i fönstret **Relaterad information** > avsnittet **Associerade projekt**).</span><span class="sxs-lookup"><span data-stu-id="88255-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

