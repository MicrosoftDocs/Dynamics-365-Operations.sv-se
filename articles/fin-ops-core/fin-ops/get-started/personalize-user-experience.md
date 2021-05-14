---
title: Anpassa användarupplevelsen
description: Det här avsnittet beskriver hur du kan anpassa appen.
author: jasongre
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 764444442aedcbf0934f1c636d7440bc0d277043
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944543"
---
# <a name="personalize-the-user-experience"></a>Anpassa användarupplevelsen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kan anpassa appen och omfattar följande ämnen: 

- **Systemövergripande alternativ** – dessa anpassningsalternativ görs på en inställningssida och är tillgängliga för alla användare. Exempel omfattar färgtema och tidszon. 
- **Begränsad anpassningsåtkomst** – på den här åtkomstnivån sparas de användaråtgärder som är kopplade till typisk sidanvändning automatiskt av appen och återställs nästa gång du besöker sidan. Exempelvis håller appen bredden på rutnätskolumner om du justerar dem, och på det expanderade/komprimerade läget för snabbflikar. 
- **Fullständig anpassningsåtkomst** – på den här åtkomstnivån har användarna tillgång till alla anpassningsfunktioner i appen. De har särskilt tillgång till verktygsfältet **anpassning**. 
- **Dela anpassningar** – användare med fullständig anpassningsbehörighet kan exportera sina sidanpassningar och dela dem med andra användare.
- **Administration av anpassningar** – privilegierade användare kan komma åt administrationssidan **Anpassningar** för att hantera alla anpassningar på befattningsnivå. 

## <a name="system-wide-options-for-the-current-user"></a>System-wide alternativ för aktuell användare

Sidan **användaralternativ** innehåller flera systeminställningar för den aktuella användaren. Dessa alternativ är tillgängliga för alla användare, även användare som inte har fått åtkomst till personlig anpassning. För att öppna sidan **användaralternativ**, välj knappen **inställningar** i navigeringsfältet, och välj sedan **användaralternativ**. Sidan **användaralternativ** har fyra flikar med olika användarinställningar:

- **Visuellt** – Välj en färg för att välja ett färgtema och standardstorleken för element på dina sidor.
- **Inställningar** – Välj standardvärden som används varje gång du öppnar systemet. Dessa värden inkluderar standardföretaget, den första sidan och standardläget visa/redigera. (Det/redigeringsläget bestämmer om en sida är låst för visning eller öppnas för redigering i varje gång du öppnar den.) Den här fliken innehåller också alternativ för språk, tidszon, och datum, tid och nummerformat. Den här fliken innehåller dessutom flera diverse inställningar som kan variera från version till version.
- **Konto:** – Visa eller justera ditt användarnamn och andra kontorelaterade inställningar.
- **Arbetsflöde** – Välj arbetsflöderelaterade alternativ.

Förutom att ändra dina användarinställningar kan du också visa och ta bort dina användardata och anpassningar från sidan **Användaralternativ**. Om du vill se dina användningsdata väljer du **användningsdata** i åtgärdsfönstret. På fliken **Anpassning** kan du visa och hantera personliga ändringar du har gjort på sidor i systemet. På den här fliken kan du också återställa bildtext (dvs. popup-fönstren som introducerar nya systemfunktioner). Du får då ett meddelande om tidigare påträffade funktioner.

> [!NOTE]
> Om funktionen [sparade vyer](saved-views.md) är aktiverad kan du visa och hantera dina anpassningar genom att välja **anpassning** i åtgärdsfönstret på sidan **Användaralternativ**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Begränsad anpassningsåtkomst (tidigare implicita anpassningar)

På nivån **Begränsad anpassningsåtkomst** sparas de användaråtgärder som är kopplade till typisk sidanvändning automatiskt av appen och återställs nästa gång du besöker sidan. Ingen explicit spara-åtgärd krävs. 

Här följer en lista över de åtgärder som ligger under normal sidanvändning och som täcks av begränsad anpassningsåtkomst: 

