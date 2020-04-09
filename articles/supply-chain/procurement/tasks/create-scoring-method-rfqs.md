---
title: Skapa en poängmetod för anbudsförfrågan
description: Den här proceduren visar hur du skapar en poängmetod.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0e1fe2a27998c01012e40d80eacf13aa11f5689
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147352"
---
# <a name="create-a-scoring-method-for-rfqs"></a>Skapa en poängmetod för anbudsförfrågan

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du skapar en poängmetod. En poängmetod är en uppsättning kriterier som kan användas för att jämföra bud som skickas som svar på en anbudsförfrågan. Du kanske till exempel vill utvärdera en leverantör för tidigare prestationer, eller bedöma om företaget är miljövänligt eller en bra samarbetspartner, eller du kanske vill jämföra bud baserat på pris. Poängmetoden kan kopplas till en typ av begäran som standardpoängmetoden för anbudsförfrågan av den typen. Dessa uppgifter utförs vanligtvis av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.

1. Gå till Anskaffning och källa > Inställning > Anbudsförfrågan > Poängsättningsmetod.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klicka på Ny.
7. Skriv ett värde i fältet Namn.
8. Ange ett värde i fältet Beskrivning.
    * Beskrivningen visas tillsammans med poängmetodsnamnet när en poängmetod markeras för en anbudsförfrågan.  
9. Ange ett nummer i fältet Intervall från.
    * Intervallgränserna som anskaffningsproffset kan ange som en poäng. Om det finns flera poängkriterier på en anbudsförfrågan, kommer poängen som har angetts läggas till varandra och summan görs tillgänglig för att låta jämföra buden.  
10. Ange ett nummer i fältet Intervall till.
11. Klicka på Ny.
12. Skriv ett värde i fältet Namn.
13. Ange ett värde i fältet Beskrivning.
14. Ange ett nummer i fältet Intervall från.
15. Ange ett nummer i fältet Intervall till.

