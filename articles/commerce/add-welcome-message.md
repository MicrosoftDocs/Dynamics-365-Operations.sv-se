---
title: Lägga till ett välkomstmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797393"
---
# <a name="add-a-welcome-message"></a>Lägga till ett välkomstmeddelande

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.

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
