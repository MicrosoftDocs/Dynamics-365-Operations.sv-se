---
title: "Balanserade journaler för internredovisning"
description: "Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 9b509e6561f017c71c5c9614af6f22c682ec89e3
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a>Balanserade journaler för internredovisning

[!include[banner](../includes/banner.md)]


Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning. 

Om redovisningposterna inte balanserar på nivån av värdena för den ekonomiska dimension, skapas ytterligare kontoposter automatiskt till att balansera journalen. Dessa kontoposter använder bokföringstyperna **Enhetsintern - debet** och**Enhetsintern - kredit** på sidan **Konton för automatiska transaktioner** för att bestämma huvudkontot. Exempelvis väljs Avdelning, som är det andra segmentet i huvudbokskonto, som den balanserade ekonomiska dimensionen och följande redovisningsposter håller på att skapas.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

I detta fall bestäms följande saldon:

-   För avdelning MSP = 100,00 CR
-   För avdelning NY = 100,00 DR

Därför skapas följande redovisningsposter automatiskt för att balansera journalen till nivån för värdena för ekonomisk dimension.

|                                   |           |
|-----------------------------------|-----------|
| (Enhetsintern debit) – MSP – OU\_256 | 100.00 DR |
| (Enhetsintern kredit) – NY – OU\_249 | 100.00 CR |






