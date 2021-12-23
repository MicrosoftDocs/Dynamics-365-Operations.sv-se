---
title: Processguideram
description: Det här ämnet ger information om ramverket för processguide som utökar våra mobila lagerprocesser i X++.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902056"
---
# <a name="process-guide-framework"></a>Processguideram

[!include [banner](../includes/banner.md)]

Det här ämnet ger information om ramverket för processguide som utökar våra mobila lagerprocesser i X++. De mobila processerna för lagerstället utökas när processerna bryts ned i små steg. Affärslogiken och användargränssnittet i varje steg har extraherats till individuella klasser, vilket gör att de kan utökas.

## <a name="overview-of-the-existing-design"></a>Översikt över befintlig design

Flödet för mobila lagerställen visas via en enda anpassad tjänsteslutpunkt. Begäran ankommer från mobilappen i form av en XML-sträng som innehåller metadata för det användargränssnitt som presenteras i den mobila appen, samt de värden som anges av användaren.

När en begäran tas emot är det första steget att deserialisera denna XML. Med klassen **WHSMobileAppServiceXMLTranslator** konverterar XML till en behållare som innehåller både kontrollinformationen och sessionsinformationen.

Efter detta används informationen i behållaren för att härleda vilken lagerprocess användaren arbetar med eller ska starta (representeras av **WHSWorkExecuteMode** uppräkning) och följaktligen instansiera en härledd klass av **WHSWorkExecuteDisplay**. Metoden **displayform()** anropas, som sedan gör följande:

-   Bearbetar data från användaren (delegerad till klassen **WHSRFControlData**, men vissa processer implementerar specifik logik genom att åsidosätta **processControl()** metod).

-   Utför affärslogik.

-   Inkrementerar steget.

-   Bygger behållaren som representerar det nya användargränssnittet (vanligtvis i ett **version...()** metod).

Behållaren returneras sedan till översättaren, som sedan serialiserar XML och skickar tillbaka den som ett svar till den mobila enheten.

Följande sekvensdiagram visar en översikt över exekveringsflödet. Observera att diagrammet är mer av en schematisk översikt och inte är en 1:1-representation av den faktiska koden.

