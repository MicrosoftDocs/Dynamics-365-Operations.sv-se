---
title: Nyheter och ändringar i Dynamics 365 Talent (31 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690062"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (31 januari 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

**Skapa 8.1.2128**

## <a name="core-hr-changes"></a>Ändringar i Core HR

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>Tjänstledighet på personkortet beaktar inte datumen i tjänstledighetsplanen
För tjänstledighetsplaner som inte fungerar på ett kalenderår, visas nu kortet **Tagen** ledig tid som sker under plandefinierade tjänstledighetsåret. Om en organisations tjänstledighetsår är 1 juni till och med den 30 maj och en medarbetare har tagit tre dagar ledigt i december kommer kortet **Tagen** den 15 januari, visa tre dagar. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>Upplupna belopp matchar inte nivådatumbasen
Nya alternativ har lagts till ledighet och frånvaro (**personal** parametrar) för att låta kunder bestämma när anställdas månader av tjänstdatum är effektiva. För vissa organisationer är datumet slutet på månaden, men för andra kan det vara början på nästa månad. Till exempel en organisation får tilldela tjänstledigt 31 december, medan en annan får tilldela tjänstledigt 1 januari. Det här alternativet låter dig välja när tilldelningen ska ske. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>Arbetarens anställningåtgärder ligger kvar i tillståndet ”Arbetsflöde slutfört”
Ändringar har gjorts som korrigerar ett problem där ett litet antal arbetsflöden slutförs med status ”arbetsflöde slutfört”. Nya arbetsflöden ska gå till läget ”slutfört” när arbetsflödet har slutförts. Alla arbetsflöden i en slutförd arbetsflödesstatus kommer övergå till felstatus för att uppdatera eller ta bort om det behövs. 
