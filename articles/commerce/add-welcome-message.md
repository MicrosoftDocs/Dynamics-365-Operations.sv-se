---
title: Lägg till ett välkomstmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 25a4e91646916b03c8a138fc713577f429ab633c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697392"
---
# <a name="add-a-welcome-message"></a>Lägg till ett välkomstmeddelande

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till ett välkomstmeddelande på Microsoft Dynamics 365 Commerce-webbplatsen.

## <a name="overview"></a>Översikt

Ett välkomstmeddelande på din e-handelswebbplats kan informera besökare om pågående försäljning, webbplatsuppdateringar eller tillgänglighet för säsongsinsamlingar. Välkomstmeddelandet ställs in med hjälp av notifieringsmodul.

Aviseringsmodulen ska läggas till platsen **Fel- och informationsmeddelande** för huvudfragment. I notifieringsmodulen kan du ange den text som visas, textfärgen och justeringen. Du kan också ange om besökare på webbplatsen kan stänga meddelandet.

När ett välkomstmeddelande läggs till i ett delat rubrikavsnitt visas det på alla sidor som använder mallen där det delade rubrikavsnittet används.

Gör så här om du vill lägga till ett välkomstmeddelande på webbplatsen:

1. I Dynamics 365 Commerce gå till webbplatsen.
1. Välj **fragment**.
1. Välj det rubrikavsnitt som meddelandet ska läggas till.
1. Expandera **fel-/informationsmeddelanden** i dispositionsträdet.
1. Välj notifieringsmodul.

    Om det inte redan finns en notifieringsregel väljer du ellipsknappen-knappen (**...**) bredvid **fel-/informationsmeddelanden** och välj sedan **Lägg till modul**. Markera notifieringsmodulen och klicka sedan på **OK**.

1. I egenskapsfönstret till höger, på fliken **Data** välj **Lägg till datakälla** och sedan **Innehåll**.
1. I fältet **Inmatningstext** ange texten för välkomstmeddelandet.
1. Spara rubrikfragmentet, checka in det och publicera det.

Välkomstmeddelandet visas nu överst på varje webbplatssida där det valda rubrikavsnittet används.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Lägg till en favicon](add-favicon.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

