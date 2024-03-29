---
title: Översikt över dubbelriktad skrivning
description: Denna artikel tillhandahåller en översikt över dubbelriktad skrivning som ger en interaktion i det närmaste i realtid mellan kundengagemangsappar och appar för ekonomi och drift.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 943607a3ef28db11b7bc7805257914117e6ae38c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289651"
---
# <a name="dual-write-overview"></a>Översikt över dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Vad är dubbelriktad skrivning?

Dubbelriktad skrivning är en färdig infrastruktur som ger i det närmaste realtidssamverkan mellan kundengagemangsappar och appar för ekonomi och drift. När data om kunder, produkter, personer och verksamhet går utanför programgränser, är alla avdelningar i organisationen berättigade.

Dubbelriktad skrivning ger dubbelriktad, tätt sammankopplad integration mellan appar för ekonomi och drift och Dataverse. Alla dataändringar i appar för ekonomi och drift orsakar skrivningar till Dataverse, och alla dataändringar i Dataverse orsakar skrivningar till appar för ekonomi och drift. Det här automatiserade dataflödet ger ett integrerat användargränssnitt mellan programmen.

![Datarelation mellan appar.](media/dual-write-overview.jpg)

Dubbelriktad skrivning har två aspekter: en *infrastruktur* aspekt och en *applikation* aspekt.

### <a name="infrastructure"></a>Infrastruktur

Infrastrukturen för dubbelriktad skrivning är utökningsbar och tillförlitlig och innehåller följande huvudfunktioner:

+ Synkront och dubbelriktat dataflöde mellan program
+ Synkronisering, tillsammans med lägena spela upp, pausa och sammanfattning för att stödja systemet i online- och offline-/asynkrona lägen.
+ Möjlighet att synkronisera ursprungliga data mellan programmen
+ Kombinerad vy över aktivitet och felloggar för dataadministratörer
+ Möjlighet att konfigurera anpassade aviseringar och tröskelvärden samt att prenumerera på meddelanden
+ Intuitivt användargränssnitt (UI) för filtrering och transformeringar
+ Möjlighet att ställa in och visa tabellberoenden och relationer
+ Utökningsbarhet för både standard- och anpassade tabeller och mappningar
+ Tillförlitlig program livscykelhantering
+ Installations upplevelse utanför lådan för nya kunder

### <a name="application"></a>Ansökning

Dubbelriktad skrivning skapar en mappning mellan koncept i appar för ekonomi och drift och koncept i kundengagemangsappar. Denna integrering stöder följande scenarier:

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


## <a name="top-reasons-to-use-dual-write"></a>Främsta anledningar att använda dubbelriktad skrivning

Dubbelriktad skrivning ger dataintegrering i Microsoft Dynamics 365-program. Detta robusta ramverk länkar sig till miljöer och gör att olika affärsprogram kan fungera tillsammans. Här följer de viktigaste skälen till varför du bör använda dubbelriktad skrivning:

+ Dubbelriktad skrivning ger tätt sammankopplade, nära realtid och dubbelriktad integrering mellan appar för ekonomi och drift och kundengagemangsappar. Den här integreringen gör Microsoft Dynamics 365 en enda kontaktpunkt för alla dina affärslösningar. Kunder som använder Dynamics 365 Finance och Dynamics 365 Supply Chain Management, men som inte använder Microsoft-lösningar för hantering av kundrelationer (CRM), flyttar till Dynamics 365 för sitt stöd till dubbelriktad skrivning.
+ Data från kunder, produkter, åtgärder, projekt och sakernas Internet (IoT) skickas automatiskt till Dataverse via dubbelriktad skrivning. Denna anslutning är användbar för företag som är intresserade av Power Platform expansioner.
+ Infrastrukturen för dubbelriktad skrivning följer principen för ingen kod/ingen kod. Minsta tekniska ansträngning krävs för att utöka standardmappningarna mellan tabeller och för att inkludera anpassade mappningar.
+ Dubbelriktad skrivning stöder både online-läge och offline-läge. Microsoft är det enda företaget som har stöd för online- och offline-lägen.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Vad innebär dubbla skrivmedel för utvecklare och arkitekter av kundengagemangsappar?

Vid dubbelriktad skrivning automatiseras dataflödet mellan appar för ekonomi och drift och kundengagemangsappar. Dubbelriktad skrivning består av två AppSource-lösningar som är installerade på Dataverse. Lösningarna utökar tabellens schema, plugin-program och arbetsflöden i Dataverse så att de kan skalas till ERP-storlek. För att implementeringen ska lyckas måste utvecklare och arkitekter av kundengagemangsappar förstå dessa ändringar och samarbeta med deras motsvarigheter inom appar för ekonomi och drift.

I syfte att skapa paritet med appar för ekonomi och drift gör dubbelriktad skrivning några viktiga ändringar i Dataverse-schemat. Om du förstår planen kan du undvika att en del design och utveckling fungerar i framtiden.

+ När AppSource-paketet för dubbelriktad skrivning är installerat får Dataverse nya begrepp som företag och part. Dessa koncept hjälper appar som bygger på Dataverse, bland annat Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service och Dynamics 365 Field Service att interagera sömlöst med appar för ekonomi och drift.

+ Aktiviteter och anteckningar är enhetliga och expanderade för att stödja både C1s (användare av systemet) och C2s (kunder i systemet).

+ För att förhindra att data går förlorade under överföring mellan olika appar för ekonomi och drift och Dataverse kan du öka antalet decimaler i datatypen valuta för kundengagemangsappar. Funktionen översätter befintliga rader till det nya utökade tillståndet i metadata-skiktet. Under den här processen översätts valutavärdet till decimal data snarare än pengadata och valuta värdet stöder 10 decimaler. Den här funktionen är inte skrivskyddad och organisationer som inte behöver mer än 4 decimalers precision behöver inte välja något. Mer information finns i [Migrering av valutadatatyp för dubbelriktad skrivning](currrency-decimal-places.md) .

+ [Gäller från](../../dev-tools/date-effectivity.md) kommer att läggas till i Dataverse . Det kommer att stödja tidigare, nuvarande och framtida data om samma tabell.

+ Produkt [enhetskonverteringar](../../../../supply-chain/pim/tasks/manage-unit-measure.md) stöds för produkter, offerter, order och fakturor.

Mer information om kommande ändringar finns i [nyheter och ändringar i dubbelriktad skrivning](whats-new-dual-write.md) .



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

