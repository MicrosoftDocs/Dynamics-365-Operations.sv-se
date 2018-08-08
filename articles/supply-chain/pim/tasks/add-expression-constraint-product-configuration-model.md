--- 
title: "Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell"
description: "I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration."
author: ShylaThompson
manager: AnnBe
ms.date: 10/27/2016
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
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration. Här visas hur du kan bestämma att hörnskyddet måste användas på en högtalare om användaren har valt ett frontgaller i metall. Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.


## <a name="create-an-expression-constraint"></a>Skapa en uttrycksbegränsning
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Hitta och markera önskad post i listan.
    * I det här exemplet används den avancerade högtalarmodellen.  
4. Klicka på länken på den valda raden i listan.
5. Expandera avsnittet Begränsningar.
6. Klicka på Lägg till.
7. Klicka på Skapa.
8. Skriv ett värde i fältet Namn.

## <a name="enter-expression"></a>Skriv uttryck
1. Klicka på Redigera uttryck.
    * Om du låser upp användargränssnittet i uppgiften som registrerar i detta skede, kan du använda IntelliSense och listan över symboler för att skapa begränsningsuttrycket.  
2. I fältet ConstraintBody anger du Implies[FrontGrill=="Metal", CornerProtection].
    * Uttryckslogiken betyder: om frontgallret är av metall, måste hörnskyddsalternativet markeras.  
3. Klicka på Validera.
    * Verifierafunktionen körs igenom begränsningsuttrycket och söker efter syntaxfel.  
4. Klicka på Stäng.
5. Klicka på OK.


