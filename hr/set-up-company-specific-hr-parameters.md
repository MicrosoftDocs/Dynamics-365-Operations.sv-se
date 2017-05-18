---
title: "Ställa in företagsspecifika HR parametrar"
description: "Inställningarna för vissa HR-parametrar delas av alla företag, medan inställningarna för andra parametrar är företagsspecifika. Den här artikeln innehåller information om hur du ställer in företagsspecifika HR-parametrar."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b4c362ecb6134158cb9f00d3670232043c7d619d
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="set-up-company-specific-hr-parameters"></a>Ställa in företagsspecifika HR parametrar

[!include[banner](includes/banner.md)]


Inställningarna för vissa HR-parametrar delas av alla företag, medan inställningarna för andra parametrar är företagsspecifika. Den här artikeln innehåller information om hur du ställer in företagsspecifika HR-parametrar.

Två sidor används för att ställa mänskliga resurser (HR) parametrar. För parametrar som delas mellan företag, kan du använda de **mänskliga resurserna delas parametrar sidan** . För parametrar som är företagsspecifika (med andra ord inställningar tillämpas på ett enda företag) kan du använda den **mänskliga resursen parametrar sidan** . På **mänskliga resurser parametrar sidan** , inställningarna är uppdelade i sex flikar:

-   Allmänt
-   Rekrytering
-   Kompensation
-   Nummersekvenser
-   Familj och medicinska lämnar Act (fmla)
-   Anställd self-service

Varje flik innehåller information som hänför sig till ett enda bolag. Inställningar på**fliken Allmänt**definierar utseendet av information om frånvaro, skador och sjukdomar, och nyanställningar. Inställningarna på den här fliken definierar också några poster som visas såsom dig arbete. Denna flik låter dig att utvälja en färg för att öppna frånvaro, ange den formatmall som används för rapporter, möjliggör integrationen mellan kurser och frånvaroregistrering och välj frånvarolöneart som används för att styra denna integration. Du kan också ange hur länge skador och sjukdomar vid incidenter ska hållas, och ange id-nummer som visas när en ny arbetstagare anställs. 

Inställningar på **fliken rekrytering** definierar dokumenttyper som används för korrespondens som automatiskt skickas till sökande och rekrytering projekt som används för oönskade ansökningar (ansökningar som inte är för en viss rekrytering projekt). Den period som definieras för rekrytering projektet åldrande avgör rekrytering projekt som ingår i den **åldrande projekt** panel i **rekryteringen av** arbetsytan. Den period som definieras för deadline varning används för att visa rekrytering projekt som närmar sig deras sista ansökningsdag på **sista ansökningsdag närmar sig** panelen i **rekryteringen** arbetsyta. 

Inställningarna på fliken **Kompensation** anger om användare måste bekräfta att de vill spara information för en fast eller variabel kompensationsplan. Om du markerar kryssrutan **Aktivera spara validering** kommer användarna när de stänger en relaterad kompensationsplanssida att få ett meddelande som frågar om de vill spara posten. Vissa sidor i kompensationshantering låter inte användare ta bort information. Därför, genom att meddela användarna att bekräfta att de vill spara information, du kan begränsa den mängd information som sparas men inte tas bort senare. Om **Aktivera spara validering** är avmarkerad, poster sparas alltid omedelbart, möjligen innan användaren är redo. Om du använder performance management, **fliken ersättningar** kan du också välja ett betyg modell att använda i stället för den modell som är tilldelade till ersättningsplaner när prestanda är klassad. 

Inställningarna på**fliken sekvensen**avgör de sekvenser som används för att automatiskt tilldela ID-nummer för objekt i mänskliga resurser, såsom applikationer, ingen registrering, ersättning process resultat, fallnummer, kurser och kurs dagordningar. För att bibehålla nummersekvensreferenser och koder, använd listsidan **Nummersekvenser** (klicka på **Organisationsadministration** &gt; **Nummersekvenser** &gt; **Nummersekvenser**). 

Inställningar på**fliken FMLA**ange hur många timmar som en anställd måste arbeta för att vara berättigade till fmla förmåner, längden på anställningen som krävs för berättigande och anställningsdatum som används för att bestämma längden på anställningen. Inställningarna även definiera antalet FMLA-timmar som de anställda har rätt till och FMLA lämnar kalendern som används för att beräkna hur många FMLA timmar anställda har använt. Det **FMLA-** fliken är endast tillgänglig för företag i Förenta staterna. 

**Obs!** Det antal timmar som arbetas inte överstiga 1250 och längden på anställningen får inte överskrida 12 månader. Dessa största värden i enlighet med federal lag i USA. Slutligen inställningarna på den **anställde självbetjäning** fliken bestämmer vilken information som en chef kan ange på uppdrag av hans eller hennes anställda.

<a name="see-also"></a>Se även
--------

[Ställa in HR parametrar över juridiska personer](set-up-hr-parameters-across-legal-entities.md)




