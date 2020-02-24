---
title: Nyheter och ändringar i Dynamics 365 Talent (23 juli 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8d89b1251429281521f32338f642cc7034420e0b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3005996"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (23 juli 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="pdf-renderer-for-candidate-documents"></a>PDF-renderare för kandidatdokument

Attract-användare kan nu visa bifogade PDF-filer för kandidater i dokumentvisningsprogrammet i stället för att hämta dem.

### <a name="signing-up-for-attract-user-research-group"></a>Registrera dig för Attract användarreferensgrupp 

När vi planerar nya produktfunktioner eller levererar funktioner för förhandsgranskning söker vi efter att våra användare hjälper oss att informera vår riktning. Intresserade användare kan nu anmäla sig till en del av vår användarreferensgrupp genom att använda registreringslänken i vår app.

### <a name="job-approvals-appear-on-the-home-page"></a>Jobbgodkännanden visas på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, jobbtitel, andra godkännare och datum när jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Entitetsstöd för anpassade fält i Common Data Service 

Med den här utgåvan stöder **arbetskalendern** och **arbetskalenderdag** nu anpassade fält i Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanser **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visa utökad information för prestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner som deras anställda hanterar gemensamt. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda. 

## <a name="coming-soon"></a>Kommer snart

### <a name="region-support-for-canada-and-southeast-asia"></a>Regionsstöd för Kanada och Sydostasien

Vi är glada att kunna tillkännage att regionerna Kanada och Sydostasien kommer att vara tillgängliga för Talent den 1 augusti 2019. Med den här ändringen kan du skapa miljöer i de kanadensiska och asiatiska regionerna, och all Talent-data kommer att enbart behållas inom dessa platser. Du kan skapa en miljö i dessa nya regioner genom att markera platsen i dialogrutan Ny miljö och använda den miljön för att konfigurera Talent i LCS enligt beskrivningen i [Konfigurera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Datamigrering av befintliga projekt från andra områden till kanadensiska och asiatiska regioner stöds inte. Endast nya projekt kan etableras för de nya regioner som stöds.
