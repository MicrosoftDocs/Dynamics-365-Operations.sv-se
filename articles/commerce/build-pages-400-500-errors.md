---
title: Bygg anpassade svarssidor för felstatuskod 4xx/5xx
description: I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799667"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Bygga anpassade svarssidor för felstatuskod 4xx/5xx

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.

Om en begäran misslyckas utfärdar servern HTTP statuskodfelsvar. Statuskoden 404 fångas in och returneras om en sida inte hittas och statuskoden 500 fångas in och returneras om ett serverfel uppstår. I Dynamics 365 Commerce kan programanvändare skapa anpassade statuskodsidor för felsvar som visas för användarna för dessa statuskodfelsvar.

## <a name="build-a-status-code-error-response-page"></a>Skapa en sida för statuskodfelsvar

Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.

1. Logga in på i din föredragna webbläsare till Dynamics 365 Commerce. 
1. Välj den webbplats som du vill skapa en 4xx/5xx-sida för felstatuskoden för.

### <a name="build-the-template"></a>Skapa mallen

Börja skapa mallen för sidan med statuskodfelsvar enligt följande instruktioner.

1. Gå till **Mallar**.
1. Skapa en ny sidmall genom att välja **Nytt**.
1. I dialogrutan **Ny mall** under **Mallnamn**, ange ett namn för den nya mallen och välj sedan **OK**.
1. Skapa mallen, baserat på strukturen som du vill att sidan med statuskodfelsvar ska ha.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 

### <a name="build-the-status-code-error-response-page"></a>Skapa en sida för statuskodfelsvar

Börja skapa en sida med statuskodfelsvar enligt följande instruktioner.

1. Gå till **sidor**.
1. Klicka på **Nytt** för att skapa en sida.
1. I dialogrutan **Välj en mall**, välj en mall och sedan under **Sidnamn**, ange ett namn för sida för statuskodfelsvar. Lämna fältet **Sid-URL** tom.
1. Skapa sidan.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

> [!NOTE]
> Du kan skapa separata sidor för statuskodfelsvar för 4xx och 5xx statuskodfel. Du kan också använda samma allmänna sida för statuskodfel för båda felkategorierna.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Ställa in en omdirigering för sidan med statuskodfelsvar

För att ställa in omdirigering för sidan med statuskodfelsvar enligt följande instruktioner.

1. Gå till **URL:ar \> Ny \> Ny alias** och välj sidan för statuskodfelsvar som du skapat tidigare.
1. I fältet **Alias** anger du antingen **standard-4xx** eller **standard-5xx**, beroende på sidan för statuskodfelsvar som du konfigurerar en omdirigering för. Dessa alias måste publiceras. Annars fungerar inte omdirigeringen.
1. Gör länken genom att välja **OK**.

> [!NOTE]
> Om du använder en enstaka statuskodsida med felsvar för båda felkategorierna upprepar du proceduren för att länka ett alias för den andra felkategorin till samma sida.

## <a name="additional-resources"></a>Ytterligare resurser

[Arbeta med mallar](work-with-templates.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Skapa URL för webbsida](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
