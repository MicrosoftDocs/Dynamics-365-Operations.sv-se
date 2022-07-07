---
title: Hur arbetare använder körningsgränssnittet för produktionsgolvet
description: I denna artikel beskrivs hur du använder körningsgränssnittet för produktionsgolvet ur en arbetares synvinkel.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 2ee316a3e6a6baef7aa8b5d46b04a2d1bb07a641
ms.sourcegitcommit: d770f0e6a012675a3027641704be804beb99754b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2022
ms.locfileid: "9022535"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Hur arbetare använder körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Körningsgränssnittet för produktionsgolvet är optimerat för beröringsinteraktion. Dess design ger visuell kontrast som uppfyller tillgänglighetskraven för verkstadsmiljöer. Den erbjuder alla funktioner som jobbkortsenhet. Det gör dock också att flera jobb startas parallellt från en jobblista. (Den här funktionen kallas även för *buntning av jobb*.) Från en jobblista kan arbetare dessutom öppna en guide som har skapats i Microsoft Dynamics 365-guiden. På så sätt kan de visa visuella instruktioner för en HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Logga in på körningsgränssnittet för produktionsgolvet som en arbetare

Innan arbetarna kan börja använda enheten måste han eller hon förbereda den och öppna rätt sida i Dynamics 365 Supply Chain Management. Mer information om hur du konfigurerar en enhet finns i [Konfigurera en enhet att köra körningsgränssnittet för produktionsgolvet](production-floor-execution-setup.md).

När enheten har förberett visas inloggningssidan på den. På den här sidan visas information om status för jobb för den lokala arbetsgruppen. Denna information uppdateras regelbundet. På sidan använder arbetarna sin ID-bricka för att logga in. Även om arbetarna inte behöver ha ett användarkonto för Supply Chain Management, måste de ha ett konto för *tidsregistrerad arbetare* som de kan använda när de loggar in.

![Inloggningssida för körningsgränssnittet för produktionsgolv.](media/pfei-sign-in-page.png "Inloggningssida för körningsgränssnittet för produktionsgolvet")

I de återstående avsnitten i denna artikel beskrivs hur arbetare interagerar med gränssnittet.

## <a name="all-jobs-tab"></a>Fliken alla jobb

Fliken **Alla jobb** tillhandahåller en jobblista som visar alla produktionsjobb som har statusen *inte startad*, *stoppad* eller *startad*. (Det här fliknamnet är anpassningsbart och kan vara ett annat för systemet.)

![Fliken Alla jobb.](media/pfei-all-jobs-tab.png "Fliken alla jobb")

Det finns följande kolumner i jobblistan. Siffrorna motsvarar siffrorna i föregående illustration.

1. **Urvalskolumn** – kolumnen längst till vänster använder en bockmarkering för att visa jobb som har valts av arbetaren. Arbetare kan välja flera jobb i listan samtidigt. Om du vill markera alla jobb i listan markerar du kryssrutan i kolumnrubriken. När ett enstaka jobb väljs visas information om jobbet i den nedre delen av sidan.
1. **Kolumn för jobbstatus** – i den här kolumnen används symboler för att visa status för varje jobb. Jobb som saknar symbol i den här kolumnen har statusen *inte startad*. En grön triangel anger jobb som har statusen *startat*. Två gula lodräta linjer indikerar jobb som har statusen *stoppad*.
1. **Kolumnen hög prioritet** – i den här kolumnen används utropstecken för att ange jobb med hög prioritet.
1. **Order** – i den här kolumnen visas produktionsordernumret för ett jobb.
1. **Beskrivning** – i den här kolumnen visas en beskrivning av den åtgärd som ett jobb ingår i.
1. **Begärd** – den här kolumnen visar den kvantitet som ett jobb har planerats att producera.
1. **Startad** – i den här kolumnen visas den kvantitet som redan har startats för ett jobb.
1. **Slutförd** – i den här kolumnen visas den kvantitet som redan har slutförts för ett jobb.
1. **Kasserad** – i den här kolumnen visas den kvantitet som redan har kasserats för ett jobb.
1. **Resterande** – i den här kolumnen visas den kvantitet som återstår att färdigställa för ett jobb.

