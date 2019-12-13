---
title: Lägg till en favicon
description: I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.
author: bicyclingfool
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 58cb6c592351a96876532ef53d5d477ff93fafa1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697001"
---
# <a name="add-a-favicon"></a>Lägg till en favicon

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.

## <a name="overview"></a>Översikt

En favicon är en liten grafisk fil som visas på en flik i webbläsaren, i adressfältet, i webbhistoriken och i bokmärken eller favoriter, bland annat. Vi rekommenderar att du lägger till en favicon på din webbplats, eftersom den representerar och stärker ditt varumärke och hjälper till att skilja din webbplats från andra webbplatser som dina kunder besöker.

Även om du kan lägga till flera favicons av olika storlekar och filtyper på din webbplats, visar det här avsnittet hur du lägger till en enskild favicon. Samma process och plats används dock för att lägga till fler favicons.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Överför en favicon till webbplatsens tillgångssamling

Överför en favicon till webbplatsens tillgångssamling genom att följa dessa steg.

1. Gå till **Tillgångar \> Överför \> Överför tillgångar**.
1. Hitta och markera favicon i det lokala filsystemet.
1. Ange en rubrik och klicka sedan på **OK**. 
1. Kopiera den offentliga URL:en för favicon i egenskapsrutan till höger.

> [!NOTE]
> Om du inte markerar alternativet **publicera resurser efter överföring** måste du gå tillbaka till sidan **tillgångar** och publicera favicon manuellt senare.

## <a name="create-the-html-for-the-favicon"></a>Skapa HTML för favicon

Om du vill skapa HTML för favicon använder du följande HTML-kodfragment. För attributet **href**, ersätt **"Public\_URL\_for\_your\_favicon"** med den offentliga URL som du kopierade tidigare.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Lägga till HTML-koden för favicon till elementet \<head\> på sidorna

Om du vill lägga till en favicon på webbplatsen använder du samma procedur som för att lägga till alla typer av HTML och skript till elementet **\<head\>** på webbplatssidorna.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

