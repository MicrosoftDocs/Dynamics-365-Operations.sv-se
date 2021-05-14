---
title: Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920891"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="fdf01-103">Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="fdf01-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fdf01-104">I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fdf01-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="fdf01-105">Här visas hur du kan bestämma att hörnskyddet måste användas på en högtalare om användaren har valt ett frontgaller i metall.</span><span class="sxs-lookup"><span data-stu-id="fdf01-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="fdf01-106">Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fdf01-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="fdf01-107">Skapa en uttrycksbegränsning</span><span class="sxs-lookup"><span data-stu-id="fdf01-107">Create an expression constraint</span></span>

1. <span data-ttu-id="fdf01-108">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="fdf01-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fdf01-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fdf01-110">I det här exemplet används den avancerade högtalarmodellen.</span><span class="sxs-lookup"><span data-stu-id="fdf01-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="fdf01-111">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="fdf01-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="fdf01-112">Visa avsnittet **Begränsningar**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="fdf01-113">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-113">Select **Add**.</span></span>
7. <span data-ttu-id="fdf01-114">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-114">Select **Create**.</span></span>
8. <span data-ttu-id="fdf01-115">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="fdf01-116">Skriv uttryck</span><span class="sxs-lookup"><span data-stu-id="fdf01-116">Enter expression</span></span>

1. <span data-ttu-id="fdf01-117">Välj **Redigera uttryck**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="fdf01-118">Om du låser upp användargränssnittet i uppgiften som registrerar i detta skede, kan du använda IntelliSense och listan över symboler för att skapa begränsningsuttrycket.</span><span class="sxs-lookup"><span data-stu-id="fdf01-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="fdf01-119">I fältet **ConstraintBody** anger du "Implies[FrontGrill=="Metal", CornerProtection]" (utan citattecken före och efter).</span><span class="sxs-lookup"><span data-stu-id="fdf01-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="fdf01-120">Uttryckslogiken betyder: om frontgallret är av metall, måste hörnskyddsalternativet markeras.</span><span class="sxs-lookup"><span data-stu-id="fdf01-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="fdf01-121">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-121">Select **Validate**.</span></span>
    * <span data-ttu-id="fdf01-122">Verifierafunktionen körs igenom begränsningsuttrycket och söker efter syntaxfel.</span><span class="sxs-lookup"><span data-stu-id="fdf01-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="fdf01-123">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-123">Select **Close**.</span></span>
5. <span data-ttu-id="fdf01-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdf01-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]