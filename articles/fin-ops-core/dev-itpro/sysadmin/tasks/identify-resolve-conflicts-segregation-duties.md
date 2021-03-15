---
title: Identifiera och lösa konflikter vid ansvarsfördelning
description: Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deff97c7728db91089d3ea834d15de738da500fa
ms.sourcegitcommit: 316200579dd5b04ad76f276a2ed6b0f55fa8c812
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "4826378"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identifiera och lösa konflikter vid ansvarsfördelning

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning. Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare. Detta koncept kallas ansvarsfördelning. När definitionen av en säkerhetsroll eller rolltilldelningarna av en användare bryter mot reglerna loggas konflikten. Alla konflikter måste lösas av administratören. Slutför proceduren nedan för att identifiera och lösa konflikter.

När en regel har lagts till kontrollerar du att alla befintliga roller är kompatibla. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera om befintliga roller och uppgifter följer de nya reglerna för ansvarsfördelning
1. Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Ansvarsfördelningsregler**.
3. Välj **Validera programbehörigheter och roller**. Om några roller strider mot reglerna visas ett meddelande som innehåller namnet på rollen, rollen och namnen på de motstridiga uppgifterna. Konfliktroller måste ändras med hjälp av **Säkerhetskonfiguration** och kan inte inkludera motstridiga uppgifter. Om inga roller strider mot den valda regeln visas ett meddelande om att alla roller efterlevs.   

> [!NOTE]
> Verifieringen utförs endast för den valda regeln. Det är viktigt att validera efterlevnad för varje regel.   

När du skapar eller ändrar en roll, verkställs automatiskt reglerna för ansvarsfördelning. Du kan inte tilldela en roll motstridiga uppgifter.

Kontrollera sedan att alla befintliga rolltilldelningar är kompatibla.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera att användarrolltilldelningar följer de nya reglerna för ansvarsfördelning
1. Gå till **Systemadministration > Säkerhet > Ansvarsfördelning > Verifiera regelefterlevnad för användarrolltilldelningar**.
2. Välj **OK**. Ett meddelande visar resultaten för valideringen. Konflikter loggas på sidan **Olösta ansvarsfördelningskonflikter**.   

När du skapar eller tilldelar användare till en roll, verkställs automatiskt reglerna för ansvarsfördelning. Om du försöker tilldela en användare till roller som innehåller motstridiga uppgifter visas ett felmeddelande. Du måste sedan lösa konflikten genom att neka eller tillåta den ytterligare rolltilldelningen. Den ytterligare rollen kommer att tilldelas efter tilldelningen är tillåten. 

> [!NOTE]
> Konflikter verifieras för närvarande inte för användare som är tilldelade roller baserat på Active Directory Domain-grupperna.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visa och lös motstridiga tilldelningar av användarroller
1. Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Olösta ansvarsfördelningskonflikter**. 
2. Markera en konflikt och klicka sedan på någon av följande åtgärder: 

  - **Neka tilldelning**: Detta nekar tilldelningen av användaren i den ytterligare säkerhetsrollen. Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen. Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet. 
-  **Tillåt tilldelning**: Detta åsidosätter konflikten och tillåt användaren tilldelas den ytterligare säkerhetsrollen. Om du åsidosätter en konflikt måste du ange en orsak i fältet **Orsak till åsidosättning**. Alla åsidosatta rolltilldelningar kan visas på sidan **Ansvarsfördelningskonflikter**.  

> [!NOTE]
> Om flera konflikter finns med för samma användare väljer du användarposten och utvärderar tilldelade roller på sidan **Användare**. Undvik den här konflikten genom att validera varje regel när den har lagts till eller ändrats.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]