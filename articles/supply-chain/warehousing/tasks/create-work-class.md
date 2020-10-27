---
title: Skapa en arbetsklass
description: I den här proceduren visas hur du ställer in en arbetsklass.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc0eb4c0a6397164d068b5dd44a0807dfdf65814
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979609"
---
# <a name="create-a-work-class"></a>Skapa en arbetsklass

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in en arbetsklass. Arbetsklasser används för att styra och/eller begränsa den typ av arbetsorderrader som en lagerarbetare kan bearbeta på en mobil enhet. De rader som en anställd kan bearbeta bestäms från de arbetsklasser på menyobjekten för mobil enhet som lagerarbetaren har tillgång till och den arbetsklass som anges i på arbetsraderna. Arbetsklasser kan också användas för att validera läggplatsen för en arbetsorderrad. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Den här proceduren är avsedd för lagerchefen.

1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetsklasser.
2. Klicka på Ny.
3. Skriv ett värde i fältet Arbetsklass-ID.
4. Ange ett värde i fältet Beskrivning.
5. Välj ett alternativ i fältet Arbetsorder.
6. Klicka på Ny.
7. Skriv ett värde i fältet Platstyp.
    * Om du väljer en platstyp anges en begränsning på var artiklar kan placeras efter att de har plockats. Denna inställning används när ett platsdirektiv försöker lösa platsen, eller om en lagerarbetare manuellt anger platsen för menyobjektet för mobil enhet.  
8. Stäng sidan.

