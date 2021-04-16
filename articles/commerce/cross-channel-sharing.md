---
title: Aktivera och använda delning av flera kanaler
description: I det här avsnittet beskrivs hur du aktiverar och använder delningsfunktionen för flera kanaler i Microsoft Dynamics 365 Commerce webbplatsskaparen.
author: psimolin
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: de317c2fae4607f5b8b887dd5e866d812043dcd3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799527"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Aktivera och använda delning av flera kanaler

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar och använder delningsfunktionen för flera kanaler i Microsoft Dynamics 365 Commerce webbplatsskaparen.

Delning mellan flera kanaler gör att återförsäljare kan återanvända och dela innehåll bland flera kanaler på en webbplats. Den här funktionen är användbar när webbplatskanalerna har ett kompatibelt grundspråk, eller när de har många gemensamma innehållsobjekt.

Delning mellan flera kanaler fungerar genom att en standardkanal aktiveras för sökning efter tillgängligt innehåll när en programspecifik version av det begärda innehållet inte hittas. Innehåll som ska delas mellan kanaler skapas i standardkanalen. Innehållet kan lokaliseras för alla språk som används på alla webbplatskanaler.

## <a name="when-to-use-cross-channel-sharing"></a>När använder du delning av flera kanaler

Delning av flera kanaler är användbart när flera kanaler på en och samma plats kan dela innehåll. En återförsäljare som har flera märken och butiker som grupperas under en enskild plats kan dela visst innehåll bland vissa eller alla av butiker. Det delade innehållet kan innehålla sidor med villkor, betalningsvillkor, leveransvillkor och vanliga frågor.

Delning av flera kanaler stöder också fragment. Därför kan en innehållssida som innehåller kanalbaserade fragment skapas som innehåll i olika kanaler. I det här fallet, även om merparten av innehållet delas mellan kanaler, kommer kanalbaserade fragment på en sida med flera kanaler endast att återges när de begärs från motsvarande butikskanal.

Webbplatser som bara har en kanal, eller webbplatser med flera kanaler som inte kan dela innehåll, får ingen nytta av delning mellan kanaler.

## <a name="enable-cross-channel-sharing"></a>Aktivera delning av flera kanaler

Delning av flera kanaler har aktiverats på webbplatsnivå. Den här åtgärden är enkelriktad. När delning mellan kanaler har aktiverats kan det alltså inte inaktiveras.

Gör så här om du vill aktivera delning mellan flera kanaler i Commerce webbplatsskaparen:

1. Gå till **Webbplatsinställningar \> Funktioner**.
1. Ställ in alternativet för funktionen **Flera kanaler** till **på**.

    ![Alternativet för flera kanaler anges till på Commerce webbplatsskaparen](./media/enabling-cross-channel-sharing.png)

När du har aktiverat delning av flera kanaler visas information om flera kanaler i avsnittet **kanaler** på **webbplatsinställningar \> funktioner**, som exemplet i bilden nedan visar.

![Information om kanaler visas efter att delning mellan kanaler har aktiverats](./media/channels-cross-channel.png)

När du har aktiverat delning av flera kanaler kommer fältet **kanal** högst upp till höger i Commerce webbplatsskaparen inkludera ett alternativ för **Onlinebutik i flera kanaler** som du kan använda för att hantera innehåll i flera kanaler, vilket visas i bilden nedan.

