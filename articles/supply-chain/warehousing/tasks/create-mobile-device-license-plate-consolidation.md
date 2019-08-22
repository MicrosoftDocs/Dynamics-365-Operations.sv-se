---
title: Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer
description: I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc610a16f4b0e574b5d5e7f8fc9ecf1e12534645
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847313"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a>Skapa ett nytt menyalternativ för mobila enheter för avstämning av ID-nummer

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar ett menyobjekt för en mobil enhet med avseende på konsolideringsarbete för registreringsskyltar. Detta gör det möjligt för lagerarbetare att konsolidera artiklar på en enda registreringsskylt med artiklar på en annan registreringsskylt på samma plats. Exempelvis kan de använda detta om efterföljande mellanlagring var desamma på båda arbetsordrar, så att arbetsuppgiften endast måste utföras en enda gång för de sammanslagna artiklarna. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Denna uppgift utförs vanligtvis av en lagerchef. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.

1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Menyalternativ.
4. Ange ett värde i fältet Titel.
5. Välj "Indirect" i fältet Model.
6. Välj "Consolidate license plates" i fältet Activity code.