- **Bredd på rutnätskolumner** – Du kan justera bredden på en kolumn i ett rutnät genom att välja storleksfältet till vänster eller till höger om kolumnrubriken och skjuta det åt vänster eller höger tills kolumnen har önskad bredd. Appen lagrar den bredd som du anger för en kolumn. Sedan ändras storleken på kolumnen till den bredden varje gång du öppnar sidan.
- **Summa för rutnätets sidfot och kolumn** – *(endast tillgängligt när den nya rutnätskontrollen är aktiverad)* du kan bestämma om en summa ska visas längst ned i en numerisk kolumn i ett rutnät och om rutnätssidfoten ska visas. Programmet lagrar dessa data och använder dem nästa gång du öppnar sidan. Mer information finns i [Rutnätsmöjligheter](grid-capabilities.md). 
- **Snabbflikar** – Vissa sidor har expanderbara avsnitt som kallas *snabbflikar*. Appen lagrar information om snabbflikar som du har utökat och komprimerat. Nästa gång du öppnar sidan kommer samma snabbflikar att visas eller döljs, utifrån din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera en snabbflik eftersom appen inte behöver hämta informationen för snabbflikar förrän de expanderas. Såsom beskrivs senare i det här avsnittet kan du också ändra ordning på snabbflikarna på en sida.
- **Faktaboxar** – vissa sidor har rutan **relaterad information** som visar skrivskyddad information som är relaterad till sidans aktuella ämne. Varje avsnitt i rutan **relaterad information** kallas en *faktabox*. Du kan utöka eller komprimera rutan **relaterad information** och du kan också visa eller dölja enskilda faktaboxar. Appen lagrar dessa inställningar. Nästa gång du öppnar sidan kommer rutan **relaterad information** och de enskilda faktaboxar antingen utökas eller komprimeras baserat på din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera ett fönster eller faktabox för **relaterad information** eftersom appen inte behöver hämta informationen för faktaboxar förrän de expanderas.
- **Åtgärdsfönster** – Ett *åtgärdsfönstret* visas längst upp på de flesta sidor. Åtgärdsfönstret innehåller knappar för många av de åtgärder som du kan utföra på den aktuella sidan. Knapparna ordnas ofta på flikarna. Du kan *öppna* hela åtgärdsfönstret och du kan konfigurera den så att den komprimeras som standard. Nästa gång du öppnar sidan kommer åtgärdsfönstret antingen att visas eller döljas, utifrån din senaste interaktion med sidan. Om du har öppnat åtgärdsfönstret visas den sista fliken som du använde.
- **Snabbfilter** – Ett *snabbfilter* visas ovanför många rutnät. Snabbfilter låter dig filtrera rutnät, baserat på en kolumn som du väljer. Appen lagrar den kolumn som du filtrerade på. Nästa gång som du öppnar sidan kommer det rutnätet att använda samma kolumn för filtrering som standard. Du kan sedan välja en annan kolumn att filtrera rutnätet på.
- **Kolumnrubrikfilter** – när du filtrerar ett rutnät med hjälp av *Kolumnrubrikfilter*, kan du ändra filteroperatör för att hitta de data som du vill. Du kan exempelvis ändra operatorn från **börjar med** till **exakt**. Varje gång du använder ett kolumnrubrikfilter och ändrar filteroperatör kommer appen att spara ändringen. Nästa gång du filtrerar efter den kolumnen kommer filteroperatören att återställas.
- **Navigeringsfönstret** – du kan öppna *navigeringsfönstret* genom att välja knappen **Expandera navigeringsfönstret** längst upp till vänster på en sida. (Den här knappen kallas ibland _**Meny**-knappen_, *hamburgare*, *hamburgarmeny* eller *hamburgarknappen*.) Du kan öppna navigeringsfönstret eller du kan hålla det komprimerat som standard. När du öppnar navigeringsfönstret håller appen det öppet tills du komprimerar det.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Fullständig anpassningsåtkomst (tidigare explicita anpassningar)

På nivån **Fullständig anpassningsåtkomst** har användarna tillgång till alla anpassningsfunktioner i appen. Eftersom olika personer och företag har olika behov när de interagerar med appen, särskilt i termer av använda fält, innehåller anpassningsverktyg som gör det möjligt för användare och organisationer att skräddarsy det sätt som informationen beställs och interageras inom appen. Dessa funktioner är viktiga för att tillhandahålla enklare, optimerade upplevelser i appen som är skräddarsydda för dig och din organisation. 