## <a name="active-jobs-tab"></a>Fliken aktiva jobb

Flikarna **Aktiva jobb** visar en lista över alla jobb som den inloggade arbetaren redan har startat. (Det här fliknamnet är anpassningsbart och kan vara ett annat för systemet.)

![Fliken Aktiva jobb.](media/pfei-active-jobs-tab.png "Fliken aktiva jobb")

Listan med aktiva jobb har följande kolumner:

- **Urvalskolumn** – kolumnen längst till vänster använder en bockmarkering för att visa jobb som har valts av arbetaren. Arbetare kan välja flera jobb i listan samtidigt. Om du vill markera alla jobb i listan markerar du kryssrutan i kolumnrubriken. När ett enstaka jobb väljs visas information om jobbet i den nedre delen av sidan.
- **Order** – i den här kolumnen visas produktionsordernumret för ett jobb.
- **Beskrivning** – i den här kolumnen visas en beskrivning av den åtgärd som ett jobb ingår i.
- **Begärd** – den här kolumnen visar den kvantitet som ett jobb har planerats att producera.
- **Startad** – i den här kolumnen visas den kvantitet som redan har startats för ett jobb.
- **Slutförd** – i den här kolumnen visas den kvantitet som redan har slutförts för ett jobb.
- **Kasserad** – i den här kolumnen visas den kvantitet som redan har kasserats för ett jobb.
- **Resterande** – i den här kolumnen visas den kvantitet som återstår att färdigställa för ett jobb.

## <a name="my-jobs-tab"></a>Fliken Mina jobb

Fliken **Mina jobb** gör det enkelt för medarbetarna att visa alla icke-startade och icke-definierade jobb som har tilldelats enkom för dem. Det är användbart i företag där jobb ibland eller alltid tilldelas till specifika medarbetare (personal) istället för andra typer av resurser (till exempel maskiner).

Planeringssystemet tilldelar automatiskt varje produktionsjobb till en viss resurspost, och varje resurspost har en typ (till exempel maskin eller person). När du konfigurerar en medarbetare som produktionsmedarbetare kan du koppla medarbetarkontot till en unik personalpost.

Fliken **Mina jobb** listar alla icke-startade och icke-definierade jobb som har tilldelats personalposten för den inloggade medarbetaren, om någon medarbetare är inloggad. Den listar aldrig jobb som har tilldelats en maskin eller annan typ av resurs, även om den inloggade medarbetaren har börjat arbeta med dessa jobb.

Om du vill visa alla jobb som har startats av den inloggade arbetaren - oavsett vilken typ av resurs som varje jobb har tilldelats - använder du fliken **Aktiva jobb**. Om du vill visa alla icke-avslutade jobb som matchar konfigurationen för det lokala jobbfiltret - oavsett medarbetar- eller startstatus - använder du fliken **Alla jobb**.

![Fliken Mina jobb.](media/pfei-my-jobs-tab.png "Fliken Mina jobb")

## <a name="my-machine-tab"></a>Min maskinflik

Fliken **Min maskin** låter arbetare välja en tillgång som är ansluten till en maskinresurs inom filteruppsättningen på fliken **Alla jobb**. Arbetaren kan sedan se tillståndet och hälsan för den valda tillgången genom att läsa värden för upp till fyra valda räknare och listor över senaste underhållsförfrågningar och registrerade driftstopp. Arbetaren kan också begära underhåll av den valda tillgången och registrera och redigera maskiners drifttid. (Det här fliknamnet är anpassningsbart och kan vara ett annat för systemet.)

![Fliken Min maskin.](media/pfei-my-machine-tab.png "Min maskinflik")

Fliken **Min maskin** har följande kolumner. Siffrorna motsvarar siffrorna i föregående illustration.

