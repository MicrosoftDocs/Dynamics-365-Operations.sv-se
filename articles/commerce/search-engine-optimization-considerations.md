---
title: Språkinformation för sökmotoroptimering (SEO) för din webbplats
description: Denna artikel avhandlar sökmotornoptimering (SEO) för din webbplats från utveckling till produktion.
author: psimolin
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 6747df3c56fb05248210f78ebf2176a56ce78329
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896911"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Språkinformation för sökmotoroptimering (SEO) för din webbplats


[!include [banner](includes/banner.md)]

Denna artikel avhandlar sökmotornoptimering (SEO) för din webbplats från utveckling till produktion.

## <a name="a-site-that-is-under-development"></a>En webbplats som är under utveckling

För att säkerställa att sökmotorer inte indexerar en webbplats under utveckling bör alla webbplatssidor ha metataggar **noindex** och **nofollow**. En bra praxis är att skapa ett fragment baserat på [MetaTags-modul](metatags-module.md) som innehåller följande metataggpost och se till att fragmentet läggs till i HTML-koden \<head\> avsnitt av alla mallar som används på din webbplats.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Mjuk start av en plats

Under en "mjuk start" görs en webbplats tillgänglig för en begränsad publik eller marknad innan den fullständiga lanseringen sker. Om du gör en mjuk start av din webbplats bör du överväga att lämna metataggarna **noindex** på plats. På så sätt garanterar du att den mjuka starten förblir begränsad till de begränsade målgrupper som du vill uppnå.

## <a name="a-site-that-is-in-production"></a>En webbplats som är i produktion

När en webbplats är i produktion bör du kontrollera att alla webbplatssidor är korrekt märkta. Microsoft Dynamics 365 Commerce använder informationen som anges för en sida för att återge all SEO-information på sidan. Följande moduler ger den här funktionen: sammanfattning av kategorisidor, sammanfattning av listsidor och sammanfattning av produktsidor.

För att optimera indexeringen använder återgivningsramverket både information från SEO-egenskaperna som konfigureras i Dynamics 365 Commerce och modulspecifik information. För en plats i produktionen bör du se till att filen robots.txt tillåter indexering av hela webbplatsen och att den innehåller länkar till det publicerade dokumentet för webbplatsöversikt. Du bör aktivera funktionen för att skapa webbplatsöversikt på **webbplatsinställningar \> webbplatsmappningar är aktiverade**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Sidinställningar för SEO för intern förhandsgranskning, begränsade målgrupper och alla målgrupper

Eftersom Dynamics 365 Commerce ger stöd för "vad du ser är vad du får" (WYSIWYG)-autentiserade förhandsgranskningar i visuell sidskapare, kan författare förbereda sitt sidinnehåll utan att behöva oroa sig om att informationen kommer att visas för besökare på webbplatsen. Om en sida måste publiceras, men dess exponering måste vara begränsad måste den ha metataggen **noindex**, så att den inte indexeras av sökmotorer. När sidan är klar för alla målgrupper bör alla de grundläggande SEO-metadata finnas tillgängliga, vilket maximerar effektiviteten hos sökmotorindexeringen. Dessutom bör metataggen **noindex** tas bort.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera näthandelsanvändare och roller](manage-ecommerce-users-roles.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

[Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
