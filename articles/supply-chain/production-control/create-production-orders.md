---
title: Skapa produktionsorder
description: "När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: bcbb07553d990c35057ba32fd56d26fbc9c6f71b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="create-production-orders"></a>Skapa produktionsorder

[!include[banner](../includes/banner.md)]


När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln.

En tillverkningsorder passerar genom faser i produktionslivscykeln. När en order skapas tilldelas den statusen **Skapad**. När en order har avslutats tilldelas den statusen **Avslutad**. Ett parameterinställning i varje fas gör att en användare kan konfigurera varje steg. Inställningen kan ställas in för en enskild användare eller för alla användare.

Produktionsstrukturlistan och produktionsflödet är de huvudsakliga enheterna för tillverkningsordern. De kopieras till tillverkningsordern baserat på den valda artikeln och kvantiteten som ska produceras. Innan tillverkningsordern startas kan produktionsstrukturlistan och -flödet redigeras.

En tillverkningsorder kan skapas i följande situationer:

-   Skapas av huvudplaneringsutförandet baserat på materialefterfrågan.
-   Skapas direkt från en försäljningsorderrad eller när en tillverkningsorder på högre nivå skapas och beräknas (peggad leverans).
-   Skapas manuellt.




