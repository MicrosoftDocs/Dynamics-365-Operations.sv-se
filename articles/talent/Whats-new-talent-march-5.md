---
title: Nyheter och ändringar i Dynamics 365 for Talent (5 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e4ad32ef71c87f52e59959d80c21ae7fcd6d6524
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519157"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (5 mars 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="extending-option-sets-in-attract"></a>Utökade alternativuppsättningar i Attract

I Attract finns flera fält som består av alternativuppsättningar i Common Data Service. Nya funktioner har införts för att utöka alternativuppsättningar, från och med orsaksfältet **Avvisning**, fältet **Anställningstyp** och fältet **tjänsteåldertyp**.

> [!IMPORTANT]
> Jobbpublicering till LinkedIn-funktionen kräver användning av fälten **Anställningstyp** och **Tjänsteåldertyp** på sidan **Projektdetaljer**. Standardvärden i dessa fält stöds av LinkedIn och visas när jobbet har publicerats. Om du publicerar jobb på LinkedIn och du ändrar befintliga alternativuppsättningsvärden i fälten, kommer jobbet fortfarande publiceras och LinkedIn visar inte de anpassade värdena för **Anställningstyp** och **Tjänsteåldertyp**.

## <a name="changes-in-onboarding"></a>Ändringar i Onboard

### <a name="private-preview-for-onboard-teams"></a>Privat förhandsgranskning för Onboard-team
Nu kan du enkelt dela och samarbeta på mallar i hela organisationen. Mer information finns i [dela regelverk inom företaget med Onboard-teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Privat förhandsgranskning för tilldelade platshållare
Du kan utöka dina mallar genom att tilldela aktiviteter till roller i stället för individer. Roller tilldelas sedan individer när guiden skapas. Mer information finns i [Förenkla guideadministration genom att tilldela aktiviteter till roller](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
**Skapa 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Konfigurera arbetsflödet till att automatiskt godkänna eller följa arbetsflöde när en personal- eller linjechef skickar eller uppdaterar begäran om ledighet
Nya arbetsflödesvillkor har lagts till för att tillåta att begäran om ledighet godkänns automatiskt om den lämnas in av en anställds chef eller av HR. Ett sätt att åstadkomma detta automatiska godkännande i ett arbetsflöde är att aktivera en automatisk åtgärd för arbetsflödesgodkännande.

Villkoret som har lagts till inkluderar:

- Inskickad av - används för att utvärdera systemanvändar-ID för den användare som skickade förfrågan till arbetsflödet.
- Skickad på uppdrag av - används för att utvärdera om ledighetsbegäran skickades på uppdrag av arbetaren som är kopplat till begäran.
- Skickad av personal - används för att utvärdera om systemanvändaren som skickade begäran till arbetsflödet är i en personalroll.
- Skickad av chef – används för att utvärdera om användaren som skickade begäran om ledighet till arbetsflödet är en radhierarkichef för arbetaren som är kopplad till begäran.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Aktivera medarbetarens fasta kompensation för framtida befattningstilldelningar
Detta gäller för medarbetare som ansluter sig till en organisation med startdatum i framtiden. Denna ändring tillåter definition av fast kompensation för anställda med framtida befattningstilldelningar.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>Fälten för löneposition är tomma när du redigerar befattningen
Med denna ändring, när du begär ändringar i befintliga befattningar, kommer lönefälten nu anges till de aktuella värdena.

### <a name="other-miscellaneous-bug-fixes"></a>Diverse andra felkorrigeringar
Den här versionen innehåller andra mindre felkorrigeringar.

### <a name="upgrade-to-common-data-service"></a>Uppgradera till Common Data Service
Tidsgränser för uppgradering till Common Data Service för appar närmar sig snabbt. Logga in på PowerApps administrationscenter för att avgöra om databasen måste uppgraderas. Mer information om deadlines och nödvändiga instruktioner för uppgradering finns i [uppgradera till Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Kommer snart

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)
I många organisationer kan kompensations- och förmånsansvariga bara komma åt vissa kompensationsposter, t.ex. poster för chefer eller regionsbaserade anställda. Med den här ändringen kan du hantera och underhålla kompensationsplaner för olika medarbetare i organisationen. Fasta och variabla planer kan tilldelas säkerhetsroller som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter. Endast roller med viss åtkomst ska kunna bearbeta kompensation för dessa anställda.

###  <a name="platform-update-24"></a>Plattform update 24
Ytterligare information om plattformsuppdatering 24 finns i [Nyheter eller ändringar i Finance and Operations plattformsuppdatering 24 (mars 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
