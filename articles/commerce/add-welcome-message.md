---
title: Lägg till ett välkomstmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5910ab85b1b0b2df992a24ad3cf7a032e7b98ea9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980142"
---
# <a name="add-a-welcome-message"></a>Lägg till ett välkomstmeddelande


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.

## <a name="overview"></a>Översikt

Ett välkomstmeddelande på din näthandelssajt kan informera besökare om pågående försäljning, webbplatsuppdateringar eller tillgänglighet för säsongsinsamlingar. Välkomstmeddelandet ställs in med hjälp av notifieringsmodul.

Aviseringsmodulen ska läggas till platsen **Fel- och informationsmeddelande** för huvudfragment. I notifieringsmodulen kan du ange den text som visas, textfärgen och justeringen. Du kan också ange om besökare på webbplatsen kan stänga meddelandet.

När ett välkomstmeddelande läggs till i ett delat rubrikavsnitt visas det på alla sidor som använder mallen där det delade rubrikavsnittet används.

Gör så här om du vill lägga till ett välkomstmeddelande på webbplatsen:

1. I Commerce webbplatsskaparen, gå till din webbplats.
1. Välj **fragment**.
1. Välj det rubrikavsnitt som meddelandet ska läggas till.
1. Expandera **fel-/informationsmeddelanden** i dispositionsträdet.
1. Markera notifieringsmodulen och klicka sedan på **OK**. Om det inte redan finns en notifieringsregel väljer du först ellipsknappen-knappen (**...**) bredvid **fel-/informationsmeddelanden** och välj sedan **Lägg till modul**.
1. I egenskapsfönstret till höger, på fliken **Data** välj **Lägg till datakälla** och sedan **Innehåll**.
1. I fältet **Inmatningstext** ange texten för välkomstmeddelandet.
1. Välj **Spara**, välj **Slutför redigering** för att checka in rubrikavsnittet och välj sedan **publicera** för att publicera den. 

Välkomstmeddelandet visas nu överst på varje webbplatssida där det valda rubrikavsnittet används.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]