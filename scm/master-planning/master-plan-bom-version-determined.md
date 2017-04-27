---
title: "Avgöra strukturlisteversionen"
description: "Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4e4f5f02dfa986669decbc8854148b5eff928c2a
ms.lasthandoff: 03/31/2017


---

# <a name="determine-the-bom-version"></a>Avgöra strukturlisteversionen

[!include[banner](../includes/banner.md)]


Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten. 

Sitedimensionen är alltid känd och anges på efterfrågetransaktionen. Följande process fastställer vilken strukturlisteversion att använda:

-   Om en strukturlisteversion har definierats för artikeln på siten för efterfrågan, används denna sitespecifika strukturlista.
-   Om ingen strukturlisteversion har definierats för artikeln på siten för efterfrågan, används en allmän strukturlista. En allmän strukturlista anger inte någon site och den gäller för flera siter. Om det finns en allmän strukturlista används den.
-   Om det inte finns någon allmän strukturlisteversion som kan användas, stannar efterfrågenedbrytningen här.

En giltig strukturlisteversion, oavsett om den är sitespecifik eller allmän, måste uppfylla kriterierna för datum och kvantitet.






