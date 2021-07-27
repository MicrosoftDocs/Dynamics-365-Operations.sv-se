---
title: Översikt över intäktsredovisning
description: Det här ämnet innehåller information om intäktsredovisningsfunktionen. Funktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för redovisning av både intäktspris och intäktsplan för order med flera element.
author: kweekley
ms.date: 11/11/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 42d126c598ee1811b686a9066e15e9f82264e4ce
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339273"
---
# <a name="revenue-recognition-overview"></a>Översikt över intäktsredovisning

[!include [banner](../includes/banner.md)]

Företag i branscher som säljer flera element, som produkter, tjänster, prenumerationer och liknande, måste kunna bryta ut order med flera element så att intäkten kan identifieras utifrån en uppsättning företagsspecifika och branschspecifika riktlinjer.

> [!NOTE]
> Intäktsredovisningsfunktionen kan inte aktiveras via funktionshantering. För närvarande måste du använda konfigurationsnycklar för att aktivera den.

> Intäktsredovisning, inklusive buntfunktionen, stöds inte för användning i Commerce-kanaler (e-handel, kassa, callcenter). Artiklar som konfigurerats med intäktsredovisning ska inte läggas till på order eller transaktioner som skapas i Commerce-kanaler.

I allmänhet kan intäktsredovisningsprocessen användas för att utföra dess uppgifter:

* Allokera intäkter som hjälp för att säkerställa att lämpligt intäktspris identifieras baserat på värdet av komponenterna i order med flera element.
* Periodisera intäkter, baserat på intäktsplaner som motsvarar avtalad tidsram och procentandel för identifiering av intäkter över tid.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

Videon om [hur du redovisar intäkter i Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (visas ovan) ingår i [spellistan för Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.

Intäktsredovisningsfunktionen ger ett flexibelt ramverk där du kan definiera företagsspecifika regler för redovisning av både intäktspris och intäktsplan.

Frisläppta produkter används för att stödja intäktsredovisning på försäljningsorderdokument. De frisläppta produkterna innehåller den inställning som behövs för att fastställa intäktspris och intäktsplan. Försäljningsordern kan ursprungligen komma från ett Tid och material-projekt.

Företag kan använda intäktsplansfunktionen utan att använda intäktsprisfunktionen. Därför används priset på försäljningsorderrader som antingen intäkt eller periodiserad intäkt. Om det finns en intäktsplan finns på försäljningsorderraden kommer priset på försäljningsorderraden att periodiseras. Om det inte finns någon intäktsplan på försäljningsorderraden kommer priset på försäljningsorderraden att bokföras på ett intäktskonto när det faktureras.

Intäktspriset beräknas antingen när försäljningsordern bekräftas eller när fakturan bokförs. För att förhandsgranska intäktspriset innan fakturan bokförs måste försäljningsordern bekräftas.

När försäljningsordern har bekräftats skapas även en förväntad intäktsplan om någon försäljningsorderrad har en intäktsplan. När försäljningsordern faktureras raderas den förväntade intäktsplanen och den förväntade intäktsplanen ersätts av den faktiska intäktsredovisningsplanen.

Uppgifterna för intäktsredovisningsplanen bevaras för respektive försäljningsorderrad. Därför kan intäktsredovisningsansvarig visa uppgifterna och frisläppa rader till intäkt när avtalad skyldighet har slutförts. I slutet av varje period kan intäktsredovisningsansvariga skapa en intäktsjournal för att frisläppa planerade rader som förfallit eller före ett datum som de definierar. Denna intäktsjournal bokförs inte omgående. Därför kan intäktsredovisningsansvarig verifiera att korrekta belopp frisläpps från periodiserad intäkt till faktisk intäkt.

Om en avtalsförändring gör att en ny försäljningsorderrad måste läggas till antingen till den befintliga försäljningsordern eller till en ny försäljningsorder kan en omallokeringsprocess köras för att korrigera intäktspriset på alla försäljningsorderrader.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]