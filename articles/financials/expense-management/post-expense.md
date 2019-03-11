---
title: Bokföra en utgiftsrapport
description: Det här avsnittet beskriver hur du bokför utgiftsrapporter i redovisningen.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1252825848aedcdaf633c04edddddca7dd09d774
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "359415"
---
# <a name="post-an-expense-report"></a>Bokföra en utgiftsrapport

[!include [banner](../includes/banner.md)]

När en utgiftsrapport har godkänts och överförts till den allmänna journalen kan rapporten bokföras i redovisningen. När du bokför en utgiftsrapport identifieras utgifter som berättigar till återbetalning av moms. Uppgiften att kontrollera och återställa momsbetalningar tilldelas den medarbetare som är ansvarig för att verifiera utgiftsrapporten.

Om utgifter i en utgiftsrapport debiteras ett annat företag än företaget som anställer medarbetaren måste du kontrollera med företaget om dessa kostnader är skulder till företaget och vilket företag som kostnaderna är skulder från. Till exempel medarbetaren som skickade en utgiftsrapport arbetar på DAT-företaget men debiterar DIR-företaget en utgift. I det här fallet är DAT företaget som utgifterna är skyldiga till och DIR är företaget som utgiften är skyldiga från. När du har kontrollerat dessa journalrader kan du bokföra utgiftsraderna i redovisningen.

Om du vill bokföra en utgiftsrapport på sidan **Godkända utgiftsrapporter** väljer du utgiftsrapporten och väljer sedan **bokför** i åtgärdsfönstret.

Du kan också bokföra alla utgiftsrapporter i listan samtidigt. Välj alla utgiftsrapporter och välj sedan **Bokför**.
