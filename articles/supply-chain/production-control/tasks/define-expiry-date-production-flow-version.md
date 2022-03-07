---
title: Definiera ett utgångsdatum för en produktionsflödesversion
description: För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87063653eb78209caaefd3fafa7783f425e710b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257301"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definiera ett utgångsdatum för en produktionsflödesversion

[!include [banner](../../includes/banner.md)]

För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen. Det är inte nödvändigt att inaktivera versionen.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Ange en utgångsdatum för att slutföra en produktionsflödesversion
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
    * Markera alla produktionsflöden som har en redan definierad version.  
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Markera vald rad i listan.
6. I fältet Utgångsdatum anger du datum och tid.
    * För utgångsdatumet kommer ingen ny version att startas eller aktiveras. Du kan heller inte längre skapa eller starta jobb för detta produktionsflöde. Du kan fortfarande utföra startade jobb efter utgångsdatumet.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]