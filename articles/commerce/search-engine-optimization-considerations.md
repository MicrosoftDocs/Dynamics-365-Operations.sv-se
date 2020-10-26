---
title: Språkinformation för sökmotoroptimering (SEO) för din webbplats
description: Det här avsnittet handlar om sökmotorns SEO-information för din webbplats från utveckling till produktion.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6ffc772addb330abe7205007662a3f3e08a3e47f
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961596"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Språkinformation för sökmotoroptimering (SEO) för din webbplats


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om varje sökmotors SEO-information för din webbplats från utveckling till produktion.

## <a name="a-site-that-is-under-development"></a>En webbplats som är under utveckling

Medan en webbplats är under utveckling ska alla sidor ha metataggarna **NOINDEX** och **NOFOLLOW** så att sökmotorer inte kan indexera sidorna och lagra utvecklingsversionerna av din webbplats i cacheminnet. För att kunna utföra den här konfigurationen måste du lägga till standardmodulen för metataggar på webbplatsmallen. Standardegenskaperna för metataggarna är sedan tillgängliga i avsnittet SEO-egenskaper i sidredigeraren. Du kan använda dessa egenskaper för att hantera metataggarna.

## <a name="soft-launch-of-a-site"></a>Mjuk start av en plats

Under en "mjuk start" görs en webbplats tillgänglig för en begränsad publik eller marknad innan den fullständiga lanseringen sker. Om du gör en mjuk start av din webbplats bör du överväga att lämna metataggarna **NOINDEX** på plats. På så sätt garanterar du att den mjuka starten förblir begränsad till de begränsade målgrupper som du vill uppnå.

## <a name="a-site-that-is-in-production"></a>En webbplats som är i produktion

När en webbplats är i produktion bör du kontrollera att alla webbplatssidor är korrekt märkta. Microsoft Dynamics 365 Commerce använder informationen som anges för en sida för att återge all SEO-information på sidan. Följande moduler ger den här funktionen: sammanfattning av kategorisidor, sammanfattning av listsidor och sammanfattning av produktsidor.

För att optimera indexeringen använder återgivningsramverket både information från SEO-egenskaperna som konfigureras i Dynamics 365 Commerce och modulspecifik information. För en plats i produktionen bör du se till att filen robots.txt tillåter indexering av hela webbplatsen och att den innehåller länkar till det publicerade dokumentet för webbplatsöversikt. Du bör aktivera funktionen för att skapa webbplatsöversikt på **webbplatsinställningar \> webbplatsmappningar är aktiverade**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Sidinställningar för SEO för intern förhandsgranskning, begränsade målgrupper och alla målgrupper

Eftersom Dynamics 365 Commerce ger stöd för "vad du ser är vad du får" (WYSIWYG)-autentiserade förhandsgranskningar i visuell sidskapare, kan författare förbereda sitt sidinnehåll utan att behöva oroa sig om att informationen kommer att visas för besökare på webbplatsen. Om en sida måste publiceras, men dess exponering måste vara begränsad måste den ha metataggen **NOINDEX**, så att den inte indexeras av sökmotorer. När sidan är klar för alla målgrupper bör alla de grundläggande SEO-metadata finnas tillgängliga, vilket maximerar effektiviteten hos sökmotorindexeringen. Dessutom bör metataggen **NOLIMIT** tas bort.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera näthandelsanvändare och roller](manage-ecommerce-users-roles.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

[Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)