![Schematisk översikt över processen.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Orsak till omdesign

Ovanstående design ger ett mycket enkelt ramverk för byggprocesser som används i mobilflöden. Precis som ovan har emellertid **displayform()**-metoderna flera ansvarsområden att ta över. De delegeras till andra metoder och klasser men om klassansvar saknas utförs det på ett inkonsekvent sätt mellan klasserna. I takt med att antalet scenarier som stöds växer, kan vissa av dessa klasser bli komplexa. För att göra det effektivare kan vissa av dessa klasser/metoder åsidosättas och används på flera olika sätt. Resultatet är mycket långa metoder med hög komplexitet. Detta har tidigare underhållsproblem. Att korrigera dessa metoder har varit riskabelt och känsligt.
Till exempel metoden **processWorkLine()** i klassen **WhsWorkExecuteDisplay** hänvisas från flera processer (i princip var som helst där arbete utförs).

Om du vill göra dessa utökningsbara är ett av alternativen att dela upp metoderna **displayForm** i mindre metoder och införa utvidgningspunkter. På grund av scenariomatrisen skulle det dock vara krävande för partner att skriva utvidgningar och validera mot dem. På grund av att det inte finns någon strukturerad ansvarsfördelning som anges ovan skulle koden inte bara innebära att koden skulle växa på ett oförutsägbart sätt över tiden och innebära otidsenliga strukturering av kvalitetstillägg.

Det innebär att det här är alternativet för omarbetning, med ett mål som innebär att du måste ha klart definierade klasser med oberoende ansvarsområden. En klass bör ha ett ansvarsområde, en orsak till ändring och en orsak till att den utökas.

## <a name="design-overview"></a>Designöversikt

I det omdesignade ramverket bygger kärnstrategin på två principer: dela upp körningsflödet i enskilda komponenter med väldefinierade ansvarsområden och har väldefinierade anknytningspunkter i var och en av komponenterna.

Namnet på det nya ramverket är "ProcessGuide". Detta beror på att syftet med dessa klasser är att leda en användare genom en affärsprocess (i motsats till den rich-klient som är en formulärbaserad erfarenhet där användaren har mer flexibilitet i hur de samverkar med data eller i vilken ordning de utför uppgifter).

> [!NOTE]
> En noterbar detalj är det avsiktliga utelämnandet av "WHS"-prefixet. Även om de mobila processerna ursprungligen införas för lagring, har de satt gränser för olika tillverknings- och lagerhanteringsprocesser. Då exkluderades lagerställereferensen i namnet på ramverket.

Om du vill identifiera komponenterna blir det första steget att undersöka processen Produktionsstart (klassen **WhsWorkExecuteDisplayProdStart**). Här är ett schema över processen.

![Bild av den schematiska processen.](media/production-start-process-schematic.png)

När du tittar på kontrollflödet behövs följande komponenter:

-   En kontrollant som går igenom hela affärsprocessen.
-   Ett steg som ansvarar för utförandet av ett steg i processen.
-   En dataprocessor för bearbetning av data i ett steg.
-   En sidskapare som ansvarar för att bygga användargränssnittet för ett steg.
-   En navigationsagent som ansvarar för stegomställningen.
-   En klass som ansvarar för att köra affärsprocessen.

Om du börjar i steg 1 och börjar bearbeta data från det föregående steget i processflödesdiagrammet ovan och sedan slutar med att bygga ett användargränssnitt, kommer dessa data att fortsätta att bearbetas i nästa steg. Detta introducerar en strikt relation mellan på varandra följande steg vilket innebär att vår nya schematiska nivå skulle se ut som följande:

![Bild av schematisk process på hög nivå.](media/high-level-schematic.png)

Följande är nyckelkomponenterna i den omdesignade processen:

-   **ProcessGuideController** - Den här klassen orkestrerar affärsprocessens övergripande körning. Den definierar de faktorer som instantierar steget och navigeringsagenten, som senare utgör processkörningen, samt rensningslogiken för annullering eller avsluta processen.

-   **ProcessGuideStep** – Den här klassen representerar ett enda steg i affärsprocessen. Den här klassen innehåller en definition av de faktorer som instantierar en sidskapare, åtgärder och dataprocessorer och ansvarar för att de visas i rätt ordningsföljd.

-   **ProcessGuideNavigationAgent** - Den här klassen ansvarar för navigering mellan stegen. När ett steg har slutförts ansvarar navigeringsagenten för att definiera nästa steg och passerar parametrar som det föregående steget kan behöva för att kommunicera med nästa.

-   **ProcessGuidePageBuilder** - Den här klassen ansvarar för att instantiera användargränssnittet.

-   **ProcessGuideAction** - Den här klassen representerar en åtgärd, visad som en knapp för användaren.

-   **ProcessGuideDataProcessor** - Den här klassen ansvarar för bearbetningen av de data som användaren har angett i ett fält.

## <a name="execution-flow"></a>Körningsflöde

Startpunkten för körningsflödet förblir oförändrad. Begäran anländer alltså fortfarande via samma slutpunkter, följt av deserialisering av XML i behållaren. Denna behållare överförs sedan till **getNextFormState()**.

Det finns tre viktiga klasser att notera:

-  **ProcessGuideSessionState** – Den här innehåller information om sessionstillstånd – läge, pass, kontrollant och steg som utförs, osv.

-  **ProcessGuidePage** – Denna innehåller en starkt typ av användargränssnittsmetadata.

-  **ProcessGuideRequest** – Detta innehåller de två ovanstående som medlemmar och är en starkt skriven representation av begäran som tagits emot från den mobila enheten.

Dessa klasser skapas med hjälp av behållarinformationen (både status och registrerade kontrolldata för användaren). På så sätt kan du komma åt och manipulera värdena på ett typ säkert sätt. Jämfört med upprepad åtkomst till behållaren under processen, är det till fördel för både läsbarhet och prestanda.

Informationen om sessionstillstånd används för att instantiera rätt **ProcessGuideController**-klass. När den har instantieras anropas metoden **createResponse()** i klassen **ProcessGuideController**. Den här metoden är startpunkten i processguidelogiken och kommer tillbaka med svaret (representerad i klassen **ProcessGuideResponse**) efter körningen. Svaret konverteras sedan tillbaka till behållaren och tillbaka till den äldre logiken, som sedan serialiserar den till XML och skickar tillbaka svaret till den mobila enheten.

Sedan behöver kontrollant hitta nästa steg för att köra. Om en ny process startas anropar kontrollanten **initialStep()** för att få ett första steg i processen. Därefter kallas det **execute()** metoden i **ProcessGuideStep**. Med den här metoden kan du instantiera en klass för **ProcessGuidePageBuilder** och anropa **buildPage()**, som kan returnera ett **ProcessGuidePage** objekt som är en virtuell representation av användargränssnittet som ska visas för användaren. Steget skickar sedan tillbaka resultatet till kontrollanten som sedan sparar den aktuella sessionen och returnerar sedan resultatet till **getNextFormState()** i formuläret för klassen **ProcessGuideResponse**.  Svaret konverteras sedan tillbaka till behållaren och serialiseras sedan till XML och skickar tillbaka svaret till den mobila enheten.

I bilden nedan förklaras det här kontrollflödet. Observera att detta är det vanligaste kontrollflödet, förenklat för att förklara designen.

![Förenklat kontrollflöde.](media/control-flow.png)

När användaren vidtar en åtgärd på den mobila enheten genom att klicka på en knapp (eller skanna ett värde – vilket vanligtvis utlöser standardåtgärden) – kommer begäran till metoden **createResponse()** i klassen **ProcessGuideController** via samma flöde. Vid denna tidpunkt vet dock kontrollanten från sessionens delstatsinformation vilket steg användaren är i. Därför instantierar det lämplig **ProcessGuideStep**-klass och startar körningsmetoden. I **ProcessGuideStep**, i sin tur, läser han eller hon åtgärdsnamnet som användaren anropar och instantierar sedan lämplig **ProcessGuideAction**-klass och anropar **execute()**.

**ProcessGuideAction**-klassen ansvarar för körning av den specifika åtgärden, men det finns två noteringsbara undantag.

Den första är **ProcessGuideOKAction**-klassen.  Den här åtgärden innebär att användaren vill bekräfta och gå framåt i processen. I enlighet med det – den här metoden anropar i själva verket ProcessGuideStep-klassen vilket innebär att steget anropar **processData()** i **ProcessGuideDataProcessor**. Den bearbetar de data som användaren har angett och uppdaterar sedan statusen för steget och skickar resultatet tillbaka till kontrollanten. Beroende på resultatet av bearbetningen startar steget sidskapare för att bygga lämpligt användargränssnitt eller anger status för steget som slutfört. Det visas i den övre halvan av sekvensdiagrammet nedan.

Det andra undantaget är annulleringsåtgärden som implementerats i klasserna **ProcessGuideCancelResetProcessAction** och **ProcessGuideCancelExitProcessAction**. Dessa åtgärder representerar en avsikten att avbryta processen och antingen gå tillbaka till början av processen eller avsluta processen helt. Precis som **OK**-åtgärden utför dessa åtgärder även en motringning till steget, som innehåller avsikten med **ProcessGuideController**.  Kontrollanten utför sedan den nödvändiga rensningen av tillståndsvariabler och flyttar antingen kontrollen till det första steget i processen eller avslutar processen helt.

När steget är slutfört, om statusvärdet för steget är **Slutfört**, instantierar kontrollanten **ProcessGuideNavigationAgent**, som returnerar namnet på nästa steg. Kontrollanten instantierar sedan det här steget och startar metoden **execute()** – och cykeln fortsätter. Vanligast är att det nya steget anropar motsvarande **ProcessGuidePageBuilder** för att bygga användargränssnittet för nästa skärm som ska visas för användaren, som sedan skickas tillbaka. Detta flöde beskrivs i den nedre halvan av sekvensdiagrammet nedan.

![sekvensdiagram.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Skapa en ny process med hjälp av ProcessGuide-ramverket

Det bästa sättet att förklara kontrollflödet är att använda ett exempel som finns i programmet – startprocessen för produktion.

## <a name="overview-of-the-production-start-process"></a>Översikt över produktionens startprocess

Vi börjar med att förstå processflödet. I det första steget tillfrågas användaren om produktionsorder-ID.

![Fråga efter produktions-ID.](media/production-id-prompt.png)

När användaren anger produktionsorder-ID valideras ordernumret. Vissa valideringar som körs baseras på om ordern finns i samma lagerställe som användaren är inloggad i och status för ordern. Om valideringen misslyckas visas ett felmeddelande. Om valideringen lyckas visas användaren information om tillverkningsordern och artikeln.

Användaren kan antingen avbryta för att gå tillbaka till början av processen eller klicka på **OK** för att bekräfta. I det senare fallet ställs tillverkningsordern in på **Startad**, motsvarande journaler bokförs, kontrollen går tillbaka till det första steget och meddelandet "Arbete slutfört" visas för användaren.


## <a name="creating-the-controller"></a>Skapa kontrollant

Det första steget i att bygga affärsprocessen är att skapa controllerklassen, som sträcker sig från **ProcessGuideController** abstrakta klassen som implementerar en kontrollants standardbeteende. Det nya klassnamnet är **ProdProcessGuideProductionStartController** och det dekoreras med **WHSWorkExecuteMode** värdet från **StartProdOrder**. Samma **SysExtension**-baserade instantiation som används i **WHSWorkExecuteDisplay** används, vilket hjälper till att instantiera controllern när användaren utför en menyartikel för det här läget.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> Klassens namnmönster är **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>kontrollant**. Detta är det mönster som används för kontrollantklasserna och som kan utökas till andra klasser.


## <a name="building-the-first-step"></a>Bygger det första steget

För att sedan definiera ett första steg ska du skapa klassen **ProdProcessGuidePromptProductionIdStep** som utökar, från **ProcessGuideStep**.

Uppgiften att instantiera klassen delegeras till en stegfabrik, som startas av basklassen **ProcessGuideController**.  Standardimplementering av fabrik instantierar steget baserat på namn. För att instantiera **ProdProcessGuidePromptProductionIdStep** som ett första steg i kontrollant måste du därför göra två saker:

-   När den här klassen avslogs **ProdProcessGuidePromptProductionIdStep**-klassen med ett **ProcessGuideStepName**-attribut. 

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   I kontrollant klassen implementerar du den abstrakta metoden **initialStepName()** för att returnera stegnamnet.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> Värdet i attributet **ProcessGuideStepName** behöver inte exakt matcha klassnamnet som visas ovan. Om du inför detta blir det dock möjligt att enhetlig och typsäkerhet kring korsreferenser när du använder klassen. Du rekommenderas att använda den här namnkonventionen.
>
> **ProcessGuideStepName** baserade instantiation av steget implementeras i **ProcessGuideStepDefaultFactory** klass. I sällsynta fall som du vill ha en annan strategi för instantiating steget, måste du göra följande:
> -   Skapa en ny fabriksklass som ärver från **ProcessGuidStepAbstractFactory**.
> -   Du kan om du vill skapa en ny parameterklass för implementering av gränssnittet **ProcessGuideIStepCreationParameters** som innehåller de parametrar som behövs för fabrikstypen.
> -   Åsidosätt metoderna **stepFactory()** och **stepCreationParameters()** i din kontrollantklass om du vill returnera fabriks- och parametrarna ovan.

Nästa steg är då att implementera funktionerna i klassen **ProdProcessGuidePromptProductionIdStep**. Du måste implementera logiken för att bygga användargränssnittet, bearbeta data som angetts av användare och bestämma när steget är slutfört.

### <a name="building-the-user-interface-for-the-first-step"></a>Bygga användargränssnittet för det första steget

Användargränssnittet skapas med en klass som ärver från den abstrakta klassen **ProcessGuidePageBuilder**.  Ge klassen ett namn som motsvarar det som den gör – **ProdProcessGuidePromptProductionIdPageBuilder**.

Instantiationsmekanismen för klassen liknar hur steget instantierades från kontrollanten. 

-   När den här klassen avslogs **ProdProcessGuidePromptProductionIdPageBuilder**-klassen med ett **ProcessGuidePageBuilderName**-attribut. 

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   I klassen **ProdProcessGuidePromptProductionIdStep** ska du implementera den abstrakta metoden **pageBuilderName()** för att returnera det här namnet.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Liknar stegfabriken men det finns även ett abstrakt fabriksmönster som implementerats för sidskapare fabrik. I sällsynta fall som du vill ha en annan strategi för instantiera sidskapare, kan du göra följande:
> - Skapa en ny fabriksklass som ärver från **ProcessGuidePageBuilderAbstractFactory**.
> - Du kan om du vill skapa en ny parameterklass för implementering av gränssnittet **ProcessGuideIPageBuilderCreationParameters** som innehåller de parametrar som behövs för fabrikstypen.
> - I din stegklass, åsidosätt metoderna **pageBuilderFactory()** och **pageBuilderCreationParameters()** om du vill returnera fabriks- och parametrarna ovan.

Om du vill implementera användargränssnittet behöver du en sida med en textruta för att ange tillverkningsorder-ID:t plus en **OK**-knapp och knappen **Avbryt**. Knappen **Avbryt** ska avsluta processen.

Om du vill implementera detta måste du åsidosätta två metoder i klassen **ProdProcessGuidePromptProductionIdPageBuilder**:

-   Använd metoden **addDataControls()** för att lägga till textrutan.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Använd metoden **addActionControls()** för att lägga till knapparna **OK** och **Avbryt**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Detta lägger till datakontrollerna, följt av knapparna. Om du istället vill skapa en skärm med varierade datakontroller och knappar kan du åsidosätta metoden **addControls()** för flexibilitet.

Ett extra scenario att ta hänsyn till är hur sidan ska byggas om ett valideringsfel uppstår, till exempel om användaren anger fel tillverkningsorder-ID. Basklassen **ProcessGuidePageBuilder** implementerar standardbeteendet, som bygger om användargränssnittet, rensar bort det skannade värdet och lägger till felkontrollen med felmeddelandet. Eftersom du vill använda standardbeteendet behöver du inte lägga till kod för hanteringsfel.

> [!TIP]
> Om du vill implementera anpassat användargränssnitt vid felsituationer kan du åsidosätta en eller flera metoderna **rebuildFromRequestPage()**, **isErrorState()** och **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Bearbeta den användarinformation som angetts i det första steget

Bearbetningen av data sker i klassen **ProcessGuideDataProcessorDefault** som i sin tur anropar den äldre klassen **WhsRfControlData**. Inga ändringar behövs av det här standardbeteendet och **WhsRfControlData** har redan logik för att validera fältet **ProdId** så du behöver inte skriva någon logik för att hantera detta. Vid obligatoriska utökningar av valideringslogiken kan det vara bra att använda **WhsControl**-baserad tilläggsmekanism.

### <a name="determine-if-the-first-step-is-complete"></a>Bestäm om det första steget är slutfört

När valideringen lyckas är det dags att markera steget som slutfört. Detta görs i basklassen men du måste implementera villkoret för att bestämma slutförandesteget. Det gör följande åsidosättningsmetod.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Steg två: Visa orderdetaljer och bekräfta

I det andra steget i processen visas användaren en skärm med detaljerad information om ordern. Användaren kan antingen klicka på knappen **OK** för att bekräfta tillverkningsordern, eller klicka på **Avbryt** för att go back gå tillbaka till början av processen. I det här exemplet ska du namnge steget **ProdProcessGuideConfirmProductionOrderStep** och sidskaparklassen **ProdProcessGuideConfirmProductionOrderPageBuilder**.

Klassen ProdProcessGuideConfirmProductionOrderStep ser ut på följande sätt.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Eftersom användaren inte anger några värden här behöver du inte åsidosätta metoden **isComplete()**.  Steget är slutfört när användaren klickar på **OK**.

Sidskaparklassen åsidosätter metoden **addDataControls()** för att lägga till tre etiketter. Den första etiketten visar tillverkningsorder-ID:t, den andra innehåller artikelinformation (t.ex. artikel-ID, dimensioner eller beskrivning) och den tredje innehåller kvantitet och måttenhet.

**addActionControls()** åsidosätts sedan för att lägga till 2 knappar – knappen **OK** och knappen **Avbryt** för att avbryta processen och gå tillbaka till början av processen.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Du kan hitta samma källkod för X++-metoderna i det här ämnet genom att använda Programutforskaren. Filtrera på klassnamnet, högerklicka sedan på klassnamnet och välj **Visa kod**.

### <a name="step-3-start-the-production-order"></a>Steg 3: Starta produktionsorder

Det tredje steget är där affärslogiken när tillverkningsordern körs. Detta steg skiljer sig något från de föregående stegen eftersom det här steget inte har något användargränssnitt. Detta steg körs i tyst ordning när användaren klickar på **OK** i föregående steg.

Den abstrakta klassen **ProcessGuideStepWithoutPrompt** implementerar standardbeteendet för sådana steg. Det aktuella steget bör därför utöka klassen **ProcessGuideStepWithoutPrompt** och åsidosätta metoden **doExecute()**.

Följande kodexempel visar klassen och metodimplementering **doExecute()**. Metoden hämtar helt enkelt order-ID och användar-ID från sessionstillstånd och aktiverar metoden för att starta denna tillverkningsorder.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

Vid ett undantag ser ramverkets undantagshanteringslogiken till att processen återställs till föregående steg.

> [!NOTE]
> Anropa till **addProcessCompletionMessage()** lägger till meddelandet "Arbete slutfört" i navigeringsparametrarna. Nästa steg (förutsatt att det har ett användargränssnitt) visar meddelandet. Basklasserna hanterar den här logiken och ingen specifik kod behöver läggas till processklasserna för att beteendet ska kunna uppnås.


### <a name="building-the-navigation-through-the-steps"></a>Bygga navigeringen genom stegen

Basklassen **ProcessGuideController** instantierar klassen **ProcessGuideNavigationAgentDefault** som förlitar sig på en fördefinierad navigeringsrutt, som är en enkel karta över käll- och destinationssteg. För produktions startscenariot, eftersom det inte finns någon villkorlig förgrening, skulle den här implementeringen avse. Därför behöver du bara åsidosätta metoden **initializeNavigationRoute()** för att definiera navigeringsflödet.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Det finns processer där det ska finnas villkorsbaserade förgrening (baserat på användaråtgärder eller andra villkor). Följande processer behövs:

-   Implementera specifika navigeringsagenter som ärvs från **ProcessGuideNavigationAgent**-klassen. 

-   Implementera den specifika navigationsagentfabriken som ärvts från klassen **ProcessGuideNavigationAgentAbstractFactory** som innehåller logik för att instansiera rätt navigeringsagent baserat på aktuellt steg, sessionstillstånd, användaråtgärd eller annan logik.

-   Du kan även åsidosätta **navigationAgentCreationParameters()** i kontrollantklassen för att skicka lämpliga parametrar.

-   Åsidosätt **navigationAgentFactory()** i kontrollant för att instantiera navigationsagentfabriken som skapats ovan.

### <a name="action-classes"></a>Åtgärdsklasser

Åtgärdsklasser representerar användaråtgärder, så i det här exemplet används **OK**-åtgärden för att visa hur åtgärderna skapas.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

Klassen måste implementera 2 abstrakta metoder:

-   **label()** som returnerar etiketten som ska visas i en knappkontroll kopplad till den här åtgärden.

-   **doExecute()** som utför åtgärden. Som tidigare har nämns utför **OK**-knappen helt enkelt en motringning till steget. Andra åtgärder kan dock ha mer komplex logik här.

Åtgärderna instantieras med **SysExtension**-ramverket baserat på attributet **ProcessGuideActionName**.  Liknar instansen av sidskapare implementerar stegklassen standardåtgärdsfabriken och det går att åsidosätta detta. Sidskapare lägger till en knappkontroll på det här sätt.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

När du gör det får den en fråga om du vill skapa en åtgärdsklass för det godkända namnet och den åtgärden ska tryckas ned på knappen.

### <a name="summary"></a>Sammanfattning

Sammanfatta allt som förklaras i det här avsnittet med en omfattande sammanfattning av den kod som behövs för processen:

1.  **ProdProcessGuideProductionStartController**

    1.  Åsidosätt **initialStepName()** om du vill ange namnet på det första steget.
    2.  Åsidosätt **initializeNavigationRoute()** när du vill skapa navigeringskartan.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Åsidosätt **isComplete()** för att ange när steget betraktas som slutfört.
    2.  Åsidosätt **pageBuilderName()** om du vill ange vilken sidskapare som ska användas.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Åsidosätt **addDataControls()** om du vill lägga till textrutan **Prod ID**.
    2.  Åstidosätt **addActionControls()** för att lägga till knapparna **OK** och **Avbryt**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Åsidosätt **pageBuilderName()** om du vill ange vilken sidskapare som ska användas.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Åsidosätt **addDataControls()** för att lägga till beställnings-, artikel- och kvantitetsinformationsetiketter.

    2.  Åstidosätt **addActionControls()** för att lägga till knapparna **OK** och **Avbryt**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > Metoden **generateItemInfoForProdId()** som används för att generera artikelinformationsetiketter finns inte med i det här avsnittet. Med den här metoden får du ett par register för att få artikel-ID, beskrivning och dimensioner. Om du vill ha en bättre förståelse för **generateItemInfoForProdId()** kan du titta på källkoden.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Åsidosätt **doExecute()** om du vill utföra produktionens startprocess och lägga till processens slutförandemeddelande.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Observera att en stor del av de vanliga mönstren (konsumtionsmönster för UI vid fel, inställning av meddelande om slutförande av process, **OK** och **Avbryt** beteende) har flyttats till ramverket – vilket sparar programutvecklaren från att skriva en kod med återkommande kod som är både felkänslig och innebär en risk för inkonsekvent beteende över processer. Där scenariot måste avvika från den gemensamma sökvägen får programutvecklaren även alternativet att åsidosätta lämpliga metoder – men det är sedan en avvikelse som är tydlig och spårbar.


### <a name="extending-a-business-process"></a>Utöka en affärsprocess

Hittills har det här avsnittet markerat hur en ny process ska byggas med ramverket **ProcessGuide**. I det sista avsnittet finns några exempel på hur den här affärsprocessen kan utökas.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Lägga till ett steg i ett flöde (med hjälp av ProcessGuideNavigationAgentDefault)

Plats att utöka:

-   Underordnad **ProcessGuideController**-klass för processen.

Så här utökar du:

-   Utöka metoden **initializeNavigationRoute()** i kontrollantklass och anropa **addFollowingStep()** i klassen **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Lägga till ett steg i ett flöde (med hjälp av anpassad navigeringsagent)

Plats att utöka:

-   Underordnad till **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Så här utökar du:

-   Skapa en ny underordnad klass av **ProcessGuideNavigationAgent** som returnerar önskat stegnamn.

-   Skapa en ny klass som härleds från **ProcessGuideNavigationAgentFactory** som enligt vissa villkor returnerar navigeringsagenten som skapats ovan.

-   Utöka metoden **navigationAgentFactory()** i kontrollantklass för att returnera fabriken som skapats ovan.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Lägga till en ny kontroll i användargränssnittet för ett befintligt steg 

Plats att utöka:

-   Underordnad **ProdProcessGuidePageBuilder** till steget.

Så här utökar du:

-   Utöka metoden **addDataControls()** och lägg till ytterligare kontroll.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Fullständigt se till att användargränssnittet används i ett befintligt steg

Plats att utöka:

-   Underordnad **ProdProcessGuideStep**.

Så här utökar du:

-   Skapa en ny underordnad klass till **ProdProcessGuidePageBuilder** och implementera önskat användargränssnitt.

-   Utöka metoden **pageBuildeName()** i stegklassen för att returnera **ProcessGuidePageBuilderNameAttribute** för klassen som skapats ovan.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Ändra logik när ett steg anses vara slutfört

Plats att utöka:

-   Underordnad **ProdProcessGuideStep**.

Så här utökar du:

-   Utöka metoden **isComplete()** om du vill bygga ytterligare logik.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]