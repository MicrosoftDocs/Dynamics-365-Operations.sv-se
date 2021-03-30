---
title: Skapa en källskattbetalning
description: Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period. Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: eae914ccafad12426cadd91c0950bada23548005
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212287"
---
# <a name="create-a-withholding-tax-payment"></a>Skapa en källskattbetalning

Jobbproceduren för källskatt kvittar källskattssaldon från leverantörsreskontra på källskattskonton, och motbokar dem på kontot för källskattskvittning för en viss period. Detta ämne innehåller en lista med steg för att ställa in en källskattebetalning.

> [!NOTE] 
> Motbokning av källskatt (från kundreskontra) räknas inte med när en källskattebetalning beräknas.

1. Gå till **Navigeringsfönster > Moduler > Skatt > Deklarationer > Källskatt > Källskattebetalning**.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kvittningsperiod**.
3. Klicka på länken på den valda raden i listan.
4. I fältet **Från datum** anger du ett datum.
5. I fältet **Transaktionsdatum**, ange ett datum.
6. Välj **Uppdatera** om du vill bokföra betalningsverifikationen för källskatt på kvittningskontot för källskatt.
7. Klicka på **OK**.

![Parametrar för betalning av källskatt](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]