---
title: "Rapportträddefinitioner i ekonomiska rapporter"
description: "Den här artikeln innehåller information om rapportdefinitioner. En rapportträdsdefinition är en rapportkomponent eller ett byggblock som bidrar till att definiera strukturen och hierarkin i din organisation."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 331f3480b8454dac7da12be169ba017f36cefa06
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="reporting-tree-definitions-in-financial-reports"></a>Rapportträddefinitioner i ekonomiska rapporter

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om rapportdefinitioner. En rapportträdsdefinition är en rapportkomponent eller ett byggblock som bidrar till att definiera strukturen och hierarkin i din organisation.

Ekonomisk rapportering stöder flexibel rapportering så att du enkelt kan göra ändringar allt eftersom din verksamhetsstruktur ändras. Rapporter är uppbyggda av olika komponenter eller byggblock. Ett av de här byggblocken är en rapportträddefinition. En rapportträddefinition hjälper till att definiera din organisations struktur och hierarki. Det är en korsdimensionell hierarkisk struktur som baseras på de dimensionella relationerna i ekonomiska data. Den innehåller information på rapporteringsenhetsnivå och sammanfattningsnivå för alla enheter i trädet. Rapportträddefinitioner kan kombineras med kolumndefinitioner och rapportdefinitioner om du vill skapa en byggblocksgrupp som kan användas för flera företag. En rapportenhet används för varje ruta i ett organisationsschema. En rapportenhet kan vara en enskild avdelning från ekonomiska data, eller så kan det vara en summeringsenhet på hög nivå som kombinerar information från andra rapportenheter. För en rapportdefinition som innehåller ett rapportträd genereras en rapport för varje rapportenhet och för sammanfattningsnivån. Alla dessa rapporter använder rad- och kolumndefinitionerna som anges i rapportdefinitionen såvida inte rapportdefinitionen anger att rapportträdet från raddefinitionen ska användas. Rad- och kolumndefinitioner är viktiga komponenter i designen och funktioner för ekonomiska rapporter. Rapportträd ökar kraften och stöder komponenterna för flexibel rapportering allt eftersom verksamhetsstrukturen ändras. Ekonomiska rapporter som inte baseras på ett rapportträd använder bara några av de funktioner som finns för ekonomisk rapportering. Du kan använda flera rapportträddefinitioner tillsammans med samma rad- och kolumndefinitioner för att visa dina företagsuppgifter på olika sätt.

## <a name="reporting-tree-best-practices"></a>Regelverk för rapportträd
Innan du skapar ett rapportträd ska du tänka på följande regelverk:

-   Bestäm först vilka rapporteringsdimensioner som din juridiska person eller företag behöver.
-   Beakta hur du har ställt in din struktur och utforma sedan ett organisationsschema för ditt företag. Organisationsschemat kommer att hjälpa dig att visualisera hur du grupperar rapportenheterna till ett eller flera rapportträd.
-   Starta med den lägsta tillgängliga detaljnivån, till exempel avdelningar och projekt som definieras i ekonomiska data. Lägg till så många rutor på detaljnivån som krävs för att visa avdelningar eller regioner på hög nivå. Varje ruta motsvarar en potentiell rapportenhet i något rapportträd som du skapar.
-   Du måste också beakta det bästa sättet att bygga upp dina träd på. Du kan använda en automatiserad byggprocess för att skapa ett rapportträd eller så kan du skapa det manuellt. Det är viktigt att förstå båda metoderna innan du utformar dina träd.
-   Du kan använda rapportenheterna som definieras i ditt ekonomiska datasystem om du vill lägga till rapportenheter till rapportträddefinitionen.

## <a name="create-multiple-reporting-trees"></a> Skapa flera rapportträd
Du kan skapa ett obegränsat antal rapportträd för att visa ditt företags data på olika sätt. Varje rapportträd kan innehålla någon kombination med avdelningar och summeringsenheter. Rapportdefinitionen kan innehålla en länk till ett enda rapportträd åt gången. Genom att ordna om strukturen för rapportenheterna, kan du skapa olika rapportträd. Du kan sedan använda samma rad- och kolumndefinitioner för varje rapportträd. På så sätt kan du snabbt skapa layouter för olika ekonomiska rapporter. Om du skapar flera rapportträd kan du skriva ut en serie bokslut varje månad som analyserar och visar företagets verksamhet på flera olika sätt. Se exempel på rapportenhetsstrukturer i slutet av den här artikeln.

## <a name="create-a-reporting-tree-definition"></a> Skapa rapportträddefinition
En rapportträddefinition innehåller de kolumner som beskrivs i följande tabell.

