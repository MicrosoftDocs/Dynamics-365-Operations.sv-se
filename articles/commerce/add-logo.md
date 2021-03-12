---
title: Lägg till en logotyp
description: I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 073c3d6f8d5ee88d51efb41f6b9c1a204b82fa12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980317"
---
# <a name="add-a-logo"></a>Lägg till en logotyp

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en logotyp till din webbplats i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

När du bygger din webbplats, en av de första sakerna som du förmodligen kommer att göra är att lägga ditt företag eller varumärke logotyp till webbplatsens rubrik. Dynamics 365 Commerce online modulbibliotek ger en modul som gör denna uppgift enkel.

Du kan lägga till en logotyp direkt i en mall, layout eller sida. På så sätt kan du enkelt ändra logotypen som visas på specifika sidor eller grupper av sidor. Det här avsnittet beskriver dock de vanligaste scenariot där du lägger till din logotyp i ett sidhuvud fragment som kan återanvändas på alla sidor på din webbplats.

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

[Välj ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

