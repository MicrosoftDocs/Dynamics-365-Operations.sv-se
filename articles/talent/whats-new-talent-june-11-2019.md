---
title: Nyheter och ändringar i Dynamics 365 for Talent (11 juni 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.author: dkrame
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a1413ea43e852c78ede227b69c0f49c07944a872
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741636"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-11-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (11 juni 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="search-engine-optimization-for-job-posts"></a>Sökmotoroptimering för jobbpubliceringar

När du har aktiverat **sökmotoroptimering** i Dynamics 365 for Talent: administrationscentret för Attract, Attract informerar din Google-indexeringens API för att crawla webbsidan när du aktiverar och publicerar ett nytt jobb eller uppdaterar ett befintligt jobb. På så sätt kommer jobbet att visas i säkresultaten för Google och andra sökmotorer.

På samma sätt informerar Attract indexerings-API varje gång du tar bort publiceringen av ett jobb så att det ej bokförda jobbet slutar att visas i sökresultaten.

> [!NOTE]
> Webbrobotar har ingen definierad tidsram för att crawla webbsidor eller uppdatera sökresultat.

## <a name="coming-soon-in-attract"></a>Kommer snart i Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Jobbgodkännanden visas på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, jobbtitel, andra godkännare och datum när jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 for Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2337.

### <a name="platform-update-27"></a>Plattform update 27

Ytterligare information om plattformsuppdatering 27 finns i [Förhandsgranskningsfunktioner i Dynamics 365 for Finance and Operations plattformsuppdatering 27 (juni 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>Funktionshanteringsarbetsyta i Talent

Arbetsytan **Funktionshantering** i **Systemadministration** låter dig visa, aktivera, inaktivera och schemalägga funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan **Funktionshantering** för att aktivera dem och visa dokumentationen för dem.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

Den utfärdande myndigheten har nu stöd för anpassade fält.

### <a name="new-common-data-service-entities"></a>Nya Common Data Service-entiteter

Entiteten Uppgiftsgrupp har lagts till.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Funktionerna för förhandsgranskning aktiveras bara i begränsade miljöer

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

När du etablerar en ny instans av Talent kan du ange om instanstypen är produktion eller begränsat läge. Med instanstypen Begränsat läge kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal (HR) i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

## <a name="coming-soon-in-core-hr"></a>Kommer snart i Core HR

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>Visa utökad information om rapportprestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda.

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Medarbetare, chefer och personal kan skriva ut en medarbetares resultatöversyn.
