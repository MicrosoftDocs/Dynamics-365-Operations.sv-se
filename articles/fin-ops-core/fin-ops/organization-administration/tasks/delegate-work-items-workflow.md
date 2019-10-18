---
title: Delegera arbetsuppgifter i ett arbetsflöde
description: Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44dc747543e32b54729d12c89a401b0187e25a61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189969"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegera arbetsuppgifter i ett arbetsflöde

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a>Manuellt delegera en arbetsuppgift

Om du vill delegera en enskild arbetsuppgift, välj alternativet **Delegera** i menyn **Arbetsflöde** och ange sedan användaren som ska delegeras till tillsammans med en kommentar. Detta tilldelar om arbetsuppgift till användaren så att de kan slutföra den.

## <a name="automatically-delegate-work-items"></a>Delegera arbetsuppgiften automatiskt

Om du tänker vara borta från kontoret eller annars inte kan åtgärda arbetsuppgifter för en viss tidsperiod, kan du automatiskt delegera nya arbetsuppgifter till andra användare på sidan **Användaralternativ**.

### <a name="set-up-automatic-delegation"></a>Ställa in automatisk delegering
1. Gå till **Allmänt > Inställningar > Användaralternativ**.
2. Klicka på **Arbetsflöde**. Kontrollera att avsnittet Delegering är expanderat. Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras. Följ dessa steg för att skapa en ny delegeringsregel.  
3. Klicka på **Lägg till**.
4. Markera ett alternativ i fältet **Omfattning**.
    - Alla – Delegera alla arbetsuppgifter som har tilldelats dig.
    - Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp. Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet Namn.
    - Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde. Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet Namn.  
5. Markera den användare som du vill delegera arbetsuppgifterna till i fältet **Delegera**. Använd fälten Startdatum/-tid och Slutdatum/-tid när du vill att arbetsuppgifterna ska delegeras automatiskt.  
6. Ange datum och tid i fältet **Startdatum/-tid**.
7. Ange datum och tid i fältet **Slutdatum/-tid**.
8. Aktivera delegeringsregeln genom att markera kryssrutan **Aktiverad**. Om du har valt **Modul** som Omfattning måste du välja modulen i fältet Namn. Om du har valt **Arbetsflöde** som Omfattning måste du välja specifikt arbetsflöde att delegera i fältet Namn.  
9. Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet **Kommentar**.

