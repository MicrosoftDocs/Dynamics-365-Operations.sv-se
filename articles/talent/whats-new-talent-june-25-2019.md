---
title: Nyheter och ändringar i Dynamics 365 for Talent (25 juni 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-25
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e32768c898e2934b95eb8ab7b212337aff0c1556
ms.sourcegitcommit: fbe6d35ed35aa01f438990e2880c3a3cf223ea8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/27/2019
ms.locfileid: "1704479"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-25-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (25 juni 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Kommer snart i Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Jobbgodkännanden visas på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, jobbtitel, andra godkännare och datum när jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2357.

### <a name="incorrect-value-displayed-for-primary-position-314266"></a>Felaktigt värde som visas för den primära positionen (314266)

Dessa ändringar kommer att visa inställningen för den **primära positionen** konsekvent på alla sidor.

### <a name="cant-edit-after-recalling-the-workflow-in-review-318180"></a>Det går inte att redigera efter att ha återkallat arbetsflödet i Granska (318180)

Granskningar som har återkallats via arbetsflödet kan nu redigeras.

### <a name="final-comments-field-in-reviews-isnt-translated-325921"></a>Fältet slutgiltiga kommentarer i Granskar är inte översatt (325921)

Etiketten **slutliga kommentarer** kommer att översättas i Talent.

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Funktionerna för förhandsgranskning aktiveras bara i begränsade miljöer

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanstypen **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

## <a name="in-preview"></a>I förhandsgranskning

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal (HR) i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

## <a name="coming-soon-in-core-hr"></a>Kommer snart i Core HR

### <a name="feature-management-area-in-talent"></a>Funktionshanteringsområde i Talent

**Funktionshantering** tas bort från **systemadministrationen** på grund av problem med funktionen. Vi kommer att införa **funktionshantering** igen i en framtida version. 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

Följande entiteter stöder anpassade fält: **Inkomstkoder för lön**, **Fast kompensationshändelse**, **Kompensationsrutnät**, **Betalningsperiod** och **kompensationsreferenspunkter**. 

### <a name="new-common-data-service-entities"></a>Nya Common Data Service-entiteter

Entiteten **orsakskoder** läggs till i Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Visa prestandainformation för direkta och utökade rapporter i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda.

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Medarbetare, chefer och personal kan skriva ut en medarbetares resultatöversyn.
