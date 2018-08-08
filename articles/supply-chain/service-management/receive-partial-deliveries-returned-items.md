---
title: Ta emot delleveranser med returnerade artiklar
description: Delvisa leveranser definieras i termer av returorderrader, inte returorderleveranser.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f9f596d31f2438a353b02bf939786b284937db86
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="receive-partial-deliveries-of-returned-items"></a>Ta emot delleveranser med returnerade artiklar    

[!include [banner](../includes/banner.md)]


Delvisa leveranser definieras i termer av returorderrader, inte returorderleveranser.

Om du därför inlevererar hela kvantiteten som anges på en returorderrad men du får inte får något inlevererat från de andra raderna på returordern anses leveransen inte vara en delleverans. Om en returorderrad kräver att 10 enheter av en artikel ska returneras, men du du bara får fyra inlevererade enheter är leveransen en delleverans.

Om en returleverans innehåller mindre än den fullständiga kvantiteten på en returorderrad kan du lägga leveransen åt sidan och vänta in resten av den returnerade kvantiteten, eller så kan du välja att registrera och bokföra delkvantiteten.

## <a name="register-and-post-a-partial-quantity"></a>Registrera och bokföra en delkvantitet

1.  När du har valt en returorder för införsel i formuläret **Införselöversikt - lagerställe: %1, plats: %2, journalnamn: %3** klickar du på **starta införsel** för att skapa införseljournalen och klickar sedan på **journaler**\>**Visa införsel från inleveranser** för att öppna formuläret **platsjournal**.

2.  Välj den journalrad som du vill arbeta med och klickar sedan på **rader** för att öppna formuläret **Journalrader, platser**.

3.  Markera raden för det artikelnummer som endast en delkvantitet har levererats för och klicka på **Funktioner** \> **Dela** för att öppna formuläret **Dela**.

4.  I fältet **Dela kvantitet**, ange kvantiteten för det totala antalet artiklar som har tagits emot i fältet och klicka sedan på **OK**.

5.  I formuläret **Journalrader, platser** markerar du raden för den kvantitet med artiklar som har levererats och klickar på **bokför**. Du kan bokföra raden för den ytterligare kvantiteten efter att artiklarna har levererats.





