---
title: Tilldela användare säkerhetsroller
description: För att komma åt appar för ekonomi och drift måste användarna ha tilldelats säkerhetsroller.
author: Peakerbl
ms.date: 02/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103881"
---
# <a name="manage-users-and-security-roles"></a>Hantera användare och säkerhetsroller

[!include [banner](../../includes/banner.md)]

För att kunna använda något annat än vanliga funktioner i appar för ekonomi och drift måste användarna tilldelas säkerhetsroller. Du kan tilldela användare roller automatiskt, baserat på regler och affärsdata, utesluta användare från den automatiska rolltilldelningen eller lägga till användare i roller manuellt.

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
I den här proceduren förklaras hur du exkluderar användare från automatiska rolltilldelningar.

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

## <a name="manually-remove-users-from-roles"></a>Ta bort användare manuellt från roller
Användare som tilldelas säkerhetsroller manuellt måste också tas bort manuellt av administratören. Dessa användare tas inte bort från roller enligt regler för automatisk rolltilldelning.

1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Tilldela användare till roller**.
2. Så här tar du bort en användare:
   1. Välj en roll i trädet. 
   2. I området **Användare som tilldelats roll**, välj den användare som ska tas bort.
   3. Välj **Ta bort** och användaren tas bort från rollen.
3. Så här tar du bort flera användare:
   1. Välj en roll i trädet. 
   2. I området **Användare som är tilldelade till rollen**, välj **Tilldela/exkludera användare manuellt**.
   3. På sidan **Tilldela användare till eller exkludera användare från rollen** har användare inte tilldelats roll **Ingen** i kolumnen **Tilldelningsläge**. Välj de användare som ska uteslutas från rollen.
   4. På **Åtgärdsfönstret**, välj **Exkludera från roll**. Kolumnen **Tilldelningsläget** uppdateras nu till **Manuellt** och användarna exkluderas från rollen.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

