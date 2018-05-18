--- 
title: Definiera ekonomiska dimensioner
description: "Den här uppgiften vägleder dig genom stegen för att skapa en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0b72acf763f0f6dbc64c3e00986bc9eb0e366bb5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-financial-dimensions"></a>Definiera ekonomiska dimensioner

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften vägleder dig genom stegen för att skapa en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension.  Guiden använder demoföretaget USMF.


## <a name="create-an-entity-backed-financial-dimension"></a>Skapa en enhetsbaserad ekonomisk dimension
1. Gå till huvudboken > kontoplan > mått > finansiella mått.
2. Klicka på Ny.
3. Välj en systemdefinierad enhet som den ekonomiska dimensionen ska baseras på i fältet Användarvärden från. 
4. Skriv ett värde som beskriver den ekonomiska dimensionen i fältet Dimensionsnamn.
    * Namnet kan vara ett annat än den systemdefinierade entiteten men får inte innehålla blanksteg eller specialtecken.  
5. Klicka på Aktivera.
    * Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.  
6. Klicka på Stäng i aktiveringsmeddelandet.
7. Klicka på Aktivera.
    * Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.  
8. Klicka på Dimensionsvärden.
    * Vissa dimensionsvärden är företagsspecifika. Du kan kontrollera om de är företagsspecifika genom att se efter om företagsnamnet visas i dimensionsvärdelistan.  

## <a name="create-a-custom-financial-dimension"></a>Skapa en anpassad ekonomisk dimension
1. Stäng sidan.
2. Klicka på Ny.
3. Välj <Custom dimension> ett alternativ i fältet Använd värden från.
4. Skriv ett värde som beskriver den ekonomiska dimensionen i fältet Dimensionsnamn.
    * Namnet kan inte innehålla blanksteg eller specialtecken.  
    * Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden.   
    * Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck. Du kan även ange nummertecken (#.) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång som dimensionsvärdet skapas. Använd ett nummertecken (#.) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav.  Exempel: Om du vill begränsa dimensionsvärdet till bokstäverna CC och tre siffror anger du CC-### i formatmasken.  
5. Klicka på Aktivera.
    * Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.  
6. Klicka på Aktivera.
    * Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.  
7. Klicka på Dimensionsvärden.
8. Klicka på Ny.
9. Skriv ett namn som beskriver det ekonomiska dimensionsvärdet i fältet Dimensionsvärde.
10. Skriv en beskrivning som beskriver den ekonomiska dimensionens värde i fältet Beskrivning.


