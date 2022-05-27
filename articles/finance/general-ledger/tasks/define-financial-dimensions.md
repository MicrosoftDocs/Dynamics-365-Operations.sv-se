---
title: Definiera ekonomiska dimensioner
description: Denna procedur visar hur du lägger till en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716955"
---
# <a name="define-financial-dimensions"></a>Definiera ekonomiska dimensioner

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du lägger till en enhetsbaserad ekonomisk dimension och en anpassad ekonomisk dimension. Guiden använder demoföretaget USMF.

## <a name="create-an-entity-backed-financial-dimension"></a>Skapa en enhetsbaserad ekonomisk dimension
1. Gå till **Navigeringsfönstret > Moduler > Redovisning > Kontoplan > Dimensioner > Ekonomiska dimensioner**.
2. Klicka på **Ny**.
3. Välj en systemdefinierad enhet som den ekonomiska dimensionen ska baseras på i fältet **Användarvärde från**. 
4. Skriv ett värde som beskriver den ekonomiska dimensionen i fältet **Dimensionsnamn**. Namnet kan vara ett annat än den systemdefinierade entiteten men får inte innehålla blanksteg eller specialtecken.
5. Klicka på **Aktivera**. Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.  
6. Klicka på **Stäng** på meddelande om aktivering.
7. Klicka på **Aktivera**. Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.  
8. I **Åtgärdsfönstret**, klicka på **Dimensionsvärden**. Vissa dimensionsvärden är företagsspecifika. Du kan kontrollera om de är företagsspecifika genom att se efter om företagsnamnet visas i dimensionsvärdelistan.  

## <a name="create-a-custom-financial-dimension"></a>Skapa en anpassad ekonomisk dimension
1. Klicka på **Ny**.
2. I **Använda värden från** fält, välj **Anpassa dimension**.
3. Skriv ett värde som beskriver den ekonomiska dimensionen i fältet **Dimensionsnamn**.
    - Namnet kan inte innehålla blanksteg eller specialtecken.  
    - Du kan även ange en kontomask för att begränsa beloppet och typen av information som du kan ange för dimensionsvärden.   
    - Du kan ange tecken som ska vara oförändrade för varje dimensionsvärde, till exempel bokstäver eller ett bindestreck. Du kan även ange nummertecken (#.) och et-tecken (&) som platshållare för bokstäver och siffror som ska ändras varje gång som dimensionsvärdet skapas. Använd ett nummertecken (#.) som platshållare för ett nummer och ett et-tecken (&) som platshållare för en bokstav.  Exempel: Om du vill begränsa dimensionsvärdet till bokstäverna CC och tre siffror anger du CC-### i formatmasken.  
4. Klicka på **Aktivera**. Om du aktiverar den ekonomiska dimensionen uppdateras tabellen med namnet på ekonomiska dimensioner och borttagna dimensioner tas bort. Du kan ange dimensionsvärden innan du aktiverar en ekonomisk dimension, men en ekonomisk dimension kan inte användas förrän den har aktiverats.     
5. Klicka på **Aktivera**. Dimensionsaktivering kan schemaläggas att köras av batchen vid ett visst datum och klockslag.      
6. I **Åtgärdsfönstret**, klicka på **Dimensionsvärden**.
7. Klicka på **Ny**.
8. Skriv ett namn som beskriver det ekonomiska dimensionsvärdet i fältet **Dimensionsvärde**.
9. Skriv en **beskrivning** som beskriver den ekonomiska dimensionens värde i fältet Beskrivning.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