Om funktionen [Sparade vyer](saved-views.md) är aktiverad krävs ett uttryckligt sparande för att ändringarna i användarupplevelsen för en viss vy ska bibehållas. När funktionen **Sparade vyer** är inaktiverad sparas ändringarna automatiskt.

Följande avsnitt beskriver omfattningen av de anpassningsfunktioner som är tillgängliga för användarna på nivån **fullständig anpassningsåtkomst**. Här följer några av dessa funktioner:

- Alternativ för snabbmeny
- Verktygsfält för **anpassning**
- Lägga till paneler, listor och länkar till arbetsytor
- Lägga till en sammanfattning från en arbetsyta till en panel
- Anpassa instrumentpanelen

### <a name="shortcut-menu-options"></a>Alternativ för snabbmeny

Snabbmenyer innehåller ett sätt för att uttryckligen ändra en sidas gränssnitt så att den passar bättre till dina behov eller ditt företags organisation. (EN snabbmeny kallas också en *högerklicksmeny* eller *kontextmenyn*.)

Några av de vanligaste och mest viktiga ändringar som kan göras till en sida visas direkt som ett alternativ på en snabbmeny. Om du t.ex. vill lägga till eller dölja kolumner i ett rutnät, bara högerklicka på en kolumnrubrik och markera **Infoga kolumner** eller **dölj denna kolumn**.

Dessutom är de vanligaste typerna av anpassning tillgängliga genom att högerklicka på ett element och sedan välja **anpassa**. (Observera att inte alla element på sidan kan anpassas). När du använder den här metoden för anpassning visas elementets *egenskapsfönster*.

![Anpassa egenskaper för ett element](./media/cli-element-property-window.png)

Du kan använda egenskapsfönstret för att anpassa ett element på följande sätt:

- Ändra elementets etikett.
- Dölj elementet så att den inte visas på sidan. Informationen i det här fältet tas inte bort eller ändras. Informationen visas bara inte på sidan längre.
- Inkludera informationen i sammanfattningsavsnittet på snabbfliken (om elementet på en snabbflik).
- Hoppa över fältet så att det inte får fokus när du tabbar genom sidan.
- Förhindra att data i fältet redigeras (för alla poster).
- Ange ett fält som krävs för inmatning av data. Om inget värde har angetts i det här fältet kommer det att visas med en röd kantlinje och en asterisk för att ange det här läget. Det här alternativet är bara tillgängligt från början i version 10.0.11 när funktionerna [Sparade vyer](saved-views.md) och **Tilldela fält enligt önskemål med anpassning** är aktiverade.

Egenskapsfönstret kan omfatta andra anpassningsfunktioner, beroende på vilket element. Exempelvis egenskapsfönstret för en panel kan låta dig flytta upp den panelen till en instrumentpanel och egenskapsfönster för element på standardpanelen kan låta dig skapa ett nytt anpassat arbetsområde.

### <a name="personalization-toolbar"></a>Verktygsfält för anpassning

Om du vill göra flera ändringar på en sida eller göra ändringar som inte är tillgängliga genom andra metoder (till exempel ändra ordning på element), kan du använda verktygsfältet **anpassning**. För att öppna verktygsfältet **anpassning**, följ något av dessa steg:

- Välj **Ctrl+Shift+P** från alla element på sidan.
- Välj **anpassa den här sidan** i ett elements egenskapsfönster.
- Välj **anpassa den här sidan** i gruppen **Anpassa** på fliken **Alternativ** på en sidas åtgärdsfönster.
- Välj knappen **inställningar** (kugghjulssymbolen) i navigeringsfältet och välj sedan **anpassa**.

