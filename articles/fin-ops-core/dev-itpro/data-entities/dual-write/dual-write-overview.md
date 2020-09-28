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
ms.openlocfilehash: 8957065bcadc3f33adb60c2a8f2be78710289631
ms.sourcegitcommit: d03f301633175b15d46690fc97067820bf21579f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2020
ms.locfileid: "3775157"
---
# <a name="dual-write-overview"></a>Översikt över dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a>Vad är dubbelriktad skrivning?

Dubbelriktad skrivning är en medföljande infrastruktur som ger nära realtidssamverkan mellan kundengagemangsappar och Finance and Operations-appar. När data om kunder, produkter, personer och verksamhet går utanför programgränser, är alla avdelningar i organisationen berättigade.

Dubbelriktad skrivning ger tätt kombinerad, dubbelriktad integration mellan Finance and Operations-appar och Common Data Service. Alla dataändringar i Finance and Operations-appar orsakar skrivningar till Common Data Service och alla dataändringar i Common Data Service orsakar skrivningar till Finance and Operations-appar. Det här automatiserade dataflödet ger ett integrerat användargränssnitt mellan programmen.

![Datarelation mellan appar](media/dual-write-overview.jpg)

Dubbelriktad skrivning har två aspekter: en *infrastruktur* aspekt och en *applikation* aspekt.

### <a name="infrastructure"></a>Infrastruktur

Infrastrukturen för dubbelriktad skrivning är utökningsbar och tillförlitlig och innehåller följande huvudfunktioner:

+ Synkront och dubbelriktat dataflöde mellan program
+ Synkronisering, tillsammans med lägena spela upp, pausa och sammanfattning för att stödja systemet i online- och offline-/asynkrona lägen.
+ Möjlighet att synkronisera ursprungliga data mellan programmen
+ Kombinerad vy över aktivitet och felloggar för dataadministratörer
+ Möjlighet att konfigurera anpassade aviseringar och tröskelvärden samt att prenumerera på meddelanden
+ Intuitivt användargränssnitt (UI) för filtrering och transformeringar
+ Möjlighet att ställa in och visa enhetsberoenden och relationer
+ Utökningsbarhet för både standard- och anpassade entiteter och kartor
+ Tillförlitlig program livscykelhantering
+ Installations upplevelse utanför lådan för nya kunder

### <a name="application"></a>Ansökning

Dubbelriktad skrivning skapar en mappning mellan koncept i Finance and Operations-appar och koncept i kundengagemangsappar. Denna integration stöder följande scenarier:

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
+ Data från kunder, produkter, åtgärder, projekt och sakernas Internet (IoT) skickas automatiskt till Common Data Service via dubbelriktad skrivning. Denna anslutning är användbar för företag som är intresserade av Microsoft Power Platform expansioner.
+ Infrastrukturen för dubbelriktad skrivning följer principen för ingen kod/ingen kod. Minsta tekniska ansträngning krävs för att utöka standardmappningarna mellan tabeller och för att inkludera anpassade kartor.
+ Dubbelriktad skrivning stöder både online-läge och offline-läge. Microsoft är det enda företaget som har stöd för online- och offline-lägen.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Vad innebär dubbla skrivmedel för utvecklare och arkitekter av kundengagemangsappar?

Vid dubbelriktad skrivning automatiseras dataflödet mellan Finance and Operations-appar och kundengagemangsappar. Dubbelriktad skrivning består av två AppSource-lösningar som är installerade på Common Data Service. Lösningarna utökar entitetens schema, plugin-program och arbetsflöden i Common Data Service så att de kan skalas till ERP-storlek. För att implementeringen ska lyckas måste utvecklare och arkitekter av kundengagemangsappar kunna känna till dessa ändringar och samarbeta med deras motsvarigheter på Finance and Operations-appar.

Om du vill skapa paritet med Finance and Operations-appar gör dubbelriktad skrivning några viktiga ändringar i Common Data Service-schemat. Om du förstår planen kan du undvika att en del design och utveckling fungerar i framtiden.

+ När AppSource-paketet för dubbelriktad skrivning är installerat får Common Data Service nya begrepp som företag och part. De här begreppen hjälper appar som bygger på Common Data Service, bland annat Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service och Dynamics 365 Field Service , för att interagera sömlöst med Finance and Operations-appar.

+ Aktiviteter och anteckningar är enhetliga och expanderade för att stödja både C1s (användare av systemet) och C2s (kunder i systemet).

+ För att förhindra att data går förlorade under överföring mellan olika Finance and Operations-appar och i Common Data Service kan du öka antalet decimaler i datatypen kundengagemangsappar. Funktionen översätter befintliga poster till det nya utökade tillståndet i metadata-skiktet. Under den här processen översätts valutavärdet till decimal data snarare än pengadata och valuta värdet stöder 10 decimaler. Den här funktionen är inte skrivskyddad och organisationer som inte behöver mer än 4 decimalers precision behöver inte välja något. Mer information finns i [Migrering av valutadatatyp för dubbelriktad skrivning](currrency-decimal-places.md) .

+ [Gäller från](../../dev-tools/date-effectivity.md) kommer att läggas till i Common Data Service . Det kommer att stödja tidigare, nuvarande och framtida data om samma enhet.

+ Produkt [enhetskonverteringar](../../../../supply-chain/pim/tasks/manage-unit-measure.md) stöds för produkter, offerter, order och fakturor.

Mer information om kommande ändringar finns i [nyheter och ändringar i dubbelriktad skrivning](whats-new-dual-write.md) .

