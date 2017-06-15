---
title: "Anpassa användarupplevelsen"
description: "Den här artikeln beskriver hur du kan personanpassa Microsoft Dynamics 365 for Operations."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 689efef6ffa10bbee30cd734f3f09ba20957834d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="personalize-the-user-experience"></a>Anpassa användarupplevelsen

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver hur du kan personanpassa Microsoft Dynamics 365 for Operations.

Det finns många typer av anpassningsalternativ i Microsoft Dynamics 365 for Operations. Vissa anpassningsalternativ är val som du gör i en lista över alternativ på en inställningssida. Vissa anpassningsalternativ är implicita, exempelvis Dynamics 365 for Operations håller koll på bredderna på rutnätskolumner om du justerar dem, och det expanderade/komprimerade läget för snabbflikar. Andra anpassningsalternativ är tydlig. För explicita anpassningsalternativ anger du en interaktiv anpassningsläget och ändra utseende på en sida genom att direkt administrera så att element eller agera på sidan. 

Alla anpassningsalternativ, av något slag, som en användare gör i Dynamics 365 for Operations är endast för den användaren, oavsett vilket företag som användaren interagerar med. Ändringar som en användare gör att en sida inte påverka andra användare i systemet.

## <a name="systemwide-options-for-the-current-user"></a>Systemtäckande alternativ för aktuell användare
I navigeringsfältet hittar du en växel bilden som heter **Inställningar**knappen meny. Öppna **menyn Inställningar** visas ett antal val. Val av **Alternativ** öppnar användarens **Alternativ** sida. Här finns det fyra alternativflikar: **Visuell**, **Inställningar**, **Konto**, och **Arbetsflöde**.

-   **Visuellt:**Används för att välja ett färgtema och standardstorleken för element på dina sidor.
-   **Inställningar:** Här kan du välja standardinställningar för varje gång du öppnar Dynamics 365 for Operations, inklusive företag, första sidan, och standardläge för visa/redigera (som avgör om en sida är låst för visning eller öppnas för redigering varje gång du öppnar den). Du skar finner dessutom språk, tidszon och datum, tid och antal formatalternativ. Slutligen den här sidan innehåller ett antal diverse inställningar som varierar från version till version.
-   **Konto:**Används för att ange ditt användar-ID och andra kontorelaterade inställningar.
-   **Arbetsflöde:**här kan du välja arbetsflödesrelaterade alternativ.

## <a name="implicit-personalizations"></a>Uttryckliga anpassningsalternativ
Uttryckliga anpassningsalternativ är de anpassningsalternativ som du utför enkelt genom att interagera med vissa kontroller som kommer ihåg deras aktuella synliga. 

**Rutnätskolumner:** Du kan justera bredden på en kolumn i en lista genom att välja storlekssortering bar till vänster eller till höger om kolumnrubriken och skjuta den åt vänster eller höger till önskad bredd. Dynamics 365 for Operations kommer att lagra bredden som du vill ha och visa den kolumnen med den bredden varje gång du öppnar sidan med den listan. 

**Snabbflikar:** Vissa sidor har expanderbara avsnitt som kallas snabbflikar. Dynamics 365 for Operations kommer att lagra vilka snabbflikar som du har expanderat och vilka snabbflikar som du har komprimerat. Varje gång du kommer tillbaka till sidan, samma snabbflikens kommer att utökas eller krympas baserat på den senaste gången du använde dem. I denna artikel beskriver vi hur du vill ändra ordning på snabbfliken sektioner. I vissa fall gör komprimering av en snabbflik att prestanda förbättras eftersom Dynamics 365 for Operations inte behöver hämta informationen för snabbfliken förrän snabbfliken expanderas. 

