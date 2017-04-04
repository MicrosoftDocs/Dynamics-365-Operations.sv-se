---
title: "Orderspärrar"
description: "Detta ämne beskriver håller på beställningar via butik och handel i Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Orderspärrar

Detta ämne beskriver håller på beställningar via butik och handel i Dynamics AX.

En order kan parkeras för diverse skäl. Du kan till exempel lägga en order tills kundens adress eller betalningssätt kan verifieras, eller tills en chef kan granska kundens kreditgräns. Under säljprocessen, finns det tillfällen när beställningar måste läggas på is. Till exempel, en säljorder kan parkeras på grund av problem med en kundbetalning, på grund av misstänkt bedrägeri eller eftersom en chef måste granska ordinationen. När en försäljningsorder parkeras en order håll kod tilldelas försäljning för att ange orsaken till avbrottet. Håll koder för försäljningsordern har konfigurerats på **försäljnings- och**&gt;**inställningar**&gt;**försäljningsorder**&gt;**Order innehåller koder**. En kundorder kan parkeras manuellt vid beställningen skapas eller senare. Dessutom kan en order kan parkeras automatiskt, baserat på bedrägeri. Medan en försäljningsorder är i vänteläge kan du behöva uppdatera den med mer information. Alternativt kanske du vill kolla så du fortsätter att arbeta på det. Du kan checka ut en försäljningsorder, kontrollera det igen och håller jämna Åsidosätt utcheckning av en annan användare med hjälp av ordern workbench (**butik och handel**&gt;**kunder**&gt;**Order innehåller**). När en order är klar att utföras, måste du ta bort spärren innan du kan slutföra orderprocessen.


