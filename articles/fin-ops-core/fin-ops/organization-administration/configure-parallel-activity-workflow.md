---
title: Konfigurera parallella aktiviteter i ett arbetsflöde
description: Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068773"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Konfigurera parallella aktiviteter i ett arbetsflöde

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.

En parallellt aktivitet består av arbetsflödesförgreningar som körs samtidigt.

## <a name="name-a-parallel-activity"></a>Namnge en parallell aktivitet

Följ dessa steg när du vill ange ett namn för en parallell aktivitet.

1. Högerklicka den parallella aktiviteten och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper**.
2. Klicka på **Grundinställningar** i det vänstra fönstret.
3. Ange ett unikt namn för den parallella aktiviteten i fältet **Namn**.
4. Klicka på **Stäng**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurera förgreningarna i en parallell aktivitet

Gör på följande sätt när du vill lägga till och konfigurera förgreningarna i denna parallella aktivitet.

1. Dubbelklicka på den parallella aktiviteten för att visa förgreningarna för den parallella aktiviteten.
2. Dra elementet **Avdelning** från området **Arbetsflödeselement** till en infogningspunkt på duken om du vill lägga till en förgrening. Följande bild visar en infogningspunkt.

    ![Infogningspunkt.](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > Ordningen för förgreningarna är oviktig eftersom alla förgreningar i en parallell aktivitet körs samtidigt.

3. Se [Konfigurera en parallella grenar i ett arbetsflöde](configure-parallel-branch-workflow.md) för att konfigurera respektive förgrening.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]