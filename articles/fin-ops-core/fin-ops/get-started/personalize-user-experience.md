---
title: Anpassa användarupplevelsen
description: Det här avsnittet beskriver hur du kan anpassa appen.
author: jasongre
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac8f154fdf892553f69d135727589bf13efd6076
ms.sourcegitcommit: 34395464ec80cea800b953eae49af579d436fc1b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935475"
---
# <a name="personalize-the-user-experience"></a>Anpassa användarupplevelsen

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan anpassa appen.

Det finns tre grundläggande klasser för anpassningar.

- Anpassningar som har gjorts på sidan Inställningar. Exempel omfattar färgtema och tidszon.
- Anpassningar som är relaterade till sidanvändning. Dessa anpassningsalternativ kallas *implicita* anpassningar. Exempelvis håller systemet koll på bredden på rutnätskolumner om du justerar dem, och på det expanderade/komprimerade läget för snabbflikar.
- Anpassningar som en användare gör för utseendet på en sida genom att ändra hur ett element visas eller fungerar på den sidan, ofta genom ett interaktivt anpassningsläge. Dessa anpassningsalternativ kallas *explicita* anpassningar. Användaren kan till exempel lägga till, dölja eller ordna om element på sidan.

Alla anpassningsalternativ som en användare gör i gäller endast för den användaren, oavsett typen av anpassning eller vilket företag som användaren för närvarande interagerar med. Ändringar som en användare gör att en sida inte påverka andra användare i systemet.

## <a name="system-wide-options-for-the-current-user"></a>System-wide alternativ för aktuell användare

Sidan **användaralternativ** innehåller flera systeminställningar för den aktuella användaren. För att öppna sidan **användaralternativ**, välj knappen **inställningar** (växel-symbol) i navigeringsfältet, och välj sedan **användaralternativ**. Sidan **användaralternativ** har fyra flikar med olika användarinställningar:

- **Visuellt** - Välj en färg för att välja ett färgtema och standardstorleken för element på dina sidor.
- **Inställningar** – Välj standardvärden som används varje gång du öppnar systemet. Dessa värden inkluderar företaget, den första sidan och standardläget visa/redigera. (Det/redigeringsläget bestämmer om en sida är låst för visning eller öppnas för redigering i varje gång du öppnar den.) Den här fliken innehåller också alternativ för språk, tidszon, och datum, tid och nummerformat. Den här fliken innehåller dessutom flera diverse inställningar som kan variera från version till version.
- **Konto:** - Justera ditt användarnamn och andra kontorelaterade inställningar.
- **Arbetsflöde** – Välj arbetsflöderelaterade alternativ.

Förutom att ändra dina användarinställningar kan du också använda sidan **Användaralternativ** för att visa och ta bort dina användardata och anpassningar. Välj bara **Användningsdata** i åtgärdsfönstret.

När du använder appen sparas många av dina val för att underlätta för dig när du använder systemet i framtiden. På fliken **Anpassning** kan du visa och hantera personliga ändringar du har gjort på sidor i systemet. På den här fliken kan du också återställa bildtext (dvs. popup-fönstren som introducerar nya systemfunktioner). Du får då ett meddelande om tidigare påträffade funktioner.

> [!NOTE]
> Om funktionen [sparade vyer](saved-views.md) är aktiverad kan du visa och hantera dina anpassningar genom att välja **anpassning** i åtgärdsfönstret på sidan **Användaralternativ**.

## <a name="implicit-personalizations"></a>Uttryckliga anpassningsalternativ

Uttryckliga anpassningsalternativ är de anpassningsalternativ som du utför enkelt genom att interagera med vissa kontroller som lagrar deras aktuella synliga tillstånd.

