---
title: "Avgöra strukturlisteversionen"
description: "Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7e6745a52138e545b557fa1aa286cd49481b2ecd
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="determine-the-bom-version"></a>Avgöra strukturlisteversionen

[!INCLUDE [banner](../includes/banner.md)]

Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten. 

Sitedimensionen är alltid känd och anges på efterfrågetransaktionen. Följande process fastställer vilken strukturlisteversion att använda:

-   Om en strukturlisteversion har definierats för artikeln på siten för efterfrågan, används denna sitespecifika strukturlista.
-   Om ingen strukturlisteversion har definierats för artikeln på siten för efterfrågan, används en allmän strukturlista. En allmän strukturlista anger inte någon site och den gäller för flera siter. Om det finns en allmän strukturlista används den.
-   Om det inte finns någon allmän strukturlisteversion som kan användas, stannar efterfrågenedbrytningen här.

En giltig strukturlisteversion, oavsett om den är sitespecifik eller allmän, måste uppfylla kriterierna för datum och kvantitet.