| Rapportträdkolumn | beskrivning|
|---|---|
| Företag               | Företagsnamn för rapportenheten. Värdet **@ANY**, som normalt bara tilldelas sammanfattningsnivån aktiverar rapportträdet som ska användas för alla företag. Alla underordnade förgreningar har ett företag som tilldelats dem.|
| Enhetsnamn             | Den kod som identifierar den här rapportenheten i det grafiska rapportträdet. Se till att upprätta ett unikt kodsystem som är konsekvent och som är enkelt för användarna att förstå. |
| Enhetsbeskrivning      | Rapportenhetsrubriken visas i rapportens sidhuvudet eller sidfoten om du anger **UnitDesc** som kod i fliken **Sidhuvud och Sidfot** på rapportdefinitionen. Rubriken visas i rapportradbeskrivningen om du anger **UnitDesc** i cellen **Beskrivning** på raddefinitionen .|
| Dimensioner            | En rapportenhet om du vill ställa ut information direkt från ekonomiska data. Den definierar den logiska placeringen och längderna för kontot och de relaterade segmenten. Varje rapportenhetsrad måste ha en dimension i den här kolumnen. Du kan också placera en dimension på en rad för en summeringsenhet (till exempel för utgifter som är direkt kopplade till enheten). Om du anger en dimension på en rad för en summeringsenhet ska konton som används i överordnade enheter inte användas i underordnade. I annat fall kan belopp dubbleras.|
| Raddefinitioner       | Namnet på raddefinitionen för rapportenheten. Samma raddefinition används för varje enhet av rapportträdet. När du genererar en rapport används raddefinitionen för varje rapportenhet. Raddefinitionen kan innehålla flera länkar för ekonomiska dimensioner. Om en raddefinition har angetts i rapportträdet väljer du kryssrutan **Använd raddefinition från rapporteringsträd** på fliken **Rapport** i rapportdefinitionen.|
| Radlänk              | Radlänken som ska användas för rapportenheten. Radlänkar definieras för att raddefinitionen ska kunna identifiera ekonomiska dimensioner som du vill länka till.|
| Extern länk         | Radlänken som ska användas för denna rapportenheten. Radlänkar definieras för att raddefinitionen ska kunna identifiera den rapport du vill länka till.|
| Extern fil         | Sökvägen till kalkylbladet för den ekonomiska rapporten som data hämtas från.|
| Sidalternativ          | Den här kolumnen styr om detaljer för rapportenheten ska ignoreras när rapporten visas eller skrivs ut.|
| Samlad uppdatering för %              | Den procentandel av rapportenheten som ska tilldelas till den överordnade enheten. Den procentandel som du anger i den här kolumnen gäller för varje rad i raddefinitionen innan värdet i raden läggs till den överordnade rapporten. Om till exempel en underordnad enhet ska fördelas jämnt mellan två avdelningar multipliceras beloppet på varje rad med 50 procent innan det läggs till i avdelningsrapporten. En rapportenhet kan inte ha två överordnade enheter. om du vill fördela beloppen från en rapportenhet till två överordnade enheter ska du skapa en annan rapportenhet med samma dimension för att samla de ytterligare 50 procenten. Ange hela procenttalet utan decimaltecken. **25** exempelvis representerar 25 procent allokering till den överordnade enheten. Om du inkluderar ett decimaltecken (**,25**) allokeras 0,25 procent till den överordnade enheten. Om du vill använda en procentsats som är mindre än 1 procent ska du använda alternativet **Tillåt samlad uppdatering &lt;1%** i rapportdefinitionen. Detta alternativ är på fliken **Ytterligare alternativ** i dialogrutan **Rapportinställningar**. Du kommer åt den här dialogrutan från knappen **Övrigt** på fliken **Inställningar** i rapportdefinitionen. |
| Enhetssäkerhet         | Begränsningar för hur användare och grupper kan komma åt informationen för rapportenheten.|
| Ytterligare text       | Text som inkluderas i rapporten.|

Om du vill skapa en rapportträddefinition, följ dessa steg:

