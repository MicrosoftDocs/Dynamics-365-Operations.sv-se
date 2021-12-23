---
title: Behovsprognoser inställning
description: Detta avsnitt beskriver de uppgifter som du måste utföra för att förbereda behovsprognoser.
author: ChristianRytt
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3abe82bb888b7501b00af44b48bfb40fbe8e2ee3
ms.sourcegitcommit: 6ef4906621fbb4e3afaf2b0d6697536288365bb1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/30/2021
ms.locfileid: "7868647"
---
# <a name="demand-forecasting-setup"></a>Behovsprognoser inställning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in efterfrågeprognosticering.  

## <a name="item-allocation-keys"></a>Artikelallokeringsnycklar

Artikelallokeringsnycklar skapar grupper av artiklar. En efterfrågan prognosen beräknas för ett objekt och dess dimensioner endast om objektet är en del av en fördelningsnyckel. Denna regel tillämpas för att gruppera ett stort antal artiklar i syfte att kunna efterfrågeprognoser kan skapas snabbare. Prognoser är skapade baserad på historiska data bara.

Ett objekt och dess dimensioner måste vara en del av endast en punkt fördelningsnyckel om posten fördelningsnyckel används under prognos.

Följ de här stegen om du vill skapa artikelallokeringsnycklar och lägga till en lagerhållningsenhet (SKU).

1. Gå till **Huvudplanering \> Inställningar \> Efterfrågeprognosticering \> Artikelallokeringsnycklar**.
1. Välj antingen en Artikelallokeringsnycklar i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny. Ange följande fältvärden i den nya eller valda nyckeln:

    - **Artikelallokeringsnyckel** – Ange ett unikt namn för nyckeln.
    - **Namn** – Ange ett beskrivande namn för nyckeln.

1. Följ något av dessa steg om du vill lägga till artiklar på den valda artikelallokeringsnyckeln eller ta bort artiklar:

    - På snabbfliken **Artikelallokering** använd knapparna **Ny** och **Ta bort** verktygsfältet för att lägga till eller ta bort artiklar efter behov. För varje rad markerar du artikelnumret och tilldelar sedan dimensionsvärden i de andra kolumnerna efter behov. Välj **Visa dimensioner** i verktygsfältet om du vill ändra uppsättningen med dimensionskolumner som visas i rutnätet. (Värdet i kolumnen **Procent** ignoreras när efterfrågeprognoser genereras.)
    - Om du vill lägga till ett stort antal artiklar i nyckeln väljer du **Tilldela artiklar** i åtgärdsfönstret för att öppna en sida där du kan hitta och tilldela flera artiklar till den valda nyckeln.

> [!IMPORTANT]
> Se till att endast relevanta artiklar inkluderas i varje artikelallokeringsnyckel. Onödiga objekt kan orsaka ökade kostnader när du använder Microsoft Azure Machine Learning.

## <a name="intercompany-planning-groups"></a>Koncerninterna planeringsgrupper

Behovsprognoser genererar gränsöverskridande företag prognoser. I Dynamics 365 Supply Chain Management grupperas företag som är planerade tillsammans i samma koncerninterna planeringsgrupp. Om du vill ange, per företag, vilka artikelallokeringsnycklar som ska beaktas vid efterfrågeprognoser, kopplar du en artikelallokeringsnyckel till medlemmen i den koncerninterna planeringsgruppen.

> [!IMPORTANT]
> Planeringsoptimering har för närvarande inte stöd för koncerninterna planeringsgrupper. Om du vill göra koncernintern planering med planeringsoptimering ställer du in batchjobb för huvudplaneringar som omfattar huvudplaner för alla relevanta företag.

Så här ställs koncerninterna planeringsgrupper in.

1. Gå till **Huvudplanering \> Inställningar \> Koncerninterna planeringsgrupper**.
1. Välj antingen en planeringsgrupp i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny. På rubriken för den nya eller valda gruppen, ställ in följande fält:

    - **Namn** – Ange ett unikt namn för planeringsgrupp.
    - **Beskrivning** – Ange en kort beskrivning av planeringsgrupp.

1. På snabbflikarna **Koncerninterna planeringsgruppmedlemmar** använder du knapparna i verktygsfältet för att lägga till en rad för varje företag (juridisk person) som ska ingå i gruppen. För varje rad anger du följande fält:

    - **Juridisk person** – Välj namnet på ett företag (juridisk person) som är medlem i den valda gruppen.
    - **Planeringsordning** – Tilldela den ordning som företaget ska bearbetas i förhållande till andra företag. Låga värden bearbetas först. Den här ordern kan vara viktig när efterfrågan på ett företag påverkar andra företag. I dessa fall bör det företag som tillhandahåller efterfrågan bearbetas sist.
    - **Huvudplan** – Välj huvudplan för som utlösare för det aktuella företag.
    - **Kopiera automatiskt till statisk plan** – Markera den här kryssrutan om du vill kopiera resultatet av planen till den statiska planen.
    - **Kopiera automatiskt till dynamisk plan** – Markera den här kryssrutan om du vill kopiera resultatet av planen till den dynamiska planen.

