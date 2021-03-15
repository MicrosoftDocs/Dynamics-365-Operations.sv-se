---
title: Livscykel för produktionsorder – översikt
description: När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28ef1da29b38354d7ccaad56fb036f21d8c9ff15
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011182"
---
# <a name="production-order-lifecycle-overview"></a>Livscykel för produktionsorder – översikt

[!include [banner](../includes/banner.md)]

När du skapar en produktionsorder initieras en begäran om att starta produktionen av en artikel. Produktionsordern innehåller information om vad som ska produceras, hur mycket samt planerat slutdatum. Den innehåller också information om vilka material som ska förbrukas och vilken process som ska följas vid produktionen av artikeln.

En tillverkningsorder passerar genom faser i produktionslivscykeln. När en order skapas tilldelas den statusen **Skapad**. När en order har avslutats tilldelas den statusen **Avslutad**. Ett parameterinställning i varje fas gör att en användare kan konfigurera varje steg. Inställningen kan ställas in för en enskild användare eller för alla användare.

Produktionsstrukturlistan och produktionsflödet är de huvudsakliga enheterna för tillverkningsordern. De kopieras till tillverkningsordern baserat på den valda artikeln och kvantiteten som ska produceras. Innan tillverkningsordern startas kan produktionsstrukturlistan och -flödet redigeras.

En tillverkningsorder kan skapas i följande situationer:

-   Skapas av huvudplaneringsutförandet baserat på materialefterfrågan.
-   Skapas direkt från en försäljningsorderrad eller när en tillverkningsorder på högre nivå skapas och beräknas (peggad leverans).
-   Skapas manuellt.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]