---
title: Överför en anläggningstillgång
description: Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167591cf160916f256e2d10f122eca312ba07639
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186841"
---
# <a name="transfer-a-fixed-asset"></a>Överför en anläggningstillgång

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden överför den ekonomiska informationen för en tillgångsförteckning från en uppsättning ekonomiska dimensioner till en ny uppsättning ekonomiska dimensioner.  Här används revisorrollen och demonstrationdata för den juridiska personen USMF.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.
2. Hitta och välj den anläggningstillgång som ska överföras.
3. Klicka på **Anläggningstillgång** i åtgärdsfönstret.
4. Överför **Överför fasta anläggningstillgångar**.
5. I fältet **Överföringsdatum**, ange ett datum.
6. Ange en kommentar som beskriver överföringen.
    
    Den här listan visar samtliga böcker för anläggningstillgången.  
7. Välj de böcker som du vill överföra till en ny ekonomisk dimensionsuppsättning.
    * Listan visar de befintliga ekonomiska dimensionsvärdena för den valda boken.  
    * Välj den ekonomiska dimension som du vill uppdatera för den valda tillgångsförteckningen.  
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Ekonomisk dimension**.
    * Ange andra värden för ekonomisk dimension om det är tillämpligt.  
    * Alla värden för ekonomisk dimension ändras när en överföring uppstår, om ett värde har angetts eller lämnats tomt. Till exempel, om du anger ett värde för BusinessUnit och lämnar de ekonomiska dimensionerna CostCenter och Avdelning tomma. Om din kontostruktur tillåter toma värden för CostCenter och Avdelning leder överföringen till att varje värdemodell har det nya värdet för BusinessUnit och ett tomt värde för CostCenter och Avdelning.  
9. Klicka på **Uppdatera**.
    * Du har möjlighet att granska ändringar innan du slutför överföringen.  
    * Granska resultaten innan du överför tillgångsförteckningarna.  
10. Klicka på **Överför**.
