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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfe07426e9ff11c60c5f703b810ba09d6c863399
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "343660"
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

