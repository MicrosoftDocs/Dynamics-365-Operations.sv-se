--- 
title: "Definiera ett utgångsdatum för en produktionsflödesversion"
description: "För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen."
author: cvocph
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definiera ett utgångsdatum för en produktionsflödesversion

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


