---
title: Bokföringskonton för avyttring av anläggningstillgång
description: Det här ämnet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a46125dbe5262ba388e3958ea452975a98243f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187163"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Bokföringskonton för avyttring av anläggningstillgång

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar.

På sidan Bokföringsprofiler för anläggningstillgångar, på snabbfliken Redovisningskonto, välj Avyttrande - försäljning och Avyttrande - kassation om du vill ställa in bokföringar till redovisningen.

För båda transaktionstyperna krediteras huvudbokskontot för anläggningstillgångens avyttringsvärde. Debiteringen bokförs till ett motkonto, vilket exempelvis kan vara ett bankkonto. Om en anläggningstillgång säljs till en kund används kundens konto istället för motkontot.

Klicka på Avyttrande och klicka sedan på Kassation och skapa sedan detaljerade konton för att återföra anläggningstillgångens bokförda nettovärde. Du kan även ange information i fälten för Bokför värde och Försäljningsvärdetyp i sidan Parametrar för avyttrande. 

Avyttrandetransaktionen för en tillgång i en lågvärdespool minskar det bokförda nettovärdet för lågvärdespoolen med enbart avyttringsbeloppet. När försäljningen av en tillgång är större än det bokförda nettovärdet av lågvärdespoolen, minskar emellertid det bokförda nettovärdet till noll.




