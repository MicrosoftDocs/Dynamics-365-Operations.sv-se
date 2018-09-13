--- 
title: "Delegera arbetsuppgifter i ett arbetsflöde"
description: "Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare."
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a>Delegera arbetsuppgifter i ett arbetsflöde

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du kommer att vara borta från kontoret under en tid eller av annat skäl inte kommer att kunna arbeta med en arbetsuppgift, kan du delegera eller omfördela dina arbetsuppgifter till andra användare. Med den här proceduren kan du konfigurera systemet att automatiskt delegera dina arbetsuppgifter till en annan användare.



Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="set-up-automatic-delegation"></a>Ställa in automatisk delegering
1. Gå till Allmänt > Inställningar > Användaralternativ.
2. Klicka på fliken Arbetsflöde.
    * Kontrollera att avsnittet för Delegering expanderas.    Om du vill konfigurera systemet för att automatiskt delegera dina arbetsuppgifter till andra användare, måste du skapa delegeringsregler som anger när vissa typer av arbetsuppgifter delegeras. Följ dessa steg för att skapa en ny delegeringsregel.  
3. Klicka på Lägg till.
4. Markera ett alternativ i fältet Omfattning.
    * Alla – Delegera alla arbetsuppgifter som har tilldelats dig.    Modul – Delegera enbart de arbetsuppgifter som är relaterade till en specifik arbetsflödestyp. Om du väljer det här alternativet måste du välja typ av arbetsflöde i fältet Namn.    Arbetsflöde – Delegera enbart de arbetsuppgifter som är relaterade till en specifik typ av arbetsflöde. Om du väljer det här alternativet måste du välja typen av arbetsflöde i fältet Namn.  
5. Markera den användare som du vill delegera arbetsuppgifterna till i fältet Delegera.
    * Använd fälten Startdatum/-tid och Slutdatum/-tid när du vill att arbetsuppgifterna ska delegeras automatiskt.  
6. Ange datum och tid i fältet Startdatum/-tid.
7. Ange datum och tid i fältet Slutdatum/-tid.
8. Aktivera delegeringsregeln genom att markera kryssrutan Aktiverad.
    * Om du har valt Modul som Omfattning måste du välja modulen i fältet Namn.    Om du har valt Arbetsflöde som Omfattning måste du välja specifikt arbetsflöde att delegera i fältet Namn.  
9. Ange en kommentar som förklarar varför du delegerar arbetsuppgifterna i fältet Kommentar.


