--- 
title: "Identifiera och lösa konflikter vid ansvarsfördelning"
description: "Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: fdc0bbd0a239c8d7719271445a4d6a5323e87aad
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identifiera och lösa konflikter vid ansvarsfördelning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare. Detta koncept kallas ansvarsfördelning. När definitionen av en säkerhetsroll eller rolltilldelningarna av en användare bryter mot reglerna loggas konflikten. Alla konflikter måste lösas av administratören. Slutför proceduren nedan för att identifiera och lösa konflikter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera om användarrolltilldelningar följer de nya reglerna för ansvarsfördelning
1. Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Verifiera regelefterlevnad för användarrolltilldelningar.
2. Klicka på OK.
    * Ett meddelande visar resultaten för valideringen.     Om en konflikt uppstår kan du öppna användarsidan och ändra användarens rolltilldelningar. Konflikter loggas även på sidan Ansvarsfördelningskonflikter.     Om du vill köra verifieringsprocessen som ett batchjobb väljer du Batchbearbetning och sedan anger övriga batchparametrar. När batchjobbet har körts kan du granska konflikterna på sidan Ansvarsfördelningskonflikter.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visa och lös motstridiga tilldelningar av användarroller
1. Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningskonflikter.
    * Välj en konflikt och klicka sedan på någon av följande knappar:   Neka tilldelning – neka tilldelningen av användaren i den ytterligare säkerhetsrollen. Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen. Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet.     Tillåt tilldelning – åsidosätt konflikten och tillåt användaren tilldelas båda säkerhetsrollerna. Om du åsidosätter en konflikt måste du ange en orsak i fältet Orsak till åsidosättning.  
2. Stäng sidan.
3. Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Olösta ansvarsfördelningskonflikter.
    * Välj en konflikt och klicka sedan på någon av följande knappar:   Neka tilldelning – neka tilldelningen av användaren i den ytterligare säkerhetsrollen. Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen. Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet.     Tillåt tilldelning – åsidosätt konflikten och tillåt användaren tilldelas båda säkerhetsrollerna. Om du åsidosätter en konflikt måste du ange en orsak i fältet Orsak till åsidosättning.    
4. Stäng sidan.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera om befintliga roller följer de nya reglerna för ansvarsfördelning
1. Gå till Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler.
    * Välj en regel.  
2. Klicka på Validera programbehörigheter och roller.
    * Om några befintliga roller strider mot den valda regeln visas ett meddelande som innehåller namnet på rollen och namnen på de motstridiga programbehörigheterna. Administratören måste antingen ange hanteringen av säkerhetrisken eller ändra rollen så att den inte bryter mot reglerna för ansvarsfördelning.     Om inga roller strider mot den valda regeln visas ett meddelande om att alla roller efterlevs.  


