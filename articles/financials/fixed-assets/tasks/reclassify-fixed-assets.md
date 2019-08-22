---
title: Omklassificera anläggningstillgångar
description: Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d8cf2ff1e275df0466a7fe327a3180c0399e49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839939"
---
# <a name="reclassify-fixed-assets"></a>Omklassificera anläggningstillgångar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp. 

När en anläggningstillgång omklassificeras:

• Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången. All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången. Statusen för den ursprungliga anläggningstillgångens böcker är Stängd. 

• De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**. Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen. Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**. 

• De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.

Följ dessa steg för att omklassificera en anläggningstillgång:

1. Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.
2. I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.
3. I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.
4. I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.
    * Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie. I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**. Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.  
5. Ange ett datum i fältet **Omklassificeringsdatum**.
6. Ange eller välj ett värde i fältet **Verifikationsserie**.
7. Klicka på **OK**.