1. **Maskintillgång** - Välj maskintillgången som du vill spåra. Börja skriva ett namn för att välja från en lista med matchande tillgångar, eller välj förstoringsglasikonen för att välja från en lista över alla tillgångar som är associerade med de resurser som finns i jobblistan.

    > [!NOTE]
    > Användare av Supply Chain Management kan tilldela en resurs till varje tillgång efter behov med hjälp av sidan **Alla tillgångar** (på fliken **Anläggningstillgång** med listrutan **Resurs**). Mer information finns i [Skapa en tillgång](../asset-management/objects/create-an-object.md).

1. **Inställningar** - Välj kugghjulsikonen för att öppna en dialogruta där du kan välja vilka räknare som ska visas för den valda maskintillgången. Värden för dessa räknare visas längst upp på fliken **Tillgångshantering**. Menyn **Inställningar** (visas i följande skärmdump) kan du aktivera upp till fyra räknare. För varje räknare som du vill aktivera använder du sökfältet högst upp i panelen för att välja en räknare. Sökfältet listar alla räknare som är kopplade till tillgången som valts högst upp på sidan **Tillgångshantering**. Ställ in varje räknare till att övervaka antingen det **aggregerade** värdet eller det senaste **faktiska** värdet för räknaren. Om du till exempel konfigurerar en räknare som spårar hur många timmar maskinen har körts ska du konfigurera den på **Aggregerat**. Om du konfigurerar en räknare för att mäta den senaste uppdaterade temperaturen eller försiktighet, bör du konfigurera den på **Faktisk**. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.

    ![Inställningar för Min maskinflik.](media/pfei-my-machine-tab-settings.png "Inställningar för Min maskinflik")

1. **Begär underhåll** - Välj den här knappen om du vill öppna en dialogruta där du kan skapa en underhållsbegäran. Du kan ange en beskrivning och en notering. Denna begäran visas för en användare av Supply Chain Management som sedan kan konvertera underhållsbehovet till en underhållsorder.
1. **Registrera drifttid** - Välj den här knappen om du vill öppna en dialogruta där du kan registrera maskiners drifttid. Du kan välja en orsakskod och ange ett datum/tidsintervall för nedtiden. Registreringen av maskinens drifttid används för att beräkna maskintillgångens effektivitet.
1. **Visa eller redigera** - Välj den här knappen om du vill öppna en dialogruta där du kan redigera eller visa befintliga nedtidsposter.

## <a name="starting-and-completing-production-jobs"></a>Starta och slutföra produktionsjobb

Arbetare startar ett produktionsjobb genom att välja ett jobb på fliken **Alla jobb** och sedan välja **Starta jobb** för att öppna dialogrutan **Starta jobb**.

![Dialogrutan Starta jobb.](media/pfei-start-job-dialog.png "Dialogrutan Startjobb")

Arbetare använder dialogrutan **Startjobb** för att bekräfta produktionskvantiteten och sedan starta jobbet. Arbetare kan justera kvantiteten genom att markera fältet **Kvantitet** och sedan använda det numeriska tangentbordet som visas. Arbetstagarna väljer sedan **Start** för att börja arbeta med jobbet. Dialogrutan **Starta jobb** stängs och jobbet läggs till på fliken **Aktiva jobb**.

Arbetare kan starta ett jobb som har status. När en arbetare startar ett jobb med statusen *Inte startad* visar **Kvantitet** i dialogrutan **Starta jobb** inledningsvis hela kvantiteten. När en arbetare startar ett jobb med statusen *Startad* eller *Stoppad* visar fältet **Kvantitet** inledningsvis kvarstående kvantitet.

## <a name="reporting-good-quantities"></a>Rapportera godkända kvantiteter

När en arbetare slutför eller delvis slutför ett jobb kan de rapportera bra kvantiteter som producerats genom att välja ett jobb på fliken **Aktiva jobb** och flik **Rapportera progress**. Sedan i dialogrutan **Rapportera framsteg** anger arbetaren den goda kvantiteten med hjälp av det numeriska tangentbordet. Kvantiteten är tom som standard. När en kvantitet har angivits kan han eller hon uppdatera status för jobbet till *pågår*, *stoppad* eller *slutfört*.