1. Om inget objekt fördelningsnycklar tilldelas företagsinterna planering gruppmedlemmar, en efterfrågan prognosen beräknas för alla artiklar som är tilldelade till alla objekt fördelningsnycklar från alla företag. Ytterligare filtreringsalternativ för företag och varufördelningsnycklar finns tillgängliga i dialogrutan **Generera statistisk baslinjeprognos** (**Huvudplanering \> Prognos \> Efterfrågeprognoser \> Generera statistisk baslinjeprognos**). För att tilldela artikelfördelningsnycklar till ett företag i den valda koncerninterna planeringsgruppen, välj företaget och sedan på **Koncerninterna planeringsgruppmedlemmar** välj **Artikelallokeringsnycklar** i verktygsfältet.

> [!IMPORTANT]
> Var noga med att endast inkludera relevanta artikeltilldelningsnycklar i varje koncernintern planeringsgrupp. Onödiga objekt kan orsaka ökade kostnader när du använder Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Ställ in parametrar för efterfrågeprognosticering

På sidan **Parametrar för efterfrågeprognosticering** kan du ställa in flera alternativ som styr hur efterfrågeprognosticering ska fungera i systemet.

### <a name="open-the-demand-forecasting-parameters-page"></a>Öppna sidan parametrar för efterfrågeprognosticering

För att konfigurera parametrar för efterfrågeprognosticering **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Parametrar för efterfrågeprognosticering**. Eftersom efterfrågan prognostisera körs cross-firma, installationen är global. Det gäller med andra ord alla juridiska personer (företag).

### <a name="general-settings"></a>Allmänna inställningar

Använd fliken **Allmänt** av sidan **Parametrar för efterfrågeprognosticering** om du vill ange allmänna inställningar för efterfrågeprognoser.

#### <a name="demand-forecast-unit"></a>Efterfrågeprognosenhet

Behovsprognoser genereras prognosen i mängder. Därför är den enhet som kvantiteten bör uttryckas i måste specificeras i **efterfrågan** . Det här fältet definierar enheten som ska användas för alla efterfrågeprognoser, oavsett de vanliga lagerenheterna för varje produkt. Genom att använda en konsekvent prognosenhet, för att säkerställa att aggregering och procentuell fördelning blir förståelig. För mer information om summering och procentuell fördelning, se [göra manuella justeringar av den ursprungliga prognosen](manual-adjustments-baseline-forecast.md).

