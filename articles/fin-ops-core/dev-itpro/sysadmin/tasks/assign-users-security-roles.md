---
title: Tilldela användare till säkerhetsroller
description: För att öppna Finance and Operations-appar måste användaren tilldelas säkerhetsroller.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143575"
---
# <a name="assign-users-to-security-roles"></a>Tilldela användare till säkerhetsroller

[!include [banner](../../includes/banner.md)]

För att kunna använda något annat än vanliga funktioner måste användarna tilldelas till säkerhetsroller. I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata. 

## <a name="automatically-assign-users-to-roles"></a>Tilldela användare automatiskt till roller
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
2. Välj "Redovisningsansvarig" i trädet. Välj den roll som du vill använda till att konfigurera regeln. Välj Redovisningsansvarig i det här exemplet. 
3. Klicka på **Lägg till regel** för att öppna dialogrutan.
4. Sök efter och markera önskad post från listan **Välj en frågan**. Välj frågan som ska användas till den här regeln.  
5. Klicka på länken på den valda raden i listan **Namn på medlemskapsregel**.
6. Klicka på **Redigera fråga**. Redigera frågan, om det behövs.  
7. Klicka på **OK**.
8. Klicka på **Kör automatisk rolltilldelning**.
9. Gå till **Navigeringsfönstret > Moduler > Systemadministration > Användare > Användare** (helst på en separat flik i webbläsaren).
10. Granska roller tilldelade olika användare för att bekräfta att rolltilldelningsfrågan var korrekt. Justera och kör om om det behövs.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exkludera användare från automatisk rolltilldelning
1. Stäng sidan.
2. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
3. Välj "Redovisningsansvarig" i trädet. Välj en roll. Välj Redovisningsansvarig för det här exemplet.  
4. I menyn **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.
5. Markera den markerade raden på listan **Tilldela användare till eller exkludera användare från roll**. Välj en användare.  
6. På **Åtgärdsfönstret**, välj **Exkludera från roll**.
    
    Klicka på **Exkludera från roll** om du vill exkludera den valda användaren från rollen. Markera de användare som du vill ta bort exkluderingar för och klicka sedan på **Återställ status** om du vill ta bort exkluderingar. När du raderar en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas igen automatiskt. Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen. Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.  
