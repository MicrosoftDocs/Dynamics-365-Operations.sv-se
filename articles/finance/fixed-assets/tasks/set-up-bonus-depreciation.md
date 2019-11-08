---
title: Ställ in bonusavskrivning
description: I den här proceduren visas hur du skapar en särskild avskrivning och kopplar den till en förteckning över anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788cddf4d822fe3d3d6a33e83d7b30f32f4b6b9c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179937"
---
# <a name="set-up-bonus-depreciation"></a>Ställ in bonusavskrivning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en särskild avskrivning och kopplar den till en förteckning över anläggningstillgångar. Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.


## <a name="create-a-special-depreciation-allowance"></a>Skapa en särskild avskrivning
1. Gå till Anläggningstillgångar > Inställningar > Särskild avskrivning.
2. Klicka på Ny.
3. Skriv ett värde i fältet Särskild avskrivning.
4. Ange ett värde i fältet Beskrivning.
5. Välj ett tal i fältet Procent.
    * Ange ett belopp om ingen procentsats indikerades.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Associera en särskild avskrivning med en räkenskapsbok för anläggningstillgångsgrupp
1. Gå till Anläggningstillgångar > Inställningar > Anläggningstillgångsgrupper.
2. I listan, välj nläggningstillgångsgruppen som är kopplad till den särskilda avskrivningen.
3. Klicka på Books.
4. I listan väljer du den räkenskapsbok som är associerad med den särskilda avskrivningen.
5. Klicka på Särskild avskrivning.
6. Klicka på Ny.
7. Ange eller välj ett värde i fältet Special depreciation allowance.
    * Förvalet för procentandel eller belopp stammar från de särskilda avskrivningsinställningarna.  
8. Välj ett tal i fältet Prioritet.
