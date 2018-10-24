---
title: Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv
description: "Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret."
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4428613441424c81f4fd7dd92bbf842c62ce860
ms.openlocfilehash: 74e7c36fb912f35252d6e40d17477ac2962cbc23
ms.contentlocale: sv-se
ms.lasthandoff: 09/22/2018

---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.

De instruktioner som lagerarbetare tar emot på en mobil enhet bestäms av de arbetsmallar som du anger i Microsoft Dynamics 365 for Finance and Operations för att definiera de olika lagerprocesserna och -uppgifterna. Arbetsmallar avgör hur arbetet utförs för varje lager. Genom att koppla en lagerplats direktiv att arbeta mallar, du kan bidra till att garantera att arbetet sker i särskilda fysiska områden i lager.

## <a name="work-templates"></a>Arbetsmallar
**Arbetsmallar** sidan låter dig definiera arbeten som måste utföras i lagret. Typiskt, warehouse arbeten består av ett par åtgärder: en lagerarbetare plockar upp lagersaldot på en plats och sedan lägger de plockade lager ned på en annan plats. 

Arbetsmallar består av ett sidhuvud och tillhörande ledningar. Varje mall för en viss *arbetsorder*. Många arbetsorder som är kopplade till källa dokument, t.ex. inköpsorder eller beställningar. Men andra arbetsordern typer utgör separata lager processer, såsom inventeras. *Arbetet pool-ID* låter dig att organisera arbetet i grupperna. 

Inställningarna i arbetet skärbordets definition kan användas för att avgöra när ett nytt arbete ska skapas. Du kan till exempel ange ett maximalt antal plocka rader och ett maximalt förväntade plocka tid. Om arbetet för en försäljning orderplockningen överskrider något av dessa värden, att arbetet är uppdelat i två delar. 

Arbetet linjerna representerar det fysiska uppgifter som krävs för att bearbeta. För exempelvis ett utgående lager, det kan vara ett arbete för att plocka upp föremål i lagerstället och en annan linje för dessa poster till en mellanlagringsplats. Det kan alltså vara en extra rad för plockning från mellanlagring och en annan linje för att objekten i en lastbil som en del av laddningen. Du kan ställa in ett *direktiv kod* på arbetsmall linjer. Ett direktiv som är kopplad till en plats och därför hjälper till att säkra att lagerarbetet bearbetas på rätt plats i lagret. 

Du kan ställa in en fråga för att kontrollera när en särskild mall används. Du kan till exempel ställa in en begränsning så att en viss mall kan användas för arbete i ett särskilt lager. Alternativt kan du ha flera mallar som används för att skapa arbete för utgående orderhantering, beroende på försäljningen ursprung. Systemet använder fältet **Sekvensnummer** för att avgöra den ordning som de tillgängliga arbetsmallarna värderas i. Därför bör du, om du har en specifik fråga för en specifik arbetsmall, tilldela den ett lågt ordningsnummer. Frågan kommer sedan att utvärderas innan andra, mer allmänna frågor. 

För att stoppa eller pausa en arbetsprocess kan du använda **stopp** på arbetet. I detta fall arbetstagare som utför arbetet inte bli ombedd att utföra nästa rad steg. Gå vidare till nästa steg, att arbetstagaren eller annan arbetstagare måste välja igen. Du kan även ta uppdrag inom ett arbete med en annan *klass-ID* för arbetsmallen.

## <a name="location-directives"></a>Platsdirektiv
Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager. Exempelvis i en försäljningsorder transaktion, en plats direktiv bestämmer var objekten ska plockas, och där plockade artiklar kommer att användas. Plats direktiven består av ett sidhuvud och därtill hörande linjer, och du skapar dem på **plats direktiven** sida. 

På huvudet, varje plats direktiv måste vara associerad med en *arbetsorder typ* som anger typ av lagertransaktionen som direktivet kommer att användas för, såsom beställningar, återfyllnad, eller råmaterial plockning. Den *arbetstyp* anger platsen direktiv kommer att användas för plockning eller arbete, eller för vissa andra lagret process, såsom inventering eller lager status ändras. Du måste också ange en *ort* och ett *lager*. Ett *direktiv kod* som du anger på skärbordet kan användas för att länka placering direktiv till en eller flera arbetsmallar. 

