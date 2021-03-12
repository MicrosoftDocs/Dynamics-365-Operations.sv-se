---
title: Ställ in ansvarsfördelning
description: Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcbd32131f9980a4f55e91b9d7ad48171069f72e
ms.sourcegitcommit: 316200579dd5b04ad76f276a2ed6b0f55fa8c812
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "4826404"
---
# <a name="set-up-segregation-of-duties"></a>Ställ in ansvarsfördelning

[!include [banner](../../includes/banner.md)]

Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare. Detta koncept kallas ansvarsfördelning. Du kan till exempel välja att inte samma person ska bekräfta inleveransen av varor och bearbeta betalningar till leverantören. Ansvarsfördelning minskar risken för bedrägeri och hjälper även till att identifiera fel eller oriktigheter. Du kan också använda ansvarsfördelning för att framtvinga interna kontrollpolicyer. Slutför följande procedur för att skapa en regel. Du måste vara systemadministratör för att slutföra den här proceduren.

1. Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Ansvarsfördelningsregler**.
2. Klicka på **Ny**.
3. I fältet **Namn** skriver du ett värde.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Första programbehörighet**.
5. Hitta och markera önskad post i listan. Välj det första programbehörigheten som kontrolleras av regeln.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Andra programbehörighet**. 
7. Hitta och markera önskad post i listan. Välj den andra programbehörigheten som kontrolleras av regeln.
10. Markera ett alternativ i fältet **Allvarlighetsgrad**. Markera allvarlighetsgraden för risken som uppstår när samma användare eller roll utför båda programbehörigheterna.  
11. Ange ett värde i fältet **Säkerhetsrisk**. Ange en beskrivning av säkerhetsrisken.  
12. Ange ett värde i fältet **Säkerhetshöjning**. Ange en beskrivning av de åtgärder som du vidtar för att minska säkerhetrisken. Du kan till exempel minska risken genom att utöva mer detaljerad granskning av processen, genom att utöva en månadsvis chefsgranskning eller genom att dela resurser med andra avdelningar.     
13. Klicka på **Spara**.

> [!IMPORTANT] 
> Efterföljanderegler för uppdelning av uppgifter kontrolleras inte när du skapar en regel. Du kan skapa en regel som skapar en konflikt för befintliga roller. Befintliga tilldelningar av användarroller kan också vara i konflikt med den nya regeln. Du måste validera efterföljande när du har skapat eller ändra en regel. För mer information, se [Identifiera och lösa konflikter vid ansvarsfördelning](identify-resolve-conflicts-segregation-duties.md)