1.  Öppna Report Designer.
2.  Klicka på **Fil** &gt; **Ny** &gt; **Rapportträddefinition**.
3.  Klicka på **Redigera** &gt; **Infoga rapportenheter från dimensioner**.
4.  I dialogrutan **Infoga Rapportenheter från Dimensioner** väljer du kryssrutan för varje dimension som ska inkluderas i rapportträdet. Dialogrutan **Infoga rapportenheter från dimensioner** innehåller följande avsnitt.

    | Avdelning                          | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
    |----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Rapportera dimensionsegmentering | Använd knapparna **Dela segment** och **Kombinera segment** för att ändra antalet och längden på segment. **Obs!** Du kan enbart kombinera segment som du har delat. Använd jokertecken i dina dimensionsvärden om du vill kombinera flera dimensioner.                                                                                                                                                                                                          |
    | Inkludera/teckenbefattning       | Det här avsnittet visar dimensionerna som definieras i ekonomiska data och antalet tecken i det längsta värdet som definieras för varje dimension. Välj kryssrutan för en dimension om du vill inkludera dimensionen i rapportträdhierarkin.                                                                                                                                                                                           |
    | Segmentera hierarkin och intervaller     | Det här avsnittet visar dimensionshierarkin. Du kan flytta dimensionerna i listan om du vill ändra deras rapporteringorder. Du kan ange många olika värden för varje dimension i fälten **Från dimension** och **Till dimension**. Om du inte anger ett intervall kommer alla dimensionsvärden att infogas i rapportträdet. **Obs!** Om du använder mer än en dimension returneras endast dimensionskombinationer som har bokförts med i resultatet. |

    Om du vill se en skärmbild som visar ett exempel på dialogrutan **Infoga rapportenheter från dimensioner** kan du titta i avsnittet "Exempel på Infoga rapporenheter från dialogrutan dimensioner" senare i den här artikeln.
5.  Om du vill skapa fler segment (såsom dela ett segment i två kortare delar) ska du klicka på den rätta platsen i fältet **Teckenposition** och sedan klicka på **Dela segment**.
6.  Om du vill slå ihop två segment till ett klickar du på någon av segmentrutorna som ska slås ihop och sedan på **Kombinera segment**.
7.  Hierarkin definierar hur dimensioner rapporterar till varandra och intervallet för varje dimension. Om du vill ändra dimensionshierarkin i området **Segmenthierarki och intervall**, välj den dimension som ska flyttas och klicka sedan på **Flytta upp** eller **Flytta ned**.
8.  Om du vill ange ett intervall med dimensionsvärden för att lägga till den nya rapportträdet i området **Segmentera hierarki och intervaller** följer du stegen nedan:
    1.  I fältet **Från dimension** för den dimensionen ska du ange det första värdet i intervallet.
    2.  I fältet **Till Dimension** anger du det sista värdet i intervallet.

9.  Upprepa steg 7 till 8 för varje dimension i området **Segmentera hierarki och intervall**.
10. Klicka på **OK** när du har definierat hur dina rapportenheter ska flyttas till det nya rapportträdet.
11. Klicka på **Fil** &gt; **Spara** för att spara rapporteringsträdet. Ange ett unikt namn och en beskrivning för rapportträdet och klicka sedan på **OK**.

### <a name="open-an-existing-reporting-tree-definition"></a>Öppna en befintlig rapportträddefinition

1.  I Report Designer klicka på **Rapportträddefinitioner** i navigeringsfönstret.
2.  Dubbelklicka på ett namn i rapportträdlistan för att öppna den.
3.  Om du vill visa alla byggblock som är associerade med rapportträdet, högerklicka på rapportträddefinitionen och välj sedan **Associationer**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Rulla upp data i ett rapportträd

När du använder ett rapportträd kan du slå ihop belopp från underordnade rapportenheter på den överordnade rapportenhetsnivån. Detta kallas rulla upp data. Följande regler används för att rulla upp belopp till överordnade enheter i ett rapportträd:

-   I ett rapportträd måste underordnade enheter innehålla dimensioner, om det inte är ett rapportträd i en nivå. Överordnade enheter innehåller vanligtvis inte dimensioner i ett rapportträd. **Obs!** När du registrerar dimensioner för både överordnade och underordnade enheter kan detta orsaka fördubbling av data i rapporten.
-   Rapportenheter som innehåller dimensioner i rapportträdet motsvarar de dimensioner som används i rad- och kolumndefinitioner. Kombinationen av dimensioner bestämmer de belopp som ska returneras för den enheten. I exempel 2 senare i den här artikeln till exempel returneras enbart raderna 6 och 7 för avdelningarna 00 respektive 01.
-   Beloppen för de överordnade rapportenheterna som inte innehåller dimensioner i rapportträdet fastställs utifrån den underordnade rapportenheten och rullar upp beloppet till den angivna överordnade enheten. Om till exempel den överordnade enheten (se Contoso USA i exempel 2 i rulla upp data-exemplet) har två underordnade enheter (022 och 023) och inte innehåller dimensioner, genereras en rapport för varje underordnad enhet och den överordnade enheten. Överordnad summan är summan av de två underordnade beloppen.

