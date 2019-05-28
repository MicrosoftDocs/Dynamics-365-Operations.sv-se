---
title: Underhåll strukturlista för produktkonfigurationsmodell
description: När du kör den här proceduren krävs en befintlig modell för produktkonfiguration.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 457aa5720919d8455a3099b200980bb36f60577f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567732"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Underhåll strukturlista för produktkonfigurationsmodell

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