- **Rutnätskolumner:** - Du kan justera bredden på en kolumn i ett rutnät genom att välja storleksfältet till vänster eller till höger om kolumnrubriken och skjuta det åt vänster eller höger tills kolumnen har önskad bredd. Appen lagrar den bredd som du anger för en kolumn. Sedan ändras storleken på kolumnen till den bredden varje gång du öppnar sidan med det rutnätet.
- **Snabbflikar** - Vissa sidor har expanderbara avsnitt som kallas *snabbflikar*. Appen lagrar information om snabbflikar som du har utökat och komprimerat. Nästa gång du öppnar sidan kommer samma snabbflikar att visas eller döljs, utifrån din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera en snabbflik eftersom appen inte behöver hämta informationen för snabbflikar förrän de expanderas. Såsom beskrivs senare i det här avsnittet kan du också ändra ordning på snabbflikarna på en sida.
- **Faktarutor** – vissa sidor har rutan **relaterad information** som visar skrivskyddad information som är relaterad till sidans aktuella ämne. Varje avsnitt i rutan **relaterad information** kallas en *faktabox*. Du kan utöka eller komprimera rutan **relaterad information** och du kan också visa eller dölja enskilda faktarutor. Appen lagrar dessa inställningar. Nästa gång du öppnar sidan kommer rutan **relaterad information** och de enskilda faktarutorna antingen utökas eller komprimeras baserat på din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera en faktabox eftersom appen inte behöver hämta informationen för faktaboxar förrän de expanderas.
- **Åtgärdsfönster** – Ett *åtgärdsfönstret* visas längst upp på de flesta sidor. Åtgärdsfönstret innehåller knappar för många av de åtgärder som du kan utföra på den aktuella sidan. Knapparna ordnas ofta på flikarna. Du kan öppna hela åtgärdsfönstret och du kan konfigurera den så att den komprimeras som standard. Nästa gång du öppnar sidan kommer åtgärdsfönstret antingen att visas eller döljas, utifrån din senaste interaktion med sidan. Om du har öppnat åtgärdsfönstret visas den sista fliken som du använde.
- **Snabbfilter** – Ett *snabbfilter* visas ovanför många rutnät. Snabbfilter låter dig filtrera rutnät, baserat på en kolumn som du väljer. Appen lagrar den kolumn som du filtrerade på. Nästa gång som du öppnar sidan med det rutnätet kommer rutnätet att filtreras på samma kolumn. Du kan sedan välja en annan kolumn att filtrera rutnätet på.
- **Kolumnrubrikfilter** – när du filtrerar ett rutnät med hjälp av *Kolumnrubrikfilter*, kan du ändra filteroperatör för att hitta de data som du vill. Du kan exempelvis ändra operatorn från **börjar med** till **exakt**. Varje gång du använder ett kolumnrubrikfilter och ändrar filteroperatör kommer appen att spara ändringen. Nästa gång du filtrerar efter den kolumnen kommer filteroperatören att återställas.
- **Navigeringsfönstret** – du kan öppna *navigeringsfönstret* genom att välja knappen **Expandera navigeringsfönstret** längst upp till vänster på en sida. (Den här knappen kallas ibland _**Meny**-knappen_, *hamburgare*, *hamburgarmeny* eller *hamburgarknappen*.) Du kan öppna navigeringsfönstret eller du kan hålla det komprimerat som standard. När du öppnar navigeringsfönstret håller appen det öppet tills du komprimerar det.

## <a name="explicit-personalizations"></a>Uttryckliga anpassningsalternativ

Olika personer och företag har ett annorlunda perspektiv på de viktigaste data eller data som inte behövs för hur de sköta verksamheten. Du kan skräddarsy hur informationen beställs och interageras med. Du kan också ange att viss information ska döljas. Dessa funktioner är viktiga för en personlig och produktiv upplevelse och är exempel på uttryckliga anpassningar. Uttryckliga anpassningar är de anpassningar som du uttryckligen utför med avsikt att ändra utseende eller funktion för ett element eller en sida.

### <a name="shortcut-menu-options"></a>Alternativ för snabbmeny

Snabbmenyer innehåller några sätt för att uttryckligen ändra en sida så att den passar bättre till dina behov eller ditt företags behov. (EN snabbmeny kallas också en *högerklicksmeny* eller *kontextmenyn*.)

Några av de vanligaste och mest viktiga ändringar som kan göras till en sida visas direkt som ett alternativ på en snabbmeny. Om du t.ex. startar i Plattformsuppdatering 17, om du vill lägga till eller dölja kolumner i ett rutnät, bara högerklicka på en kolumnrubrik och markera **lägg till kolumner** eller **dölj denna kolumn**.

Dessutom är de vanligaste typerna av uttrycklig anpassning tillgängliga genom att högerklicka på ett element och sedan välja **anpassa**. (Observera att inte alla element på sidan kan anpassas). När du använder den här metoden för anpassning visas elementets egenskapsfönster.

![Anpassa egenskaper för ett element](./media/personalization-element-properties.png)