[![Verktygsfält för anpassning](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigera på sidan

När verktygsfältet **anpassning** är öppet är den underliggande sidan skrivskyddad (d.v.s. det går inte att redigera data), men den är fortfarande interaktiv. Du kan t.ex. visa eller dölja rutan **relaterad information**, växla flikar och visa eller dölja avsnitt, på samma sätt som du vanligtvis utför dessa åtgärder på sidan. Om du vill använda en anpassning till ett komprimerbart avsnitt eller flik (till exempel för att dölja en snabbflik) behöver du bara välja knappen bredvid det avsnittet eller den fliken när det får tangentbordfokus eller när du för muspekaren över den.

#### <a name="personalization-tools"></a>Verktyg för anpassning

Följande verktyg är tillgängliga i fältet verktygsfältet **anpassning**:

- Använd verktyget **Välj** för att välja och öppna ett elements egenskaper. Om du vill använda det här verktyget väljer du knappen **Välj** i verktygsfältet och väljer sedan det önskade elementet. Elementets egenskapsfönster visas och du kan ändra egenskaperna för det elementet. Du kan upprepa processen för andra element som kan anpassas på den sidan. Observera att vissa anpassningsegenskaper kanske inte är tillgängliga i vissa fall. Exempelvis kan du inte låsa ett fält som krävs.
- Använd verktyget **Dölj** verktyg för att dölja ett element på sidan. Om du vill använda det här verktyget väljer du knappen **Dölj** i verktygsfältet och väljer sedan det element som ska döljas. När du väljer verktyget **Dölj** kommer alla element som döljs för närvarande vara synliga och visas i en skuggad behållare. Du kan sedan göra ett element synligt genom att markera det. Om du vill se hur sidan ser ut när elementen är dolda, växlar du till ett annat anpassningsverktyg eller stäng verktygsfältet för anpassning.
- Använd verktyget **Lägg till fält** för att lägga till ett fält till din sida. När du använder det här verktyget kan du bara lägga till fält som är en del av siddefinitionen. Information om hur du skapar nya fält som inte ingår i definitionen av sidan finns i [Skapa och arbeta med anpassade fält](user-defined-fields.md). När du har valt knappen **Lägg till fält** på verktygsfältet måste du först välja det rutnät eller avsnitt där du vill lägga till ett fält. En dialogruta visar en lista med fält som är relaterade till det valda rutnätet eller avsnittet. Välj ett eller flera fält i dialogrutan och välj sedan **Uppdatera**. Om du vill ta bort ett fält som du tidigare lade du upprepar hela processen och ta bort markeringen i fältet i dialogrutan.
- Använd verktyget **Flytta** för att flytta ett element till en annan plats inom aktuell grupp av element. Observera att du inte kan flytta ett element utanför dess överordnade grupp. Om du vill använda det här verktyget väljer du knappen **Flytta** i verktygsfältet och väljer sedan det element som ska flyttas. När du markerar ett element kommer appen att bestämma platser som elementet kan flyttas till. Dessa platser kallas *släppzoner*. När du drar runt elementet inom den aktuella gruppen visas varje ”släppzon” med färgade rader i fetstil bredvid området där elementet kan släppas.
- Använd **Hoppa över** för att ta bort ett element från sidan tangentbordstabbsekvens. När du väljer knappen **Hoppa över** på verktygsfältet kommer alla element som för närvarande hoppas över att visas i en skuggad behållare. Du kan ta bort eller lägga till fält interaktivt i tabbsekvensen.
- Använd verktyget **Visa i rubrik** när du vill att ett fält ska visas i sammanfattningen på snabbfliken. När du väljer knappen **Visa i rubrik** i verktygsfältet har alla fält som har valts som sammanfattningsfält visas i en skuggad behållare. Du kan interaktivt lägga till fält på snabbfliken sammanfattning och ta bort fält från sammanfattning genom att markera fälten.
- Använd verktyget **Kräv** för att tilldela ett element som krävs för inmatning av data. När du väljer knappen **Kräv** på verktygsfältet kommer alla element som har anpassats för att krävas att visas i en skuggad behållare. Du kan sedan göra dem inte obligatoriska igen. Det här alternativet är tillgängligt version 10.0.12 och senare när funktionen **Tilldela fält enligt önskemål med anpassning** är aktiverade.
- Använd verktyget **Låsa** för att markera ett element som antingen redigerbart eller inte redigerbart. När du väljer knappen **Låsa** på verktygsfältet kommer alla element som för närvarande icke är redigerbara att visas i en skuggad behållare. Du kan sedan göra dem redigerbara igen. Observera att vissa fält är obligatoriska och kan göras icke redigerbara. Ett hänglåssymbol visas bredvid dessa fält.
- Använd verktyget **Lägg till en app från Power Apps** under infoga i ett program som har skapats med hjälp av Microsoft Power Apps på sidan. För detaljerad information om hur du bäddar in en app från Power Apps på en sida finns i [Bädda in appar från Power Apps](embed-power-apps.md). Det här alternativet är bara tillgängligt om funktionen [sparade vyer](saved-views.md) är inaktiverad.
- Använd knappen **Lägg till en app** för att bädda in en app, antingen en skapad från Microsoft Power Apps eller en tredje part på sidan. Det här alternativet är bara tillgängligt om funktionen [sparade vyer](saved-views.md) är aktiverad. 
- Använd verktyget **Rensa** för att återställa sidan till dess installerade standardtillstånd. Alla anpassningar på den aktuella sidan kommer att rensas. Du kan inte ångra denna åtgärd. Använd därför endast detta verktyg om du är säker på att du vill återställa sidan. När funktionen **Sparade vyer** är aktiverad rensar det här verktyget anpassningarna för den aktuella vyn.
- Använd verktyget **Importera** för att ladda en anpassning från en fil som du eller någon annan tidigare skapade. 

    - När funktionen **Sparade vyer** är inaktiverad kan du välja om du vill lägga till eller ersätta befintliga anpassningar med de anpassningar som importeras för sidan. Du kan inte ångra denna åtgärd. När du har importerat anpassningar måste du därför manuellt rensa eller ångra de ändringar som du inte vill ha.
    - När funktionen **Sparade vyer** aktiveras blir de importerade anpassningarna en vy på sidan. Om vyn redan finns kan du hoppa över importen, ersätta den aktuella vyn som har samma namn eller byta namn på den importerade vyn.

- Använd verktyget **exportera** om du vill spara dina anpassningar för sidan till en fil. Du kan sedan dela dina anpassningar med andra användare. Användarna behöver bara importera filen med dina anpassningar för sidan. När funktionen **Sparade vyer** är aktiverad sparar det här verktyget din aktuella vy till en fil för delning.
- Välj knappen **Stäng** för att stänga verktygsfältet **Anpassning** och återställa sidan till sin tidigare interaktiva status.

När verktygsfältet **anpassning** används kommer dina anpassningar att börja gälla så fort du gör dem. Om funktionen [sparade vyer](saved-views.md) är aktiverad måste du uttryckligen spara anpassningar i en vy som du väljer.

I vissa fall visas en hänglåssymbol bredvid ett element när du väljer ett verktyg. Den här symbolen visar att du inte kan ändra egenskaperna för elementet som är relaterade till det valda verktyget eftersom ändringar i de egenskaperna som förhindrar att sidan fungerar som den ska.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Lägga till paneler, listor och länkar till arbetsytor

För vissa sidor som innehåller listor är anpassningsfunktionen **Lägg till på arbetsyta** tillgänglig i gruppen **Anpassa** på fliken **alternativ** i åtgärdsfönstret. Med den här funktionen kan du skicka relevant information från den aktuella listan till en viss arbetsyta. Informationen som visas på arbetsytan kan antingen baseras på hela listan eller en filtrerad och sorterad version av listan. Du kan också ange om informationen ska visas på arbetsytan som en lista, en sammanfattande sida som kan visa antalet objekt i listan eller en länk.

> [!NOTE]
> Om funktionen [sparade vyer](saved-views.md) är aktiv länkas det innehåll som du flyttar till en arbetsyta direkt till en vy. Frågan används för att hämta data på arbetsytan och på motsvarande sida eller länk i arbetsytan öppnas sidan i vyn så att frågans fråga och anpassningar tillämpas på den. Om vyn uppdateras ändras motsvarande element i arbetsytan till den nya vydefinitionen.

[![Lägg till på arbetsyta](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lägg till en lista i en arbetsyta, sortera först eller filtrera listan på sidan så att den visar information som du vill ska visas på arbetsytan. (Om funktionen **Sparade vyer** är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Lista**. När du har valt **konfigurera**, visas en dialogruta, där du kan välja vilka kolumner som ska visas i listan i arbetsytan. Du kan också ange etiketten som ska användas för i listan i arbetsytan.
- För att lägga till en panel till en arbetsyta, filtrera först listan på sidan så att den visar de data som du vill sammanfatta eller som vill ha snabb tillgång till. (Om funktionen **Sparade vyer** är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Panel**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för panelen på arbetsytan. Du kan också ange om panelen ska visa ett antal. När du har lagt till en panel i arbetsytan kan du välja den för att öppna den aktuella sidan från arbetsytan. Du kan sedan visa den filtrerade listan som är kopplad till panelen.
- Om du vill lägga till en länk till en arbetsyta filtrerar du först listan så att den visar de data du är intresserad av. (Om funktionen **Sparade vyer** är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Länk**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för länken. Du kan också ange en etikett för ett nytt avsnitt som innehåller länken.

När du har lagt till en lista, panel eller länk har lagts till en arbetsyta kan du öppna den arbetsytan och ordna om elementen i den som du vill.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Lägga till en sammanfattning från en arbetsyta till en panel

En del arbetsytor innehåller antalet paneler (detta är paneler som har nummer på dem) och vill kanske vill att dessa paneler ska visas på instrumentpanelen. I arbetsytan högerklickar du på en räkneverkspanel, väljer **Anpassa** och sedan **Fäst på instrumentpanelen** i panelens egenskapsfönster. Nästa gång som du öppnar (och uppdaterar) den valda instrumentpanelen kommer antalet att visas under navigeringspanelen för den arbetsytan. Du kan välja att gå direkt till de data som representerar antalet.

### <a name="personalizing-your-dashboard"></a>Anpassa instrumentpanelen

Instrumentpanelen är ofta den första sida som du ser när du öppnar appen. Den kan anpassas på samma sätt som andra sidor i systemet, med hjälp av samma mekanismer som beskrivs tidigare i det här avsnittet. 

> [!WARNING]
> När du döljer innehåll på instrumentpanelen för närvarande är det viktigt att du direkt anpassar en panel, inte utrymmet runt det. Om du döljer gruppen runt en panel kan det bli oväntade resultat om fler paneler läggs till senare, eller om systemet växlas till ett annat språk.

En unik anpassningskapacitet som är tillgänglig på instrument panelen är möjligheten att lägga till paneler. 

- Om funktionen **Helsideappar** är inaktiverad, lägger du till en ny panel genom att högerklicka på ett element på instrumentpanelen och sedan välja **Lägg till en arbetsyta**. En ny panel i arbetsytan skapas längst ned på instrumentpanelen. Du kan byta namn på denna nya arbetsytapanel som helst. Du kan också lägga till listor, rutor och länkar till arbetsytan enligt avsnittet [Lägga till paneler, listor och länkar till arbetsytor](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace) i det här ämnet.
- Om funktionen **Helsideappar** är aktiverad, lägger du till en ny panel genom att högerklicka på ett element på instrumentpanelen och sedan välja **Lägg till en app**. I dialogrutan väljer du om du vill lägga till en panel för en ny arbetsyta eller en sida som har innehåll från Power Apps eller en webbplats. Följ sedan stegen för att konfigurera alternativet som du har valt. En ny panel skapas längst ned på instrumentpanelen. 

## <a name="sharing-personalizations"></a>Dela anpassningar

När du anpassar en sida finns det ett antal metoder du kan använda dig av i syfte att dela dina anpassningar med andra användare: I följande lista är metoderna sorterade i ordning, från de högst rekommenderade till lägst rekommenderade.

1. Publicera vyer för användarna.
2. Kopiera vyer eller anpassningar till användarna.
3. Exportera och importera vyer eller anpassningar.

### <a name="publish-views-to-users"></a>Publicera vyer för användarna

Om funktionen [Sparade vyer](saved-views.md) är aktiverad – och sidan har stöd för vyer – är det bästa sättet att dela anpassningar med andra användare att publicera vyn för användare med en eller flera säkerhetsroller. För mer information, se [Publicera vyer](saved-views.md#publishing-views).

### <a name="copy-views-or-personalizations-to-users"></a>Kopiera vyer eller anpassningar till användarna

Om funktionen [Sparade vyer](saved-views.md) är inaktiverad, eller om sidan inte har stöd för vyer, bör du kopiera anpassningarna mellan användarna. Denna metod är bara tillgänglig för privilegierade användare (till exempel systemadministratörer). Administratörer kan dock söka efter en viss användares personliga anpassning i systemet (inklusive användarens personliga vy, om sparade vyer har aktiverats) och kopiera konfigurationen till andra användare.

Om sparade vyer har aktiverats följer du dessa steg för att kopiera personliga anpassningar.

1. Gå till **Systemadministration \> Inställningar \> Anpassning**.
2. Följ de här stegen när du vill kopiera personliga vyer:

    1. Välj **Personliga vyer**.
    2. Välj önskade vyer i listan.
    3. Markera **Kopiera till användare**.
    4. Markera de användare som du vill fördela vyerna till.

    Följ anvisningarna nedan om du vill kopiera anpassningar på sidor som inte har stöd för vyer:

    1. Välj **Användarinställningar**.
    2. Välj den användare som har den anpassning som du vill distribuera.
    3. Välj **Hantera alla anpassningar**.
    4. Välj önskade anpassningar i listan.
    5. Markera **Kopiera till användare**.
    6. Markera de användare som du vill distribuera anpassningarna till.

Om sparade vyer har aktiverats följer du dessa steg för att kopiera en anpassning.

1. Gå till **Systemadministration \> Inställningar \> Anpassning**.
2. Välj **Tillämpa**.
3. Markera de användare som du vill distribuera anpassningen till.
4. Välj **Befintlig personanpassning**.
5. Hitta och välj den (enskilda) personanpassning som du är intresserad av.
6. Välj **OK**.

### <a name="export-and-import-views-or-personalizations"></a>Exportera och importera vyer eller anpassningar

Ett annat sätt att dela anpassningar är genom export och import. Enskilda användare, eller en administratör som agerar för deras räkning, kan använda den här metoden för att exportera sina anpassningar eller vyer och sedan ge den exporterade filen till andra användare som ska importeras. Alternativt kan användare ge sina exporterade personanpassningar till en användare som har administratörsbehörighet, och den användaren kan sedan använda administrationssidan **Anpassning** för att tillämpa personanpassningsfilen på många användare samtidigt.

#### <a name="export"></a>Export

I allmänhet kan du exportera en av dina egna vyer eller anpassningar genom att öppna lämplig sida, öppna verktygsfältet **Personanpassning** och sedan välja **Exportera**. Mer information om verktygsfältet finns i avsnittet [Verktygsfält för anpassning](#personalization-toolbar) tidigare i det här avsnittet. Om [sparade vyer](saved-views.md) har aktiverats kan du även gå till **Inställningar \> Användaralternativ \> Anpassningar** för att visa en lista över samtliga dina anpassningar i systemet. Därifrån kan du välja vilka vyer eller personanpassningar som ska exporteras, och sedan välja **Exportera**.

Dessutom kan administratörer exportera andra användares passningar genom att följa stegen nedan.

1. Gå till **Systemadministration \> Inställningar \> Anpassningar**.
2. På fliken **Användare** väljer du önskad användare.
3. Hitta och välj den vy eller anpassning som du är intresserad av.
4. Välj **Exportera**.

#### <a name="import"></a>Import

Om du vill importera en vy eller anpassning öppnar du bara verktygsfältet **Anpassning** och väljer **Importera**. Dessutom kan administratörer importera en fil och omedelbart ge den till en eller flera användare.

Om sparade vyer har aktiverats följer du dessa steg.

1. Gå till **Systemadministration \> Inställningar \> Anpassningar**.
2. I åtgärdsfönstret väljer du **Importera vyer \> Användarvyer**.
3. Välj importläget.

    - **Markera specifika användare** – Ge vyn eller anpassningen till valda användare.
    - **Importera i befintligt skick** – Importera vyn eller personanpassningen till samma användare som exporterade den.

4. Välj **Bläddra** och leta sedan upp och välj den anpassning du vill importera.
5. Välj **Nästa**.
6. Om du väljer **Välj specifika användare** i steg 3 ska du markera de användare som anpassningen ska importeras till.
7. Välj **Importera**.
8. Lös konflikter vid behov.

Om sparade vyer inte har aktiverats följer du dessa steg.

1. Gå till **Systemadministration \> Inställningar \> Anpassningar**.
2. Välj **Tillämpa**.
3. Markera de användare som du vill distribuera anpassningen till.
4. Välj **Importera anpassningar från en fil**.
5. Välj **Bläddra** och leta sedan upp och välj den anpassning du vill importera.
6. Välj **OK**.

## <a name="administration-of-personalizations"></a>Administration av anpassning

Sidan **Anpassning** är det centrala navet för hantering av anpassningar på organisationsnivå. Innehållet och funktionerna på den här sidan beror på om funktionen **Sparade vyer** har aktiverats.

Information om kunder som har aktiverat funktionen **Sparade vyer** finns i avsnittet "Hantera vyer globalt" i ämnet [Sparade vyer](saved-views.md).

För kunder som inte har aktiverat funktionen [sparade vyer](saved-views.md) har den här sidan fyra flikar:

- **Tillämpa** – Du kan importera eller välja en anpassning för en eller flera användare. Om du vill använda en anpassning till en eller flera användare, markerar du först en roll och användare som har rollen. Välj sedan en befintlig anpassning som gäller för de valda användare eller importera en anpassningsfil. Anpassningen valideras och gäller för de alla valda användare nästa gång de öppnar den markerade sidan.

- **Rensa** – Du kan rensa alla anpassningar för arbetsyta för en eller flera användare. Välj först en sida eller arbetsyta för att se en lista över de användare som har anpassat den. Sedan väljer du de användare vars anpassningar för den aktuella sidan eller arbetsytan ska avmarkeras och välj **Rensa**. Alla anpassningar som de valda användarna har kopplat till den valda sidan eller arbetsytan tas bort. Denna åtgärd kan inte ångras. Om en anpassning sparades för sidan eller arbetsytan, kan den anpassningen emellertid återimporteras.

- **Användare** – Välj en användare för att visa listan över sidor som användaren har anpassat. Du kan sedan aktivera eller inaktivera den valda användarens förmåga att använda anpassningar för specifika sidor eller för hela systemet. D kan också importera, exportera eller rensa anpassningar för denna användare. Du kan dessutom återställa en användares bildtexter för funktioner. I detta fall, om användaren tidigare stängde alla popup-fönster som introducerar nya funktioner visas det i detta fall igen nästa gång användaren påträffar dessa funktioner.

- **System** – Du kan temporärt inaktivera alla anpassningar för samtliga användare i systemet. I det här fallet tas alla anpassningar bort för alla användare, och alla sidor återställs till standardtillståndet. Om du senare aktiverar anpassningen igen kommer alla anpassningar att återappliceras. Du kan också ta bort alla anpassningar permanent för samtliga användare i systemet. Det går inte att återställa anpassningar som har tagits bort. Se därför till att du har exporterat den här uppgiften för att exportera alla anpassningar som du kanske vill ha senare.

## <a name="personalizing-inventory-dimensions"></a>Anpassning av lagerdimensioner

När du anpassar inställningarna för lagerdimensionerna på en sida, beakta inställningarna som har skapats med hjälp av alternativet **Visa dimension**. Du använder till exempel anpassning om du vill dölja en kolumn för batchnummerdimensionen men kolumnen visas nästa gång som sidan öppnas. Detta händer på grund av att inställningarna för **Dimensionsvisning** kontrollerar de lagerdimensionskolumner som visas. Inställningarna för **Dimensionsvisning** tillämpas på alla sidor och åsidosätter eventuella anpassade inställningar av lagerdimensionsfälten på enskilda sidor.

Därför i det föregående exemplet om du inte vill att kolumnen för batchnummer lagerdimensionen ska visas på en sida, måste du avmarkera dimensionen som en del av alternativet **visa mått** för den sidan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
