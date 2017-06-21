---
title: "Konfigurera en parallell aktivitet i ett arbetsflöde"
description: "Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4c2f98803164d5c761d2089152c077cfb9e83c43
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Konfigurera en parallell aktivitet i ett arbetsflöde

[!include[banner](../includes/banner.md)]


Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.

En parallellt aktivitet består av arbetsflödesförgreningar som körs samtidigt.

## <a name="name-a-parallel-activity"></a>Namnge en parallell aktivitet
Följ dessa steg när du vill ange ett namn för en parallell aktivitet.
1.  Högerklicka den parallella aktiviteten och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper**.
2.  Klicka på **Grundinställningar** i det vänstra fönstret.
3.  Ange ett unikt namn för den parallella aktiviteten i fältet **Namn**.
4.  Klicka på **Stäng**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurera förgreningarna i en parallell aktivitet
Gör på följande sätt när du vill lägga till och konfigurera förgreningarna i denna parallella aktivitet.
1.  Dubbelklicka på den parallella aktiviteten för att visa förgreningarna för den parallella aktiviteten.
2.  Dra elementet **Avdelning** från området **Arbetsflödeselement** till en infogningspunkt på duken om du vill lägga till en förgrening. Följande bild visar en infogningspunkt.![Infogningspunkt](./media/workflow_insertionpoint.gif)
    | **Obs!**                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | Ordningen för förgreningarna är oviktig eftersom alla förgreningar i en parallell aktivitet körs samtidigt. |

3.  Se [Konfigurera en parallell gren](configure-parallel-branch-workflow.md) för att konfigurera respektive förgrening.