![Dialogrutan Rapportera framsteg.](media/pfei-report-progress-dialog.png "Dialogrutan rapportera framsteg")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Rapportering av bra kvantiteter på batchorder som har samprodukter och biprodukter

Arbetare kan använda gränssnittet för exekvering av produktionsgolvet för att rapportera framsteg på batchorder. Denna rapportering inkluderar rapportering om biprodukter och biprodukter.

Vissa tillverkare, särskilt i processindustrier, använder batchorder för att hantera sina produktionsprocesser. Batchorder skapas från recept och dessa recept kan definieras så att de har samprodukter och biprodukter som utleverans. När återrapportering om dessa batchorder rapporteras måste utleveransbeloppet registreras för receptartikeln, och även på samprodukterna och biprodukterna.

När en arbetare slutför eller delvis slutför ett jobb på en batchorder kan han eller hon rapportera kvantiteter av bra kvalitet eller kassation för varje produkt som har definierats som utleverans för ordern. Produkter som definieras som utleverans för en batchorder kan vara av typen *Formel*, *Samprodukt* eller *Biprodukter*.

Om du vill rapportera bra kvantiteter för produkterna väljer arbetaren ett jobb på fliken **Aktiva jobb** och väljer sedan **Rapportera förlopp**.

Sedan kan arbetaren i dialogrutan **Rapportera förlopp** välja bland de produkter som definieras som utdata för batchordern som ska rapporters. Arbetaren kan välja en eller flera produkter i listan och sedan välja **Rapportprocess**. För varje produkt är kvantiteten tom som standard och arbetaren kan använda det numeriska tangentbordet för att ange kvantiteten. Arbetaren kan använda knapparna **Föregående** och **Nästa** för att förflytta sig mellan de valda produkterna. Efter att kvantiteten har angetts för varje produkt kan han eller hon uppdatera status för jobbet till *pågår*, *stoppad* eller *slutfört*.

![Rapportera samprodukter och biprodukter.](media/report-co-by-products.png "Rapportera samprodukter och biprodukter")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Rapportering av batchorder för planering av artiklar

När en arbetare slutför ett jobb i en batchorder för en planeringsartikel rapporterar de bara kvantiteter för samprodukter och biprodukter, eftersom planering av artiklar inte innehåller en artikel av typen *Formel*.

### <a name="reporting-co-product-variation"></a>Rapportering av variation för samprodukt

Om en batchorder skapas från en receptversion där alternativet **variation av samprodukter** har ställts in som *Ja*, kan arbetaren rapportera om samprodukter som inte ingår i definitionen för batchorder. Den här funktionen används i scenarier där oväntade produktutdata kan inträffa i produktionsprocessen.

I det här fallet kan arbetaren ange samprodukten och kvantiteten som ska rapporters genom att välja **variationer av samprodukter** i dialogrutan för rapportförloppet. Arbetaren kan sedan välja bland alla frisläppta produkter som definieras som samprodukter.

### <a name="reporting-catch-weight-items"></a>Rapportera artiklar med nominell vikt

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Medarbetare kan använda gränssnittet för exekvering på produktionsgolvet för att rapportera framsteg rörande batchorder om skapats för artiklar med nominell vikt. Batchorder skapas från formler, vilkar kan definieras så att de har artiklar med nominell vikt som formelartiklar, samprodukter och biprodukter. En formel kan också definieras till att ha formelrader för ingredienser som är definierade för nominell vikt. Artiklar med nominell vikt använder två måttenheter för att spåra lager: nominell viktkvantitet och lagerkvantitet. Inom till exempel livsmedelsindustrin kan förpackat kött definieras som en nominell viktartikel, där den nominella viktkvantiteten används för att spåra antalet kartonger och lagerkvantiteten används för att spåra kartongerna.

## <a name="reporting-scrap"></a>Rapportera kassation