Du kan använda egenskapsfönstret för att anpassa ett element på följande sätt:

- Ändra elementets etikett.
- Dölj elementet så att den inte visas på sidan. Informationen i det här fältet tas inte bort eller ändras. Informationen visas bara inte på sidan längre.
- Inkludera informationen i sammanfattningsavsnittet på snabbfliken (om elementet på en snabbflik).
- Hoppa över fältet så att det inte får fokus när du tabbar genom sidan.
- Förhindra att data i fältet redigeras (för alla poster).

Egenskapsfönstret kan omfatta andra anpassningsfunktioner, beroende på vilket element. Exempelvis egenskapsfönstret för en panel kan låta dig flytta upp den panelen till en instrumentpanel och egenskapsfönster för en instrumentpanel låter dig skapa en ny arbetsyta på den här instrumentpanelen.

### <a name="the-personalization-toolbar"></a>Verktygsfält för anpassning

Om du vill göra flera ändringar på en sida eller göra ändringar som inte är tillgängliga genom andra metoder (till exempel ändra ordning på element), kan du använda verktygsfältet **anpassning**. För att öppna verktygsfältet **anpassning**, följ något av dessa steg:

- Välj **anpassa det här formuläret** i ett elements egenskapsfönster.
- Välj **anpassa den här sidan** i gruppen **Anpassa** på fliken **Alternativ** på en sidas åtgärdsfönster.
- Välj knappen **inställningar** (kugghjulssymbolen) i navigeringsfältet och välj sedan **anpassa**.

