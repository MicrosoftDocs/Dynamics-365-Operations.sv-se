---
title: "Orderspärrar"
description: "I det här avsnittet beskrivs spärrar på order i Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: c0c0e9a0f863eb33d544f63e40e0531cdaaf6426
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017



---

# Orderspärrar
<a id="order-holds" class="xliff"></a>

[!include[banner](includes/banner.md)]


I det här avsnittet beskrivs spärrar på order i Dynamics 365 for Retail.

En order kan parkeras för diverse skäl. Du kan till exempel lägga en order tills kundens adress eller betalningssätt kan verifieras, eller tills en chef kan granska kundens kreditgräns. Under säljprocessen, finns det tillfällen när beställningar måste läggas på is. Till exempel, en säljorder kan parkeras på grund av problem med en kundbetalning, på grund av misstänkt bedrägeri eller eftersom en chef måste granska ordinationen. När en försäljningsorder parkeras en order håll kod tilldelas försäljning för att ange orsaken till avbrottet. Försäljningsorder håll koder är konfigurerade på **Försäljning och marknadsföring** &gt; **Installation** &gt; **Försäljningsorder** &gt; **Orderspärrningskoder**. En kundorder kan parkeras manuellt vid beställningen skapas eller senare. Dessutom kan en order kan parkeras automatiskt, baserat på bedrägeri. Medan en försäljningsorder är i vänteläge kan du behöva uppdatera den med mer information. Alternativt kanske du vill kolla så du fortsätter att arbeta på det. Du kan checka ut en försäljningsorder, checka in den igen och även åsidosätta utcheckning för en annan användare genom att använda arbetsbänken för att spärra order (**Detaljhandel** &gt; **Kunder** &gt; **Orderspärrar**). När en order är klar att utföras, måste du ta bort spärren innan du kan slutföra orderprocessen.




