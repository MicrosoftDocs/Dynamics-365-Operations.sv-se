---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (augusti 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
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
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: db7c91ea6599bde7d4c589a021d2d3b262e57ec9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010462"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-august-2018"></a>Nyheter och ändringar i Dynamics 365 Talent: Core HR (augusti 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.104**

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent: Core HR.

## <a name="view-expiring-records-in-manager-self-service"></a>Visa utgående poster i självbetjäning för chef

Du kan nu visa utgående poster i självbetjäning för chef. Nya alternativ låter dig konfigurera vilken information som ska vara tillgängliga för chefer att visa. Dessa omfattar:

-   Intyg

-   Identifieringsnummer

-   Provanställningsperioder

-   Kontroller

-   Tester

Den här funktionen ger även möjlighet att ange det antal dagar som ska sökas efter poster som upphör att gälla.

## <a name="configurable-transfer-actions"></a>Konfigurerbara överföringsåtgärder

Du kan konfigurera efter roll de alternativ som är tillgängliga vid registrering av en överföringsbegäran. Denna funktion ger ytterligare flexibilitet mellan roller i organisationen.

T.ex. chefer som begär överföring av medarbetare kanske inte har åtkomst till att föreslå eller ange kompensationsbelopp eller välja uppgiftslistor som kommer att vara associerade till överföringsbegäran. I detta fall kan chefer skapa och skicka överföringsbegäranden men de får inte ange kompensation eller lista aktivitetstilldelningar. I samma konfiguration kommer personalavdelningen att kunna tilldela nya kompensationsvärden och även tilldela eventuella ytterligare checklistor som ska slutföras som ett resultat av att överföringen slutförs.

Som standard ställs nya konfigurationsalternativ in för att inte ändra funktionerna före uppdateringen.

## <a name="leave-and-absence"></a>Tjänstledighet och frånvaro

Det finns nu fler datumfält i Ledighet och frånvaro.

Du kan ange underlag för periodiseringsperiod på plannivå för att använda specifika medarbetardatum. Detta inkluderar andra datum än startdatum för planen som ska användas under periodiseringsprocessen för ledigheten. Alternativen för specifika medarbetardatum omfattar följande värden:

-   Anpassad (tillgänglig innan denna uppdatering)

-   Årsdag

-   Ursprungligt anställningsdatum

-   Datum för tjänsteålder

-   Arbetarens justerade startdatum

-   Arbetarens startdatum

När de är konfigurerade för att använda ett av de medarbetarspecifika datumen kommer registreringsprocessen att använda detta datum för beräkning av periodiseringsperioderna. Periodiseringsperiodens grund visas också på medarbetarens planregistrering för att hjälpa dig att förstå vad som används under periodiseringsprocessen.

## <a name="microsoft-word-integration"></a>Microsoft Word-integrering

Dokumentmallar har aktiverats i Core HR. Den här funktionen låter dig skapa brev och rapporter baserat på Word-mallar som du skapar.

Mer information om den här funktionen finns i [Office integration självstudier](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).


## <a name="other-fixes"></a>Andra korrigeringar

Den här versionen innehåller ett antal olika felkorrigeringar, tillägg av nya entiteter, korrigeringar för befintliga entiteter och lokaliserade etikettändringar.
