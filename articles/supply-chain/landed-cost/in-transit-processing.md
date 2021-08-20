---
title: Bearbetning av varor på väg
description: Det här avsnittet beskriver hur du arbetar med beställningar av varor på väg. När en order eller ett färd har ställts in för att använda bearbetning av varor på väg, kan varor faktureras innan de har inkommit i lagerstället för förbrukning.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d4503b6939e3d01ae5bcf1d79c1f85d39348fbb6233cfb7a965f84f3a3b0699a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744808"
---
# <a name="goods-in-transit-processing"></a>Bearbetning av varor på väg

[!include [banner](../../includes/banner.md)]

Det här avsnittet beskriver hur du arbetar med beställningar av varor på väg. Den här ordertypen används bara i modulen **Hemtagningskostnad**. När en order eller ett färd har ställts in för att använda bearbetning behöver du inte vänta tills varor tas emot i lagret innan du kan fakturera dem. Istället faktureras varorna när de lämnar leverantörens lagerställe eller ursprungsport och de ekonomiska kostnaderna redovisas när färden börjar. Med den här funktionen kan du ta ansvar för lager på rätt sätt, eftersom varor ofta blir organisationens egendom när de lämnar leveransporten.

När order för varor på väg används tas de ekonomiskt uppdaterade artiklarna emot i ett interimslagerställe som kallas för ett lager för varor på väg. Varorna stannar sedan i det här lagerstället tills de kan tas emot på det slutliga lagerstället (det lagerställe som har definierats på inköpsraden). De kan inte tas bort manuellt.

Så länge artiklarna är på väg är de inte tillgängliga i lagret och kan inte plockas från lagret för en leverans. Du kan dock visa lager för varor på väg. Du kan också använda varor för huvudplanering. I det här fallet ska du använda det bekräftade leveransdatumet på inköpsorderraden som förväntat datum då lagret blir tillgängligt för förbrukning.

I följande avsnitt beskrivs de inställningar som krävs för att bearbeta lager och färder genom att använda koncept och funktioner för varor på väg.

## <a name="terms-of-delivery"></a>Leveransvillkor

När du aktiverar **Hemtagningskostnad** förbättras standard *leveransvillkor* för att ge stöd till funktionen varor på väg.

När alternativet **Hantering av varor på väg** anges till *Ja* för tillämpliga leveransvillkorsposten placeras varorna i lager för varor på väg. Den här åtgärden initieras bara om lagerinleveransen inte bearbetas innan en faktura bearbetas. När leveransvillkoren för en order har ställts in för att använda varor på väg, kan användarna inte längre bokföra en produktinleverans för inköpsordern. Om de försöker uppstår ett fel. Felmeddelandet visar att de måste använda funktionen för varor på väg när de går vidare.

