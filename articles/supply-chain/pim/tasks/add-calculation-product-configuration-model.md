--- 
title: "Lägg till en beräkning i en produktkonfigurationsmodell"
description: "I den här proceduren visas hur du kan lägga till en ny beräkning i en produktkonfigurationsmodell."
author: ShylaThompson
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2db8fb922b085a7f118822ef4fd974ac338f4d99
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

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