För arbete mallar, du kan sätter upp en fråga att avgöra när en viss plats direktiv används. Du kan till exempel ange att när e-handeln är ursprunget till en försäljningsorder, lager måste plockas upp från ett särskilt område i lagret. Systemet använder fältet **Löpnummer** för att avgöra den ordning som de tillgängliga platsdirektiven värderas i. 

Platsdirektivraderna anger ytterligare begränsningar för tillämpningen av reglerna för platssökning. Du kan ange en minsta kvantitet och en maximal kvantitet att direktivet bör gälla, och du kan ange att direktivet bör vara en viss lagerenhet. Till exempel, om enheten är pallar, poster i pallar kan placeras i en specifik placering. Du kan också ange om kvantiteten kan delas upp över flera platser. Precis som platsdirektivrubriken har varje platsdirektivrad ett serienummer som bestämmer den ordning som raderna värderas i. 

Platsdirektiv har en ytterligare detaljnivå: *platsdirektivåtgärder*. Du kan definiera flera plats direktiv åtgärder för varje linje. Återigen används ett ordningsnummer för att avgöra i vilken ordning åtgärderna bedöms. På den här nivån kan du skapa en fråga för att definiera hur du hittar den bästa platsen i lagerstället. Du kan också använda fördefinierade **inställningar för strategi för** att finna en optimal placering.

## <a name="location-directives-configuration-details"></a>Konfigurationsdetaljer för platsdirektiv 

 ### <a name="sequence-number"></a>Löpnummer
 
Det här numret anger den ordning som ett platsdirektiv bearbetas i för vald ordertyp. Den kan ändras med hjälp av **Flytta upp** och **Flytta ned** på menyn.
 
 ### <a name="work-type"></a>Arbetstyp
 
Detta är typen av arbete som ska utföras. Den typ av arbete som finns tillgängligt baseras på den typ av lagertransaktion som du har valt i fältet **Typ av arbetsorder**.
-   **Placera** - En arbetstyp som motsvarar **Placera** innebär att platsdirektivet kommer att söka efter den bästa platsen att placera eller hitta lager som kommer till systemet, antingen från mottagande, produktion, lager eller lagerjusteringar. Den kan också användas för att definiera en fasplats eller vikdörr som leveransplatsen.
-   **Plocka** - En arbetstyp som motsvarar **Plocka** innebär att lagerstället ska hitta den bästa platsen att reservera fysiskt lager från (skapa arbete). Plockningen kan slutföras (plocka arbetsrad kan stängas), även om arbetet inte slutförs. Användaren kan slutföra fysisk plockning som är ett plockningssteg. Användaren kan sedan avbryta från en mobil enhet och slutföra arbetet senare. Arbetsrubriken stängs när slutgiltiga platsen slutförs. 
-   **Inventering, justeringar, anpassa, ändring av lagerstatus, skapa registreringsskylt, skriva ut, statusändra, packa till kapslade ID-nummer** - Dessa kan inte användas i någon inställning för platsdirektiv. Detta är en enum så att ingen filtrering görs ansluten till arbetsordertypen. 

### <a name="directive-code"></a>Direktivkod

Välj direktivkod som ska associeras till en arbetsmall eller lagerpåfyllnadsmall. I formuläret **Direktivkod** kan du skapa nya koder som kan användas för anslutningar mellan en lagerpåfyllnadsmall för arbetsmall och platsdirektiv. Detta kan också användas för att fastställa sambandet mellan alla arbetsmallrader och platsdirektiv (t.ex. Baydoor eller fasplats).

Observera att om en kod anges, kommer systemet inte att söka platsdirektivet när arbete genereras efter sekvens, sökningen kommer att göras efter direktivkod. Detta innebär att du kan vara mer specifik när det gäller vilken platsmall som används för ett visst steg i en arbetsmall, till exempel mellanlagring av material. 

### <a name="site"></a>Webbplats

Site är ett obligatoriskt fält eftersom platsdirektivet behöver site och lagerställe som det gäller för. 

### <a name="warehouse"></a>Lagerställe

Lagerställe är ett obligatoriskt fält eftersom platsdirektivet behöver site och lagerställe som det gäller för.

### <a name="multiple-sku"></a>Flera SKU-enheter

