---
title: Bygg anpassade svarssidor för felstatuskod 4xx/5xx
description: I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 060f5e5616624279711f61f582e6a898c7eb7785
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415801"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Bygg anpassade svarssidor för felstatuskod 4xx/5xx


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar anpassade svarssidor för 4xx och 5xx-statuskodfel med hjälp av redigeringsverktygen i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

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
