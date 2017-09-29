--- 
title: "Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell"
description: "I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="f8049-103">Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="f8049-103">Add an expression constraint to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8049-104">I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8049-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="f8049-105">Här visas hur du kan bestämma att hörnskyddet måste användas på en högtalare om användaren har valt ett frontgaller i metall.</span><span class="sxs-lookup"><span data-stu-id="f8049-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="f8049-106">Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f8049-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="f8049-107">Skapa en uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="f8049-107">Create an expression constraint</span></span>
1. <span data-ttu-id="f8049-108">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="f8049-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="f8049-109">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8049-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="f8049-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f8049-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f8049-111">I det här exemplet används den avancerade högtalarmodellen.</span><span class="sxs-lookup"><span data-stu-id="f8049-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="f8049-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f8049-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f8049-113">Expandera avsnittet Begränsningar.</span><span class="sxs-lookup"><span data-stu-id="f8049-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="f8049-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f8049-114">Click Add.</span></span>
7. <span data-ttu-id="f8049-115">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="f8049-115">Click Create.</span></span>
8. <span data-ttu-id="f8049-116">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f8049-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="f8049-117">Skriv uttryck</span><span class="sxs-lookup"><span data-stu-id="f8049-117">Enter expression</span></span>
1. <span data-ttu-id="f8049-118">Klicka på Redigera uttryck.</span><span class="sxs-lookup"><span data-stu-id="f8049-118">Click Edit expression.</span></span>
    * <span data-ttu-id="f8049-119">Om du låser upp användargränssnittet i uppgiften som registrerar i detta skede, kan du använda IntelliSense och listan över symboler för att skapa begränsningsuttrycket.</span><span class="sxs-lookup"><span data-stu-id="f8049-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="f8049-120">I fältet ConstraintBody anger du Implies[FrontGrill=="Metal", CornerProtection].</span><span class="sxs-lookup"><span data-stu-id="f8049-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="f8049-121">Uttryckslogiken betyder: om frontgallret är av metall, måste hörnskyddsalternativet markeras.</span><span class="sxs-lookup"><span data-stu-id="f8049-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="f8049-122">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="f8049-122">Click Validate.</span></span>
    * <span data-ttu-id="f8049-123">Verifierafunktionen körs igenom begränsningsuttrycket och söker efter syntaxfel.</span><span class="sxs-lookup"><span data-stu-id="f8049-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="f8049-124">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="f8049-124">Click Close.</span></span>
5. <span data-ttu-id="f8049-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f8049-125">Click OK.</span></span>


