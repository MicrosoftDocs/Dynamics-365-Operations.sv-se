---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (1 oktober 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
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
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306239"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (1 oktober 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.1035.0**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Stäng av validering av elektroniska betalningar

Validering av elektronisk betalningsinformation sker om du ställer in utbetalningar för direktinsättning antingen genom arbetsytan **Självbetjäning för medarbetare** (ESS) eller direkt i medarbetarformuläret. Detta alternativ ger dig flexibilitet att ta bort denna verifiering om du inte behöver valideringskontroller för belopp och resterande värden. Den här funktionen är användbar om du integrerar med ett externt lönesystem som har olika krav.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Självbetjäning för chef - lägga till mål för teammedlemmar via panelen Teamprestationsmål

Innan den här versionen kan chefer lägga till mål till deras anställda individuellt genom prestationsmål som är kopplade till varje medarbetare. Med denna uppdatering kan chefer komma åt panelen **Teamprestationsmål** och skapa nya mål genom att välja någon av deras direktrapporter.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Självbetjäning för chef - lägga till granskningar för teammedlemmar via panelen Teamprestationsgranskningar

Innan den här versionen kan chefer lägga till granskningar till deras anställda individuellt genom granskningar som är kopplade till varje medarbetare. Med denna uppdatering kan chefer komma åt panelen **Teamprestationsgranskningar** och skapa nya granskningar genom att välja någon av deras direktrapporter.

## <a name="configure-proration-options-by-leave-plan"></a>Konfigurera alternativ för proportionell fördelning genom tjänstledighetsplan

Organisationer tilldela ledig tid olika beroende på om medarbetarna börjar eller slutar på företaget. För vissa organisationer får anställda fullständig fördelningen på startdatum medan andra får en proportionell fördelning. Nya alternativ ges i denna version för att välja hur den proportionell fördelningen och trädkopplingar och förtid uppgår i organisationen. Alternativen är: proportionellt fördelade, fullständig periodisering och ingen periodisering.

## <a name="other-changes"></a>Andra ändringar

-   Medarbetare uppdaterad - Titeln **personlig** kan nu uppdatera Excel tillägget/datahantering.

-   Säkerhetsändringar för borttagning av knapparna **bort** och **inaktivera** i medarbetarens självbetjäning för betalningsinformation.

## <a name="known-issue"></a>Kända problem

-   **Problem:** när du lägger till en ny bilaga till en arbetare är knapparna **Ny** och **Redigera** nedtonade. **Lösning:** innan du öppnar bilagesidan, se till att faktarutorna på sidan **arbetare** är stängda. Om faktarutorna är stängda när sidan **arbetare** hämtas **Bilagor** kommer att aktiveras. (Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)