**Faktarutor:** Vissa sidor har ett avsnitt som kallas faktaruta. Den här rutan innehåller skrivskyddad information relaterad till det aktuella ämnet på sidan. Varje avsnitt i faktaruta rutan kallas en faktaruta. Du kan expandera eller komprimera en faktaruta, och Dynamics 365 for Operations sparar inställningarna. I vissa fall gör komprimering av en faktaruta att prestanda förbättras eftersom Dynamics 365 for Operations inte behöver hämta informationen för faktarutan förrän faktarutan expanderas.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Explicit anpassningsalternativ med anpassning toolbar
Varje person och företag har olika perspektiv på vilka data som är viktigast för dem, eller vilka data finnas inte nödvändigt för det sätt de sköter sina affärer. Möjligheten att skräddarsy hur din information beställs, samverkar med eller till och med döljs är nyckeln till att göra Dynamics 365 for Operations till en personlig och givande upplevelse. 

Explicita anpassningar är de anpassningar som du uttryckligen utför med avsikt att ändra utseende och funktion för ett element eller en sida, genom att välja en meny för anpassning. Den vanligaste typen av explicit anpassning är när du högerklickar på ett element och väljer **Anpassa**. (Observera att inte alla element på sidan kan anpassas). När du väljer den här metoden för anpassning visas elementets egenskapsfönster. 

