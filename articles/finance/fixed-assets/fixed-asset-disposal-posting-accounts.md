---
title: Bokföringskonton för avyttring av anläggningstillgång
description: Det här ämnet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c82cb8b82f2cc8424675f76c68613a2b5aa76745
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675528"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Bokföringskonton för avyttring av anläggningstillgång

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar.

För att ställa in redovisningskonton som ska användas när du gör dig av med en tillgång väljer du **Avyttringar - försäljning** och **Avyttringar - kassation** på snabbfliken **Redovisningskonton** på sidan **Bokföringsprofiler för anläggningstillgångar**.

För båda transaktionstyperna (avyttra en tillgång genom försäljning eller kassering) krediteras huvudbokskontot för anläggningstillgångens avyttringsvärde. Debiteringen bokförs till ett motkonto, vilket exempelvis kan vara ett bankkonto. Om en anläggningstillgång säljs till en kund används kundens konto istället för motkontot. Mer information finns i [Avyttra en anläggningstillgång som kassation](dispose-of-a-fixed-asset-as-scrap.md).

Klicka på **Avyttrande** och klicka sedan på **Försäljning** eller **Kassation** och skapa sedan detaljerade konton för att återföra anläggningstillgångens bokförda nettovärde. Du kan även ange information i fälten för **Bokför värde** och **Försäljningsvärdetyp** i sidan **Parametrar för avyttrande**. 

Avyttrandetransaktionen för en tillgång i en lågvärdespool minskar det bokförda nettovärdet för lågvärdespoolen med enbart avyttringsbeloppet. När försäljningen av en tillgång är större än det bokförda nettovärdet av lågvärdespoolen, minskar emellertid det bokförda nettovärdet till noll.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
