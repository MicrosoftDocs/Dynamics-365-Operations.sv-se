---
title: Ställ in global källskatt
description: Detta ämne ämnet innehåller en lista med steg för att ställa in global källskatt för försäljning och inköp.
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7ee577651694f0553447d6e9d0851402a586f363
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060795"
---
# <a name="set-up-global-withholding-tax"></a>Ställ in global källskatt

Detta ämne ämnet innehåller en lista med steg för att ställa in global källskatt för försäljning och inköp. 

1. Ställ in källskattemyndigheter på sidan **Källskattemyndigheter**.

2. Ställ in kvittningsperioder för källskatt på sidan **Kvittningsperioder för källskatt**.

3. Ställ in bokföringsgrupp för källskatt på sidan för **Källskatt > Bokföringsgrupp för redovisning**.

   > [!Note] 
   >
   > Kontot för **Källskatt** kommer att tilldelas ett huvudkonto med bokföringstypen **Källskatt**. Kontot för **Källskattsförskjutning** kommer också att tilldelas ett huvudkonto med **Bokföringstypen** "Källskattsförskjutning". Gå till **Redovisning > Kontoplan > Konton > Huvudkonton**, konfigurera **Bokföringstyp** i det underordnade formuläret **Bokföringsvalidering** för huvudkontona.

4. Konfigurera källskattekoder på sidan **Källskattekoder**.

5. Konfigurera källskattekoder på sidan **Källskattegrupper**.

6. Konfigurera intäktstyper för källskatt på sidan **Intäktstyper för** för **källskatt**.

7. Konfigurera källskattegrupper på sidan **Källskattegrupper för artiklar** för en artikel eller tjänst.

8. Ställ in **Minsta fakturabelopp** på sidan **Redovisningsparametrar > Källskatt**.
