---
title: "Anpassa användarupplevelsen"
description: "Det här ämnet beskriver hur du kan anpassa Microsoft Dynamics 365 for Finance and Operations."
author: TLeforMicrosoft
manager: AnnBe
ms.date: 05/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 862bbf4d1d9b0dc2b6dc418ee766ed4dedef49fe
ms.openlocfilehash: 8ad5bd607f08d4e0b266d86a96a0b7f3e352c4cd
ms.contentlocale: sv-se
ms.lasthandoff: 05/24/2018

---

# <a name="personalize-the-user-experience"></a>Anpassa användarupplevelsen

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du kan anpassa Microsoft Dynamics 365 for Finance and Operations.

Det finns tre grundläggande klasser anpassningar i Finance and Operations. 
- Anpassningar som har gjorts på sidan Inställningar. Exempel omfattar färgtema och tidszon.
- Anpassningar relaterade till sidanvändning kallas *implicita* anpassningar. Exempelvis håller Finance and Operations koll på bredden på rutnätskolumner om du justerar dem, och på det expanderade/komprimerade läget för snabbflikar. 
- Anpassningar som en användare gör för att ändra utseendet på en sida genom att ändra hur ett element visas eller fungerar på den sidan, ofta genom ett interaktivt anpassningsläge. Dessa anpassningsalternativ kallas *uttryckliga* anpassningar. Användaren kan till exempel lägga till, dölja eller ordna om element på sidan.

Alla anpassningsalternativ som en användare gör i Finance and Operations gäller endast för den användaren, oavsett typen av anpassning eller vilket företag som användaren för närvarande interagerar med. Ändringar som en användare gör att en sida inte påverka andra användare i systemet.

## <a name="system-wide-options-for-the-current-user"></a>System-wide alternativ för aktuell användare
Sidan **användaralternativ** innehåller flera systeminställningar för den aktuella användaren. För att öppna sidan **användaralternativ**, välj menyn **inställningar** (växel-symbol) i navigeringsfältet, och välj sedan **användaralternativ**. Sidan **användaralternativ** har fyra flikar med olika användarinställningar:

- **Visuellt** - Välj en färg för att välja ett färgtema och standardstorleken för element på dina sidor.
- **Inställningar** – Välj standardvärden som används varje gång du öppnar Finance and Operations. Dessa värden inkluderar företaget, den första sidan och standardläget visa/redigera. (Det/redigeringsläget bestämmer om en sida är låst för visning eller öppnas för redigering i varje gång du öppnar den.) Den här fliken innehåller också alternativ för språk, tidszon, och datum, tid och nummerformat. Den här fliken innehåller dessutom flera diverse inställningar som kan variera från version till version.
- **Konto:** - Justera ditt användarnamn och andra kontorelaterade inställningar.
- **Arbetsflöde** – Välj arbetsflöderelaterade alternativ.

## <a name="implicit-personalizations"></a>Uttryckliga anpassningsalternativ
Uttryckliga anpassningsalternativ är de anpassningsalternativ som du utför enkelt genom att interagera med vissa kontroller som kommer ihåg deras aktuella synliga.

