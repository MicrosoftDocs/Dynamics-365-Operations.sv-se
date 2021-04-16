---
title: Delegera arbetsuppgifter i ett arbetsflöde
description: Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed21f6d32cdcf74eb153daba32c20b7cef94d4e4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747379"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegera arbetsuppgifter i ett arbetsflöde

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Manuellt delegera en arbetsuppgift

Om du vill delegera en enskild arbetsuppgift, välj alternativet **Delegera** i menyn **Arbetsflöde** och ange sedan användaren som ska delegeras till tillsammans med en kommentar. Detta tilldelar om arbetsuppgift till användaren så att de kan slutföra den.

## <a name="manually-delegate-multiple-work-items"></a>Delegera flera arbetsuppgifter manuellt

Flera arbetsuppgifter kan delegeras till varandra från sidan **Arbetsuppgifter som tilldelats till mig**. Följande arbetsflödestyper är berättigade för massdelegering: arbetsflöde för godkännande av inköpsavtal, arbetsflöde för inköpsorder, granskning av inköpsrekvisition och arbetsflöde för leverantör. Funktionen **Delegera flera arbetsuppgifter** är inaktiverad som standard och kan aktiveras i **Arbetsytor > Funktionshantering**. Kontakta systemadministratören om du vill ha hjälp med att aktivera den här funktionen.
1.  Gå till **Gemensamt > Gemensamt > Arbetsuppgifter > Arbetsuppgifter som tilldelats till mig**.
2.  Välj de arbetsuppgifter som ska delegeras.
3.  Klicka på menyn **Delegera arbetsuppgifter**.
4.  I fältet **användare** markera den användare som du vill delegera arbetsuppgifterna till.
5.  Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet **Kommentar**.
6.  Klicka på knappen **Delegera arbetsuppgifter** om du vill slutföra delegeringen av arbetsuppgiften.

## <a name="automatically-delegate-work-items"></a>Delegera arbetsuppgiften automatiskt

Om du tänker vara borta från kontoret eller annars inte kan åtgärda arbetsuppgifter för en viss tidsperiod, kan du automatiskt delegera nya arbetsuppgifter till andra användare på sidan **Användaralternativ**.

### <a name="set-up-automatic-delegation"></a>Ställa in automatisk delegering
1. Gå till **Allmänt > Inställningar > Användaralternativ**.
2. Klicka på **Arbetsflöde**. Kontrollera att avsnittet Delegering är expanderat. Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras. Följ dessa steg för att skapa en ny delegeringsregel.  
3. Klicka på **Lägg till**.
4. Markera ett alternativ i fältet **Omfattning**:
    - Alla – Delegera alla arbetsuppgifter som har tilldelats dig.
    - Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp. Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet **Namn**.
    - Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde. Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet **Namn**.  
5. I fältet **Namn**:
    - För omfattningen **Modul** välj målmodul.
    - För omfattningen **Arbetsflöde** välj målarbetsflöde.
6. Markera den användare som du vill delegera arbetsuppgifterna till i fältet **Delegera**. Använd fälten **Startdatum/-tid** och **Slutdatum/-tid** när du vill att arbetsuppgifterna ska delegeras automatiskt.  
7. Ange datum och tid i fältet **Startdatum/-tid**.
8. Ange datum och tid i fältet **Slutdatum/-tid**.
9. Aktivera delegeringsregeln genom att markera kryssrutan **Aktiverad**. 
10. Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet **Kommentar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]