[![Anpassa egenskaper för ett element](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Anpassa ett elements egenskaper på din sida på detta sätt om du bara vill ändra elementets etikett, dölja element så att det inte visas på sidan (detta ändrar inte några uppgifter, det visar helt enkelt ingen information för dig), inkludera informationen i snabbflikens sammanfattningsavsnitt (om elementet är i en snabbflik), hoppa över det här fältet om du gör fel eller gör det så att data inte kan ändras genom att markera det som "redigera inte". 

När du vill flytta eller dölja delar eller göra flera ändringar, kan du med hjälp av anpassningsfönstret toolbar, tillgänglig från elementen egenskapsfönstret genom att välja **anpassa formuläret**. Personalisering toolbar finnas dessutom tillgängligt på blanketten rutan åtgärd, enligt anpassa grupp på **fliken Alternativ** . Välj **anpassa denna blankett,** och du skar ser anpassningen verktygsfältet. 

[![Verktygsfältet Anpassning](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

Verktygsfältet Anpassning har ett antal anpassningsåtgärder. **Verktyget Välj** när du vill välja och ändra egenskaperna för många element, ett i taget. Först genom att klicka på verktyget Välj och klicka sedan på element vars egenskaper du vill redigera. När du väljer ett element, elementet egendom fönster öppnas och du kan ändra egenskaperna för det elementet. Du kan upprepa processen för andra element på din blankett som personanpassning. I vissa fall kan du välja ett element och se att vissa egenskaper inte ändras. Detta innebär att, baserat på det sätt det nuvarande elementet används, kan Dynamics 365 for Operations inte låta dig du ändra egenskapen. Exempelvis du kan skinnet en fält som krävs. 

Välj **verktyget Flytta** när du vill välja och flytta en del till en annan plats inom aktuell grupp av element. (Du kan inte flytta ett inslag utanför dess överordnade grupp). Klicka först flytta verktyget och klicka sedan på det element som du vill flytta. När du klickar på det element som du vill flytta, Dynamics 365 for Operations kommer att skanna formuläret för att förstå vart detta element kan flyttas och skapar en serie av "släppzoner" som visas som en färgad, fet linje bredvid det område där elementet kan släppas när du drar elementet runt inom den aktuella gruppen. 

Välj **Dölj** verktyg att välja och döljer en del. För att dölja en del, välj helt enkelt dölja verktyg och klicka på de element som du vill dölja. När du väljer att dölja verktyg, alla dolda element kommer att göras synliga och visas i en skuggig behållare så att du kan välja elementet för att visa det igen. Välj verktyg för att se hur han sida kommer att se ut med de valda element dolda. Välj **sammanfattning** verktyg när du vill ha en numeriskt värde eller sträng att visa i snabbfliken sammanfattning området. Sammanfattningen verktyg kommer endast att gälla områden som är inneslutna i en snabbfliken avsnitt. När du väljer sammanfattningsverktyget visar Dynamics 365 for Operations alla fält som har valts som sammanfattningsfält genom att innesluta dem i ett nedtonad behållare. Du kan interaktivt lägga till och ta bort fält från ett snabbfliken sammanfattning genom att klicka på fältet. 

Välj verktyget **Hoppa över** för att ta bort ett element från sidan tangentbordstabbsekvens. När du väljer verktyget Hoppa över visas alla tillfället överhoppade element i en nedtonad behållare, så att du kan välja dem igen för att göra dem till en del av tabbsekvensen genom att välja ett överhoppat element. 

Välj **Redigera** verktyg när du vill markera ett element som redigeras eller inte redigerbart. När du väljer Redigera verktyg, alla icke-redigerbara element visas i en skuggig behållare så att du kan välja att göra dem redigerbart. Observera att vissa fält är obligatoriska och kan göras icke redigerbara. Dessa fält visas med ett hänglås-ikonen bredvid dem. 

Välj **Lägg till** för att lägga till ett fält till din sida. Med Lägg till verktyg, du kan inte skapa ett nytt fält, men du kan lägga till fält som är en del av den aktuella sidan definition, men visas inte på sidan. När du väljer Lägg till verktyg, måste du först markera den grupp eller det område där du vill lägga till ett fält. En dialogruta visas en lista med fält som är relaterade till det avsnitt som du har valt. I dialogrutan kan du välja en eller flera fält och klicka på Infoga. Om du senare vill ta bort ett fält som du tidigare har lagts till, upprepa processen, utan helt enkelt rensa fältet som du tidigare angett. 

Välj knappen **Hantera** för att visa en lista över hanteringsalternativ som är relaterade till alla anpassningar för den aktuella sidan. 

Välj **Rensa** för att återställa sidan till dess installerade standardtillstånd. Alla anpassningar på den aktuella sidan kommer att rensas. Det finns ingen Ångra-åtgärd, så använd bara det här alternativet om du är säker på att du vill återställa sidan. 

Välj **Importera** en anpassning från en anpassning som du eller någon annan tidigare skapade för denna sida. Importera en anpassning kommer att rensa bort varje anpassningsalternativ som du har utfört på hela sidan och i stället använda alla anpassningsalternativ från den valda filen. Om du vill spara eller dela en anpassning, då får du välja **alternativet Exportera för** att spara anpassningsalternativ till en fil. 

Välj **Stäng** för att stänga verktygsfältet och återgå till det tidigare interaktiv. 

Med anpassning toolbar, spara är implicit. Din anpassningsalternativ träder i kraft omedelbart när du gör dem och det finns inget behov av att klicka på **knappen Save** . I vissa fall visas en hänglåsikon bredvid ett element när du väljer ett verktyg. Detta innebär att du inte kan ändra egenskaperna som hör till det valda verktyget om sidan ska fungera korrekt. När det gäller anpassning toolbar finnas öppnat, sidan blir icke-interaktivt. Du kan inte ange data eller expandera eller komprimera sektioner.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Explicit anpassning: Lägga till en panel eller lista i en arbetsyta
Några sidor med listor kommer att ha ytterligare en anpassningsfunktion som finns inom dess rutan åtgärd, enligt anpassa grupp på fliken Alternativ. Välj **Lägg till arbetsytan för**att öppna listrutan som ger dig möjlighet att visa informationen i den aktuella listan (filtered och sorterat eller standard) på en arbetsyta som en lista eller en sammanfattning panel (som kan användas för att visa antal objekt i listan). 

[![Lägg till på arbetsyta](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Om du vill lägga till en arbetsyta ska du först sortera eller filtrera listan med den information du vill se på din arbetsyta och sedan välja Lägg till i arbetsytans dialogruta. Välj därefter önskad arbetsyta och välj **lista** från Presentation drop-down listan. När du väljer **Lista**, en dialogruta öppnas där du kan välja vilka kolumner du vill se i listan, och etiketten för listan som visas på arbetsytan. 

Lägg till en sida till en arbetsyta, första filtrera listan för att representera data du vill summerade (eller vill ha snabb tillgång till). Öppna sedan Lägg till arbetsytan tappar dialog. Välj därefter önskad arbetsyta och välj **sida** från presentationen i listrutan. När du väljer **Panel**, en dialogruta öppnas där du kan ange en panel etikett och besluta om panelenkommer att visa en räkning. När den placeras på en arbetsyta, låter panelen dig öppna den aktuella sidan från arbetsytan, och visa en lista över information som är relaterad till panelen. 

När din lista eller panel läggs till en arbetsyta kan du sedan öppna arbetsytan och re-order i listan eller panel inom gruppen placerades.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Explicit anpassning: Lägga till en sammanfattning från en arbetsyta till en panel
Vissa arbetsytor innehåller räknepaneler (paneler med siffror på) som också ska visas på instrumentpanelen. På en arbetsyta, högerklicka på en räknepanel och välj **Anpassa**. Välj **PIN-kod för att instrumentpanelen**. Nästa gång du navigerar till (och uppdatera de valda instrumentpanelen ser du att räkna under arbetsytan navigeringsmeny panel på instrumentpanelen.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Explicit anpassning: Anpassa din instrumentpanel
Instrumentpanelen är ofta den första sidan du ser när du öppnar Dynamics 365 for Operations. Du kan anpassa instrumentpanelen för att döpa din arbetsyta navigation paneler, för att endast visa panelerna som du skulle vilja se, byta panel, eller arrangerar panelerna i den ordning du föredrar att se dem. För att anpassa instrumentpanelen, välj någon panel och högerklicka för att öppna en snabbmeny. På snabbmenyn, välj **Anpassa**. Om den valda panelen är samma som du vill dölja eller ändra namn på eller hoppa över, du kan göra ändringar direkt i fönstret med egenskaper som har visats. Om du vill ordna paneler, välj sedan **anpassa denna form** i fastigheten för att öppna verktygsfältet anpassning. Sedan kan du använda verktyget Flytta till arrangerar panelerna.

## <a name="administration-of-personalization"></a>Administration av anpassning
Det är möjligt att anpassa en sida och dela det med andra användare genom att helt enkelt exportera personliga sida och ber andra användare till navigerar till personliga sida och importera anpassningen fil som du har skapat. Om en användare har administratörsbehörighet, de kan även hantera anpassningsalternativ för andra användare i fönstret **Anpassning inställningssida** . Navigera till b-sidan. I fönstret **Anpassning** sida, du hittar två flikar, en märkt **System** och en märkt**användare**. 

**System:** Det är där du kan inaktivera tillfälligt eller "stänga av" alla anpassningsalternativ i systemet. Detta tar inte bort anpassningsalternativ, instead den återställer alla blanketter till sina standardvärden. Senare kan du återaktivera anpassning så att alla anpassningsalternativ återappliceras för varje användarformulär. Du kan även ta bort alla anpassningsalternativ för alla användare. Observera att när du tar bort anpassningsalternativ, det finns inget sätt att automatiskt återaktivera anpassningsalternativ från systemet. Se till att du har exporterat anpassningsalternativ som du kanske vill senare importera innan detta steg. 

**Användar:** Det är där du bestämmer för varje användare om de kan göra antingen explicit eller implicit anpassning. Du kan också bestämma om varje användare kan utföra explicit eller implicit anpassning på en särskild blankett. Slutligen kan du importera eller exportera eller radera en anpassning för varje användare. 

**Obs!** I sin ursprungliga version kan anpassningsadministration bara hanteras av en användare på användarbasis.