- **Rutnätskolumner:** - Du kan justera bredden på en kolumn i ett rutnät genom att välja storleksfältet till vänster eller till höger om kolumnrubriken och skjuta det åt vänster eller höger tills kolumnen har önskad bredd. Finance and Operations lagrar den bredd som du anger för en kolumn. Sedan ändras storleken på kolumnen till den bredden varje gång du öppnar sidan med det rutnätet.
- **Snabbflikar** - Vissa sidor har expanderbara avsnitt som kallas *snabbflikar*. Finance and Operations lagrar information om snabbflikar som du har utökat och komprimerat. Varje gång du kommer tillbaka till sidan kommer samma snabbflikar att visas eller döljs, utifrån din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera en snabbflik eftersom Finance and Operations inte behöver hämta informationen för snabbfliken förrän snabbfliken expanderas. Såsom beskrivs senare i det här avsnittet kan du också ändra ordning på snabbflikarna på en sida.
- **Faktarutor** - Vissa sidor har ett fönster som kallas *Faktaruta*. Den här rutan innehåller skrivskyddad information relaterad till det aktuella ämnet på sidan. Varje avsnitt i faktaruta rutan kallas en *faktaruta*. Du kan dölja eller visa hela faktarutan och du kan också visa eller dölja enskilda faktarutor. Finance and Operations sparar dina inställningar. Sedan utifrån varje gång du kommer tillbaka till sidan kommer faktarutans fönster och de enskilda faktarutorna att återställas baserat på din senaste interaktion med sidan. I vissa fall kan du hjälpa till att förbättra systemet genom att komprimera en faktaruta eftersom Finance and Operations inte behöver hämta informationen för den faktarutan förrän faktarutan expanderas.
- **Åtgärdsfönster** – Ett *åtgärdsfönstret* visas längst upp på de flesta sidor. Åtgärdsfönstret innehåller knappar för många av de åtgärder som du kan utföra på den aktuella sidan. Knapparna ordnas ofta på flikarna. Du kan öppna hela åtgärdsfönstret och du kan konfigurera den så att den komprimeras som standard. Nästa gång du öppnar sidan kommer Finance and Operations att återställa det fästa tillståndet för åtgärdsfönstret. Om åtgärdsfönstret är fäst öppen, visar Finance and Operations även fliken med åtgärder som användes senast.
- **Snabbfilter** – Ett *snabbfilter* visas ovanför många rutnät. Snabbfilter låter dig filtrera rutnät, baserat på en kolumn som du väljer. Finance and Operations lagrar den kolumn som du filtrerade på. Nästa gång som du öppnar sidan med det rutnätet kommer rutnätet att filtreras på samma kolumn. Du kan sedan filtrera rutnätet i en annan kolumn.
- **Kolumnrubrikfilter** – när du filtrerar ett rutnät med hjälp av *Kolumnrubrikfilter*, kan du ändra filteroperatör för att hitta de data som du vill. Du kan exempelvis ändra operatorn från **börjar med** till **exakt**. Varje gång du använder ett kolumnrubrikfilter och ändrar filteroperatör kommer Finance and Operations att spara ändringen. Det återställer sedan filteroperatör nästa gång du filtrerar efter den kolumnen.
- **Navigeringsfönstret** – du kan öppna *navigeringsfönstret* genom att välja knappen **meny** till vänster på en sida. (Knappen **meny** kallas ibland *hamburgare*, *hamburgarmeny*, eller *hamburgarknappen*.) Du kan fästa det öppna navigeringsfönstret eller du kan hålla det komprimerat som standard. När du fäster navigeringsfönstret håller Finance and Operations det öppet tills du komprimera det.

## <a name="explicit-personalizations"></a>Uttryckliga anpassningsalternativ
Olika personer och företag har ett annorlunda perspektiv på de viktigaste data eller data som inte behövs för hur de sköta verksamheten. I Finance and Operations kan du skräddarsy hur informationen beställs och interageras med. Du kan också ange att viss information ska döljas. Dessa funktioner är viktiga för en personlig och produktiv upplevelse och är exempel på uttryckliga anpassningar. Uttryckliga anpassningar är de anpassningar som du uttryckligen utför med avsikt att ändra utseende eller funktion för ett element eller en sida.

### <a name="shortcut-menu-options"></a>Alternativ för snabbmeny
Snabbmenyer innehåller några sätt för att uttryckligen ändra en sida så att den passar bättre till dina behov eller ditt företags behov. (EN snabbmeny kallas också en *högerklicksmeny* eller *kontextmenyn*.)

Några av de vanligaste och mest viktiga ändringar som kan göras till en sida visas direkt som ett alternativ på en snabbmeny. Om du till exempel vill lägga till eller dölja kolumner i ett rutnät, bara högerklicka på en kolumnrubrik och markera **lägg till kolumner** eller **dölj denna kolumn**.

Dessutom är de vanligaste typerna av uttrycklig anpassning tillgängliga genom att högerklicka på ett element och sedan välja **anpassa**. (Observera att inte alla element på sidan kan anpassas). När du använder den här metoden för anpassning visas elementets egenskapsfönster.

