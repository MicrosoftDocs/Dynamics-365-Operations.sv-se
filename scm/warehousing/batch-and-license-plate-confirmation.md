---
title: "Bekräftelse av batch och ID-nummer"
description: "Det här avsnittet beskriver hur du ställer in och använder bekräftelse av batch och registreringsskylt från en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 70a8c18560f0cfc7a44625520f2f035a6004618a
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017

---

# <a name="batch-and-license-plate-confirmation"></a>Bekräftelse av batch och ID-nummer

[!include[banner](../includes/banner.md)]

Batch-bekräftelse låter dig bekräfta att korrekt batch hämtas från den mobila enheten. På den första plockningen för batch ovan-objekt, anger *batch ovan* att om batch-intervall överskrider placering i sökningshierarkin måste du kontrollera att den batch som plockas matchar batchen på arbetsraden. 

Bekräftelse för registreringsskylt låter dig bekräfta att korrekt registreringsskylt hämtas från den mobila enheten. När du plockar arbete från en fasplats måste du kontrollera att registreringsskylten som plockas matchar registreringsskylten som associeras med arbetet. Om arbetet har påbörjats genom att skanna en registreringsskylt, kommer detta bekräftelsesteg att hoppas över.

## <a name="where-it-applies"></a>När det gäller
Bekräftelse tillämpas detta i följande fall:

- Batch-bekräftelse gäller första plockningen för arbete för batch ovan-objekt.
- Bekräftelse för registreringsskylt gäller för plockning från fasplatser.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Ange bekräftelse av batch och registreringsskylt
Du kan konfigurera bekräftelse av batch och registreringsskylt från mobila enhetens menyalternativ.  
1.  Ange inställning av arbetsbekräftelse från mobila enhetens menyalternativ.  
2.  Välj alternativ för bekräftelse av batch eller registreringsskylt. Båda alternativen är tillgängliga för arbetstypen plockning som inte har automatisk bekräftelse aktiverad.  

