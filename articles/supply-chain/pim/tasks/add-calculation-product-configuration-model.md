---
title: Lägg till en beräkning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9754c46010e7bbdb2edef0d6e68162f344bb1257
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "343177"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Lägg till en beräkning i en produktkonfigurationsmodell

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell. Här visas hur du kan skapa använda för logiskt uttryck med operatorn ”If” när du vill ange att högtalarhöjden ska vara 10 för vita högtalare och 15 för övriga. Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.


## <a name="add-a-calculation"></a>Lägga till en beräkning

## <a name="create-calculation-expression"></a>Skapa ett beräkningsuttryck
1. Klicka på Redigera uttryck.
2. I ConstraintBody fältet anger du If[CabinetFinish=="White", 10, 15].
3. Klicka på Validera.
4. Klicka på Stäng.
5. Klicka på OK.

