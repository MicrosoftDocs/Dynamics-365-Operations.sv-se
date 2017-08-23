--- 
title: "Ställ in ansvarsfördelning"
description: "Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare."
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 2ab30f4326b627406f9a39d6c3203b181b67d68f
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-segregation-of-duties"></a>Ställ in ansvarsfördelning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare. Detta koncept kallas ansvarsfördelning. Du kan till exempel välja att inte samma person både ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören. Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter. Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer. Slutför följande procedur för att skapa en regel. Du måste vara systemadministratör för att slutföra den här proceduren. Det demonstrationsdataföretag som används för att skapa den här proceduren är DAT. 

1. Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
    * Ange ett namn på regeln.  
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Första programbehörighet.
5. Hitta och markera önskad post i listan.
    * Välj det första programbehörigheten som kontrolleras av regeln.  
6. Klicka på länken på den valda raden i listan.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Andra programbehörighet.
8. Hitta och markera önskad post i listan.
    * Välj den andra programbehörigheten som kontrolleras av regeln.  
9. Klicka på länken på den valda raden i listan.
10. Markera ett alternativ i fältet Allvarlighetsgrad.
    * Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.  
11. Ange ett värde i fältet Säkerhet.
    * Ange en beskrivning av säkerhetsrisken.  
12. Ange ett värde i fältet Säkerhetshöjning.
    * Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken. Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.  
13. Klicka på Spara.


