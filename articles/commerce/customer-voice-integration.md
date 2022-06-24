---
title: Integrera Customer Voice med webbplatssidor för näthandel
description: Denna artikel beskriver hur man integrerar Microsoft Dynamics 365 Customer Voice i Dynamics 365 Commerce-näthandelssidor.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850340"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Integrera Customer Voice med webbplatssidor för näthandel

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur man integrerar Microsoft Dynamics 365 Customer Voice i Dynamics 365 Commerce-näthandelssidor.

Du kan integrera [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) i din näthandelsplats för att samla in, analysera och spåra återrapportering från kunder i realtid. För att komma igång med integreringen måste du skapa ett konto och välja en Customer Voice-projektmall för den typ av feedback som du vill samla in.

## <a name="integrate-the-customer-voice-service"></a>Integrera Customer Voice-tjänst

Om du vill skapa ett Customer Voice-konto, gå till [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) och följ uppmaningen.

När du har skapat ett konto för Customer Voice och loggat in är nästa steg att välja en projektmall för den typ av feedback som du vill samla in.

Följ dessa steg för att välja en Customer Voice-projektmall.

1. Gå till [sidan för Customer Voice projektmall](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Välj **Komma igång**.
1. Välj projektmallen för den typ av feedback som du vill samla in och välj sedan **Nästa**.
1. På fliken **Skicka**, under **Välj ett inbäddningsformat**, välj ett inbäddningsformat. Fältet **Inbäddad kod** visar koden som måste bäddas in i Commerce-webbplatsbyggaren.

I exemplen i denna artikel används projektmallen **Periodisk kundöversikt** och det inbäddade formatet **Knapp**.

Följande exempelillustration visar sidan för projektmall **Periodisk kundöversikt** där alternativet för inbäddat format för **Knapp** inbäddningsformatet är valt och inbäddningskoden för det alternativet visas i fältet **Inbäddad kod**. Tre separata åtgärder krävs för att den angivna koden ska vara obligatorisk på dina webbplatssidor, enligt beskrivningen i följande avsnitt.

![Enkätsida för periodisk kund Customer Voice med alternativet Knapp valt.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Bädda in den externa skriptets URL

På alla webbplatssidor som bör ha en Customer Voice-undersökning måste du bädda in den externa skript-URL som Customer Voice angav i inbäddningskoden. Det bästa sättet att bädda in skriptet på flera webbplatssidor är att skapa ett fragment i webbplatsbyggaren som innehåller den externa skriptets URL och sedan lägga till fragmentet i lämpliga sidmallar. När du har publicerat en uppdaterad mall kommer den inbäddade externa skriptkoden att likna följande exempel på berörda webbplatssidor.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

För information om fragment, se [Arbeta med fragment](work-with-fragments.md).

> [!NOTE]
> Du behöver bara lägga till URL till fragmentet. Den externa skriptmodulen lägger till den andra skriptkoden.

Om du vill ändra den externa skript-URL-adressen till ett fragment följer du dessa steg.

1. Skapa ett fragment som baseras på den [externa skriptmodulen](script-module.md) i webbplatsskaparen.
1. I det nya fragmentet, välj platsen **externt standardskript**.
1. I egenskapsfönster **externt standardskript** i fältet **skripkälla**, ange den externa skriptets URL, som visas i följande exempelillustration.

    ![Extern URL för skript i fältet Skriptkälla för det nya fragmentet.](media/customer-voice-integration-2.png)

1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Välj **publicera** om du vill publicera fragmentet.

Det nya fragmentet som innehåller det inbäddade externa skriptblocket är nu klart att läggas till i rätt sidmall.

### <a name="embed-the-external-style-sheet-code"></a>Så här förser du den externa formatmallkoden

Sedan, på alla webbplatssidor som bör ha en Customer Voice-undersökning måste du bädda in den externa formatmallkoden som Customer Voice angav i inbäddningskoden. Som i föregående avsnitt är det bästa sättet att bädda in den externa stilmallskoden på flera webbplatssidor att skapa ett fragment i webbplatsbyggaren som innehåller stilmallskoden och sedan lägga till fragmentet i lämpliga sidmallar. Den inbäddade externa formatmallkoden liknar följande exempelkod.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Om du vill ändra den externa formatmallkoden till ett fragment följer du dessa steg.

1. Skapa ett fragment som baseras på den [Modul för metataggar](metatags-module.md) i webbplatsskaparen.
1. Välj plats i fragmentet **Standard metataggar**.
1. I egenskapsfönster **Standardmetataggar** i fältet **Metataggar**, ange den externa formatmallkoden, som visas i följande exempelillustration.

    ![Extern formatmallkod i fältet Metataggar för det nya fragmentet.](media/customer-voice-integration-3.png)

1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Välj **publicera** om du vill publicera fragmentet.

Det nya fragmentet som innehåller det inbäddade externa formatmallkoden är nu klart att läggas till i rätt sidmall.

### <a name="embed-the-inline-script-code"></a>Bädda in den inbyggda skriptkoden 

Sedan, på alla webbplatssidor som bör ha en Customer Voice-undersökning måste du bädda in den infogade skriptkoden som Customer Voice angav i inbäddningskoden. Som i föregående avsnitt är det bästa sättet att bädda in den infogade skriptkoden på flera webbplatssidor att skapa ett fragment i webbplatsbyggaren som innehåller den infogade skriptkoden och sedan lägga till fragmentet i lämpliga sidmallar.

I följande exempel på infogade skriptkoden **SURVEY\_KEY** är en platshållare. Värdet för **SURVEY\_KEY** bör matcha den faktiska undersökningsnyckeln som Customer Voice angav i inbäddningskoden. Den sista raden anropar koden för att återge översiktsknappen efter en sekund, för att säkerställa att skripten har tillräckligt med tid att läsas in. Beroende på vilken översikt du har valt, kanske du också måste lägga till eller uppdatera andra metadata, till exempel företagsnamnet.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Om du vill ändra den infogade skriptkoden till ett fragment följer du dessa steg.

1. Skapa ett fragment som baseras på den [infogade skriptmodulen](script-module.md) i webbplatsskaparen.
1. I fragmentet, välj platsen **infogat standardskript**.
1. I egenskapsfönster **Infogat standardskript** i fältet **Internt skript**, ange den infogade skriptkoden, som visas i följande exempelillustration.

    ![Den infogade skriptkoden i fältet Skriptkälla för det nya fragmentet.](media/customer-voice-integration-4.png)

1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Välj **publicera** om du vill publicera fragmentet.

Det nya fragmentet som innehåller det inbäddade den infogade skriptkoden är nu klart att läggas till i rätt sidmall.

## <a name="add-fragments-to-a-template"></a>Lägga till fragment i en mall

När du har skapat fragmenten som innehåller Customer Voice inbäddade kod måste du lägga till dem i sidmallarna som är kopplade till de webbplatssidor där du vill använda dem. I följande exempelillustration har de tre exempelfragmenten lagts till i en produktinformationssida (PDP)-mall.

![Exempelfragment som har lagts till en PDP-mall.](media/customer-voice-integration-5.png)

Efter att den uppdaterade mallen har publicerats kommer Customer Voice-undersökningen att dyka upp på alla sidor som styrs av mallen.

Mer information om hur mallar, se [Arbeta med mallar](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Konfigurera innehållssäkerhetspolicy

Som standard tillåter inte säkerhetspolicy för innehåll (CSP) samtal till andra tjänster om inte ytterligare konfiguration har gjorts. När du har publicerat de uppdaterade mallarna är det därför sannolikt att översikten inte kommer att läsas in på relevanta webbplatssidorna. Om du vill visa CSP-relaterade fel öppnar du webbläsarens utvecklingsverktyg (F12) och gå sedan till en sida som har undersökningen. De CSP-relaterade felen visas i konsolresultat.

Följ dessa steg för att konfigurera CSP i webbplatsbyggaren för att åtgärda felen.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. På fliken **Innehållssäkerhetspolicy**, lägg till `https://customervoice.microsoft.com/` till direktivet **child-src**.
1. Lägg till `https://customervoice.microsoft.com/` i direktivet **frame-src**.
1. Lägg till `https://mfpembedcdnmsit.azureedge.net` och **.azureedge.net** till direktivet **img-src**.

Mer information finns i [säkerhetsprinciper för innehåll](manage-csp.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Extern skriptmodul](script-module.md)

[Modul för metataggar](metatags-module.md)

[Internt skriptmodul](script-module.md)

[Säkerhetsprinciper för innehåll](manage-csp.md)

[Arbeta med fragment](work-with-fragments.md)

[Arbeta med mallar](work-with-templates.md)
