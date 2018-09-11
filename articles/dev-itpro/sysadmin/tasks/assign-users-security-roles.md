--- 
title: "Tilldela användare till säkerhetsroller"
description: "Om du vill komma åt Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, måste användarna ha tilldelats säkerhetsroller."
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 551048af26f46d334c562d1968963aed262a5e03
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="assign-users-to-security-roles"></a>Tilldela användare till säkerhetsroller

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill komma åt Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, måste användarna ha tilldelats säkerhetsroller. I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="automatically-assign-users-to-roles"></a>Tilldela användare automatiskt till roller
1. Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.
2. Välj "Redovisningsansvarig" i trädet.
    * Välj den roll som du vill använda till att konfigurera regeln. Välj Redovisningsansvarig i det här exemplet.  
3. Klicka på Lägg till regel för att öppna dialogrutan.
4. Hitta och markera önskad post i listan.
    * Välj frågan som ska användas till den här regeln.  
5. Klicka på länken på den valda raden i listan.
6. Klicka på Redigera fråga.
    * Redigera frågan, om det behövs.  
7. Klicka på OK.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exkludera användare från automatisk rolltilldelning
1. Stäng sidan.
2. Gå till systemadministrationen > Säkerhet > Tilldela användare till roller.
3. Välj "Redovisningsansvarig" i trädet.
    * Välj en roll. Välj Redovisningsansvarig för det här exemplet.  
4. Klicka på Tilldela/exkludera användare manuellt.
5. Markera vald rad i listan.
    * Välj en användare.  
6. Klicka på Exkludera från roll.
    * Klicka på Exkludera från roll om du vill exkludera den valda användaren från rollen. Markera de användare som du vill ta bort exkluderingar för och klicka sedan på Återställ status om du vill ta bort exkluderingar. När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt. Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen. Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.  


