---
title: Nyheter och ändringar i Dynamics 365 Human Resources (20 augusti 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 20 augusti 2020.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f0e8e450a4c4fd515419c735f9307be80c8df098
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054486"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (20 augusti 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3478. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Visa kommande och väntande ledighetsuppgifter till kort på arbetsytan personer

Väntande och kommande alternativ för tjänstledighet är nu tillgängliga på frånvarokorten på arbetsytan **personer**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>Fältet Privat är normalt inte Ja för medarbetarroll i självbetjäning för medarbetare (477106)

Fältet **privat** är nu som standard **Ja** när medarbetare lägger till nya adressposter via sidan **personlig information** i Självbetjäning för medarbetare. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>Snabbfliken kandidater att anställa i personalhantering visar felaktigt antal kandidater (470110)

Sidan **personalhantering** visar nu antalet kandidater att anställa. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>Det går inte att ange sjukdom för avslutad medarbetare när periodiseringen är inställd på noll (446195)

Tjänstledighetstransaktioner tillåts nu för medarbetare som har avslutats i framtiden och periodiseringen är inställd på noll. Tjänstledighetstransaktioner kan registreras till medarbetarens uppsägningsdatum. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>Lägga till anpassade fält i formuläret nytt arbetsformulär inaktiverar fälten i åtgärdsfönstret för hantera tjänstledighet (473314)

Alternativen för åtgärdsfönster i formuläret **Arbetare** i **Hantera tjänstledighet** kommer inte längre att inaktiveras om anpassade fält har lagts till i det nya formuläret **arbetare**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Om du gör fältet lämna kommentarsfält obligatoriskt kan en begäran om att lämna en begäran skickas när ingen kommentar har angetts (473543)

Kommentarsfält kan nu vara obligatoriska och lämna förfrågningar följer den här inställningen. Obligatoriska fält är en förhandsgranskningsfunktion.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF-enhet tillgänglig för periodiserade avstängningar

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="mandatory-fields"></a>Obligatoriska fält

Du kan göra fält obligatoriska genom att använda anpassningsfunktioner för personal. Den här funktionen kräver **sparade vyer**. Mer information om sparade vyer, se.

- [Sparade vyer-allmän tillgänglighet](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) i Dynamics 365 2020 utgivningsvåg 2-plan
- [Skapa formulär som fullt ut utnyttjar sparade vyer](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns i:

- [Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 1-planen
- [Personal-app i Teams](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>Kommer snart

### <a name="human-resources-app-in-teams-preview-features"></a>Förhandsfunktioner för Personal-app i Teams
 
-  **Meddelanden**: skicka och granskare av tidsförfrågningar kommer att meddelas i modulen Personal-app i Teams. Godkännare kommer att kunna godkänna eller neka förfrågningar om att en begäran har godkänts eller nekats.
 
- **Ledighetskalender för chef**: chefer kommer att kunna se godkänd och väntande ledighet för sina underställda i en kalendervy. Den här vyn gör det enklare att förstå när gruppmedlemmarna är borta från arbetet.

### <a name="checklist-entities-included-in-dataverse"></a>Entiteter för checklista inkluderade i Dataverse

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.

## <a name="known-issues"></a>Kända problem

Arbetsytan **funktionshantering** visas funktioner som har inaktiverats som förhandsgranskningsfunktioner när de är allmänt tillgängliga. Nedan visas en lista med funktioner för allmänt tillgängliga som visar en felaktig status. 

- Hantering av förmåner
- Ärendehantering
- Databasloggning (granskning)
- Ledighetsperiodisering för ett enskilt företag eller en enskild plan
- Uppskjuten periodisering för tjänstledighet och frånvaro
- Orsakskod och kommentar för saldojustering
- Köpa och sälja tjänstledighet
- Kalender för ledighet och frånvaro
- Överföringsregler för tjänstledighet
- Granskning av periodisering av tjänstledighet
- Ta bort periodiserad tjänstledighet
- Runda av periodiserad ledighet
- Konfigurera flera tjänstledighetstyper i en enda tjänstledighetsplan
- Förbättringar av Uppdatera ledig tid
- Använd en medarbetares befattning motsvarande heltid för periodiseringar
- Kompensationsvy för korsföretag
- Skriv ut resultatöversyner
- Korrigeringar för periodisering av ledighet

### <a name="benefit-plan-employee-entity"></a>Entiteten förmånsplan för medarbetare 

Vi har nyligen upptäckt två frågeställningar om **BenefitsPlanEmployee**-entiteten. När du importerar medarbetares registreringar **Omfattningskod** och **Plantypkod** ställs in felaktigt. Det här problemet medför att medarbetar förmånsplaner visas felaktigt i formuläret **förmånsplan för arbetare** och i formuläret **öppen anmälan** i Självbetjäning för medarbetare. Det här problemet kan även påverka medarbetarens förmåga att välja planer i Självbetjäning för medarbetare. Det finns för närvarande ingen lösning. Vi behandlar detta som en hög prioritetskorrigering och tar bort korrigeringen med vår nästa utgåva.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]