För varje enhet som används för artiklar som ingår i behovsprognoser, se till att det finns en konverteringsregel för enheten och den allmänna prognoser enhet, som du väljer här. När du genererar en prognos loggas listan över objekt som inte har en måttenhetskonvertering. Därför kan du enkelt korrigera inställningarna. När du genererar en prognos loggas listan över objekt som inte har en måttenhetskonvertering [Hantera måttenheter](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Transaktionstyper

Använd fälten på snabbflikarna **Transaktionstyper** för att välja de transaktionstyper som används när den statistiska baslinjeprognosen genereras.

Behovsprognoser kan användas för att förutse både beroende och oberoende behov. Om till exempel endast försäljningen för alternativ **försäljningsorder** är *Ja* markerad och om alla punkter som anses för behovsprognoser är artiklar som säljs, beräknar systemet oberoende efterfrågan. Men kritiska delkomponenterna kan läggas till punkt fördelningsnycklar och ingår i behovsprognoser. I det här fallet, om alternativet **Produktionslinje** anges *Ja* är markerad, beräknas en beroendeprognos.

Du kan åsidosätta transaktionstyper för en eller flera specifika artikelallokeringsnycklar genom att använda fliken **Artikelallokeringsnycklar**. På den fliken visas liknande fält.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Välj hur baslinjeprognosen ska skapas

I fältet **Strategi för prognosgenerering** kan du välja vilken metod som ska användas för att skapa en baslinjeprognos. Tre metoder är möjliga:

- *Kopiera över historisk efterfrågan* – Skapa prognoser genom att bara kopiera historiska data.
- *Azure Machine Learning Service* – Använd en prognosmodell som använder Azure Machine Learning Service. Azure Machine Learning Service är den aktuella maskininlärningslösningen för Azure. Därför rekommenderar vi att du använder den om du vill använda en prognosmodell.
- *Azure Machine Learning* – Använd en prognosmodell som använder Azure Machine Learning Studio (klassisk). Azure Machine Learning Studio (klassisk) har avaktiverats och kommer snart att tas bort från Azure. Därför rekommenderar vi att du väljer *Azure Machine Learning Service* om du ställer in efterfrågeprognoser för första gången. Om du för närvarande använder Azure Machine Learning Studio (klassisk) du bör planera att växla till Azure Machine Learning Service så snart som möjligt.

Du kan åsidosätta prognosgenereringsmetoden för en eller flera specifika artikelallokeringsnycklar genom att använda fliken **Artikelallokeringsnycklar**. På den fliken visas liknande fält.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Åsidosätta standardparametrar för prognosalgoritmer globalt

Standardparametrar och värden för prognosalgoritm tilldelas sidan **Parametrar för efterfrågeprognoser** (**Huvudplanering \> Konfiguration \> Efterfrågeprognoser \> Parametrar för efterfrågeprognoser**). Du kan dock åsidosätta dem globalt genom att använda snabbflikarna **Parametrar för prognosalgoritm** på sidan **General** för sidan **Parametrar för efterfrågeprognosticering**. (Du kan också åsidosätta dem för specifika allokeringsnycklar genom att använda fliken **Artikelallokeringsnycklar** på sidan **Parametrar för efterfrågeprognosticering**.)

Använd knapparna **Lägg till** och **Ta bort** på verktygsfältet för att upprätta den nödvändiga samlingen av parameter åsidosättning. Välj ett värde i fältet **Namn** för varje parameter i listan och ange ett lämpligt värde i fältet **Värde**. Alla parametrar som inte anges här får sina värden från inställningarna på sidan **Parametrar för efterfrågeprognoser**. Mer information om hur du använder standardparametrarna och väljer värden för dem finns i avsnittet [Standardparametrar och värden för modeller för efterfrågeprognosticering](#model-parameters).

### <a name="set-forecast-dimensions"></a>Ange prognostiseringsdimension

En prognos dimensionen anger nivån av detaljen att prognosen är definierad för. Företags-, webbplats- och artikelallokeringsnyckel är prognosdimensioner som krävs. Du kan också generera prognoser på lagerställe, lagerstatus, kundgrupp, kundkonto, land/region, stat och artikel samt alla objektdimensionsnivåer. Använd fliken **Prognosdimensioner** på sidan **Parametrar för efterfrågeprognosticering** kan du även välja den uppsättning prognosdimensioner som ska användas när efterfrågeprognosen genereras.

Du kan när som helst lägga prognosen dimensioner till listan av dimensioner som används för behovsprognoser. Du kan också ta bort prognos mått från listan. Men manuella justeringar går förlorade om du lägger till eller tar bort en prognos dimension.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Ställ in åsidosättningar för specifika artikelallokeringsnycklar

Inte alla objekt fungerar på samma sätt från en behovsprognoser perspektiv. Därför kan du upprätta allokeringsnyckelspecifika åsidosättningar för de flesta inställningar som har definierats på fliken **Allmänt**. Undantaget är enheten för efterfrågeprognos. Ställ in åsidosättningar för en specifik artikelallokeringsnyckel genom att följa dessa steg.

1. På sidan **Parametrar för efterfrågeprognosticering** på fliken **Artikelallokeringsnycklar** använder du verktygsfältsknapparna för att lägga till artikelallokeringsnycklar till rutnätet till vänster, eller ta bort dem efter behov. Välj sedan den allokeringsnyckel som du vill ställa in åsidosättningar för.
1. På snabbflikarna **Transaktionstyper** kan du aktivera de transaktionstyper som du vill använda för att generera statistisk baslinjeprognos för produkter som tillhör den valda allokeringsnyckeln. Inställningarna fungerar precis som de fungerar på fliken **Allmänt**, men de gäller endast för den valda artikelallokeringsnyckeln. Alla inställningar här (både *Ja*-värden och *Nej*-värden) åsidosätter alla **Transaktionstyper** på fliken **Allmänt**.
1. På snabbfliken **Parametrar för prognosalgoritm** väljer du parametern prognosgenereringsstrategi och prognosalgoritm för produkter som tillhör den valda allokeringsnyckeln. Inställningarna fungerar precis som de fungerar på fliken **Allmänt**, men de gäller endast för den valda artikelallokeringsnyckeln. Använd knapparna **Lägg till** och **Ta bort** på verktygsfältet för att definiera den nödvändiga samlingen av parameter åsidosättning. Välj ett värde i fältet **Namn** för varje parameter i listan och ange ett lämpligt värde i fältet **Värde**. Mer information om hur du använder standardparametrarna och väljer värden för dem finns i avsnittet [Standardparametrar och värden för modeller för efterfrågeprognosticering](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Ställa in anslutningen till Azure Machine Learning Service

Använd fliken **Azure Machine Learning Service** när du ställer in anslutningen till Azure Machine Learning Service. Den här lösningen är ett av alternativen för att skapa baslinjeprognosen. De här inställningarna på den här fliken har bara effekt när fältet **Strategi för prognosgenerering** är inställt på *Azure Machine Learning Service*.

Mer information om hur du ställer in Azure Machine Learning Service och sedan använder inställningarna här för att ansluta till den finns i avsnittet [Ställa in avsnittet Azure Machine Learning Service](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Ställa in anslutningen till Azure Machine Learning Studio (klassisk)

> [!IMPORTANT]
> Azure Machine Learning Studio (klassisk) har avskrivits. Därför kan du inte längre skapa nya arbetsytor för det i Azure. Den har ersatts av Azure Machine Learning Service, som innehåller liknande funktioner med mera. Om du inte redan använder Azure Machine Learning bör du börja använda Azure Machine Learning Service. Om du redan har en arbetsyta som har skapats för Azure Machine Learning Studio (klassiskt) så kan du fortsätta att använda den tills funktionen är helt borttagen från Azure. Vi rekommenderar dock att du uppdaterar till Azure Machine Learning Service så snart som möjligt. Även om programmet fortsätter att varna dig om att Azure Machine Learning Studio (klassisk) har inaktuellt, påverkas inte prognosresultatet. Mer information om hur du ställer in ny Azure Machine Learning Service och hur du konfigurerar det finns i avsnittet [Ställa in avsnittet Azure Machine Learning Service](#setup-amls).
>
> Du kan fritt växla mellan de nya och gamla maskininlärningslösningarna med Supply Chain Management under så länge din gamla arbetsyta Azure Machine Learning Studio (klassisk) arbetsyta förblir tillgänglig.

Om du redan har en tillgänglig arbetsyta för Azure Machine Learning Studio (klassisk) kan du använda den för att skapa prognoser genom att koppla den till Supply Chain Management. Du kan upprätta den här anslutningen genom att använda fliken **Azure Machine Learning** på sidan **Parametrar för efterfrågeprognoser**. (Inställningarna på den här fliken har endast effekt när fältet **Strategi för prognosgenerering** ställs in på *Azure Machine Learning*). Ange följande information för din Azure Machine Learning Studio (klassisk)-arbetsyta:

- Web Service API (application programming interface)
- Webbtjänstens slutpunktsadress
- Azure Storage kontonamn
- Azure Storage kontonyckel

> [!NOTE]
> Azure-lagringskontonamn och nyckeln behövs bara om du använder ett anpassat lagringskonto. Om du använder den lokala versionen måste du ha ett anpassat lagringskonto på Azure, detta så att Machine Learning kan få åtkomst till historiska data.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Standardparametrar och standardvärden för modeller för efterfrågeprognoser

När du använder Machine Learning för att generera dina prognosplaneringsmodeller kontrollerar du maskininlärningsalternativen genom att ställa in värden för *parametrar i prognosalgoritmen*. Värdena skickas från Supply Chain Management till Azure Machine Learning. På sidan **Parametrar för prognosalgoritmer** kan du kontrollera vilka typer av värden som ska anges och vilka värden som de ska ha.

För att ställa in de standardparametrar kan konfigureras för modeller för efterfrågeprognosticering går du till **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Parametrar för prognosalgoritm**. Det finns en standarduppsättning parametrar. Varje partner har följande fält:

- **Namn** – Namnet på parametern, som används av Azure. Vanligtvis ska du inte ändra det här namnet om du inte har anpassat den i Azure Machine Learning.
- **Beskrivning** – Ett vanligt namn för parametern. Det här namnet används för att identifiera parametern på andra ställen i systemet (till exempel på sidan **Parametrar för efterfrågeprognoser**).
- **Värde** – Standardvärdet parametern. Värdet du ska ange beror på vilken parameter du redigerar. 
- **Förklaring** – En kort beskrivning av parametern och hur den ska användas. Den här beskrivningen innehåller normalt tips om giltiga värden för fältet **Värde**.

Följande parametrar anges som standard. (Om du aldrig måste återgå till denna standardlista väljer du **Återställ** i åtgärdsfönstret.)

- **Konfidensnivå i procent** – Ett konfidensintervall består av ett antal värden som fungerar som goda prognoser för efterfrågan. En 95-procentig konfidensnivå procenttal indikerar att det finns en 5-procentig risk att framtida efterfrågan faller utanför konfidensintervallet.
- **Framtvinga säsongsvarianter** – Anger om modellen ska använda en viss typ av säsongsvarianter. Denna parameter gäller endast ARIMA och ETS. Alternativ: *AUTO (standard)*, *NONE*, *ADDITIVE*, *MULTIPLICATIVE*.
- **Prognosmodell** – Anger vilken prognosmodell som ska användas. Alternativ: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *ALL*. För att välja den modell som passar bäst, använd *ALL*.
- **Maximalt prognostiserat värde** – Anger det högsta värde som ska användas för prognoser. Format: + 1E[n] eller numerisk konstant.
- **Minimalt prognostiserat värde** – Anger det minsta värde som ska användas för prognoser. Format: -1E[n] eller numerisk konstant.
- **Värdeersättning saknas** – Anger hur luckor i historiska data ska fyllas i. Alternativ: *(numeriskt värde)*, *MEAN*, *PREVIOUS*, *INTERPOLATE LINEAR*, *INTERPOLATE POLYNOMIAL*.
- **Intervall för ersättning för saknat värde** – Anger om värdesubstitutionen endast gäller datumområdet för varje enskilt granularitetsattribut eller för hela datauppsättningen. Följande alternativ är tillgängliga för att fastställa det datumintervall som används i systemet vid ifyllning av luckor i historiska data:

    - *GLOBAL* – Systemet använder hela datumintervallet för alla granularitetsattribut.
    - *HISTORY_DATE_RANGE* – Systemet använder ett specifikt datumintervall som definieras i fälten **Från datum** och **Till datum** i fältgruppen **Historisk horisont** i dialogrutan **Generera statistisk baslinjeprognos**.
    - *GRANULARITY_ATTRIBUTE* – Systemet använder datumintervallet för det för tillfället bearbetade granularitetsattributet.

    > [!NOTE]
    > Ett granularitetsattribut är en kombination av prognosdimensioner som prognosen görs mot. Du kan definiera prognosdimensioner på sidan **Parametrar för efterfrågeprognosticering**.

- **Ledtråd för säsongsvarianter** – För säsongsvariationsdata anger du en ledtråd för prognosmodellen för att förbättra prognosnoggrannheten. Format: heltal som representerar antalet grupper som ett efterfrågansmönster upprepas. Ange till exempel *6* för data som upprepas var 6:e månad.
- **Testuppsättningsstorlek i procent** – Procentandel av historiska data som ska användas som testuppsättning för beräkning av prognosexakthet.

Du kan åsidosätta värdena för dessa parametrar genom att gå till **Huvudplanering \> Konfigurera \> Efterfrågeprognosticering \> Parametrar för efterfrågeprognosticering**. På sidan **Parametrar för efterfrågeprognosticering** kan du åsidosätta parametrarna på följande sätt:

- Använda fliken **Allmänt** för att åsidosätta parametrarna globalt.
- Använda fliken **Artikelallokeringsnycklar** för att åsidosätta parametrarna för specifika artikelallokeringsnycklar. Parametrar som åsidosätts för en specifik fördelningsnyckel som endast påverkar prognosen för de objekt som associeras med objektet fördelningsnyckel.

> [!NOTE]
> På sidan **Parametrar för prognosalgoritm** kan du använda knapparna i åtgärdsfönstret för att lägga till parametrar i listan, eller ta bort parametrar från listan. Vanligtvis ska du inte använda denna metod om du inte har anpassat den i Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Ställa in Azure Machine Learning Service

Supply Chain Management beräknar efterfrågeprognoser med hjälp av Azure Machine Learning Service, som du måste ställa in och köra på ditt eget Azure-abonnemang. Det här avsnittet beskriver hur du ställer in Azure Machine Learning Service i Azure och sedan ansluter den till din Supply Chain Management-miljö.

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until 10.0.23 GA -->

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Aktivera Azure Machine Learning Service i funktionshantering

Innan du kan använda Azure Machine Learning Service för efterfrågeprognoser måste du aktivera integreringen genom att aktivera en funktion i Supply Chain Management. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *Azure Machine Learning Service för efterfrågeprognosticering*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Ställa in Machine Learning i Azure

Om du vill att Azure ska kunna använda Machine Learning för att bearbeta dina prognoser måste du ställa in en Azure-Machine Learning-arbetsyta för det här syftet. Det finns två alternativ:

- För att ställa in arbetsytan genom att köra ett skript som tillhandahålls av Microsoft, följ instruktionerna i avsnittet [Alternativ 1: Kör ett skript för att automatiskt ställa in din Machine Learning-arbetsyta](#ml-workspace-script) och hoppa sedan till [Ställ in anslutningsparametrar för Azure Machine Learning Service i Supply Chain Management](#demand-forecast-parameters).
- För att ställa in arbetsytan manuellt, följ instruktionerna i avsnittet [Alternativ 2: Kör ett skript för att manuellt ställa in din Machine Learning-arbetsyta](#ml-workspace-manual) och hoppa sedan till [Ställ in anslutningsparametrar för Azure Machine Learning Service i Supply Chain Management](#demand-forecast-parameters). Det här alternativet tar längre tid men ger dig mer kontroll.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Alternativ 1: Köra ett skript om du automatiskt vill ställa in din Machine Learning-arbetsyta

I det här avsnittet beskrivs hur du ställer in Machine Learning-arbetsytan genom att använda ett automatiskt skript som tillhandahålls av Microsoft. Om du vill kan du manuellt ställa in alla resurser genom att följa instruktionerna i [alternativ 2: Ställa in arbetsytan manuellt.](#ml-workspace-manual) Båda alternativen behöver inte slutföras.

1. I GitHub, öppna [Mall för Dynamics 365 Supply Chain Management efterfrågeprognoser med Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) lagringsplats och hämta följande filer:

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Öppna ett PowerShell-fönster och kör det **quick_setup.ps1**-skript som du hämtade i det föregående steget. Följ instruktionerna på skärmen. Skriptet ställer in önskad arbetsyta, lagring, standarddatalager och resurser för beräkning. Du måste dock fortfarande skapa de pipelines som krävs genom att följa de återstående stegen i den här proceduren. (Pipelines är ett sätt att starta prognosskript från Supply Chain Management.)
1. I Azure Machine Learning Studio, överför filen **sampleInput.csv** som du hämtat i steg 1 till den programbehållare som heter *demplan-azureml*. (Skriptet quick_setup.ps1 skapade den här programbehållaren.) Den här filen krävs för att publicera försäljningsförloppet och generera en testprognos. Instruktioner finns i [Ladda upp ett blockblob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. I Azure Machine Learning Studio väljer **Anteckningsböcker** i navigeringsfönstret.
1. Hitta följande plats i strukturen **Filer**: **Users/\[current user\]/src**.
1. För över de återstående fyra filerna som du hämtat i steg 1 till den plats som du hittade i det föregående steget.
1. Välj den **api_trigger.py** fil som du just förde över och kör den. Det skapar ett försäljningsförlopp som kan initieras via API:t.
1. Arbetsytan är nu inställd. Gå vidare till avsnittet [Ställ in anslutningsparametrar Azure Machine Learning Service i Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Alternativ 2: Ställa in Machine Learning-arbetsytan manuellt

I det här avsnittet beskrivs hur du ställer in Machine Learning-arbetsytan manuellt. Du måste bara slutföra procedurerna i det här avsnittet om du har beslutat att inte köra det automatiska inställningsskriptet enligt beskrivningen i [alternativ 1: Kör ett skript för att ställa in din Machine Learning-arbetsyta](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Steg 1: Skapa en ny arbetsyta

Använd följande procedur om du vill skapa en ny Machine Learning-arbetsyta.

1. Logga in på Azure-portal.
1. Öppna tjänsten **Machine Learning**.
1. Välj **Skapa** i verktygsfältet för att öppna guiden **Skapa**.
1. Slutför guiden genom att följa instruktionerna på skärmen. Tänk på följande när du arbetar:

    - Använd standardinställningar om inte andra poäng i den här listan rekommenderar andra inställningar.
    - Se till att välja den geografiska region som matchar den region där din instans av Supply Chain Management är distribuerad. I annat fall kanske vissa data passerar regiongränser. Mer information finns i avsnittet [Sekretesspolicy](#privacy) senare i det här avsnittet.
    - Använd dedikerade resurser, till exempel resursgrupper, lagringskonton, behållarregister, Azure nyckelvalv och resursresurser.
    - På sidan **Ställ in anslutningparametrar för Azure Machine Learning Service** i guiden måste du ange ett namn för lagringskontot. Använd ett konto som är dedikerad till efterfrågeprognoser. Indata och utdata för efterfrågeprognosticering lagras i det här lagringskontot.

Mer information finns i [Skapa en arbetsyta](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Steg 2: Konfigurera lagring

Använd följande procedur för att ställa in din lagring.

1. I GitHub, öppna [Mallar för Dynamics 365 Supply Chain Management efterfrågeprognoser med Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) lagringsplats och hämta följande **sampleInput.csv** fil.
1. Öppna lagringskontot som du skapade i [Steg 1: Skapa ett nytt arbetsyta](#create-workspace).
1. Följ instruktionerna i [Skapa en programbehållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) om du vill skapa en programbehållare som kallas *demplan-azureml*.
1. Överför filen **sampleInput.csv** som du hämtade i steg 1 till programbehållaren som du just skapade. Den här filen krävs för att publicera försäljningsförloppet och generera en testprognos. Instruktioner finns i [Ladda upp ett blockblob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Steg 3: Konfigurera ett standarddatalager

Använd följande procedur för att ställa in ditt standarddatalager.

1. I Azure Machine Learning Studio väljer **Datalager** i navigeringsfönstret.
1. Skapa det nya datalagret av typen *Azure Blob Storage* som pekar på den *demplan-azureml* Blob Storage-programbehållare du skapade i avsnittet [Steg 2: Konfigurera lagring](#config-storage). (Om autentiseringstypen för den nya datalagringen är *Kontonyckel*, tillhandahålla en kontonyckel för det skapade lagringskontot. Instruktioner finns i [Hantera åtkomstnycklar för lagringskonto](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)).
1. Gör din nya datalager till standarddatalager genom att öppna dess detaljer och välja **Ställ in som standarddatalager**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Steg 4: Konfigurera beräkningsresurser

Använd följande procedur när du ställer in en resurs för beräkning i Azure Machine Learning Studio för att köra dina prognosgenereringsskript.

1. Öppna detaljsidan för maskininlärningsarbetsytan som du skapade i [Steg 1: Skapa en ny arbetsyta](#create-workspace). Sök efter värdet **Studio webbadress** och markera länken för att öppna det.
1. Klicka på **Beräkning** i navigeringsfönstret.
1. På fliken **Beräkningsinstans**, välj **Ny** om du vill öppna en guide som hjälper dig att skapa en ny beräkningsinstans. Följ instruktionerna på skärmen. Beräkningsinstansen används för att skapa försäljningsförloppet för efterfrågeprognosticering (Det kan tas bort när försäljningsförloppet har publiceras.) Använd standardinställningarna.
1. På fliken **beräkningskluster**, välj **Ny** om du vill öppna en guide som hjälper dig att skapa en ny beräkningskluster. Följ instruktionerna på skärmen. Beräkningsklustret används för att generera efterfrågeprognoser. Inställningarna påverkar prestanda och den maximala parallelliseringsnivån för körningen. Ställ in följande fält, men använd standardinställningarna för alla andra fält:

    - **Namn** – Ange *e2ecpucluster*.
    - **Virtuell maskinstorlek** – Justera den här inställningen efter den mängd data som du förväntar dig att använda som indata för efterfrågeprognoser. Nodantalet bör inte överstiga 11 eftersom en nod krävs för att utlösa genereringen av efterfrågeprognoser och det maximala antalet noder som sedan kan användas för att generera en prognos är 10. (Du ställer även in nodräkningen i parameters.py-filen i avsnittet [Steg 5: Skapa pipelines](#create-pipelines).) På varje nod kommer det att finnas flera arbetsprocesser som kör prognosskript parallellt. Det totala antalet arbetsprocesser i ditt jobb kommer att vara *Antal kärnar som en nod har* × *Nodantal*. Om till exempel ditt beräkningskluster har typen *Standard\_D4* (åtta kärnor) och maximalt 11 noder och om värdet `nodes_count` är inställt på *10* i filen parameters.py blir den faktiska nivån för 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Steg 5: Skapa pipelines

Pipelines är ett sätt att starta prognosskript från Supply Chain Management. Använd följande procedur när du skapar önskade pipelines.

1. I GitHub, öppna [Mall för Dynamics 365 Supply Chain Management efterfrågeprognoser med Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) lagringsplats och hämta följande filer:

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. I Azure Machine Learning Studio väljer **Anteckningsböcker** i navigeringsfönstret.
1. Hitta följande plats i strukturen **Filer**: **Users/\[current user\]/src**.
1. För över de fyra filerna som du hämtat i steg 1 till den plats som du hittade i det föregående steget.
1. Öppna och granska i Azure filen **parameters.py** som du nyss förde över. Kontrollera att värdet `nodes_count` är lägre än värdet som du konfigurerat för beräkningsklustret i [Steg 4: Konfigurera beräkningskluster](#config-compute-resources). Om värdet `nodes_count` är större än eller lika med antalet noder i beräkningsklustret kan pipeline-körning starta. Den kommer sedan att sluta svara medan den väntar på de nödvändiga resurserna. Mer information om nodantalet finns i avsnittet [Steg 4: Konfigurera beräkna resurser](#config-compute-resources).
1. Välj den **api_trigger.py** fil som du just förde över och kör den. Det skapar ett försäljningsförlopp som kan initieras via API:t.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Ställa in ett nytt Active Directory-program

Ett Active Directory-program måste autentiseras med de resurser som är dedikerade till efterfrågeprognosticering med hjälp av tjänstens huvudnamn. Därför bör programmet ha den lägsta behörighetsnivå som krävs för att skapa prognosen.

1. Logga in på Azure-portal.
1. Registrera en ny app i klientorganisationens Azure Active Directory (Azure AD). För instruktioner, se [Så här använder du portalen för att skapa ett Azure AD-program och ett tjänstekonto som har åtkomst till resurser](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Följ instruktionerna på skärmen när du fullföljer guiden. Använd standardinställningarna.
1. Ge ditt nya Active Directory-program åtkomst till följande resurser som du skapade i avsnittet [Ställ in Machine Learning i Azure](#ml-workspace). Instruktioner finns i Tilldela [Azure-roller med hjälp av Azure-portalen](/azure/role-based-access-control/role-assignments-portal?tabs=current). Det här steget gör det möjligt att importera och exportera prognosdata och utlösa försäljningsförloppet för maskininlärning från Supply Chain Management.

    - Rollen deltagare till Machine Learning-arbetsyta
    - Rollen deltagare till det dedikerade lagringskontot
    - Storage Blob Data rollen deltagare till det dedikerade lagringskontot

1. I avsnittet **Intyg och hemlighet** för programmet du skapade, skapa en hemlighet för appen. Instruktioner finns i [Lägga till en klienthemlighet](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Gör en notering om program-ID och dess hemlighet. Du behöver mer information om programmet senare när du ställer in sidan **Efterfrågeprognosparametrar** i Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Konfigurera anslutningsparametrar för Azure Machine Learning Service i Supply Chain Management

Använd följande procedur för att ansluta din Supply Chain Management-miljö till maskininlärningstjänsten som du just konfigurerade i Azure.

1. Logga in på Supply Chain Management.
1. Gå till **Huvudplanering \> Inställningar \> Efterfrågeprognosticering \> Parametrar för efterfrågeprognosticering**.
1. På fliken **Allmänt** kontrollera att fältet **Prognosgenereringsstrategi** anges till *Azure Machine Learning Service*.
1. På fliken **Artikelallokeringsnycklar** kontrollerar du att fältet **Strategi för prognosgenerering** anges till to *Azure Machine Learning Service* för varje allokeringsnyckel som ska använda Azure Machine Learning Service för efterfrågeprognoser.
1. På fliken **Azure Machine Learning Service**, ställ in följande fält.

    - **Klientorganisations-ID** – Ange ID för din Azure-klientorganisation. Supply Chain Management använder detta ID för att autentisera med Azure Machine Learning Service. Ditt innehavares-ID finns på sidan **Översikt** för i Azure AD i Azure-portal.
    - **App-ID för tjänstens huvudnamn** – Ange app-ID för appen du skapade i avsnittet [Active Directory-app](#aad-app). Det här värdet används för att auktorisera API-förfrågningar till Azure Machine Learning Service.
    - **Hemlighet för tjänstens huvudnamn** – Ange apphemlighet för tjänstens huvudnamn för appen du skapade i avsnittet [Active Directory-app](#aad-app). Det här värdet används för att hämta åtkomsttoken för säkerhetsprincipen som du har skapat för att utföra behöriga operationer mot Azure Storage och arbetsytan för Azure Machine Language.
    - **Namn på lagringskonto** – Ange namnet på det Azure-lagringskonto som du angav när du körde installationsguiden i Azure-arbetsytan. (Mer information finns i avsnittet [Ställ in Machine Learning i Azure](#ml-workspace).)
    - **Slutpunktsadress för pipeline** – Ange URL:en för försäljningsförloppets REST-slutpunkt för din Azure Machine Learning Service. Du skapade försäljningsförloppet som ett sista steg när du [ställer in maskininlärning i Azure](#ml-workspace). För att hämta pipeline-URL, logga in på din Azure-portal, välj **Pipelines** i navigeringen. På fliken **Pipeline** väljer du den slutpunkt för försäljningsförloppet som kallas **TriggerDemandForecastGeneration**.  Kopiera sedan REST-slutpunkten som visas.

    ![Parametrar på fliken Azure Machine Learning Service för sidan behovsprognosparametrar.](media/azure-ml-service-parameters.png "Parametrar på fliken Azure Machine Learning Service för sidan behovsprognosparametrar")

## <a name="privacy-notice"></a><a name="privacy"></a>Sekretesspolicy

När du väljer *Azure Machine Learning Service* som din strategi för prognosgenerering skickar Supply Chain Management automatiskt dina kunddata för historisk efterfrågan, till exempel aggregerade kvantiteter, produktnamn och deras produktdimensioner, leverans- och mottagningsplatser, kundidentifierare och även prognosparametrar, till den geografiska regionen där maskininlärningsytan och det kopplade lagringskontot finns, för prognostiserade framtida behov. Azure Machine Learning Service kan vara i en annan geografisk region än den geografiska regionen där Supply Chain Management distribueras. Vissa användare kan styra om den här funktionen är aktiverad genom att välja strategi för prognosgenerering på sidan **Parametrar för efterfrågeprognoser**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Efterfrågeprognosticering – översikt](introduction-demand-forecasting.md)
- [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)
- [Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
