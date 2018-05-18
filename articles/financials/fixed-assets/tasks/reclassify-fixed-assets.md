--- 
title: "Omklassificera anläggningstillgångar"
description: "Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: 6bce294329c7ec6dc436c3d3baf6597e0283c9bd
ms.contentlocale: sv-se
ms.lasthandoff: 10/30/2017

---
# <a name="reclassify-fixed-assets"></a>Omklassificera anläggningstillgångar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp. 

När en anläggningstillgång omklassificeras:

• Alla värdemodeller för den befintliga anläggningstillgången skapas för den nya anläggningstillgången. All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången. Statusen för den ursprungliga anläggningstillgångens värdemodell är Stängd. 

• De nya värdemodellerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet Anskaffningsdatum. Datumet i körfältet Avskrivning kopieras från den ursprungliga tillgångsinformationen. Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet för senaste avskrivning. 

• De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.

1. Gå till Anläggningstillgångar > Periodiska uppgifter > Omklassificering.
2. I fältet Anläggningstillgångsgrupper väljer du den grupp som du vill omklassificera.
3. I nummerfältet för Anläggningstillgång väljer du den anläggningstillgång du vill omklassificera.
4. I fältet Ny anläggningstillgångsgrupp väljer du den grupp du vill överföra anläggningstillgången till.
    * Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet Nytt anläggningstillgångsnummer att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie. I annat fall uppdateras fältet Nytt anläggningstillgångsnummer med numret från den nummerserie som är inställd på sidan Parametrar för anläggningstillgångar. Om ingen nummerserie har angetts på sidan för Parametrar för anläggningstillgångar, ange då ett nummer i nummerfältet för Ny anläggningstillgång.  
5. Ange ett datum i fältet Omklassificeringsdatum.
6. Ange eller välj ett värde i fältet Voucher series.
7. Klicka på OK.