### <a name="manage-reporting-units"></a>Hantera rapportenheter

Varje rapportträddefinition visas i separata vyer. Det finns en grafisk vy för att visa den överordnade/underordnade hierarkin och en kalkylbladsvy som visar särskild information för varje rapportenhet. Den grafiska vyn och kalkylbladvyn är kopplade. När du väljer en rapportenhet i en vy markeras den också i den andra vyn. Du kan bygga korsdimensionella hierarkier som baseras på de dimensionella relationerna i ekonomiska data. När du skapar en rapportträddefinition kan du använda samma raddefinitioner flera gånger oavsett om du skapar en resultaträkning för avdelningar eller en konsoliderad översiktsresultaträkning. Dimensionerna som definieras i raddefinitionen kan kombineras med dimensioner i rapportträddefinitionen för att ge en mängd olika vyer av organisationens resultat.

### <a name="reporting-unit-structure"></a> Rapportenhetsstruktur

Följande typer av rapportenheter används i ekonomisk rapportering:

-   En detaljenhet hämtar information direkt från ekonomiska data från ett Excel-kalkylblad eller från ett annat kalkylblad för ekonomisk rapportering.
-   En summeringsenhet sammanfattar data från enheter på lägre nivå.

En överordnad rapportenhet är en summeringsenhet som samlar in sammanfattande information från en detaljenhet. En summeringsenhet kan vara både en detalj- och en summeringsenhet. Därför kan en summeringsenhet hämta information från en enhet på lägre nivå, från ekonomiska data eller från ett Excel-kalkylblad. En överordnad enhet kan vara en underordnad enhet till en högre överordnad enhet. En underordnad rapportenhet kan vara en detaljenhet som hämtar information direkt från ekonomiska data eller från ett Excel-kalkylblad. En underordnad rapportenhet kan även vara en mellanliggande summeringsenhet. Med andra ord kan den vara en överordnad enhet till en enhet på en lägre nivå och även vara en underordnad enhet till en summeringsenhet på en högre nivå. Det vanligaste scenariot för rapportenheter är att överordnade enheter har en tom cell i kolumnen **Dimensioner** och att underordnade enheter har länkar till dimensionskombinationer för specifika tecken eller jokertecken.

### <a name="organize-reporting-units"></a> Ordna rapportenheter

Du kan ändra ordning på organisationsstrukturen för en rapportträddefinition genom att flytta rapportenheterna i den grafiska vyn. Du kan också höja upp rapportenheter till en högre nivå i rapportträdet eller flytta ned dem till en lägre nivå.

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Välj en rapportenhet i den grafiska vyn av rapportträddefinitionen.
3.  Dra enheten till en ny position. Alternativt kan du högerklicka på enheten och sedan välja **Höj upp rapportenhet** eller **Sänk ned rapportenhet.**
4.  Klicka på **Fil** &gt; **Spara** för att spara dina ändringar.

### <a name="add-text-about-a-reporting-unit"></a> Lägg till en text om en rapportenhet

En extra textpost är en statisk textsträng på upp till 255 tecken som lägger till information i rapportträddefinitionen. Den extra texten kan till exempel vara en kort företagsbeskrivning. Du kan skapa upp till tio ytterligare textinmatningar för varje rapportenhet i en rapportträddefinition. Den extra texten visas i rapporten för den rapportenhet som texten är tilldelad till. Du kan lägga till textposter från kolumnen **Beskrivning** i raddefinitionen och från fliken **Sidhuvud och sidfot** i rapportdefinitionen.

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Dubbelklicka på cellen **Mer text** på raden för rapportenheten.
3.  Skriv texten i den första tomma raden i dialogrutan **Mer text**. Den första raden som innehåller text refereras till som UnitText1, oavsett dess position i dialogrutan **Mer text**.
4.  Skriv in mer text på en tom rad om du vill lägga till fler textposter i den här rapportenheten.
5.  Klicka på **OK**.

### <a name="remove-additional-text-from-a-reporting-unit"></a>Ta bort ytterligare text från en rapportenhet

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Dubbelklicka på cellen **Mer text** på raden för rapportenheten.
3.  I dialogrutan **Mer text** kan du välja en post du vill ta bort och sedan klicka på **Rensa**. Du kan också högerklicka på posten och välj sedan **Klipp ut**.
4.  Klicka på **OK**.

### <a name="restrict-access-to-a-reporting-unit"></a>Begränsa åtkomst till en rapportenhet