Detta tillåter flera lagerhållningsenheter (SKU) på en plats, exempelvis i baydoor. Om du väljer **flera SKU**, måste platsen anges i arbete (vilket förväntas), men det ska bara kunna hantera flera objekt (om arbete omfattar olika SKU att plockas och placeras, inte en enskild SKU). Om du inte väljer **flera SKU**, kommer platsen endast anges om den bara har en typ av SKU. Du måste ange två rader med flera SKU på och en med flera SKU av om du vill använda båda åtgärderna. De måste ha samma struktur och inställningar. För läggoperationer behöver du platsdirektiv som är identiska, även om du inte skiljer på en eller flera SKU:er på arbets-ID. Du måste också ställa in för plockning, om du har en order med fler än ett objekt.

### <a name="sequence-number"></a>Löpnummer

Ange den ordning som platsdirektivraden bearbetas i för vald arbetstyp. Du kan också ändra sekvensen, eventuellt med **Flytta upp** och **Flytta ned**.

### <a name="fromto-quantity"></a>Från/till kvantitet

Detta ger dig möjlighet att ange ett kvantitetsintervall för när den mittersta rutnätssekvensen ska väljas. Du kan ange från/till intervall på kvantitet i respektive enhet.

### <a name="unit"></a>Enhet

Du kan ange en minsta kvantitet och en maximal kvantitet att direktivet bör gälla, och du kan ange att direktivet bör vara en viss lagerenhet. Enhetsfältet på raden används endast för utvärdering av kvantitet.

När du kontrollerar om platsdirektivraden gäller baseras detta på kvantiteten i respektive enhet som anges på platsdirektivraden. Varje gång en platsdirektivrad har nåtts, görs försök att konvertera efterfrågeenheten till en enhet som har angetts på raden. Om enhetskonvertering saknas fortsätter den till nästa rad. 

### <a name="locate-quantity"></a>Hitta kvantitet

Det här alternativet används endast för lägga/hitta kvantitet till lagret. Det är bara för arbetstypen lägga. Giltiga värden är:

-   **Kvantitet av registreringsskylt** - Vid utvärdering av om kvantiteten ligger inom kvantitetsintervallen "Från" och "Till", använd kvantiteten på registreringsskylten som tas emot.
-   **Sammansatt kvantitet** - Vid utvärdering av om kvantiteten ligger inom kvantitetsintervallen "Från" och "Till", använd kvantiteten som sammansätts under den specifika transaktionen.
-   **Resterande kvantitet** - Vid utvärdering av om kvantiteten är inom kvantitetsintervallen "Från" och "Till" använder du den kvantitet som återstår inköpsorderraden som kontrolleras.
-   **Förväntad kvantitet** - Vid utvärdering av om kvantiteten är inom kvantitetsintervallen "Från" och "Till" använder du den totala kvantitet som återstår, oavsett vad som redan har mottagits.

### <a name="restrict-by-unit"></a>Begränsa per enhet

Detta gör att en platsdirektivrad görs specifik för en måttenhet eller flera måttenheter. Vid reservation av kvantitet, om du vill reservera lastpallar från en viss uppsättning platser, skulle den mittersta rutnätssekvensen begränsa den särskilda sekvensen till ”PL” så att alla kvantiteter som är mindre än en lastpall inte väljer sekvensen. Välj **Begränsa efter enhet** för att ställa in enheter. Du kan också begränsa raden till flera enheter. Detta fungerar bara med platsdirektiv av typen Plocka. 

### <a name="round-up-to-unit"></a>Avrunda uppåt till enhet

Det här fältet fungerar tillsammans med fältet **Begränsa per enhet**. Om platsdirektivraden **begränsa per enhet** anges till ”ruta”, markerar du **avrunda uppåt till enhet** anges att arbete som genereras från direktivet för råmaterialplockning ska avrundas upp till en multipel av en hanteringsenhet (enligt **Begränsa per enhet**). Observera att detta endast fungerar för råmaterialplockning och endast med platsdirektiv av typen Plocka.

### <a name="locate-packing-qty"></a>Placera förpackningskvantitet

Om en förpackningskvantitet anges i en försäljningsorder, överföringsorder eller produktionsorder, begränsas systemet till att endast välja platser med en förpackningskvantitet på plats. Detta fungerar bara med platsdirektiv av typen Plocka.

