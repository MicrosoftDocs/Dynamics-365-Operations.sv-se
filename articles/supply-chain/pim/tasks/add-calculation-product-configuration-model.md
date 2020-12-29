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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e703c6d505f1e2e77f454732301de7a6c130c58a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437683"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Lägg till en beräkning i en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell. Här visas hur du kan skapa använda för logiskt uttryck med operatorn ”If” när du vill ange att högtalarhöjden ska vara 10 för vita högtalare och 15 för övriga. Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.


## <a name="add-a-calculation"></a>Lägga till en beräkning

## <a name="create-calculation-expression"></a>Skapa ett beräkningsuttryck
1. Klicka på Redigera uttryck.
2. I ConstraintBody fältet anger du 'If[CabinetFinish=="White", 10, 15]'.
3. Klicka på Validera.
4. Klicka på Stäng.
5. Klicka på OK.