När en arbetare slutför eller delvis slutför ett jobb kan de rapportera kassation genom att välja ett jobb på **Aktiva jobb** och flik **Rapportera kassation**. Sedan i dialogrutan **Rapportera kassation** anger arbetaren kassationskvantiteten med hjälp av det numeriska tangentbordet. Arbetaren väljer också en orsak (*ingen*, *maskin*, *operatör* eller *material*).

![Dialogrutan rapportera kassation.](media/pfei-report-scrap-dialog.png "Dialogrutan rapportera kassation")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Justera materialförbrukning och gör materialreservationer

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Arbetare kan justera materialförbrukning för varje produktionsjobb. Denna funktion används i scenarier där den faktiska kvantiteten av material som förbrukades av ett produktionsjobb var mer eller mindre än den planerade kvantiteten. Därför måste den justeras för att hålla lagernivåerna aktuella.

Arbetare kan även göra reservationer på parti- och serienummer för material. Den här funktionen används i scenarier där en arbetare manuellt måste ange vilka materialbatch- eller serienummer som förbrukats för att uppfylla kraven på materialspårning.

Arbetare kan ange kvantiteten som ska justeras genom att välja **Justera material**. Denna knapp är tillgänglig på följande platser:

- I Dialogrutan **rapportera kassation**
- I dialogrutan **Rapportera framsteg**
- I verktygsfältet till höger

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Justera materialförbrukning från dialogrutan Rapportera kassation och rapportförlopp

När en arbetare har anger den kvantitet som ska rapporters i dialogrutan **Rapportera förlopp** eller **Rapport kassation** blir knappen **Justera material** tillgänglig. När användaren väljer den här knappen visas dialogrutan **Justera material**. Den här dialogrutan visar de artiklar som har planerats att förbrukas när den vara eller kasserade kvantiteten rapporteras för jobbet.

Listan i dialogrutan visar följande information:

- **Produktnummer** – produktmall och produktvariant.
- **Produktnamn** – Produktens namn.
- **Förslag** – Den uppskattade materialkvantiteten som kommer att förbrukas när förlopp eller kassation rapporteras för den angivna kvantiteten för jobbet.
- **Förbrukning** – Den faktiska materialkvantiteten som kommer att förbrukas när förlopp eller kassation rapporteras för den angivna kvantiteten för jobbet.
- **Reserverad** – Den materialkvantitet som fysiskt reserverats i lagret.
- **Enhet** – Strukturlisteenheten.

Höger sida av dialogrutan visar följande information:

- **Produktnummer** – produktmall och produktvariant.
- **Uppskattad** – Uppskattad kvantitet som ska förbrukas.
- **Startad** – Den kvantitet som har startats för produktionsjobbet.
- **Resterande kvantitet** – Av den uppskattade kvantiteten, den kvantitet som återstår att förbruka.
- **Frisläppt kvantitet** – Den kvantitet som har förbrukats.

Följande åtgärder kan utföras:

- Arbetaren kan ange kvantiteten som ska justeras för ett material genom att välja **Justera förbrukning**. När kvantiteten har bekräftats uppdateras kvantiteten i kolumnen **Förbrukning** med den justerade kvantiteten.
- När arbetaren väljer **Justera material** skapas en journal för produktionsplockningslista. Den här journalen innehåller samma artiklar och kvantiteter som listan **Justera material**.
- När arbetaren justerar en kvantitet i dialogrutan **Justera material**, uppdateras fältet **Förslag** på motsvarande journalrad med samma kvantitet. Om arbetaren väljer **Avbryt** i dialogrutan **Justera material**, tas plocklistan bort.
- Om arbetaren väljer **OK** tas inte plocklistan bort. Det bokförs när jobbet rapporteras i dialogrutan **Rapportera kassation** eller **Rapport förlopp**.
- Om arbetaren väljer **Avbryt** i dialogrutan **Rapportera framsteg** eller **Rapportera kassation** tas plocklistan bort.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Justera material från det primära eller sekundära verktygsfältet