Du kan förhindra vissa användare och grupper från åtkomst till en rapportenhet. Det går även att definiera begränsningar så att de gäller för rapportenheter som är underordnade andra rapportenheter.

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Dubbelklicka på cellen **Enhetssäkerhet** som rapportenhetsraden ska begränsa åtkomst till.
3.  I dialogrutan **Användare och grupper** klickar du på **Enhetssäkerhet**.
4.  Markera de användare eller grupper som ska ha åtkomst till rapportenheten och klicka sedan på **OK**.
5.  Markera kryssrutan **Lägg till säkerhet för underordnad rapportenhet** om du vill begränsa åtkomsten till underordnade rapportenheter.
6.  Klicka på **OK**.

### <a name="remove-access-to-a-reporting-unit"></a>Ta bort åtkomst till en rapportenhet

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Dubbelklicka på cellen **Enhetssäkerhet** på raden för rapportenheten som åtkomsten ska tas bort för.
3.  I dialogrutan **Enhetssäkerhet** väljer du ett namn och klickar sedan på **Ta bort.**.
4.  Klicka på **OK**.

### <a name="link-to-reports"></a>Länk till rapporter

Efter att du har skapat kolumnen **Rapport** i raddefinitionen och angett vilken rapport som ska inkluderas i rapporten måste du uppdatera rapportträdet med den länkade kolumnen och informationen om rapporten. En rapport kan importeras till alla enheter i rapportträdet.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identifiera rapporten i ett rapportträd

1.  Öppna rapportträddefinitionen i Report Designer för att ändra den.
2.  Kolumnen **Raddefinitioner** visar informationen i cellerna som baseras på information i den valda raden eftersom samma raddefinition måste användas i alla enheter i rapportträdet. Dubbelklicka på cellen **Raddefinitioner** och välj sedan den raddefinition som innehåller information om rapporten.
3.  I cellen **Länk till kalkylblad** för en rapportenhet väljer du det länknamn som motsvarar rapporten.
4.  Ange namnet på rapporten eller sök för att välja rapporten i cellen **Arbetsbok eller rapportsökväg**.
5.  Om du vill ange ett kalkylblad i rapporten skriver du in namnet på kalkylbladet i cellen **Kalkylbladsnamn**.
6.  Upprepa steg 3–5 för varje rapportenhet som ska ta emot data från en rapport. För att förhindra felaktiga data från att visas i din rapport ska du se till att korrekta rapportnamn visas för motsvarande enhet i rapportträdet

## <a name="examples"></a>Exempel
### <a name="reporting-unit-structure--example-1"></a>Rapportenhetsstruktur – Exempel 1

Här är strukturen för rapportenheter i följande rapportträd:

-   Rapporteringsenheten för Contoso Japan är överordnad enhet till de underordnade enheterna Contoso Japan Sales och Contoso Japan Consulting.
-   Enheten för Contoso Japan Sales division är både en underordnad enhet till enheten Contoso Japan och en överordnad enhet till enheterna Home Sales och Auto Sales.
-   Detaljrapportenheterna på lägsta nivån (Home Sales, Auto Sales, Client Services och Operations) representerar avdelningar i ekonomiska data. Dessa rapportenheter är det skuggade i området i diagrammet.
-   Summeringsenheterna på högre nivå sammanfattar informationen från detaljenheterna.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Rapportenhetsstruktur – Exempel 2

Följande diagram visar ett rapportträd för en organisationsstruktur som är uppdelad efter affärsfunktioner. [![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Exempel på dialogrutan Infoga Rapportenheter från Dimensioner

Det här illustrationen visar ett exempel på dialogrutan **Infoga Rapportenheter från Dimensioner**. I det här exemplet returnerar resultaten en kombination av affärsenheter, kostnadsställen och avdelningar. [![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png) Den resulterande rapportträdsdefinitionen sorteras efter affärsenheter, därefter efter kostnadsställe och sedan efter avdelning. Dimensionen för den femte rapportenheten är **Affärsenhet = \[001\], Kostnadsställe =\[\], Avdelning = \[022\]** och identifierar en rapportenhet för konton som är specifika för affärsenheten 001 och avdelningen 022. [![Rapporteringsträd](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Exempel på rulla upp data

Följande exempel visar möjlig information som används i en rapportträddefinition för ett exempel på att rulla upp data.

#### <a name="example-1"></a>Exempel 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Exempel 2

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

# <a name="see-also"></a>Se även

[Ekonomisk rapportering](financial-reporting-intro.md)