Om du vill arbeta med leveransvillkor för varor på väg går du till **Anskaffning och inköp \> Inställningar \> Distribution \> Leveransvillkor**. I tabellen nedan beskrivs de fält som modulen **Hemtagningskostnad** lägger till på sidan **Leveransvillkor** för att ge stöd till funktionen varor på väg. Båda fälten finns på snabbfliken **Allmänt**. Mer information om de andra fälten på den här sidan finns [i Leveransvillkor (formulär)](/dynamicsax-2012//terms-of-delivery-form).

| Fält | beskrivning |
|---|---|
| Leveranshamn måste anges | Ange alternativet till *Ja* om en leveransport är obligatorisk när leveransvillkoren gäller. |
| Hantering av varor på väg | Ställ in det här alternativet till *Ja*, om du vill använda hantering av varor på väg när leveransvillkoren gäller. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Lagerställen för varor på väg och underleverans

När du aktiverar modulen **Hemtagningskostnad** förbättras standard *lagerställen* förbättras för att möjliggöra fakturering av inköpsorder medan varorna finns i ett lager för varor på väg.

Hemtagningskostnad lägger till två nya typer av lagerställe: *varor på väg* och *under leverans*. Lagerställen av båda typerna kan väljas som standardlagerställen. En lyckad bearbetning av beställningar av varor på väg kräver att både lagerstället för varor på väg och lagerstället för under leverans måste konfigureras på sidan **Lagerställen**. För varje standardlagerställe som ska användas med hemtagningskostnad och varor på väg måste därefter lagerstället för varor på väg och lagerstället för under leverans väljas för de tillgängliga lagerställena för varje typ.

Lagerställetypen *varor på väg* kommer att associeras med ditt lagerställe för varor på väg och det lagerstället kommer att användas för att behandla varorna på beställningen för varor på väg innan de tas emot på det slutliga destinationslagret. I allmänhet räcker ett lagerställe för varor på väg för varje plats om Plats och Lagerställe är de enda lagerdimensioner som används för lagerhantering. Om lagerdimensionen Plats används, måste ett lager för varor på väg ställas in för varje kombination av en plats och ett lagerställe, så att standardplatsen också kan anges.

Om du vill arbeta med inställningar för varor på väg för dina lagerställen går du till **Lagerhantering \> Inställningar \> Lageruppdelning \> Lagerställen**. I tabellen nedan beskrivs de fält som modulen **Hemtagningskostnad** lägger till på sidan **Lagerställen** för att ge stöd till funktionen varor på väg. Båda fälten finns på snabbfliken **Allmänt**. Mer information om övriga fält på snabbfliken finns i [Lagerställen (formulär)](/dynamicsax-2012//warehouses-form).

| Fält | beskrivning |
|---|---|
| Distributionslager för varor på väg | Identifiera det lagerställe för varor på väg som är relaterat till huvudlagerstället. |
| Distributionslager för underleverans | Identifiera det lagerställe för under leverans som är relaterat till huvudlagerstället. |

## <a name="posting-rules-for-landed-cost"></a>Bokföringsregler för hemtagningskostnad

Hemtagningskostnad lägger till två nya bokföringsregler som du kan konfigurera. Dessa bokföringsregler används för att ekonomiskt bokföra de direkta fakturabeloppen för inköpsorder för att identifiera ägarskapet för varorna när de lämnar ursprungspunkten. Den här processen ersätter begreppet *mottagna varor som ej fakturerats*, eftersom varorna faktureras innan de tas emot. <!-- KFM: Add a link to the related scenario when available. -->

Om du vill arbeta med bokföringsprofiler går du **Lagerhantering \> Inställningar \> Bokföring \> Bokföring**. På fliken **Inköpsorder** är följande nya bokföringsregler tillgängliga:

- **Hemtagningskostnader, varor på väg** – Ange bokföringsreglerna för hantering av varor på väg.
- **Hemtagningskostnad, periodisering av avgift** – Ange bokföringsregler för periodisering för avgiftskonto.

## <a name="goods-in-transit-orders"></a>Order för varor på väg

Du kan granska och hantera order för varor på väg direkt i modulen **Hemtagningskostnad**. Du kan bearbeta order för varor på väg direkt från sidan **order för varor på väg**. Alternativt kan du gå till den färd som har associerats med order för varor på väg och bearbeta hela färden, leveransbehållaren eller folio. När du fakturerar en färd och skapar order för varor på väg, skapas en ny order för varor på väg för varje kombination av lager och lagerdimensioner som är associerad med inköpsorderraden.

För att hantera varor på väg använder hemtagningskostnad en procedur med två steg:

1. En artikel tas emot när en lagerfaktura bearbetas och tilldelas status *under transport*.
1. Order för varor på väg bearbetas på sidan **Order för varor på väg** och tas sedan emot på det lagerställe som har angetts på inköpsordern. Vid den punkten ändras status till *Inlevererade*.

Om du vill arbeta med order för varor på väg, gå till **Hemtagningskostnad \> Periodiska uppgifter \> Order för varor på väg**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Ta emot lager från lagerstället för varor på väg

Du kan ta emot varor från en order för varor på väg på många sätt, beroende på inställningarna i ditt system.

### <a name="in-transit-receiving"></a>Inleverans på väg

Du kan ta emot uppgifter på väg från någon av följande sidor:

- Sidan **Order för varor på väg**, välj raden och välj sedan i åtgärdsfönstret **Inleverera**.
- På sidan **Alla färder** väljer du eller öppnar en färd. I åtgärdsfönstret, flik **Hantera** i gruppen **Varor på väg**, välj **Ta emot varor på väg**.
- På sidan **Alla leveransbehållare**, välj eller öppna leveransbehållare. I åtgärdsfönstret, flik **Hantera** i gruppen **Varor på väg**, välj **Ta emot varor på väg**.
- På sidan **Alla folio** väljer du eller öppnar en folio. I åtgärdsfönstret, flik **Hantera** i gruppen **Varor på väg**, välj **Ta emot varor på väg**.

> [!NOTE]
> Inleverans på väg används vanligtvis i situationer där platser och batch-/seriespårning inte används.

### <a name="arrival-journal"></a>Införseljournal

Du kan också ta emot varor genom att skapa en införseljournal. Du kan skapa en införseljournal direkt från sidsidan. De metodtips som din organisation har upprättat avgör om införseljournalen används för att ta emot varor.

1. Öppna den färd, behållaren eller folio.
1. I åtgärdsfönstret, på fliken **Hantera** i gruppen **Funktioner** markerar du **Skapa införseljournal**.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Initiera kvantitet** – Ange detta alternativ till *Ja* om du vill ställa in kvantiteten från kvantiteten under transport. Om det här alternativet ställs in på *Nej* ges ingen standardkvantitet från varor på väg rader.
    - **Skapa från varor på väg** - Ange det här alternativet till *Ja* för att ta kvantiteter från de valda transitraderna för den markerade färden, behållare eller folio.
    - **Skapa från orderrader** – Ange det här alternativet till *Ja* om du vill ange standardkvantiteten i införseljournalen från inköpsorderraderna. Standardkvantiteten i införseljournalen kan endast anges på det här sättet om kvantiteten på inköpsorderraden matchar kvantiteten på order för varor på väg.

1. Bearbeta införseljournalen enligt beskrivningen i [Registrera artikelinleveranser med en artikelinföringsjournal](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> Införseljournalen används vanligtvis i situationer där platser och batch-/seriespårning används, men lagerstyrning används inte.
>
> Standardinleveransplatser ska inte anges på orderraderna om en inlagringsplatsen ska anges i införseljournalen.

## <a name="warehouse-management"></a>Lagerstyrning

När du aktiverar modulen **Hemtagningskostnad** flera sidor i modulen **Hantering av distributionslager** modifieras så att orderhantering (specifikt bearbetning av varor på väg) kan göras via **Hemtagningskostnad**. Det här avsnittet beskriver fälten och processerna som läggs till i modulen **Lagerstyrning**.

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

Varor kan tas emot med hjälp av en mobil enhet under förutsättning att menyn för den mobila enheten och modulen **Lagerstyrning** har ställts in för att ta emot order för varor på väg. Det här avsnittet beskriver inställningarna som är associerade med inleverans av varor på väg.

För att ställa in mobila enheter för bearbetning av varor på väg, gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ för mobila enhet**.

Hemtagningskostnad lägger till följande arbetsgenereringsprocesser i menyn för mobila enheter som stöd för bearbetning av varor på varor:

- Artikelinleverans av varor på väg
- Varor på väg som mottagande och inleverans

Konfigurationsinställningarna för dessa processer liknar inställningarna för de [processer som används för att skapa arbetsprocesser för inköpsorder](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). I processen *Varor på väg som mottagande och inleverans* läggs även följande fält till.

- **Aktivera fullständig leveransbehållare** – Om det här alternativet är inställt på *Ja*, när inlagringsarbete är slutfört, tillhandahåller mobilappen för distributionslagerhantering ett ytterligare alternativ som kallas **fullständig leveransbehållare**. När det alternativet har valts kan arbetaren bekräfta att behållaren är slutförd. Då behandlas alla korta inleveranser som en undertransaktion.

### <a name="location-directives"></a>Platsdirektiv

Hemtagningskostnad lägger till en ny arbetsordertyp som heter *Varor på väg* på sidan **Platsdirektiv**. Denna arbetsordertyp ska konfigureras på samma sätt som [arbetsordertyperna för inköpsorder](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Arbetsmallar

I avsnittet beskrivs funktioner som modulen **Hemtagningskostnad** lägger till i arbetsmallar.

#### <a name="goods-in-transit-work-order-type"></a>Arbetsordertyp för varor på väg

Hemtagningskostnad lägger till en ny arbetsordertyp som heter *Varor på väg* på sidan **Arbetsmallar**. Denna arbetsordertyp ska konfigureras på samma sätt som [arbetsordermallar för inköpsorder](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Arbetsrubrikuppdelningar

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Arbetsmallar som har arbetsordertypen *Varor på väg* kan konfigureras att dela arbetsuppgiftsrubriker. På sidan **Arbetsmallar** följer du något av dessa steg:

- Ange max för arbetsuppgiftsrubrik på fliken **Allmänt** för mallen. Dessa max fungerar på samma sätt som de fungerar för arbetsmallar för inköpsorder. (Mer information finns i [arbetsmallar för inköpsorder](/dynamicsax-2012/appuser-itpro/create-a-work-template).)
- Använd knappen **Arbetsuppgiftshuvudet delas** för att definiera när nya arbetsuppgiftsrubriker ska skapas i systemet baserat på fält som används vid sortering. Om du till exempel vill skapa ett arbetshuvud för varje container-ID, väljer du **Redigera fråga** i åtgärdsrutan och lägger sedan till fältet **Container-ID** på fliken **Sortera** i frågeredigeraren. Fält som läggs till på fliken **Sortering** är tillgängliga för markering som *grupperingsfält*. För att ställa in grupperade fält väljer du **Arbetsuppgiftshuvudet delas** i åtgärdsrutan och markerar kryssrutan i kolumnen **Gruppera efter detta fält** för varje fält som du ska använda som grupperingsfält.

Hemtagningskostnaden [skapar en övertransaktion](over-under-transactions.md) om den registrerade kvantiteten överstiger den ursprungliga orderkvantiteten. När en arbetsuppgiftsrubrik har slutförts uppdaterar systemet status för lagertransaktionerna för den huvudsakliga orderkvantiteten. Den uppdaterar emellertid först den kvantitet som är kopplad till övertransaktionen när det huvudsakliga har köpts in helt.

Om du avbryter en arbetsuppgiftsrubrik för en övertransaktion som redan har registrerats, reduceras övertransaktionen först med den annullerade kvantiteten. När övertransaktionen har reducerats till kvantiteten 0 (noll) tas posten bort och eventuella ytterligare kvantiteter tas bort från den huvudsakliga orderkvantiteten.