Knappen **Justera material** kan konfigureras så att den visas i det primära eller sekundära verktygsfältet. (Mer information finns i [Designa körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md).) En arbetare kan välja **Justera material** för ett produktionsjobb som pågår. I det här fallet visas dialogrutan **Justera material**, där arbetaren kan göra de önskade justeringarna. När dialogrutan är öppen skapas en produktionsplockningslista som innehåller rader för de justerade kvantiteterna för tillverkningsordern. Om arbetaren väljer **Bokför nu**, bekräftas justeringen och plocklistan bokförs. Om arbetaren väljer **Avbryt**, plocklistan raderas och ingen justering görs.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Justera materialförbrukning för nominella viktartiklar

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Medarbetarna kan justera materialförbrukningen för nominella viktartiklar. Denna funktion används i scenarier där den faktiska kvantiteten av material med nominell vikt som förbrukats av ett produktionsjobb var mer eller mindre än den planerade kvantiteten. Därför måste den justeras för att hålla lagernivåerna aktuella. När en medarbetare justerar förbrukningen av en artikel med nominell vikt kan han eller hon justera både kvantiteten med nominell vikt och lagerkvantiteten. Om till exempel ett produktionsjobb planeras att förbruka fem lådor med en uppskattad vikt på 2 kilo per låda kan medarbetaren justera båda antalet lådor som ska förbrukas och lådornas vikt. Systemet validerar att den angivna vikten för lådorna ligger inom den definierade minimi- och maximitröskel som definierats på den frisläppta produkten.

### <a name="reserve-materials"></a>Reservera material

I dialogrutan **Justera material** kan en arbetare göra och justera materialreservationer genom att välja **Reservera material**. I dialogrutan **Reservera material** som visas det fysiskt tillgängliga lagret för artikeln för varje lagrings- och spårningsdimension.

Om material har aktiverats för de avancerade lagerställeprocesserna visar listan bara det fysiskt tillgängliga lagret för platsen för produktionsinleverans för materialet. Platsen för produktionsindata definieras på resursen där produktionsjobbet planeras. Om artikelnumret är batch- eller serienummerkontrollerat visas den fullständiga listan över fysiskt tillgängliga batch- och serienummer. Om du vill ange en kvantitet som ska reserveras kan arbetaren välja **Reservera material**. Om du vill ta bort en befintlig reservation kan arbetaren välja **Ta bort reservation**.