### <a name="allow-split"></a>Tillåt delning

Detta anger om ett platsdirektiv tillåts att dela upp den mottagna kvantiteten eller kvantiteten som har reserverats på flera lagerställen eller hela kvantiteten måste finnas på en plats eller reserveras från en enda plats i syfte att skapa arbete. 

### <a name="sequence-number"></a>Löpnummer

Det här numret är den ordning som platsdirektiven bearbetas i för vald arbetstyp. Du kan ändra sekvensen vid behov. Var emellertid försiktig med löpnummer, eftersom behandling alltid körs i sekvens. 

### <a name="name"></a>Namn

Ange ett namn på platsdirektivåtgärden. Kom ihåg vara specifik när du anger ett namn.

### <a name="fixed-location-usage"></a>Användning av fast lagerplats 

-   **Fasta och inte fasta lagerplatser** Platsdirektivet beaktar alla platser.
-   **Endast fasta lagerplatser för produkten** - Platsdirektivet beaktar endast fasta lagerplatser för produkter.
-   **Endast fasta lagerplatser för produktvarianten** - Platsdirektivet beaktar endast fasta lagerplatser för produktvarianter.

### <a name="allow-negative-inventory"></a>Tillåt negativt lager

Välj det här alternativet om du vill tillåta negativt lager på det angivna lagerstället i platsdirektiv. 

### <a name="batch-enabled"></a>Batch aktiverad 

Markera om du vill använda batchstrategier för artiklarna som är batchaktiverade. Om en rad har nåtts anges **batchen aktiveras** med en ingen batchh-artikel, processen fortsätter till nästa åtgärdsrad. 

### <a name="strategy"></a>Strategi

-   **Konsolidera** - Denna strategi används för konsolidering av artiklar på en viss plats när andra artiklar redan är tillgängliga. Detta fungerar bara med placeringstypen för platsdirektiv. Vanliga inställningar för placering är att konsolidera på den första åtgärdsraden och sedan på andra försöket placera utan konsolidering. Konsolidera varor gör senare plockning effektivare.
-   **Matcha förpackningskvantitet** - Denna strategi används för att verifiera att en plockplats har den angivna kvantiteten. Detta fungerar bara för platsdirektiv av typen Plocka. 
-   **FEFO-batchreservation** - Denna strategi används när lagret lokaliseras med hjälp av en batch för utgångsdatum och allokeras för batchreservation. Du kan bara använda denna strategi för batchen aktiverade artiklar. Detta fungerar bara för platsdirektiv av plockarbetstyper. 
-   **Avrunda uppåt till full reg.skylt** - Denna strategi används för att summera lagerkvantiteten för att matcha den registreringsskyltskvantitet som tilldelas artiklarna som ska plockas. Du kan bara använda den här strategin för typ av lagerpåfyllnad för platsdirektiv av typen Plocka. 
-   **Tom plats utan inkommande arbetsuppgifter** - Denna strategi används för att söka tomma platser. Platsen anses vara tom om den inte har något fysiskt lager och inget förväntat inkommande arbete. Denna strategi används endast för platsdirektivet Plockningstyp. 

### <a name="example-of-the-use-of-location-directives"></a>Exempel på användning av platsen direktiven

I det här exemplet kommer vi att överväga en inköpsorder där placering direktiv måste hitta ledig kapacitet inom ett lager för inventarier som just registrerats vid mottagningsplatsen. Först måste du försöka hitta ledig kapacitet inom lagret genom att konsolidera med befintliga lagersaldot. Om konsolideringen är inte möjligt, då måste du hitta en tom plats. 

För detta scenario, måste du definiera två platsdirektivåtgärder. Den första åtgärden i sekvensen måste **konsolidera** strategi, och den andra ska använda den **tomma platsen med några inkommande arbete** strategi. Om du definierar en tredje handlingsplan för att hantera ett överskott scenario två utfall är möjliga när det inte finns något mer kapacitet i lagret: arbete kan skapas även om inga lagerplatser definieras eller arbete processen kan misslyckas. Resultatet bestäms av inställningar på **plats direktiv fel** sida, där du kan bestämma om du vill välja **stopp på plats direktiv fel** alternativ för varje arbetsorder.

