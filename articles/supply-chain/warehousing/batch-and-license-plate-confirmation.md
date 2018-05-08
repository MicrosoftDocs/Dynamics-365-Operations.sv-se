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
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0444caa0f1cc176153c322b8619db65bd377ddd0
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="batch-and-license-plate-confirmation"></a>Bekräftelse av batch och ID-nummer

[!include [banner](../includes/banner.md)]

Batch-bekräftelse låter dig bekräfta att korrekt batch hämtas från den mobila enheten. På den första plockningen för batch ovan-objekt, anger batch ovan att om batch-intervall överskrider placering i sökningshierarkin måste du kontrollera att den batch som plockas matchar batchen på arbetsraden. 

Bekräftelse för registreringsskylt låter dig bekräfta att korrekt registreringsskylt hämtas från den mobila enheten. När du plockar arbete från en fasplats måste du kontrollera att registreringsskylten som plockas matchar registreringsskylten som associeras med arbetet. Om arbetet har påbörjats genom att skanna en registreringsskylt, kommer detta bekräftelsesteg att hoppas över.

## <a name="where-it-applies"></a>När det gäller
Bekräftelse tillämpas detta i följande fall:

- Batch-bekräftelse gäller första plockningen för arbete för batch ovan-objekt.
- Bekräftelse för registreringsskylt gäller för plockning från fasplatser.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Ange bekräftelse av batch och registreringsskylt
Du kan konfigurera bekräftelse av batch och registreringsskylt från mobila enhetens menyalternativ.  
1.  Ange inställning av arbetsbekräftelse från mobila enhetens menyalternativ.  
2.  Välj alternativ för bekräftelse av batch eller registreringsskylt. Båda alternativen är tillgängliga för arbetstypen plockning som inte har automatisk bekräftelse aktiverad.  