![Alternativet för onlinebutik i flera kanaler i fältet kanaler när delning mellan kanaler har aktiverats](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Skapa och använda delning av innehåll

Du kan skapa och använda innehåll över kanaler på flera sätt. Du kan till exempel skapa fragment, skapa sidor i fler kanaler som använder flera kanaler och innehåll i flera kanaler och åsidosätta fragment med flera kanaler med miljöspecifika versioner av fragment.

### <a name="create-a-cross-channel-fragment"></a>Skapa ett fragment med flera kanaler

För att skapa fragment i flera kanaler i Commerce webbplatsskaparen:

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Nytt fragment** välj modulen **Kampanjbanderoll** och sedan under **Fragmentets namn** ange ett namn (till exempel **Banderoll i flera kanaler**). Välj sedan **OK**.
1. I egenskapsfönstret i modulen **Kampanjbanderoll** välj **Lägg till meddelande** och välj sedan **Meddelande**.
1. I dialogrutan **Meddelande** under **Text**, ange **Flera kanaler** och välj **OK**. 
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

Det här fragmentet kan användas på flera olika kanaler eller specifika sidor som skapas på alla platskanaler.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Skapa en sida med flera kanaler som använder innehåll med flera kanaler

Du kan använda sidor på flera kanaler på vilken kanal som helst på din webbplats. Därför kan du skapa en delad innehålls sida en gång och göra efterföljande uppdateringar på en och samma plats. Till exempel en sida i flera kanaler för **villkor** som har URL `/toc` kan delas mellan alla kanaler på en plats. Om bas-URLa för webbplatskanalerna är `www.fabrikam.com/brand1` och `www.fabrikam.com/brand2` är samma kanal, delade sidan för **villkor** tillgängliga från båda URL:erna för webbplatskanaler `www.fabrikam.com/brand1/toc` respektive `www.fabrikam.com/brand2/toc`. Om sidan för **villkor** måste uppdateras senare, måste du bara uppdatera den enda delade sidan.

Skapa en sida för flera kanaler i Commerce webbplatsskaparen där innehåll med flera kanaler används genom att följa stegen nedan.

1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en mall, t.ex. **Marknadsföring**.
1. Under **Sidnamn** anger du ett namn för sidan (till exempel **Sida med flera kanaler**).
1. Under **Sid-URL**, anger du en sid-URL (till exempel **examplepage**) och väljer sedan **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Lägg till fragment** väljer du det fragment med flera kanaler som du skapade tidigare med en erbjudande banderoll och väljer sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör se kampanjens banderoll med texten "flera kanaler".
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Skapa en kanalspecifik sida som använder innehåll med flera kanaler

Genom att använda innehåll i flera kanaler på kanalspecifika sidor kan du skapa ett delat innehållsfragment en gång och sedan använda det på kanalspecifika sidor. Denna "enda källa" är användbar för delat innehåll, t.ex. villkor, betalningsvillkor eller kontaktinformation.

Skapa en kanalspecifik sida i Commerce webbplatsskaparen där innehåll med flera kanaler används genom att följa stegen nedan.

1. Från en viss kanal, t.ex. **Fabrikam utökade online-butik**, gå till **Sidor** och välj sedan **Ny** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en mall, t.ex. **Marknadsföring**.
1. Under **Sidnamn** anger du ett namn för sidan (till exempel **Kanalspecifik sida**).
1. Under **Sid-URL**, anger du en sid-URL (till exempel **channelspecificpage**) och väljer sedan **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Lägg till fragment** under **Kanal**, välj **Onlinebutik i flera kanaler**. Fragment mellan kanaler som du skapade tidigare ska visas i listan. Välj det och välj sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör se kampanjens banderoll med texten "flera kanaler".
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Skapa en kanalspecifik version av en sida med flera kanaler

Delning av flera kanaler stöder åsidosättningar av innehåll i olika kanaler. Alla utom en av dina webbplatskanaler delar samma innehåll. Att en webbplatskanal kräver annat innehåll. Om du vill använda det olika innehållet för det kan du åsidosätta innehållet i det kanalbaserade innehållet genom att skapa en kanalspecifik version av sidan med flera kanaler.

Följ dessa steg för att skapa en kanalspecifik version av en sida mellan kanaler i Commerce webbplatsskaparen.

1. I fältet **Kanal** högst upp till höger väljer du **Onlinebutik i flera kanaler**.
1. Öppna sidan för den sida mellan kanaler som du skapade tidigare.
1. I fältet **Kanal** högst upp till höger väljer du den kanal som ska ha specifikt innehåll. Sidredigeraren visar ett meddelande där du uppmanas att skapa en ny variant av sidan.
1. Välj **skapa variant av sidan**.
1. I platsen **Huvud** i sidvariant markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Kampanjbanderoll** och klicka sedan på **OK**.
1. I egenskapsfönstret i modulen **Kampanjbanderoll** välj **Lägg till meddelande** och välj sedan **Meddelande**.
1. I dialogrutan **Meddelande** under **Text**, ange **Kanalspecifik** och välj **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör se kampanjens banderoll med texten "Kanalspecifik".
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

Om du använder bas-URL:en för kanalen och går till URL:en för sidan på den här webbplatsen visas det kanalbaserade innehållet i stället för innehållet i flera kanaler.

## <a name="additional-resources"></a>Ytterligare resurser

[Sätt att lägga till innehåll](add-manage-content.md)

[Ordlista för sidmodell](page-elements-overview.md)

[Dokumentera tillstånd och livscykel](document-states-overview.md)

[Arbeta med publiceringsgrupper](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
