---
title: Identifiera och lösa konflikter vid ansvarsfördelning
description: Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning.
author: peakerbl
manager: AnnBe
ms.date: 07/08/2019
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
ms.openlocfilehash: b7e25a568b86ce3161e2c52045ff2361c0bc4a0e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681604"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identifiera och lösa konflikter vid ansvarsfördelning

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning. Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare. Detta koncept kallas ansvarsfördelning. När definitionen av en säkerhetsroll eller rolltilldelningarna av en användare bryter mot reglerna loggas konflikten. Alla konflikter måste lösas av administratören. Slutför proceduren nedan för att identifiera och lösa konflikter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera om användarrolltilldelningar följer de nya reglerna för ansvarsfördelning
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Verifiera regelefterlevnad för användarrolltilldelningar**.
2. Välj **OK**. Ett meddelande visar resultaten för valideringen. Om en konflikt uppstår kan du öppna sidan **Användare** och ändra användarens rolltilldelningar. Konflikter loggas även på sidan **Ansvarsfördelningskonflikter**. Om du vill köra verifieringsprocessen som ett batchjobb väljer du **Batchbearbetning** och sedan anger övriga batchparametrar. När batchjobbet har körts kan du granska konflikterna på sidan **Ansvarsfördelningskonflikter**.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visa och lös motstridiga tilldelningar av användarroller
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningskonflikter.** Välj en konflikt och klicka sedan på någon av följande knappar: **Neka tilldelning – neka tilldelningen av användaren i den ytterligare säkerhetsrollen**. Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen. Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet. Tillåt tilldelning – **åsidosätt** konflikten och tillåt användaren tilldelas båda säkerhetsrollerna. Om du åsidosätter en konflikt måste du ange en orsak i fältet **Orsak till åsidosättning**.  
2. Stäng sidan.
3. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Olösta ansvarsfördelningskonflikter**. Välj en konflikt och klicka sedan på någon av följande knappar: **Neka tilldelning – neka tilldelningen av användaren i den ytterligare säkerhetsrollen**. Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen. Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet. Tillåt tilldelning – **åsidosätt** konflikten och tillåt användaren tilldelas båda säkerhetsrollerna. Om du åsidosätter en konflikt måste du ange en orsak i fältet **Orsak till åsidosättning**.    
4. Stäng sidan.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Verifiera om befintliga roller följer de nya reglerna för ansvarsfördelning
1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Säkerhet > Ansvarsfördelning > Ansvarsfördelningsregler**. Välj en regel.  
2. Välj **Validera programbehörigheter och roller**. Om några befintliga roller strider mot den valda regeln visas ett meddelande som innehåller namnet på rollen och namnen på de motstridiga programbehörigheterna. Administratören måste antingen ange hanteringen av säkerhetrisken eller ändra rollen så att den inte bryter mot reglerna för ansvarsfördelning. Om inga roller strider mot den valda regeln visas ett meddelande om att alla roller efterlevs.  

