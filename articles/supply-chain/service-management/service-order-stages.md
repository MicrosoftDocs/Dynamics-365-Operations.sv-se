---
title: Serviceorderfaser
description: Genom att definiera faser för en serviceorder och tilldela dem till arbetare kan du styra flödet för en serviceorder genom uppgifterna som olika personer utför i serviceorganisationen.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52bcb72e8222b378198fcd044428fa1a4a0e8944
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978445"
---
# <a name="service-order-stages"></a><span data-ttu-id="8dfd2-103">Serviceorderfaser</span><span class="sxs-lookup"><span data-stu-id="8dfd2-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8dfd2-104">Du kan ställa in faser för en serviceorder ska definieras uppgifter, som måste utföras, ordern, som de är i, och arbetarna som är ansvarig för att slutföra dem.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="8dfd2-105">Genom att definiera faser för en serviceorder och tilldela dem till arbetare kan du styra flödet för en serviceorder genom uppgifterna som olika personer utför i serviceorganisationen.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="8dfd2-106">Sekvensen med faser måste omfatta en första fas.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="8dfd2-107">Du kan också definiera de åtgärder som tillåts i varje fas.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="8dfd2-108">Om du exempelvis avmarkerar kryssrutan **Bokför** för alla utom den sista fasen förhindrar du att serviceordern bokförs innan den har gått igenom hela fassekvensen.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="8dfd2-109">Branchning i serviceorderfaser</span><span class="sxs-lookup"><span data-stu-id="8dfd2-109">Branching in service order stages</span></span>

<span data-ttu-id="8dfd2-110">När du ställer in en servicefas, kan du skapa flera alternativ, eller förgreningar, att välja mellan för nästa servicefas.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="8dfd2-111">Alla avdelningar som du skapar kan väljas när den inledande fasen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="8dfd2-112">Du ställer till exempel in **Planering** som en ursprunglig fas.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="8dfd2-113">Du skapar två faser med namne **Pågår** och **Avbryt** och väljer sedan **Planering** som det överordnade objektet för dem.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="8dfd2-114">Du tilldelar **Planering** in fasen till försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="8dfd2-115">När planeringsfasen för försäljningsordern är slutförd, kan du välja fasen **Pågår**, om försäljningsordern är klar att arbeta på, eller välja fasen **Avbryt**, om försäljningsordern är annullerad.</span><span class="sxs-lookup"><span data-stu-id="8dfd2-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dfd2-116">Se även</span><span class="sxs-lookup"><span data-stu-id="8dfd2-116">See also</span></span>

[<span data-ttu-id="8dfd2-117">Ställ in serviceorderfaser</span><span class="sxs-lookup"><span data-stu-id="8dfd2-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="8dfd2-118">Ändra serviceorderfasen</span><span class="sxs-lookup"><span data-stu-id="8dfd2-118">Change the service order stage</span></span>](change-service-order-stage.md)

  


