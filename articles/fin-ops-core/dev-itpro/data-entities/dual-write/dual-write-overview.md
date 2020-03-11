---
title: Översikt över dubbelriktad skrivning
description: Det här ämnet ger en översikt över dubbelriktad skrivning. Dubbelriktad skrivning är en infrastruktur som ger nära realtids samverkan mellan Microsoft Dynamics 365 modellstyrda appar och Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076004"
---
# <a name="dual-write-overview"></a>Översikt över dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a>Vad är dubbelriktad skrivning?

Dubbelriktad skrivning är en medföljande infrastruktur som ger nära realtidssamverkan mellan Microsoft Dynamics 365 och Finance and Operations-appar. När data om kunder, produkter, personer och verksamhet går utanför programgränser, är alla avdelningar i organisationen berättigade.

Dubbelriktad skrivning ger tätt kombinerad, dubbelriktad integration mellan Finance and Operations-appar och Common Data Service. Alla dataändringar i Finance and Operations-appar orsakar skrivningar till Common Data Service och alla dataändringar i Common Data Service orsakar skrivningar till Finance and Operations-appar. Det här automatiserade dataflödet ger ett integrerat användargränssnitt mellan programmen.

![Datarelation mellan appar](media/dual-write-overview.jpg)

Dubbelriktad skrivning har två aspekter: en *infrastruktur* aspekt och en *applikation* aspekt.

### <a name="infrastructure"></a>Infrastruktur

Infrastrukturen för dubbelriktad skrivning är utökningsbar och tillförlitlig och innehåller följande huvudfunktioner:

+ Synkront och dubbelriktat dataflöde mellan program
+ Synkronisering, tillsammans med lägena spela upp, pausa och sammanfattning för att stödja systemet i online- och offline-/asynkrona lägen.
+ Möjlighet att synkronisera ursprungliga data mellan programmen
+ Konsoliderad vy över aktivitet och felloggar för dataadministratörer
+ Möjlighet att konfigurera anpassade aviseringar och tröskelvärden samt att prenumerera på meddelanden
+ Intuitivt användargränssnitt (UI) för filtrering och transformeringar
+ Möjlighet att ställa in och visa enhetsberoenden och relationer
+ Utökningsbarhet för både standard- och anpassade entiteter och kartor
+ Tillförlitlig program livscykelhantering
+ Installations upplevelse utanför lådan för nya kunder

### <a name="application"></a>Ansökning

Dubbelriktad skrivning skapar en mappning mellan koncept i Finance and Operations-appar och koncept i modellstyrda appar i Dynamics 365. Denna integration stöder följande scenarier:

+ Integrerad kundmaster
+ Tillgång till kundförmånskort och belöningspoäng
+ Enhetlig produkthanteringsupplevelse
+ Medvetenhet över organisationshierarki
+ Integrerat leverantörshuvud
+ Åtkomst till ekonomi- och momsreferensdata
+ Prismotor upplevelse på begäran
+ Integrerad potentiell kund till pengar-upplevelse
+ Möjlighet att betjäna både interna tillgångar och kundtillgångar via fältagenter
+ Integrerat procure-to-pay-upplevelse
+ Integrerade aktiviteter och anteckningar för kunddata och dokument
+ Möjlighet att söka efter tillgänglighet för lagerbehållning och information
+ Projekt till kontanter-upplevelse
+ Möjlighet att hantera flera adresser och roller via partens begrepp
+ En källhantering för användare
+ Integrerade kanaler för återförsäljning och marknadsföring
+ Synlighet för erbjudanden och rabatter
+ Funktioner för service för begäran
+ Förenklade tjänsteåtgärder

## <a name="top-reasons-to-use-dual-write"></a>Främsta anledningar att använda dubbelriktad skrivning

Dubbelriktad skrivning ger dataintegrering i Microsoft Dynamics 365-program. Detta robusta ramverk länkar sig till miljöer och gör att olika affärsprogram kan fungera tillsammans. Här följer de viktigaste skälen till varför du bör använda dubbelriktad skrivning:

+ Dubbelriktad skrivning ger tätt sammankopplade, nära realtid och dubbelriktad integration mellan Finance and Operations-appar och modellstyrda appar i Dynamics 365. Den här integrationen gör Microsoft Dynamics 365 en enda kontaktpunkt för alla dina affärslösningar. Kunder som använder Dynamics 365 Finance och Dynamics 365 Supply Chain Management, men som inte använder Microsoft-lösningar för hantering av kundrelationer (CRM), flyttar till Dynamics 365 för sitt stöd till dubbelriktad skrivning.
+ Data från kunder, produkter, åtgärder, projekt och sakernas Internet (IoT) skickas automatiskt till Common Data Service via dubbelriktad skrivning. Denna anslutning är mycket användbar för företag som är intresserade av Microsoft Power Platform expansioner.
+ Infrastrukturen för dubbelriktad skrivning följer principen för ingen kod/ingen kod. Minsta tekniska ansträngning krävs för att utöka standardmappningarna mellan tabeller och för att inkludera anpassade kartor.
+ Dubbelriktad skrivning stöder både online-läge och offline-läge. Microsoft är det enda företaget som har stöd för online- och offline-lägen.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>Vad betyder dubbelriktad skrivning för användare och arkitekter av CRM-produkter?

Vid dubbelriktad skrivning automatiseras dataflödet mellan Finance and Operations-appar och Common Data Service. I framtida versioner kommer begreppen i modellstyrda appar i Dynamics 365 (t.ex. kund, kontakt, offert och order) att skalas till mellan marknaden och kunder på den övre marknaden.

I den första versionen hanteras den mesta av automatisering av lösningar för dubbelriktad skrivning. I framtida versioner kommer dessa lösningar att bli en del av Common Data Service. Genom att förstå de kommande ändringarna i Common Data Service, kan du spara pengar på lång sikt. Här är några av de avgörande förändringarna:

+ Common Data Service kommer att ha nya begrepp, t.ex. företag och part. Dessa begrepp påverkar alla program som är byggda på Common Data Service, till exempel Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service och Dynamics 365 Field Service.
+ Aktiviteter och anteckningar är enhetliga och expanderade för att stödja både C1s (användare av systemet) och C2s (kunder i systemet).
+ Här är några av de kommande ändringarna i Common Data Service:

    - Den decimala datatypen ersätter datatypen pengar.
    - Gäller från kommer att stödja tidigare, nuvarande och framtida data på samma ställe.
    - Det kommer att bli mer stöd för valuta och valutakurser och API:n **Valutakurs** kommer att revideras.
    - Enhetskonverteringar stöds.

Mer information om kommande ändringar finns i [Data i Common Data Service – fas 1 och 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).