[![Verktygsfält för anpassning](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navigera på sidan

När verktygsfältet **anpassning** är öppet är den underliggande sidan skrivskyddad (d.v.s. det går inte att redigera data), men den är fortfarande interaktiv. Du kan t.ex. visa eller dölja rutan **relaterad information**, växla flikar och visa eller dölja avsnitt, på samma sätt som du vanligtvis utför dessa åtgärder på sidan. Om du vill använda en anpassning till ett komprimerbart avsnitt eller flik (till exempel för att dölja en snabbflik) behöver du bara välja knappen bredvid det avsnittet eller den fliken när det får tangentbordfokus eller när du för muspekaren över den.

#### <a name="personalization-tools"></a>Verktyg för anpassning

Följande verktyg är tillgängliga i fältet verktygsfältet **anpassning**:

- Använd verktyget **Välj** för att välja och öppna ett elements egenskaper. Om du vill använda det här verktyget väljer du knappen **Välj** i verktygsfältet och väljer sedan det önskade elementet. Elementets egenskapsfönster visas och du kan ändra egenskaperna för det elementet. Du kan upprepa processen för andra element som kan anpassas på den sidan. Observera att vissa anpassningsegenskaper kanske inte är tillgängliga i vissa fall. Exempelvis kan du inte låsa ett fält som krävs.
- Använd verktyget **Dölj** verktyg för att dölja ett element på sidan. Om du vill använda det här verktyget väljer du knappen **Dölj** i verktygsfältet och väljer sedan det element som ska döljas. När du väljer verktyget **Dölj** kommer alla element som döljs för närvarande vara synliga och visas i en skuggad behållare. Du kan sedan göra ett element synligt genom att markera det. Om du vill se hur sidan ser ut när elementen är dolda, växlar du till ett annat anpassningsverktyg.
- Använd verktyget **Lägg till ett fält** för att lägga till ett fält till din sida. När du använder det här verktyget kan du bara lägga till fält som är en del av siddefinitionen. Information om hur du skapar nya fält som inte ingår i definitionen av sidan finns i [Skapa och arbeta med anpassade fält](user-defined-fields.md). När du har valt knappen **Lägg till ett fält** på verktygsfältet måste du först välja den grupp eller det område där du vill lägga till ett fält. En dialogruta visar en lista med fält som är relaterade till den valda gruppen eller området. Välj ett eller flera fält i dialogrutan och välj sedan **Infoga**. Om du vill ta bort ett fält som du tidigare lade du upprepar hela processen och ta bort markeringen i fältet i dialogrutan.
- Använd verktyget **Flytta** för att flytta ett element till en annan plats inom aktuell grupp av element. Observera att du inte kan flytta ett element utanför dess överordnade grupp. Om du vill använda det här verktyget väljer du knappen **Flytta** i verktygsfältet och väljer sedan det element som ska flyttas. När du markerar ett element kommer appen att bestämma platser som elementet kan flyttas till. Dessa platser kallas *släppzoner*. När du drar runt elementet inom den aktuella gruppen visas varje ”släppzon” med färgade rader i fetstil bredvid området där elementet kan släppas.
- Använd **Hoppa över** för att ta bort ett element från sidan tangentbordstabbsekvens. När du väljer knappen **Hoppa över** på verktygsfältet kommer alla element som för närvarande hoppas över att visas i en skuggad behållare. Du kan ta bort eller lägga till fält interaktivt i tabbsekvensen.
- Använd verktyget **Visa i rubrik** när du vill att ett fält ska visas i sammanfattningen på snabbfliken. När du väljer knappen **Visa i rubrik** i verktygsfältet har alla fält som har valts som sammanfattningsfält visas i en skuggad behållare. Du kan interaktivt lägga till fält på snabbfliken sammanfattning och ta bort fält från den genom att markera fälten.
- Använd verktyget **Låsa** för att markera ett element som antingen redigerbart eller inte redigerbart. När du väljer knappen **Låsa** på verktygsfältet kommer alla element som för närvarande icke är redigerbara att visas i en skuggad behållare. Du kan sedan göra dem redigerbara igen. Observera att vissa fält är obligatoriska och kan göras icke redigerbara. Ett hänglåssymbol visas bredvid dessa fält.
- Använd knappen **Lägg till PowerApp** under infoga i ett program som har skapats med hjälp av Microsoft PowerApps på sidan. För detaljerad information om hur du bäddar in en PowerApps-app på en sida finns i [bädda in PowerApps-appar](embed-power-apps.md).
- Använd verktyget **Rensa** för att återställa sidan till dess installerade standardtillstånd. Alla anpassningar på den aktuella sidan kommer att rensas. Det finns ingen ångra-åtgärd. Använd därför endast detta verktyg om du är säker på att du vill återställa sidan.
- Använd verktyget **Importera** för att ladda en anpassning från en fil som du eller någon annan tidigare skapade. När du importerar anpassningar för en sida kan du välja om de ska läggas till i eller ersätta alla befintliga anpassningar för sidan. Det finns ingen ångra-åtgärd. När du har importerat anpassningar måste du därför manuellt rensa eller ångra de ändringar som du inte vill ha.
- Använd verktyget **exportera** om du vill spara dina anpassningar för sidan till en fil. Du kan sedan dela dina anpassningar med andra användare. Användarna behöver bara importera filen med dina anpassningar för sidan.
- Välj knappen **Stäng** för att stänga verktygsfältet **Anpassning** och återställa sidan till sin tidigare interaktiva status.

När verktygsfältet **anpassning** används kommer dina anpassningar att börja gälla så fort du gör dem. Om funktionen [sparade vyer](saved-views.md) är aktiverad måste du uttryckligen spara anpassningar i en vy som du väljer.

I vissa fall visas en hänglåssymbol bredvid ett element när du väljer ett verktyg. Den här symbolen visar att du inte kan ändra egenskaperna för elementet som är relaterade till det valda verktyget eftersom ändringar i de egenskaperna som förhindrar att sidan fungerar som den ska.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Lägga till en panel, lista eller länk till en arbetsyta

För vissa sidor som innehåller listor är anpassningsfunktionen **Lägg till på arbetsyta** tillgänglig i gruppen **Anpassa** på fliken **alternativ** i åtgärdsfönstret. Med den här funktionen kan du skicka relevant information från den aktuella listan till en viss arbetsyta. Informationen som visas på arbetsytan kan antingen baseras på hela listan eller en filtrerad och sorterad version av listan. Du kan också ange om informationen ska visas på arbetsytan som en lista, en sammanfattande sida som kan visa antalet objekt i listan eller en länk.

> [!NOTE]
> Om funktionen [sparade vyer](saved-views.md) är aktiv länkas det innehåll som du flyttar till en arbetsyta direkt till en vy. Frågan används för att hämta data på arbetsytan och på motsvarande sida eller länk i arbetsytan öppnas sidan i vyn så att frågans fråga och anpassningar tillämpas på den.

[![Lägg till på arbetsyta](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lägg till en lista i en arbetsyta, sortera först eller filtrera listan på sidan så att den visar information som du vill ska visas på arbetsytan. (Om funktionen Sparade vyer är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Lista**. När du har valt **konfigurera**, visas en dialogruta, där du kan välja vilka kolumner som ska visas i listan i arbetsytan. Du kan också ange etiketten som ska användas för i listan i arbetsytan.
- För att lägga till en panel till en arbetsyta, filtrera först listan på sidan så att den visar de data som du vill sammanfatta eller som vill ha snabb tillgång till. (Om funktionen Sparade vyer är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Panel**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för panelen på arbetsytan. Du kan också ange om panelen ska visa ett antal. När du har lagt till en panel i arbetsytan kan du välja den för att öppna den aktuella sidan från arbetsytan. Du kan sedan visa den filtrerade listan som är kopplad till panelen.
- Om du vill lägga till en länk till en arbetsyta filtrerar du först listan så att den visar de data du är intresserad av. (Om funktionen Sparade vyer är aktiverad kan du inte fortsätta förrän du har sparat en vy som har dessa villkor.) Välj sedan **Lägg till i arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Länk**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för länken. Du kan också ange en etikett för ett nytt avsnitt som innehåller länken.

När du har lagt till en lista, panel eller länk har lagts till en arbetsyta kan du öppna den arbetsytan och ordna om elementen i den som du vill.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Lägga till en sammanfattning från en arbetsyta till en panel

En del arbetsytor innehåller antalet paneler (detta är paneler som har nummer på dem) och vill kanske vill att dessa paneler ska visas på instrumentpanelen. I arbetsytan högerklickar du på en räkneverkspanel, väljer **Anpassa** och sedan **Fäst på instrumentpanelen** i panelens egenskapsfönster. Nästa gång som du öppnar (och uppdaterar) den valda instrumentpanelen kommer antalet att visas under navigeringspanelen för den arbetsytan. Du kan välja att gå direkt till de data som representerar antalet.

### <a name="personalizing-your-dashboard"></a>Anpassa instrumentpanelen

Instrumentpanelen är ofta den första sida som du ser när du öppnar appen. Du kan anpassa instrumentpanelen så att den bara visar arbetsytans paneler som du vill visa. Du kan också ordna om panelerna så att de är i samma ordning som du föredrar att visa dem i, byta namn på din arbetsytas navigeringspaneler eller lägga till en ny panel i arbetsytan.

För att anpassa instrumentpanelen högerklickar du på en kakel och väljer sedan **anpassa** för att öppna panelens egenskapsfönster.

- Om du vill dölja eller byta namn på den valda färgen kan du ändra direkt i egenskapsfönstret.
- Om du vill omorganisera arbetsytans paneler, välj i egenskapsfönstret **Anpassa det här formuläret** för att öppna verktygsfältet **Anpassning**. Du kan sedan använda verktyget **Flytta** för att arrangera om panelerna som du vill.
- Om du vill lägga till en ny panel i arbetsytans egenskapsfönster, välj **lägg till en arbetsyta**. En ny panel i arbetsytan skapas längst ned på instrumentpanelen. Du kan byta namn på denna nya arbetsytapanel som helst. Du kan också lägga till listor, rutor och länkar till arbetsytan enligt avsnittet [Lägga till listor, rubriker eller länkar till arbetsytor](#adding-a-tile-list-or-link-to-a-workspace) i det här ämnet.

## <a name="administration-of-personalizations"></a>Administration av anpassning

När du anpassar en sida kan du dela dina anpassningar med andra användare genom att exportera den anpassade sidan. Du kan sedan be andra användare att öppna den anpassade sidan och importera anpassningsfilen som du har skapat. Alternativt kan du ge dina anpassningar till en användare med administratörsbehörighet. Användaren kan sedan använda den anpassade filen till många användare samtidigt.

Användare med administratörsbehörighet kan även hantera anpassningsalternativ för andra användare på sidan **Anpassning** .

För kunder som inte har aktiverat funktionen [sparade vyer](saved-views.md) har den här sidan fyra flikar:

- **Tillämpa** – Du kan importera eller välja en anpassning för en eller flera användare. Om du vill använda en anpassning till en eller flera användare, markerar du först en roll och användare som har rollen. Välj sedan en befintlig anpassning som gäller för de valda användare eller importera en anpassningsfil. Anpassningen valideras och gäller för de alla valda användare nästa gång de öppnar den markerade sidan.
- **Rensa** – Du kan rensa alla anpassningar för arbetsyta för en eller flera användare. Välj först en sida eller arbetsyta för att se en lista över de användare som har anpassat den. Sedan väljer du de användare vars anpassningar för den aktuella sidan eller arbetsytan ska avmarkeras och välj **Rensa**. Alla anpassningar som de valda användarna har kopplat till den valda sidan eller arbetsytan tas bort. Denna åtgärd kan inte ångras. Om en anpassning sparades för sidan eller arbetsytan, kan den anpassningen emellertid återimporteras.
- **Användare** – Välj en användare för att visa listan över sidor som användaren har anpassat. Du kan sedan aktivera eller inaktivera den valda användarens förmåga att använda anpassningar för specifika sidor eller för hela systemet. D kan också importera, exportera eller rensa anpassningar för denna användare. Du kan dessutom återställa en användares bildtexter för funktioner. I detta fall, om användaren tidigare stängde alla popup-fönster som introducerar nya funktioner visas det i detta fall igen nästa gång användaren påträffar dessa funktioner.
- **System** – Du kan temporärt inaktivera alla anpassningar för samtliga användare i systemet. I det här fallet tas alla anpassningar bort för alla användare, och alla sidor återställs till standardtillståndet. Om du senare aktiverar anpassningen igen kommer alla anpassningar att återappliceras. Du kan också ta bort alla anpassningar permanent för samtliga användare i systemet. Det går inte att återställa anpassningar som har tagits bort. Se därför till att du har exporterat den här uppgiften för att exportera alla anpassningar som du kanske vill ha senare.

För kunder som inte har aktiverat funktionen [sparade vyer](saved-views.md) har sidan **Anpassning** fem flikar:

- **Publicerade vyer** – de här vyerna har publicerats i din organisation. Om du vill ändra vilka användare som är riktade till dessa vyer kan du ändra säkerhetsrollerna eller de juridiska personer som är kopplade till varje vy. Du kan också exportera eller ta bort en eller flera publicerade vyer.
- **Opublicerade vyer** – dessa vyer är mappvyer som har importerats till ditt system men ännu inte publicerats. Du kan publicera, exportera eller ta bort dessa vyer.
- **Personliga vyer** – de här vyerna har skapats av användare i systemet. Du kan publicera en personlig vy till organisationen, eller kopiera en eller flera av dessa vyer till andra användare. Du kan också exportera eller ta bort dessa vyer.
- **Användare** – Välj en användare för att visa listan över sidor som användaren har anpassat. Du kan sedan aktivera eller inaktivera den valda användarens förmåga att använda anpassningar för specifika sidor eller för hela systemet. D kan också importera, exportera eller rensa anpassningar för denna användare. Du kan dessutom återställa en användares bildtexter för funktioner. I detta fall, om användaren tidigare stängde alla popup-fönster som introducerar nya funktioner visas det i detta fall igen nästa gång användaren påträffar dessa funktioner.
- **System** – Du kan temporärt inaktivera alla anpassningar för samtliga användare i systemet. I det här fallet tas alla anpassningar bort för alla användare, och alla sidor återställs till standardtillståndet. Om du senare aktiverar anpassningen igen kommer alla anpassningar att återappliceras. Du kan också ta bort alla anpassningar permanent för samtliga användare i systemet. Det går inte att återställa anpassningar som har tagits bort. Se därför till att du har exporterat den här uppgiften för att exportera alla anpassningar som du kanske vill ha senare.

Användare som har åtkomst till sidan **anpassning** kan också importera personliga vyer eller verktygspalettsvyer genom att använda knappen **Importera vyer** i åtgärdsfönstret.

## <a name="personalizing-inventory-dimensions"></a>Anpassning av lagerdimensioner

När du anpassar inställningarna för lagerdimensionerna på en sida, beakta inställningarna som har skapats med hjälp av alternativet **Visa dimension**. Du använder till exempel anpassning om du vill dölja en kolumn för batchnummerdimensionen men kolumnen visas nästa gång som sidan öppnas. Detta händer på grund av att inställningarna för **Dimensionsvisning** kontrollerar de lagerdimensionskolumner som visas. Inställningarna för **Dimensionsvisning** tillämpas på alla sidor och åsidosätter eventuella anpassade inställningar av lagerdimensionsfälten på enskilda sidor.

Därför i det föregående exemplet om du inte vill att kolumnen för batchnummer lagerdimensionen ska visas på en sida, måste du avmarkera dimensionen som en del av alternativet **visa mått** för den sidan.
