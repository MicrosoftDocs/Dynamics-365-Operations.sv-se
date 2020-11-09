---
title: Skapa platsdirektiv
description: Det här avsnittet innehåller information om hur du skapar platsdirektiv. Platsdirektiv är användardefinierade regler som hjälper till att identifiera plockning och inlagringsplatser för lagerrörelse.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 4f634b7f526fd198b394af6d3870c43ee560813e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016780"
---
# <a name="create-location-directives"></a>Skapa platsdirektiv

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du skapar platsdirektiv. Platsdirektiv är användardefinierade regler som hjälper till att identifiera plockning och inlagringsplatser för lagerrörelse. I en försäljningsordertransaktion fastställer till exempel ett direktiv platsen där artiklarna ska plockas och var de plockade artiklarna ska inlagras.

> [!NOTE]
> Det här ämnet gäller funktioner i modulen **Lagerstyrning**. Den gäller inte funktioner i modulen [Lagerhantering](../inventory/inventory-home-page.md).

Du kan använda platsdirektiv när du slutför följande uppgifter:

- Inlagra inkommande artiklar.
- Plocka och placera artiklar för utgående transaktioner.
- Plocka och placera råmaterial för produktion.
- Påfyllnadsplatser.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan skapa ett platsdirektiv måste du följa dessa steg för att se till att kraven är på plats.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. Skapa ett lagerställe.
1. På snabbfliken **Lagerställe** ange alternativet **Använd lagerstyrningsprocesser** till *Ja*.
1. Skapa platser, platstyper, platsprofiler och platsformat. Mer information finns i [Konfigurera platser i ett WMS-aktiverat lagerställe](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Skapa platser, zoner och zongrupper. Mer information finns i [Konfigurera lagerställe](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) och [Konfigurera platser i ett WMS-aktiverat lagerställe](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Ställ in

### <a name="create-location-directives"></a>Skapa platsdirektiv

Gör så här om du vill skapa ett platsdirektiv.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I listrutan anger du fältet **arbetsordertyp** för den typ av lagertransaktion som du skapar ett platsdirektiv för.
1. I åtgärdsfönstret, välj **Ny** för att skapa ett nytt platsdirektiv.
1. För det nya platsdirektivet anger du fälten enligt beskrivningen i följande tabell.

    | Fält | beskrivning |
    |---|---|
    | Löpnummer | Ange ett heltal som anger placeringen av platsdirektivet. Sekvenspositioner bestämmer när varje platsdirektiv behandlas för den valda arbetsordertypen. |
    | Namn | Ange ett namn på platsdirektivet. | 
    | Arbetstyp | Välj den typ av arbete som ska utföras. Listan över värden beror på den typ av lagertransaktion som du har valt i fältet **Arbetsordertyp**. Följande värden kan finnas:<ul><li>**Placera** – platsdirektivet gör ett försök att hitta den bästa platsen för att placera eller hitta det lager som kommer till systemet via mottagnings-, produktions- eller lagerjusteringar. Platsdirektivet används också för att definiera placera på platsen eller leveransplatsen för vikdörren i det utgående flödet.</li><li>**Plocka** – platsdirektivet kommer att försöka hitta de bästa platserna för fysiskt reservlager från (skapa arbete). Plockningen kan slutföras (plocka arbetsrad kan stängas), även om arbetet inte slutförs. Användaren kan slutföra fysisk plockning. I systemet är den åtgärden ett plockningssteg. Användaren kan sedan avbryta från en mobil enhet och slutföra arbetet (till exempel placera) senare. Arbetsrubriken stängs när första platsen slutförs.</li><li>**Inventering** , **justeringar** , **anpassa** , **ändring av lagerstatus** , **skapa registreringsskylt** , **skriva ut** , **statusändra** och **packa till kapslade ID-nummer** – Dessa kan inte användas i någon inställning för platsdirektiv.</li></ul> |
    | Site | Välj den webbplats där arbetet bör ha slutförts. |
    | Lagerställe | Välj den lagerställeplats där arbetet ska slutföras. |
    | Direktivkod | Välj en direktivskod som ska vägleda valet av platsdirektiv som är relaterade till arbetsmallens inleveransrader med den här koden tilldelad. På sidan **direktivkod** kan du skapa nya koder som kan användas för att koppla en arbetsmall till ett platsdirektiv. Du kan också använda den sidan för att fastställa sambandet mellan alla arbetsmallrader och platsdirektiv (t.ex. vikdörr eller fasplats). Mer information om hur man konfigurerar en direktivkod med en arbetsmall, se [Kontrollera lagerarbete med arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).<p>Om en direktivkod ställs in, när arbete måste genereras, kommer systemet att söka efter platsdirektiv med direktivkod istället för efter sekvens. På detta sätt kan du vara mer exakt om platsmallen som används för ett specifikt steg i en arbetsmall, till exempel steget för att iscensätta materialen.</p> |
    | Dispositionskod | Välja en dispositionskod om du vill omdirigera inlagrat för de inlevererade artiklarna till en plats. (Mer information finns i [Ställ in dispositions koder](tasks/set-up-dispositions-codes.md).) Det här fältet är endast tillgängligt om fältet **Arbetsordertyp** är inställt på *inköpsorder* , *returorder* eller *färdiga varor som förts in*. |
    | Flera SKU-enheter | Ange det här alternativet till *Ja* om du vill använda flera lagerhållningsenheter (SKUs) på en plats. Det här alternativet måste till exempel ställas in på *Ja* för vikdörren.<p>Om alternativet **Flera SKU** är inställt på *Ja* , anges placeringsplatsen i arbete (som förväntat). Placeringsplatsen kan dock bara hantera resurser för flera artiklar om arbetet innehåller olika SKU:er som måste plockas och tas, inte om arbetet bara inkluderar en enda SKU som måste placeras.</p><p>Om alternativet **flera SKU** anges till *Nej* , kommer platsen endast anges om den bara har en typ av SKU.</p><p>Om du vill använda båda tillvägagångssätten måste du ange två rader som har samma struktur och inställning, men ange att alternativet **flera SKU:er** ska vara *Ja* för en av raderna och *Nej* för den andra. Med andra ord, två identiska platsdirektiv krävs för placeringsoperationer, även om du inte behöver skilja mellan enstaka och flera SKU:er i arbets-ID. Du måste också ställa in platsdirektiv för plockning, om du har en order med fler än ett objekt.</p><p>**Obs!** Om du anger **flera SKU** till *ja* för ett platsdirektiv för arbetstypen *Placering* kommer systemet alltid välja det första platsdirektivet oavsett andra begränsningar som skapas i raderna.</p> |

1. Valfritt: Välj i åtgärdsfönstret **Redigera frågan** om du vill välja platser eller ange eventuella begränsningar som gäller när du väljer ett visst platsdirektiv.
1. Skapa en eller flera **rader** för att ange enheter och för att hitta eller reservera kvantitet i ett lagerställe på snabbfliken.
1. På varje ny linje anger du fälten enligt beskrivningen i följande tabell.

    | Fält | beskrivning |
    |---|---|
    | Löpnummer | Ange ett heltal som anger placeringen av platsdirektivet. Sekvenspositioner bestämmer när varje platsdirektiv behandlas för den valda arbetstypen. |
    | Från-kvantitet | Ange början av kvantitetsintervall för när den mittersta rutnätssekvensen ska väljas. Ange mängden i den måttenhet som har valts i fältet **Enhet**. |
    | Till-kvantitet | Ange slutet av kvantitetsintervall för när den mittersta rutnätssekvensen ska väljas. Ange mängden i den måttenhet som har valts i fältet **Enhet**. |
    | Enhet | Välj måttenhet för artiklarna.<p>Du kan ange en minsta kvantitet och en högsta kvantitet som direktivet ska gälla för. Du kan även ange att direktivet ska användas för en viss lagerenhet. Fältet **Enhet** används endast för utvärdering av kvantitet.</p><p>För att avgöra om en platsdirektivrad gäller, evaluerar systemet kvantiteter genom att använda värdet **enhet** som anges på raden. Varje gång en platsdirektivrad har nåtts, görs försök att konvertera efterfrågeenheten till en enhet som har angetts på raden. Om enhetskonverteringen inte finns, kommer systemet att gå vidare till nästa rad.</p> |
    | Hitta kvantitet | Det här fältet är endast giltigt när du försöker att placera eller lokalisera kvantitet i lagerstället. Det betyder att det bara är giltigt för *Placera* arbete. Välj den metod som används för att kontrollera om kvantiteten är i det intervall som anges i fälten **Från kvantitet** och **Till kvantitet**. Om platsdirektivet är för en inkommande transaktion, välj ett av följande alternativ:<ul><li>**Kvantitet av registreringsskylt** - För utvärdering om kvantiteten ligger inom målkvantitetsintervallet, använd kvantiteten på registreringsskylten som tas emot.</li><li>**Sammansatt kvantitet** - För utvärdering om kvantiteten ligger inom målkvantitetsintervallet, använd kvantiteten som är sammansatt under transaktionen. Om du till exempel kan ta emot en kvantitet på 1 000 på ett lagerställe och bryta ned den till 10 registreringsskyltar per 100 styck, kan du använda en kvantitet på 1 000 artiklar i stället för registreringsskyltskvantiteten på 100.</li><li>**Resterande kvantitet** - För att utvärdera av om kvantiteten är inom målkvantitetsintervallet använder du den kvantitet som återstår inköpsorderraden som kontrolleras.</li><li>**Förväntad kvantitet** - Vid utvärdering av om kvantiteten är inom målkvantitetsintervallet använder du den totala kvantitet som återstår, oavsett kvantiteten som redan har mottagits.</li></ul> |

1. Valfritt: På snabbfliken **rader** kan välja följande ytterligare fält.

    | Fält | beskrivning |
    |---|---|
    | Begränsa per enhet | Markera den här kryssrutan om du vill begränsa vilka måttenheter som är giltiga urvalskriterier för platsdirektivraderna. När måttenheter har angetts, kommer endast artiklar där enheten matchar minst en enhet som har definierats för enhetsseriegruppen att betraktas som giltiga för radurvalet.<p>Enheten är till exempel begränsad till lastpallar och artikeln associeras med en enhetsseriegrupp som innehåller enheten *Lastpallar*. I detta fall betraktas artiklarna som giltiga alternativ för platsdirektivet.</p><p>Men kryssrutan **begränsa efter enhet** styr inte enheten eller enheterna som används på arbetsraderna. Enhetsbegränsningen gäller endast de enheter som har gjorts tillgängliga via enhetsseriegruppen.</p><p>Till exempel är ett objekt associerat med en enhetsseriegrupp som inkluderar båda enheterna *Lastpallar* och *styck*. En måttenhet har definierats där 1 lastpall = 100 st, och i platsdirektivet används endast funktionen **begränsa efter enhet** för lastpallar. Dessutom har en arbetsmall definierats som begränsar skapandet av arbetshuvud till 50 st. I det här fallet skapas arbetsrader på 50 stycken.</p><p>Följ dessa steg för att specificera måttenheten för begränsning</p><ol><li>På snabbfliken **Rader** välj **begränsa per enhet**. Den här knappen blir tillgänglig när du har markerat kryssrutan **begränsa per enhet** och sedan väljer **Spara**.</li><li>I fältet **Enhet** välj måttenhet för att begränsa plockning och inlagring.</li></ol> |
    | Avrunda uppåt till enhet | Välj detta alternativ för att ange om plockningen av råmaterial ska avrundas uppåt till en multipel av den hanteringsenhet som anges i fältet **Begränsa efter enhet**. Detta fält gäller endast råmaterialplockning och platsdirektiv av typen *Plocka*. |
    | Placera förpackningskvantitet | Markera den här kryssrutan om en förpackningsenhetskvantitet har angetts på sidan för **Försäljningsorder**. Om du markerar den här kryssrutan, väljs bara platserna med denna kvantitet i förpackningsenheten. |
    | Tillåt delning | Markera den här kryssrutan om du vill dela kvantiteten över flera platser. |
    | Mall för omedelbar lagerpåfyllnad | Skapa en anslutning till en påfyllnadsmall för att starta påfyllnad omedelbart om artiklar inte har tilldelats. Om fältet är tomt startar inte artikelpåfyllnad förrän alla rader i platsdirektivet har körts klart.<p>Det här fältet är endast tillgängligt för de valda arbetsordertyperna där återanskaffning tillåts, t.ex. *försäljnings order* och *råmaterialplockning*.</p> |

1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** om du vill välja platsen eller intervallet med platser.
1. I fältet **Sekvensnummer** visas i vilken ordning som platsdirektivet kommer att bearbetas i för den valda arbetstypen. Du kan ändra sekvensen. Tänk dock på att vara försiktig med ordningsnummer för platsdirektivåtgärder, eftersom platsdirektivåtgärder alltid körs i den här sekvensen.
1. I fältet **Namn** anger du namnet för platsdirektivsåtgärden. Var specifik så att det är klart vad åtgärden är.
1. Valfritt: Välj **Redigera fråga** om du vill ändra lagerställeplatserna och andra kriterier.
1. Valfritt: Du kan ange följande ytterligare fält för ett platsdirektiv.

    | Fält | beskrivning |
    |---|---|
    | Användning av fast lagerplats | Välj vilka platser som platsdirektivet beaktar.<ul><li>**Fasta och inte fasta lagerplatser** – Platsdirektivet beaktar alla platser.</li><li>**Endast fasta lagerplatser för produkten** – Platsdirektivet beaktar endast fasta lagerplatser för produkter.</li><li>**Endast fasta lagerplatser för produktvarianten** – Platsdirektivet beaktar endast fasta lagerplatser för produktvarianter.</li></ul> |
    | Tillåt negativt lager | Markera den här kryssrutan om du vill tillåta negativt lager på den angivna lagerställeplatsen. |
    | Batch aktiverad | Markera den här kryssrutan om du vill använda batchstrategier för artiklarna som är batchaktiverade. Om den här kryssrutan är markerad och fältet **strategi** fältet är inställt på *ingen* , förs systemet vidare till nästa åtgärdsrad. |
    | Strategi | Välj den strategi som platsdirektivet ska använda:<ul><li>**Ingen** – ingen strategi kommer att användas.</li><li>**Matcha förpackningskvantitet** – Denna strategi används för att verifiera att en plockplats har den angivna kvantiteten. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *plocka*.</li><li>**Konsolidera** – Denna strategi konsoliderar artiklar på en viss plats när andra artiklar redan är tillgängliga. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *placera*. I en typisk inställning för placera försöker systemet konsolidera på den första åtgärdsraden och sedan försöker den på den andra åtgärdsraden placera utan konsolidering. Konsolidera varor gör senare plockning effektivare.</li><li>**FEFO-batchreservation** – Denna strategi används när lagret lokaliseras med hjälp av en batch för utgångsdatum och allokeras för batchreservation. FEFO-strategin (först utgått, först ut) för batchreservation används också när lagret identifieras med hjälp av en batch med bästföredatum utöver utgångsdatumet. Du kan bara använda denna strategi för batchen aktiverade artiklar. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *plocka*. När du väljer den här strategin åsidosätter du alla frågesorteringar för batchnummer som används.</li><li>**Avrunda uppåt till full reg.skylt** - Denna strategi avrundar lagerkvantiteten för att matcha den registreringsskyltskvantitet som tilldelas artiklarna som ska plockas. Denna strategi kan endast användas för påfyllningstypen för platsdirektiv och endast om fältet **arbetstyp** är inställt på *plockning*.</li><li>**Tom plats utan inkommande arbetsuppgifter** – Denna strategi används för att söka tomma platser. Platsen anses vara tom om den inte har något fysiskt lager och inget förväntat inkommande arbete. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *placera*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Exempel på användning av platsen direktiven

I det här exemplet kommer vi att överväga en inköpsorder där placering direktiv måste hitta ledig kapacitet inom ett lager för inventarier som just registrerats vid mottagningsplatsen. Först måste du försöka hitta ledig kapacitet inom lagret genom att konsolidera med befintliga lagersaldot. Om konsolideringen är inte möjligt, då måste du hitta en tom plats.

För detta scenario, måste du definiera två platsdirektivåtgärder. Den första åtgärden i sekvensen måste **konsolidera** strategi, och den andra ska använda den **tomma platsen med några inkommande arbete** strategi. Om du definierar en tredje handlingsplan för att hantera ett överskott scenario två utfall är möjliga när det inte finns något mer kapacitet i lagret: arbete kan skapas även om inga lagerplatser definieras eller arbete processen kan misslyckas. Resultatet bestäms av inställningar på **plats direktiv fel** sida, där du kan bestämma om du vill välja **stopp på plats direktiv fel** alternativ för varje arbetsorder.

## <a name="next-step"></a>Gå vidare

När du har skapat platsdirektiv kan du associera varje direktivkod med en arbetsmallkod för att skapa arbete. Mer information finns i [Lagerpåfyllnad och Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Teknisk information för systemadministratörer

Om du inte har åtkomst till de sidor som används för att slutföra den här uppgiften, kontakta systemadministratören och ange information som visas i följande tabell.

| Kategori | Förutsättning |
|---|---|
| Konfigurationsnycklar | Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**. Visa licensnyckel **Handel** och konfigurationsnyckel för konfigurationsnyckeln för **lager- och transporthantering**. |
