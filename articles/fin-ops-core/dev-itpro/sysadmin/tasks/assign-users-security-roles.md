---
title: Tilldela användare till säkerhetsroller
description: För att öppna Finance and Operations-appar måste användaren tilldelas säkerhetsroller.
author: Peakerbl
manager: AnnBe
ms.date: 05/06/2020
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
ms.openlocfilehash: f0421ad6c932f2c91de51169bda6c98f53d3bc65
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346455"
---
# <a name="assign-users-to-security-roles"></a>Tilldela användare till säkerhetsroller

[!include [banner](../../includes/banner.md)]

För att kunna använda något annat än vanliga funktioner i Finance and Operations måste användarna tilldelas säkerhetsroller. Du kan tilldela användare roller automatiskt, baserat på regler och affärsdata, utesluta användare från den automatiska rolltilldelningen eller lägga till användare i roller manuellt.

## <a name="automatically-assign-users-to-roles"></a>Tilldela användare automatiskt till roller
I den här proceduren förklaras hur systemadministratörer kan tilldela användarna roller automatiskt, baserat på affärsdata. 
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
2. Välj "Redovisningsansvarig" i trädet. Välj den roll som du vill använda till att konfigurera regeln. Välj Redovisningsansvarig i det här exemplet. 
3. Välj **Lägg till regel** för att öppna dialogmenyn.
4. Sök efter och markera önskad post i listan **Välj en fråga**. Välj frågan som ska användas till den här regeln.  
5. Klicka på länken på den valda raden i listan **Namn på medlemskapsregel**.
6. Välj **Redigera fråga**. Redigera frågan, om det behövs.  
7. Välj **OK**.
8. Välj **Kör automatisk rolltilldelning**.
9. Gå till **Navigeringsfönstret > Moduler > Systemadministration > Användare > Användare** (helst på en separat flik i webbläsaren).
10. Granska roller tilldelade olika användare för att bekräfta att rolltilldelningsfrågan var korrekt. Justera och kör om om det behövs.

## <a name="exclude-users-from-automatic-role-assignment"></a>Exkludera användare från automatisk rolltilldelning
1. Stäng sidan.
2. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
3. Välj "Redovisningsansvarig" i trädet. Välj en roll. Välj Redovisningsansvarig för det här exemplet.  
4. I menyn **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.
5. Markera den markerade raden på listan **Tilldela användare till eller exkludera användare från roll**. Välj en användare.  
6. På **Åtgärdsfönstret**, välj **Exkludera från roll**.
7. Välj **Exkludera från roll** om du vill exkludera den valda användaren från rollen. Markera de användare som du vill ta bort exkluderingar för och klicka sedan på **Återställ status** om du vill ta bort exkluderingar. När du tar bort en exkludering genom att återställa användarens status, kommer användarens roll att tilldelas automatiskt. Men användaren tilldelas inte omedelbart rollen eller exkluderas från rollen när du återställer statusen. Istället tilldelas användaren antingen rollen eller tas bort från rollen nästa gång som reglerna för automatisk rolltilldelning körs.  

## <a name="manually-assign-users-to-roles"></a>Tilldela användare till roller manuellt
Användare som tilldelas säkerhetsroller manuellt måste också tas bort manuellt av administratören. Dessa användare tas inte bort från roller enligt regler för automatisk rolltilldelning.

1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
2. I trädet väljer du roll och i menyn **Användare tilldelade till rollen**, väljer du **Tilldela/exkludera användare manuellt**.
4. I **Tilldela användare till eller exkludera användare från rollen** visas användare som inte har tilldelats roll med **Tilldelningsläge** med inställningen **Ingen**. Välj en eller flera användare som ska tilldelas rollen.
5. I **Åtgärdsfönstret**, välj **Tilldela till roll**. **Tilldelningsläget** uppdateras till **Manuellt** och användarna har nu fått en ny roll tilldelad.
