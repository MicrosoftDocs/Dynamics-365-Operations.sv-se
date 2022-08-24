---
title: Lägga till en logotyp
description: I denna artikel beskrivs hur du lägger till en logotyp på din webbplats i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 4bd47907791edfd0ab81282bd1e465ac54172cdf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278108"
---
# <a name="add-a-logo"></a>Lägga till en logotyp

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du lägger till en logotyp på din webbplats i Microsoft Dynamics 365 Commerce.

När du bygger din webbplats, en av de första sakerna som du förmodligen kommer att göra är att lägga ditt företag eller varumärke logotyp till webbplatsens rubrik. Dynamics 365 Commerce online modulbibliotek ger en modul som gör denna uppgift enkel.

Du kan lägga till en logotyp direkt i en mall, layout eller sida. På så sätt kan du enkelt ändra logotypen som visas på specifika sidor eller grupper av sidor. Denna artikel beskriver emellertid det vanligaste scenariot, där du lägger till din logotyp i ett sidhuvudfragment som kan återanvändas på alla sidor på din webbplats.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan lägga till en logotyp på alla sidor på webbplatsen måste du utföra dessa uppgifter.

1. Överför din logotyp till mediebiblioteket.
1. Skapa ett rubrikavsnitt. Mer information om hur du skapar och använder fragment finns [arbeta med fragment](work-with-fragments.md).
1. Inkludera rubrikavsnitt i mallen som webbplatsens sidor använder för layoutalternativ och modulalternativ. Mer information om hur mallar, se [Arbeta med mallar](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Lägga till en logotyp i ett rubrikavsnitt

Gör så här om du vill lägga till en logotyp i rubrikavsnitt för din webbplats.

1. I navigeringsfönstret till vänster, välj **fragment**.
1. Markera det sidfragment som du skapade tidigare och välj sedan **Redigera**.
1. Expandera modulen rubrik.
1. Ange en bild och en länk för logotypen i egenskapsfönstret för huvudmodulen. 
1. Spara rubrikfragmentet, slutför redigeringen och publicera det.

När du har publicerat det uppdaterade rubrikavsnitt visas din logotyp på alla webbplatssidor som använder mallen som innehåller sidhuvudet.

## <a name="additional-resources"></a>Ytterligare resurser

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägga till en favoritikon](add-favicon.md)

[Lägga till ett copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
