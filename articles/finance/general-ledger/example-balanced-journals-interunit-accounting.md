---
title: Balanserade journaler för internredovisning
description: Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5f73606708b8c32a7a8ebc364af6ba57c4c343
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205533"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Balanserade journaler för internredovisning

[!include [banner](../includes/banner.md)]

Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning. 

Om redovisningposterna inte balanserar på nivån av värdena för den ekonomiska dimension, skapas ytterligare kontoposter automatiskt till att balansera journalen. Dessa kontoposter använder bokföringstyperna **Enhetsintern – debet** och **Enhetsintern – kredit** på sidan **Konton för automatiska transaktioner** för att bestämma huvudkontot. Exempelvis väljs Affärsenhet, som är det andra segmentet i huvudbokskonto, som den balanserade ekonomiska dimensionen och följande redovisningsposter håller på att skapas.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

I detta fall bestäms följande saldon:

-   För Affärsenhet MSP = 100,00 CR
-   För Affärsenhet NY = 100,00 DR

Därför skapas följande redovisningsposter automatiskt för att balansera journalen till nivån för värdena för ekonomisk dimension.

|                                   |           |
|-----------------------------------|-----------|
| (Enhetsintern debit) – MSP – OU\_256 | 100.00 DR |
| (Enhetsintern kredit) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]