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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cfc1425aca7a62205e0c7c50237f206a179a0e7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968864"
---
# <a name="reclassify-fixed-assets"></a>Omklassificera anläggningstillgångar

[!include [banner](../../includes/banner.md)]

Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp. 

När en anläggningstillgång omklassificeras:

* Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången. All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången. Statusen för den ursprungliga anläggningstillgångens böcker är Stängd. 

* De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**. Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen. Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**. 

* De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.

Följ dessa steg för att omklassificera en anläggningstillgång:

1. Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.
2. I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.
3. I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.
4. I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.
    * Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie. I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**. Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.  
5. Ange ett datum i fältet **Omklassificeringsdatum**.
6. Ange eller välj ett värde i fältet **Verifikationsserie**.
7. Klicka på **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]