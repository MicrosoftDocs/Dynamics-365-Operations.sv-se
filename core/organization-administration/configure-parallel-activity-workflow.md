---
title: "Konfigurera en parallell aktivitet i ett arbetsflöde"
description: "Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 818fb054742b935d002a7341e54a37eca0bb4761
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Konfigurera en parallell aktivitet i ett arbetsflöde

Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.

En parallellt aktivitet består av arbetsflödesförgreningar som körs samtidigt.

## <a name="name-a-parallel-activity"></a>Namnge en parallell aktivitet
Följ dessa steg när du vill ange ett namn för en parallell aktivitet.
1.  Högerklicka på den parallella aktiviteten och välj **egenskaper** att öppna den **egenskaper** formuläret.
2.  Klicka på **Grundinställningar** i det vänstra fönstret.
3.  Ange ett unikt namn för den parallella aktiviteten i fältet **Name**.
4.  Klicka på **Stäng**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurera förgreningarna i en parallell aktivitet
Gör på följande sätt när du vill lägga till och konfigurera förgreningarna i denna parallella aktivitet.
1.  Dubbelklicka på den parallella aktiviteten för att visa förgreningarna för den parallella aktiviteten.
2.  Dra elementet **Branch** från området **Workflow elements** till en infogningspunkt på duken om du vill lägga till en förgrening. Följande bild visar en infogningspunkt.![Infogningspunkt](./media/workflow_insertionpoint.gif)
    | **Obs! **                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | Ordningen för förgreningarna är oviktig eftersom alla förgreningar i en parallell aktivitet körs samtidigt. |

3.  Se [Configure a parallel branch](http://axhelp.dynamics.com/en/wiki/configure-a-parallel-branch/) för att konfigurera respektive förgrening.




