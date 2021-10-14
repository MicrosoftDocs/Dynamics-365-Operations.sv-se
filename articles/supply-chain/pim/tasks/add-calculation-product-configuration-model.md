---
title: Lägg till en beräkning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d201061ff47203f09f96dc08ff6fc8ac437a6f9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570667"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Lägg till en beräkning i en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell. Här visas hur du kan skapa använda för logiskt uttryck med operatorn ”If” när du vill ange att högtalarhöjden ska vara 10 för vita högtalare och 15 för övriga. Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.


## <a name="add-a-calculation"></a>Lägga till en beräkning

## <a name="create-calculation-expression"></a>Skapa ett beräkningsuttryck
1. Klicka på Redigera uttryck.
2. I ConstraintBody fältet anger du If[CabinetFinish=="White", 10, 15].
3. Klicka på Validera.
4. Klicka på Stäng.
5. Klicka på OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]