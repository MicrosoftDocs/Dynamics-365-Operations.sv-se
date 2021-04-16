---
title: Skapa URL för webbsida
description: I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98743d8948669f32d3c74e1915c7ed53db81141c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795701"
---
# <a name="create-a-page-url"></a>Skapa URL för webbsida

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs de grundläggande begreppen och procedurerna för att skapa en sidadress på webbplatsen.

Den fullständiga eller absoluta URL som pekar mot en sida på din webbplats består av separata delar. Till exempel URL-adressen `https://www.contoso.com/en-us/contactus` har följande delar:

- `https://www.contoso.com`– HTTP-protokollet och platsens domän.
- `/en-us`– Platsens språksökväg.
- `/contactus`– Den relativa URL-adressen för sidan **kontakta oss**. En relativ URL kallas också för en URL *instruktion*.

Du upprättar platsens domän och valfri språksökväg när du ställer in platsen. Du kan lägga till fler domäner och språksökvägar till webbplatsen via sidan onlinebutiker i webbplatsinställningarna.

URL-instruktionen för en sida finns som en fristående enhet i webbplatsredigeringsmiljön. En sid-URL består av två delar: ett namn som representerar URL-instruktionen och en pekare till en sida på antingen en webbplats eller en extern webbplats. En sid-URL kan också konfigureras för att fungera som en omdirigering till en annan sida på antingen en webbplats eller en extern plats.

## <a name="create-a-page-url"></a>Skapa URL för webbsida

Det finns två sätt att skapa URL:

- Automatiskt, när du skapar en sida
- Manuellt, från **URL**-sidan

### <a name="create-a-page-url-when-you-create-a-page"></a>Skapa en sid-URL när du skapar en sida

Om du anger ett namn i fältet **URL** när du skapar en ny sida, skapas en sid-URL som pekar mot sidan automatiskt på sidan **URL:er**. När du har publicerat URL:en och sidan som den pekar mot, kan webbplatsanvändare (dina kunder) komma åt den sida som är kopplad till URL:en.

> [!NOTE]
> Om du publicerar en URL utan att publicera sidan som den pekar mot, får webbplatsanvändarna ett 404-fel när de försöker öppna sidan. Om du publicerar en sida utan att publicera den URL som pekar mot den, går det inte att komma åt sidan via en URL.

### <a name="manually-create-a-page-url"></a>Manuellt skapa en sida-URL

När du skapar nya sidor behöver du inte ange någon sidadress. Om du lämnar URL-fältet tomt skapas sidan i ett olänkat tillstånd. I det här fallet kommer kunderna inte att kunna komma åt sidan, även om den publiceras. Om du vill göra sidan åtkomlig måste du skapa URL:en och länka den till sidan manuellt.

Om du vill skapa en sid-URL för en sida manuellt följer du stegen nedan.

1. Välj **URL** på sidan **Tillgångsstruktur**.
1. Välj den webbplatssida som du vill associera med URL.
1. Ange URL-instruktionen och klicka sedan på **OK**.

I det här läget är URL-adressen i ett utkast. Den måste publiceras innan webbplatsanvändare kan komma åt den associerade sidan.

## <a name="update-a-page-url"></a>Uppdatera en sid-URL

Om du vill uppdatera målsidan för en sid-URL följer du stegen nedan.

1. På sidan **URL** väljer du den URL som ska uppdateras.
1. Markera ellipsknappen i egenskapsrutan till höger (**...**) bredvid fältet för målsidan.
1. I dialogrutan väljer du en annan sida och klickar på **OK**.
1. Spara och publicera URL.

## <a name="redirect-a-page-url"></a>Omdirigera en sid-URL

Ibland vill du kanske att dina kunder ska kunna visa en annan sida när de begär en viss URL. I dessa fall är den bästa och enklaste metoden ofta att ändra sidan som sid-URL:en pekar mot. Du kan dock ha legitima skäl för att använda HTTP 301- eller 3023-omdirigeringar för att omdirigera begäranden för en URL till en annan URL.

Om du vill omdirigera en URL till en annan URL följer du stegen nedan.

1. På sidan **URL** väljer du den URL som ska uppdateras.
1. I egenskapsrutan till höger, välj **Omdirigera**.
1. Välj ett mål för omdirigeringen:

    - Om du vill peka mot en annan sida på webbplatsen markerar du **Intern URL**, väljer ellipsknappen (**...**) och väljer den URL du vill omdirigera till.
    - Om du vill peka mot en sida på en extern webbplats väljer du **Extern URL**, och anger sedan full URL-adressen för sidan. Se till att du inkluderar protokollet. Ange exempelvis `https://domain.com/new/page`. Om URL:en redan omdirigeras till en intern URL måste du välja **Rensa urval** innan du kan ange en extern URL.

1. Välj en omdirigeringstyp:

    - **Permanent omdirigering (301)** – Välj det här alternativet när du vet att innehållet flyttas permanent och inte återgår till föregående URL. Sökmotorer tilldelar SEO-värdet (Search Engine Optimization) för den omdirigerade URL:en till den URL som omdirigeras till och uppdaterar posten för att visa den nya URL:en. 
    - **Tillfällig omdirigering (302)** – Välj det här alternativet om du vill dirigera om trafiken utan att uppdatera sökmotorer. Den här metoden används vanligtvis om innehållet kommer att återgå till föregående URL-adress.

1. Spara och publicera URL:en när du är klar att implementera omdirigeringen.

## <a name="additional-resources"></a>Ytterligare resurser

[Anpassa webbplatsnavigeringen](customize-site-navigation.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
