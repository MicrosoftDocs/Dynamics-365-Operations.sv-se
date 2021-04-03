---
title: Lägg till en beräkning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e23d33c6911310cca6aac0df4589e909568a86a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258081"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="341aa-103">Lägg till en beräkning i en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="341aa-103">Add a calculation to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="341aa-104">I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell.</span><span class="sxs-lookup"><span data-stu-id="341aa-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="341aa-105">Här visas hur du kan skapa använda för logiskt uttryck med operatorn ”If” när du vill ange att högtalarhöjden ska vara 10 för vita högtalare och 15 för övriga.</span><span class="sxs-lookup"><span data-stu-id="341aa-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="341aa-106">Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="341aa-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="341aa-107">Lägga till en beräkning</span><span class="sxs-lookup"><span data-stu-id="341aa-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="341aa-108">Skapa ett beräkningsuttryck</span><span class="sxs-lookup"><span data-stu-id="341aa-108">Create calculation expression</span></span>
1. <span data-ttu-id="341aa-109">Klicka på Redigera uttryck.</span><span class="sxs-lookup"><span data-stu-id="341aa-109">Click Edit expression.</span></span>
2. <span data-ttu-id="341aa-110">I ConstraintBody fältet anger du If[CabinetFinish=="White", 10, 15].</span><span class="sxs-lookup"><span data-stu-id="341aa-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="341aa-111">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="341aa-111">Click Validate.</span></span>
4. <span data-ttu-id="341aa-112">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="341aa-112">Click Close.</span></span>
5. <span data-ttu-id="341aa-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="341aa-113">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]