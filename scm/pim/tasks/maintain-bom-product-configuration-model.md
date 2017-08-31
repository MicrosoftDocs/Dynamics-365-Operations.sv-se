--- 
title: "Underhåll strukturlista för produktkonfigurationsmodell"
description: "När du kör den här proceduren krävs en befintlig modell för produktkonfiguration."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 645d748235935ae67867295a87a84a6539710ab0
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Underhåll strukturlista för produktkonfigurationsmodell

[!include[task guide banner](../../includes/task-guide-banner.md)]

När du kör den här proceduren krävs en befintlig modell för produktkonfiguration. Högtalarmodellen i demonstrationsföretaget USMF används för att skapa den här proceduren.


## <a name="add-a-bom-line"></a>Lägga till en strukturlisterad
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Hitta och markera önskad post i listan.
    * Välj den avancerade högtalaren till proceduren.  
4. Klicka på länken på den valda raden i listan.
5. Expandera avsnittet Strukturlisterader.
6. Klicka på Lägg till.
7. Skriv ett värde i fältet Namn.
8. Ange ett värde i fältet Beskrivning.
9. Klicka på Spara.

## <a name="add-bom-line-details"></a>Lägga till information om strukturlisterad
1. Klicka på Information för strukturlisterad.
2. Ange eller välj ett värde i fältet Artikelnummer.
    * Du kan till exempel välja artikeln M0055.  
    * För varje strukturlisteradsegenskap kan du välja om det behövs ett fast värde eller om det ska mappas till ett attribut.  
3. Markera kryssrutan Uppsättning.
4. Välj Ja i fältet Beräkning.
    * När du ställer in beräkningsegenskapen på Ja garanteras att strukturlisteraden ingår i kostnadsberäkningarna.  
5. Klicka på fliken Inställningar.
6. Markera kryssrutan Uppsättning.
7. Ange ett tal i fältet Kvantitet.
    * Kvantitetsfältet bestämmer hur mycket av artikeln som ska inkluderas i strukturlistan. Detta kan vara en uppenbar kandidat till en attributmappning.  
8. Klicka på fliken Dimension.
    * Kontrollera om någon av produktdimensionerna är aktiva, och därför måste ha ett värde eller ett attribut.  
9. Klicka på OK.