Mer information om hur du konfigurerar platsen för produktionsindata finns i följande inlägg: [Ställa in platsen för produktionsindata](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> Reservationer som en arbetare gör dialogrutan **Reservera material** finns kvar när arbetaren väljer **Avbryt** i dialogrutan **Rapportera framsteg** eller **Rapport kassation**.
>
> Det går inte att justera reservationer för artiklar med nominell vikt.

## <a name="completing-a-job-and-starting-a-new-job"></a>Slutföra ett jobb och starta ett nytt jobb

Vanligtvis slutför arbetarna ett jobb genom att välja ett eller flera aktuella jobb på fliken **Aktiva jobb** och sedan välja **Rapportera framsteg**. Därefter anger de kvantiteten som producerades (den godkända kvantiteten) och konfigurerar statusen för att *slutföra*. Om fler än ett jobb har valts använder en arbetare sedan knapparna **Föregående** och **Nästa** för att förflytta sig mellan dem. Om du vill starta ett nytt jobb väljer arbetaren det på fliken **Alla jobb** och väljer sedan **Starta jobb**.

En arbetare kan också starta ett nytt jobb medan deras tidigare jobb fortfarande är öppet. Återigen väljer arbetaren det nya jobbet på fliken **Alla jobb** och väljer sedan **Starta jobb**. I det här fallet informerar dialogrutan **Starta jobb** arbetaren att de för närvarande arbetar med ett jobb och att de därför måste antingen sluta eller slutföra det jobbet innan de börjar det nya jobbet.

## <a name="working-on-multiple-jobs-in-parallel"></a>Arbeta med flera jobb parallellt

En arbetare kan arbeta med flera jobb samtidigt (det vill säga parallellt). I det här fallet kallas samlingen av jobb som arbetaren arbetar på en *jobbunt*. Arbetaren kan lägga till nya jobb i bunten eller fylla i ett eller flera jobb i bunten. I följande två scenarier visas hur en arbetare kan arbeta med jobb parallellt.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenario 1: en arbetare som inte har aktiva jobb vill starta två jobb och arbeta med dem parallellt

Arbetaren väljer de två jobben på fliken **Alla jobb** och väljer sedan **Starta jobb**. Dialogrutan **Starta jobb** visar båda valda jobb och arbetaren kan justera kvantiteten så att den startar på varje jobb. Arbetaren bekräftar sedan dialogrutan och kan starta båda jobben.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenario 2: en arbetare som har två aktiva jobb som pågår vill starta ett tredje jobb parallellt med de andra två

Arbetaren väljer det tredje jobbet på fliken **Alla jobb** och väljer sedan **Bunt**. I dialogrutan **Bunt** kan arbetaren justera kvantiteten så att den startar. Arbetaren bekräftar sedan dialogrutan genom att välja **bunt**.

## <a name="working-on-indirect-activities"></a>Arbeta på indirekta aktiviteter

Indirekta aktiviteter är aktiviteter som inte är direkt relaterade till en produktionsorder. Indirekta aktiviteter kan anges på ett flexibelt sätt, enligt beskrivningen i [konfigurera indirekta aktiviteter för tid och närvaro](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Till exempel Shannon, en butiksarbetare i Contoso, vill delta i ett företagsmöte och möten betraktas som en indirekt aktivitet. Ett av följande två scenarier gäller:

- **Shannon arbetar med ett eller flera aktiva jobb.** Shannon väljer **aktivitet**, identifierar aktiviteten (mötet) och bekräftar valet. Ett meddelande som visas med information om att hon har jobb som pågår. Med hjälp av meddelandet kan Shannon välja att slutföra eller stoppa jobb som hon arbetar med innan hon går till mötet.
- **Shannon har inga aktiva jobb.** Shannon väljer **aktivitet**, identifierar aktiviteten (mötet) och bekräftar valet. Hon är nu registrerad som på mötet.

När Shannon bekräftar sina val i båda scenarierna, går hon antingen till inloggningssidan eller en sida som väntar på att hon ska bekräfta att hon har returnerat från sin indirekta aktivitet. Vilken sida som visas beror på konfigurationen av körningsgränssnittet för produktionsgolvet. (Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Registrering av raster

Arbetare kan registrera raster. Raster kan definieras flexibelt, vilket beskrivs i [lön baserat på registreringar](pay-based-on-registrations.md).

En arbetare registrerar en rast genom att välja **rast** och sedan välja det kort som representerar rasttypen (t.ex. lunch). När personen har bekräftat urvalet visar enheten antingen inloggningssidan eller en sida som väntar på att personen ska bekräfta att de har returnerats från rasten. Vilken sida som visas beror på konfigurationen av körningsgränssnittet för produktionsgolvet. (Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](production-floor-execution-configure.md).)

## <a name="view-the-my-day-dialog"></a>Visa dialogrutan "Min dag"

I dialogrutan **Mitt dag** får medarbetare en översikt över sina registreringar och saldon. Dialogrutan är uppdelad i följande tre avsnitt:

- Huvudavsnittet listar de registreringar som den aktuella arbetaren har gjort på ett valt datum. Här visas registreringar för den aktuella dagen och ett datumplockningsfält som gör att arbetaren kan visa andra dagar.
- I avsnittet för **Senast beräknade dagliga saldo** visas arbetarens aktuella saldon för betald tid, betald övertid, frånvaro och betald frånvaro. Värdena baseras på de registreringar som har beräknats under godkännandeprocessen.
- Avsnittet **Saldon** ger en översikt över saldona inom en angiven period för valda kategorier av registreringar (till exempel semester, standardtid och övertid). De här saldona baseras på de statistiska saldona i **tids- och närvaromodulen**. Mer information om hur du konfigurerar en konfiguration finns i [Visa semestersaldon i körningsgränssnittet för produktionsgolvet](production-floor-execution-payroll-stats.md).

Administratörer kan lägga till den här funktionen i gränssnittet genom att trycka på knappen **Min dag** på ett verktygsfält för varje relevant flik som beskrivs i [Designa gränssnittet för utförande av produktionsgolvet](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Arbeta i team

När flera arbetare tilldelas samma produktionsjobb kan de ingå i ett team. Teamet kan utnämna en arbetare till ledare. De återstående arbetarna blir automatiskt medhjälpare till ledare. För det resulterande teamet måste bara ledaren registrera jobbstatus. Tidsposter gäller för alla gruppmedlemmar.

### <a name="prerequisites"></a>Förutsättningar

För att använda team måste en administratör aktivera åtgärden **Assistent** för det primära verktygsfältet på fliken **Alla jobb** i körningsgränssnittet för produktionsgolvet. Se instruktioner i [Designa körningsgränssnittet för produktionsgolv](production-floor-execution-tabs.md).

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Skapa ett nytt team som har en ledare och en assistent

En arbetare kan registrera sig som assistent genom att välja **Assistent** på fliken **Alla jobb**. I dialogrutan **Välj en medarbetare som ska hjälpa till** kan arbetaren sedan välja en pilot i en lista med medarbetare som är ansvarig för att arbeta med ett jobb. När arbetaren har bekräftat sitt val blir de en medhjälpare till den valda arbetaren, som blir ledare för det nya teamet.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Tilldela en ny ledare till ett befintligt team

När ett team vill välja en ny ledare måste den aktuella piloten välja en annan arbetare i teamet som ny ledare. Om du vill ange en ny pilot väljer den aktuella piloten **Assistent** på fliken **Alla jobb**. I dialogrutan **Ändra pilot** som visas kan sedan piloten välja en ny pilot i en lista över arbetare som redan finns i teamet. När den aktuella ledaren har bekräftat sitt val tas de bort helt från teamet. De kan dock ansluta tillbaka till teamet efter behov.

### <a name="assistant-clocks-out"></a>Medhjälpare stämplar ut

När en arbetare som arbetar som assistent stämplar ut lämnar de teamet. Om alternativen **Permanenta team** och **Starta om vid instämpling** ställs in på *Ja*, kommer en arbetare som stämplar ut automatiskt att ansluta till teamet nästa gång de stämplar in. De här alternativen finns på fliken **Allmänt** på sidan **Tids - och närvaroparametrar**.

## <a name="opening-instructions"></a>Öppnar instruktioner

Arbetare kan öppna ett dokument som är kopplat till ett jobb genom att välja **instruktioner**. Knappen **instruktioner** är endast tillgänglig om ett dokument är kopplat till jobbet i huvuddata. Till exempel kan ett dokument som är kopplat till en produkt på sidan **frisläppta produkter** i Supply Chain Management kommer att vara tillgängligt för arbetare som ska öppnas i gränssnittet för arbetsstyrningskörning.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Öppnade guider för mixad verklighet för HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) kan hjälpa arbetarna att erbjuda praktisk utbildning med hjälp av mixad verklighet. Du kan definiera standardiserade processer med steg-för-steg-instruktioner som vägleder medarbetare till de verktyg och delar de behöver och visa hur de kan använda verktygen i verkliga arbetssituationer. Här finns en översikt av processen.

1. Varje gång en arbetare öppnar en jobblista i gränssnittet för arbetsstyrningskörningen, hittar gränssnittet alla relevanta guider för de jobb som visas.
1. Arbetaren väljer själv **guider** som visar listan över guider.
1. Arbetaren väljer en relevant guide i listan.
1. I gränssnittet för arbetsstyrningskörning visas en QR-kod för den valda guiden.
1. Arbetaren ger en HoloLens och en överblick över QR-koden för att starta guiden.
1. Arbetaren går igenom guiden för att lära sig uppgiften.

Mer information om hur du skapar, tilldelar och använder guider för HoloLens finns i [Ange guider för mixad verklighet för arbetare i produktion](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
