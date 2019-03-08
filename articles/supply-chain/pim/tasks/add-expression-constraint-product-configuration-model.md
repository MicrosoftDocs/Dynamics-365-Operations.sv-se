---
title: Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f94b82f8b2642b12a993bde7d6bb323da79f98
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "360588"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="55368-103">Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="55368-103">Add an expression constraint to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55368-104">I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="55368-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="55368-105">Här visas hur du kan bestämma att hörnskyddet måste användas på en högtalare om användaren har valt ett frontgaller i metall.</span><span class="sxs-lookup"><span data-stu-id="55368-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="55368-106">Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="55368-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="55368-107">Skapa en uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="55368-107">Create an expression constraint</span></span>
1. <span data-ttu-id="55368-108">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="55368-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="55368-109">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="55368-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="55368-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="55368-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="55368-111">I det här exemplet används den avancerade högtalarmodellen.</span><span class="sxs-lookup"><span data-stu-id="55368-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="55368-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="55368-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="55368-113">Expandera avsnittet Begränsningar.</span><span class="sxs-lookup"><span data-stu-id="55368-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="55368-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="55368-114">Click Add.</span></span>
7. <span data-ttu-id="55368-115">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="55368-115">Click Create.</span></span>
8. <span data-ttu-id="55368-116">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="55368-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="55368-117">Skriv uttryck</span><span class="sxs-lookup"><span data-stu-id="55368-117">Enter expression</span></span>
1. <span data-ttu-id="55368-118">Klicka på Redigera uttryck.</span><span class="sxs-lookup"><span data-stu-id="55368-118">Click Edit expression.</span></span>
    * <span data-ttu-id="55368-119">Om du låser upp användargränssnittet i uppgiften som registrerar i detta skede, kan du använda IntelliSense och listan över symboler för att skapa begränsningsuttrycket.</span><span class="sxs-lookup"><span data-stu-id="55368-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="55368-120">I fältet ConstraintBody anger du Implies[FrontGrill=="Metal", CornerProtection].</span><span class="sxs-lookup"><span data-stu-id="55368-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="55368-121">Uttryckslogiken betyder: om frontgallret är av metall, måste hörnskyddsalternativet markeras.</span><span class="sxs-lookup"><span data-stu-id="55368-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="55368-122">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="55368-122">Click Validate.</span></span>
    * <span data-ttu-id="55368-123">Verifierafunktionen körs igenom begränsningsuttrycket och söker efter syntaxfel.</span><span class="sxs-lookup"><span data-stu-id="55368-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="55368-124">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="55368-124">Click Close.</span></span>
5. <span data-ttu-id="55368-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55368-125">Click OK.</span></span>

