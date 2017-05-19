---
title: Skapa produktionsorder
description: "När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b55c4c729350fbe8311953cc21f85bb4122f39f8
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


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





