---
title: Avgöra strukturlisteversionen
description: Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten.
author: roxanadiaconu
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91a55bfcd10ee0efbbf1170ad29194c17ea72d62cf5516e2661b43bad7446808
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766084"
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