[![Anpassa egenskaper för ett element](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg)

Du kan använda egenskapsfönstret för att anpassa ett element på följande sätt:

- Ändra elementets etikett.
- Dölj elementet så att den inte visas på sidan. Informationen i det här fältet tas inte bort eller ändras. Informationen visas bara inte på sidan längre.
- Inkludera informationen i sammanfattningsavsnittet på snabbfliken (om elementet på en snabbflik).
- Hoppa över fältet när du trycker på TABB för att flytta mellan fälten på sidan.
- Förhindra att data i fältet (en post) inte kan redigeras.

Egenskapsfönstret kan omfatta andra anpassningsfunktioner, beroende på vilket element. Exempelvis egenskapsfönstret för en panel kan låta dig flytta upp den panelen till en instrumentpanel och egenskapsfönster för en instrumentpanel låter dig skapa en ny arbetsyta på den här instrumentpanelen.

### <a name="the-personalization-toolbar"></a>Verktygsfält för anpassning
När du vill flytta eller dölja element eller göra flera ändringar till en sida använder du verktygsfältet **anpassning**. För att öppna verktygsfältet **anpassning**, välj **anpassa formuläret** i ett elements egenskapsfönster. Du kan också välja **anpassa det här formuläret** i gruppen **anpassa** på fliken **alternativ** för varje sidas åtgärdsfönster.

[![Verktygsfält för anpassning](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

När värktygsfältet **anpassning** är öppet blir sidan icke-interaktiv. Därför kan du inte ange data eller expandera eller komprimera sektioner. Du kan bara ändra de element som utgör sidan.

Följande verktyg är tillgängliga i fältet verktygsfältet **anpassning**:

- Använd verktyget **Välj** för att välja och öppna ett elements egenskaper. Välj verktyget **Välj** och välj sedan elementet som egenskaperna ska ändras för. När du väljer ett element, öppnas elementets egenskapsfönster och du kan ändra egenskaperna för det elementet. Du kan upprepa processen för andra element som kan anpassas på den sidan. Men eftersom vissa element används på ett visst sätt låter Finance and Operations dig inte ändra en del av deras egenskaper. Därför när du väljer ett element kan du se att vissa av egenskaperna inte kan ändras. Exempelvis du kan skinnet en fält som krävs.
- Använd verktyget **Flytta** för att flytta ett element till en annan plats inom aktuell grupp av element. (Du kan inte flytta ett element utanför dess överordnade grupp). Välj verktyget **flytta** och välj sedan elementet du vill flytta. När du markerar ett element kommer Finance and Operations att söka igenom för att avgöra om elementet kan flyttas eller inte. Det skapar sedan ett antal ”släppzoner”. När du drar runt elementet inom den aktuella gruppen visas varje ”släppzon” med färgade rader i fetstil bredvid området där elementet kan släppas.
- Använd verktyget **Dölj** verktyg för att dölja ett element på sidan. Välj verktyget **Göm** och välj sedan elementet du vill gömma. När du väljer verktyget **Dölj** kommer alla element som döljs för närvarande vara synliga och visas i en skuggad behållare. Du kan sedan göra dem synliga. Genom att välja verktyget **Välj** kan du se hur sidan kommer att se ut med de valda elementen dolda.
- Använd verktyget **sammanfattning** när du vill att ett element ska visas i sammanfattningen på snabbfliken. Sammanfattningsverktyget gäller endast fält som är på snabbfliken. När du väljer verktyget **Sammanfattning** har alla fält som har valts som sammanfattningsfält visas i en skuggad behållare. Du kan interaktivt lägga till fält på snabbfliken sammanfattning och ta bort fält från snabbfliken sammanfattning genom att markera fälten.
- Använd **Hoppa över** för att ta bort ett element från sidan tangentbordstabbsekvens. När du väljer verktyget **Hoppa över** kommer alla element som för närvarande hoppas över att visas i en skuggad behållare. Du kan sedan göra delar av fliksekvensen igen.
- Använd verktyget **Redigera** för att markera ett element som antingen redigerbart eller inte redigerbart. När du väljer verktyget **Redigera** kommer alla element som för närvarande inte är redigerbara att visas i en skuggad behållare. Du kan sedan göra dem redigerbara igen. Observera att vissa fält är obligatoriska och kan göras icke redigerbara. Ett hänglåssymbol visas bredvid dessa fält.
- Använd knappen **infoga** för att visa en lista med element som kan infogas på en sida.

    - Välj verktyget **fält** under **infoga** för att lägga till ett fält till sidan. När du använder verktyget **fält**, du kan lägga till fält som ingår i definitionen för sidan, men som för tillfället visas inte på sidan. Information om hur du skapar nya fält som inte ingår i definitionen av sidan finns [anpassade fält](user-defined-fields.md). När du har valt verktyget **fält** måste du först välja den grupp eller det område där du vill lägga till ett fält. En dialogruta visar en lista med fält som är relaterade till den valda gruppen eller området. Välj ett eller flera fält i dialogrutan och välj sedan **Infoga**. Om du vill ta bort ett fält som du tidigare lade du upprepar hela processen och ta bort markeringen i fältet i dialogrutan.
    - Välj verktyget **PowerApp** under **infoga** i ett program som har skapats med hjälp av Microsoft PowerApps på sidan. För detaljerad information om hur du bäddar in en PowerApps-app på en sida finns i [bädda in PowerApps](embed-power-apps.md).

- Välj knappen **Hantera** för att visa en lista över hanteringsalternativ som är relaterade till alla anpassningar för den aktuella sidan.

    - Välj **Rensa** för att återställa sidan till dess installerade standardtillstånd. Alla anpassningar på den aktuella sidan kommer att rensas. Det finns ingen ångra-åtgärd. Använd därför endast detta alternativ om du är säker på att du vill återställa sidan.
    - Välj **Importera** för att ladda en anpassning från en fil som du eller någon annan tidigare skapade för denna sida. Alla aktuella anpassningar för sidan ersätts med anpassningar från den valda filen.
    - Välj **exportera** om du vill spara dina anpassningar för sidan till en fil. Du kan dela dina anpassningar med andra användare. Användarna behöver bara importera filen med dina anpassningar för sidan.

- Välj knappen **Stäng** för att stänga verktygsfältet **Anpassning** och återställa sidan till sin tidigare interaktiva status.

När verktygsfältet **anpassning** används, är det implicit att spara åtgärder. Dina anpassningar börjar gälla så fort du gör dem och du behöver inte välja en **spara**-knapp. I vissa fall visas en hänglåssymbol bredvid ett element när du väljer ett verktyg. Den här symbolen visar att du inte kan ändra egenskaperna för elementet som är relaterade till det valda verktyget eftersom ändringar i de egenskaperna som förhindrar att sidan fungerar som den ska.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Lägga till en panel, lista eller länk till en arbetsyta
En ytterligare anpassningsfunktion är tillgänglig för vissa sidor med listor. Knappen **lägga till arbetsyta** i gruppen **anpassa** på fliken **alternativ** i åtgärdsfönstret låter dig visa informationen från den aktuella listan i en viss arbetsyta. Du kan visa en filtrerad och sorterad informationen på arbetsytan eller också kan visa standardvyn. Du kan också ange om informationen ska visas på arbetsytan som en lista, en sammanfattande sida som kan visa antalet objekt i listan eller en länk.

[![Lägg till på arbetsyta](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Lägg till en lista i en arbetsyta, sortera först eller filtrera listan på sidan så att den visar information som du vill ska visas på arbetsytan. Välj sedan **lägg till arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Lista**. När du har valt **konfigurera**, visas en dialogruta, där du kan välja vilka kolumner som ska visas i listan i arbetsytan. Du kan också ange etiketten som ska användas för i listan i arbetsytan.
- För att lägga till en panel till en arbetsyta, filtrera först listan på sidan så att den visar de data som du vill sammanfatta eller som vill ha snabb tillgång till. Välj sedan **lägg till arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Panel**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för panelen på arbetsytan. Du kan också ange om panelen ska visa ett antal. När panelen har lagts till på arbetsytan kan du välja att öppna den aktuella sidan från arbetsytan och visa den filtrerade listan som associeras med panelen.
- Om du vill lägga till en länk till en arbetsyta filtrerar du först listan så att den visar de data du är intresserad av. Välj sedan **lägg till arbetsytan**. Välj en arbetsyta och sedan i fältet **Presentation** väljer du **Länk**. När du har valt **konfigurera**, visas en dialogruta där du kan ange etiketten som ska användas för länken. Du kan också ange en etikett för ett nytt avsnitt som innehåller länken.

När din lista, panel eller länk har lagts till en arbetsyta kan du öppna den arbetsytan och beställa om elementen i den som du vill.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Lägga till en sammanfattning från en arbetsyta till en panel
En del arbetsytor innehåller antalet paneler (detta är paneler som har nummer på dem) och vill kanske vill att dessa paneler ska visas på instrumentpanelen. På en arbetsyta, högerklicka på en räknepanel och välj **Anpassa**. I den andra panelens egenskapsfönster, markera **fäst på instrumentpanelen**. Nästa gång som du öppnar (och uppdaterar) den valda instrumentpanelen kommer antalet att visas under navigeringspanelen för den arbetsytan. Du kan välja att gå direkt till de data som representerar antalet.

### <a name="personalizing-your-dashboard"></a>Anpassa instrumentpanelen
Instrumentpanelen är ofta den första sida som du ser när du öppnar Finance and Operations. Du kan anpassa instrumentpanelen så att den bara visar arbetsytans paneler som du vill visa. Du kan också ordna om panelerna så att de är i samma ordning som du föredrar att visa dem i, byta namn på din arbetsytas navigeringspaneler eller lägga till en helt ny panel i arbetsytan.

För att anpassa instrumentpanelen högerklickar du på en kakel och väljer sedan **anpassa** för att öppna panelens egenskapsfönster.

- Om du vill dölja eller byta namn på den valda färgen kan du ändra direkt i egenskapsfönstret.
- Om du vill omorganisera arbetsytans paneler, välj i egenskapsfönstret **Anpassa det här formuläret** för att öppna verktygsfältet **Anpassning**. Du kan sedan använda verktyget **Flytta** för att arrangera panelerna som du vill.
- Om du vill skapa en ny panel i arbetsytans egenskapsfönster, välj **lägg till en arbetsyta**. En ny panel i arbetsytan skapas längst ned på instrumentpanelen. Du kan byta namn på denna nya arbetsytapanel som helst. Du kan också lägga till listor, rutor och länkar till arbetsytan enligt avsnittet [Lägga till listor, rubriker eller länkar till arbetsytor](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace) i det här ämnet.

## <a name="administration-of-personalization"></a>Administration av anpassning
När du anpassar en sida kan du dela dina anpassningar med andra användare genom att exportera den anpassade sidan. Du kan sedan be andra användare att öppna den anpassade sidan och importera anpassningsfilen som du har skapat. Alternativt kan du ge dina anpassningar till en användare med administratörsbehörighet. Användaren kan sedan använda den anpassade filen till många användare samtidigt.

Användare med administratörsbehörighet kan även hantera anpassningsalternativ för andra användare på sidan **Anpassning** . Den här sidan innehåller fyra flikar:

- **Tillämpa** – Du kan importera eller välja en anpassning för en eller flera användare. Om du vill använda en anpassning till en eller flera användare, markerar du först en roll och användare som har rollen. Välj sedan en befintlig anpassning som gäller för de valda användare eller importera en anpassningsfil. Anpassningen valideras och gäller för de alla valda användare nästa gång de öppnar den markerade sidan.
- **Rensa** – Du kan rensa alla anpassningar för arbetsyta för en eller flera användare. Välj först en sida eller arbetsyta för att se en lista över de användare som har anpassat den. Sedan väljer du de användare vars anpassningar för den aktuella sidan eller arbetsytan ska avmarkeras och välj **Rensa**. Alla anpassningar som de valda användarna har kopplat till den valda sidan eller arbetsytan tas bort. Denna åtgärd kan inte ångras. Om en anpassning sparades för sidan eller arbetsytan, kan den anpassningen emellertid återimporteras.
- **Manager per användare** – Välj en användare för att visa listan över sidor som personen har anpassat. Du kan sedan aktivera eller inaktivera den valda användarens förmåga att använda anpassningar för specifika sidor eller för hela systemet. D kan också importera, exportera eller rensa anpassningar för denna användare.
- **System** – Du kan temporärt inaktivera alla anpassningar för samtliga användare i systemet. I detta fall tas anpassningarna bort. Alla sidor återställs bara till standardinställningarna för alla användare. Om du senare återaktiverar anpassningen kommer alla anpassningar att återappliceras. Du kan också ta bort alla anpassningar permanent för samtliga användare i systemet. Det går inte att återställa anpassningar som har tagits bort. Se därför till att du har exporterat den här uppgiften för att exportera alla anpassningar som du kanske vill ha senare.

## <a name="personalization-of-inventory-dimensions"></a>Anpassning av lagerdimensioner

När du anpassar inställningarna för lagerdimensionerna på en sida, beakta inställningarna som har skapats med hjälp av alternativet **Visa dimension**. Du använder till exempel anpassning om du vill dölja en kolumn för batchnummerdimensionen men kolumnen visas nästa gång som sidan öppnas. Detta händer på grund av att inställningarna för **Dimensionsvisning** kontrollerar de lagerdimensionskolumner som visas.

Inställningarna för **Dimensionsvisning** tillämpas på alla sidor och åsidosätter eventuella anpassade inställningar av lagerdimensionsfälten på enskilda sidor.

Därför i det föregående exemplet om du inte vill att kolumnen för batchnummerlagerdimensionen ska visas, måste du avmarkera dimensionen som en del av alternativet **visa mått** för tabellen. Slutligen används ändringen inte bara på en specifik sida utan på alla sidor.

