---
title: Avgöra strukturlisteversionen
description: Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 370091eed4ee050031d5d135aa7b1d8d0fe82491
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570979"
---
# <a name="determine-the-bom-version"></a>Avgöra strukturlisteversionen

[!include [banner](../includes/banner.md)]

Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten. 

Sitedimensionen är alltid känd och anges på efterfrågetransaktionen. Följande process fastställer vilken strukturlisteversion att använda:

-   Om en strukturlisteversion har definierats för artikeln på siten för efterfrågan, används denna sitespecifika strukturlista.
-   Om ingen strukturlisteversion har definierats för artikeln på siten för efterfrågan, används en allmän strukturlista. En allmän strukturlista anger inte någon site och den gäller för flera siter. Om det finns en allmän strukturlista används den.
-   Om det inte finns någon allmän strukturlisteversion som kan användas, stannar efterfrågenedbrytningen här.

En giltig strukturlisteversion, oavsett om den är sitespecifik eller allmän, måste uppfylla kriterierna för datum och kvantitet.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]