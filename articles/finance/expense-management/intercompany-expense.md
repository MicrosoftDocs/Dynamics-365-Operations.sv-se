---
title: Koncerninterna utgifter
description: En medarbetare som anställts av en juridisk entitet i en organisation kan utföra arbete för en annan juridisk person inom samma organisation. I denna situation kan du använda funktionen för företagsinterna utgifter för att tilldela medarbetarens utgifter till den juridiska person som arbetet utförts för.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390894"
---
# <a name="intercompany-expenses"></a>Koncerninterna utgifter

[!include [banner](../includes/banner.md)]

En medarbetare som anställts av en juridisk entitet i en organisation kan utföra arbete för en annan juridisk person inom samma organisation. I denna situation kan du använda funktionen för företagsinterna utgifter för att tilldela medarbetarens utgifter till den juridiska person som arbetet utförts för. Den juridiska entiteten som anställer medarbetaren kallas för "utlånande juridisk person". Den juridiska entiteten som medarbetaren genererar utgifter för kallas "lånande juridisk person". 

Innan en medarbetare kan skapa och skicka in utgifter för arbete som utförs för en annan juridisk person måste du, på sidan **Parametrar för utgiftshantering**, välja alternativet **Tillåt företagsinterna utgiftsrader** i den utlånande juridiska personen. 

## <a name="tax-posting-for-intercompany-expenses"></a>Momsbokföring för koncerninterna utgifter

[!include [banner](../includes/banner.md)]

Om du vill använda momsgrupper som är kopplade till den utlånande juridiska personen (källan) i stället för den lånande juridiska personen (mål) i utgiftsrapporten måste du konfigurera den här inställningen i momsinställningarna för redovisningen. När redovisningsparametern **Juridisk person för koncernintern momsbokföring** är inställd på **Källa** och **Tillämpa momsskatt regler** ställs in på **Nej** kommer moms kombinationen för den lånande juridiska personen att användas. När samma parameter anges som **Mål** kommer momskombinationen för lånande juridisk person att användas. För juridiska personer i USA gäller att när parametern är inställd på **Källa** måste även fältet **Momsfordran** konfigureras på den nya sidan **Bokföringsgrupper för redovisning**. Redovisningsmotorn kommer att använda informationen från det här fältet för att ange en skatterelaterad redovisningspost.   
Beteendet är konsekvent för utgiftsrader som bokförts med eller utan projekt.  
