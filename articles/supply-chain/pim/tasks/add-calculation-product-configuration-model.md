--- 
title: "Lägg till en beräkning i en produktkonfigurationsmodell"
description: "I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9754c46010e7bbdb2edef0d6e68162f344bb1257
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="5f526-103">Lägg till en beräkning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="5f526-103">Add a calculation to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f526-104">I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="5f526-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="5f526-105">Här visas hur du kan skapa använda för logiskt uttryck med operatorn ”If” när du vill ange att högtalarhöjden ska vara 10 för vita högtalare och 15 för övriga.</span><span class="sxs-lookup"><span data-stu-id="5f526-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="5f526-106">Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5f526-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="5f526-107">Lägga till en beräkning</span><span class="sxs-lookup"><span data-stu-id="5f526-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="5f526-108">Skapa ett beräkningsuttryck</span><span class="sxs-lookup"><span data-stu-id="5f526-108">Create calculation expression</span></span>
1. <span data-ttu-id="5f526-109">Klicka på Redigera uttryck.</span><span class="sxs-lookup"><span data-stu-id="5f526-109">Click Edit expression.</span></span>
2. <span data-ttu-id="5f526-110">I ConstraintBody fältet anger du If[CabinetFinish=="White", 10, 15].</span><span class="sxs-lookup"><span data-stu-id="5f526-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="5f526-111">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="5f526-111">Click Validate.</span></span>
4. <span data-ttu-id="5f526-112">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="5f526-112">Click Close.</span></span>
5. <span data-ttu-id="5f526-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5f526-113">Click OK.</span></span>


