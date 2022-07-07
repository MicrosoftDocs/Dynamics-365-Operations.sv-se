---
title: Ställ in räkenskapsintegrering för handelskanaler
description: Denna artikel ger riktlinjer för att skapa funktionen för räkenskapsintegrering för Commerce-kanaler.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 695f3c1e704f2712f392d0d7179da63f47731f46
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027068"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Ställ in räkenskapsintegrering för handelskanaler

[!include [banner](../includes/banner.md)]

Denna artikel ger riktlinjer för att skapa funktionen för räkenskapsintegrering för Commerce-kanaler. Mer information om räkenskapsintegrering finns i [översikt över räkenskapsintegrering för handelskanaler](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>Aktivera funktioner i Commerce headquarters

Aktivera funktioner som är relaterade till funktionen räkenskapsintegrering för handelskanaler genom att följa dessa steg.

1. I Commerce headquarters går du till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Hitta och aktivera följande funktioner:

    - **Direkt räkenskapsintegrering från kassaregister** – Den här funktionen utökar ramverket för skatteintegrering genom att lägga till möjligheten att skapa skatteanslutningar som körs i kassan (POS). Denna typ av anslutningsprogram kommunicerar med en räkenskapsenhet eller tjänst som tillhandahåller ett API (HTTP-approgrammeringsgränssnitt) och behöver inte en dedicerad fysisk maskin i butiken. Den här funktionen aktiverar till exempel skatteintegrering för mobila enheter utan att det krävs delad maskinvara.
    - **Åsidosättningar av räkenskapsintegrering för teknisk profil** av den här funktionen kan konfigurationen av skatteintegrering expanderas och kapaciteten att kontrollera kopplingsparametrarna på inställningssidan för ett kassaregister läggs till. När den här funktionen är aktiverad kan du åsidosätta parametrarna för en teknisk profil.
    - **Räkenskapsregistreringstillstånd för kassaregister** – När den här funktionen är aktiverad kan du inaktivera räkenskapsregistreringsprocessen för specifika kassaregister. Om skatteregistreringen inaktiveras för ett kassaregister kan försäljningstransaktioner inte slutföras på den kassan.
    - **Säkerhetskopiering av lokal datalagring för bokföringsintegrering** – Den här funktionen utökar felhanteringsmöjligheterna i ramverket för finansiell integrering. Det gör det också möjligt att automatiskt säkerhetskopiera räkenskapsregistreringsdata vid dataförlust, så att data i lokal lagring återställs när en enhet aktiveras.

## <a name="set-up-commerce-parameters"></a>Ställ in Commerce-parametrar

Så här ställer du in Commerce-parametrar.

1. På sidan **gemensamma handelsparametrar** på fliken **allmänna** anger du alternativet till **aktivera räkenskapsintegrering** till **Ja**.
1. På fliken **Nummerserier** definierar du nummerserier för följande referenser:

    - Nummer för teknisk profil för räkenskaper
    - Gruppnummer för räkenskapskoppling
    - Nummer för registreringsprocess

1. På sidan **Handelsparametrar** definierar du nummerserier för funktionell profilnummer för räkenskap.

> [!NOTE]
> Nummerserier är valfria. Numren för alla entiteter för räkenskapsintegrering kan genereras från nummerserier eller manuellt.

## <a name="set-up-a-fiscal-registration-process"></a>Ställa in process för räkenskapsregistrering

Processen för att konfigurera räkenskapsintegrering inkluderar följande uppgifter:

- Konfigurera räkenskapskopplingar som representerar räkenskapsenheter eller tjänster som används för räkenskapsregistrering såsom kvittoskrivare.
- Konfigurera dokumentleverantörer som skapar skattedokument som registreras i räkenskapsenheter eller tjänster av räkenskapskopplingar.
- Konfigurera räkenskapsregistreringsprocessen som definierar en uppsättning steg i räkenskapsregistrering och räkenskapskopplingar och skattedokumentleverantörer som används för varje steg.
- Tilldela räkenskapsregistreringsprocess till en funktionsprofil för kassa.
- Tilldela koppling tekniska profiler till maskinvaruprofiler.
- Tilldela anslutningsprogramtekniska profiler till profiler för kassamaskinvara eller funktion.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Överför konfigurationer av leverantörer av skattedokument

En leverantör av skattedokument ansvarar för generering av skattedokument som representerar transaktioner och händelser som har registrerats i POS i ett format som även används för interaktionen med en räkenskapsenhet eller tjänst. En leverantör av skattedokument kan generera en representation av en kvittoskrivare i XML-format.

Följ dessa steg för att överföra konfigurationer av leverantörer av skattedokument.

1. I Commerce headquarters, gå till sidan **Leverantörer av skattedokument** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Leverantörer av skattedokument**).
1. Överför en XML-konfiguration för varje enhet eller tjänst som du tänker använda.

> [!TIP]
> Genom att markera **Visa**, kan du visa alla funktionella profiler som är relaterade till aktuell leverantör av skattedokument.

> [!NOTE]
> Datamappning betraktas som en del av skattedokumentprovidern. Om du vill konfigurera olika datamappningar för samma typ av koppling (till exempel delstatsspecifika regler) bör du skapa olika leverantörer för skattedokument.

### <a name="upload-configurations-of-fiscal-connectors"></a>Överför konfigurationer av räkenskapskopplingar

En räkenskapskoppling ansvarar för kommunikationen med en räkenskapsenhet eller tjänst. En räkenskapskoppling kan skicka en kvittoskrivare som en leverantör av skattedokument skapat i XML-format till en kvittoskrivare. Mer information om komponenter för räkenskapsintegrering finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegrering för kvittoskrivarenheter och tjänster](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Följ dessa steg för att överföra konfigurationer av räkenskapskopplingar.

1. I Commerce headquarters, gå till sidan **Räkenskapskopplingar** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Räkenskapskopplingar**).
1. Överför en XML-konfiguration för varje enhet eller tjänst som du tänker använda för räkenskapsintegrering.

> [!TIP]
> Genom att markera **Visa**, kan du visa alla funktionella och tekniska profiler som är relaterade till aktuell räkenskapskoppling.

Exempel på konfigurationer av anslutningsprogram för samt leverantörer av skattedokument finns i [Exempel på räkenskapsintegrering i Commerce SDK](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Skapa funktionsprofiler för koppling

Följ dessa steg för att skapa funktionsprofiler för kopplingar.

1. I Commerce headquarters, gå till sidan **Funktionsprofiler för koppling** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Funktionsprofiler för koppling**).
1. För varje kombination av en finansiell anslutning och en finansiell dokumentleverantör som är relaterad till denna räkenskapskoppling skapar du en funktionsprofil för anslutning genom att följa dessa steg:

    1. Välj namnet på en koppling.
    1. Välj en dokumentleverantör.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Ändra parametrarna för datamappning i en funktionsprofil för koppling

Du kan ändra parametrarna för datamappning i en funktionsprofil för koppling. Följande tabell innehåller några exempel på parametrar för datamappning i en funktionsprofil för anslutning.

| Parameter | Format | Exempel |
|-----------|--------|---------|
| Inställning av momssatser | värde: VATrate | 1 : 2000, 2 : 1800 |
| Mappning av momskoder | VATcode : värde | vat20 : 1, vat18 : 2 |
| Mappning av betalningsmedelstyper | TenderType : värde | Kontant: 1 kort: 2 |

Återställ standardparametrar som är definierade i konfigurationen av providern av skattedokument, markera **Uppdatera** på sidan **Funktionsprofiler för koppling**.

> [!NOTE]
> Funktionsprofiler för koppling är företagsspecifika. Om du planerar att använda samma kombination av räkenskapskoppling och skattedokumentleverantör i olika företag, bör du skapa en funktionsprofil för koppling för varje företag.

### <a name="create-connector-technical-profiles"></a>Skapa tekniska profiler för koppling

Följ dessa steg för att skapa tekniska profiler för kopplingar.

1. I Commerce headquarters, gå till sidan **Tekniska profiler för koppling** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Tekniska profiler för koppling**).
1. Skapa en teknisk profil för koppling för respektive räkenskapskoppling genom att följa stegen nedan:

    1. Välj namnet på en koppling.
    1. Välj en kopplingstyp:

        - För enheter eller tjänster som är anslutna till en maskinvara eller finns i det lokala nätverket väljer du **Lokal**.
        - Välj **extern** för externa tjänster.
        - För interna kontakter i Commerce Runtime (CRT) väljer du **Intern**. 

    1. Välj en anslutningsplats:

        - Om kopplingen finns på hårdvarustationen, välj **Maskinvarustation**.
        - Om kopplingen finns i kassaapparaten väljer du **Registrera**.

Parametrarna på flikarna **enhet** och **inställningar** i en teknisk profil för koppling kan ändras. Återställ standardparametrar som är definierade i konfigurationen av räkenskapskoppling, markera **uppdatering**. När en ny version av en XML-konfiguration laddas får du ett meddelande om att aktuellt räkenskapskoppling eller leverantör av skattedokument används redan. Den här proceduren åsidosätter inte manuella ändringar som gjorts i tidigare funktionsprofiler för koppling och tekniska profiler för koppling. För att tillämpa standarduppsättningen med parametrar från en ny konfiguration, klicka på **uppdatera** på sidan **Funktionsprofiler för koppling** och **Uppdatera**.

Om du måste konfigurera specifika parametrar för en enskild kassaapparat eller butik följer du dessa steg.

1. Välj menyalternativet **Åsidosätt**.
1. Skapa en ny post på sidan **Åsidosätt**.
1. Välj en butik eller en kassa. Du kan åsidosätta parametrarna i den valda tekniska profilen för en enskild kassa eller alla kassor i en enskild butik.
1. Ange parametrar för den valda kassan eller butiken på fliken **Enhet**.

### <a name="create-fiscal-connector-groups"></a>Skapa grupper för räkenskapskoppling

En grupp för räkenskapskoppling kombinerar funktionella profiler med räkenskapskopplingar som utför identiska funktioner som används i samma fas inom en räkenskapsregistrering. Om flera kvittoskrivarmodeller kan användas i butik, räkenskapskopplingar för de kvittoskrivare kombineras i en grupp för räkenskapskoppling.

Gör så här om du vill skapa grupp för räkenskapskoppling.

1. Gå till sidan **Grupp för räkenskapskoppling** (**Butik och handel \> kanalinställning \> räkenskapsintegrering \> grupper för räkenskapskoppling**).
1. Skapa en ny grupp för grupp för räkenskapskoppling.
1. Lägg till funktionella profiler till kopplingsgruppen. På sidan **Lägg till** på sidan **funktionella profiler** och välj ett profilnummer. Varje anslutningsprogram för räkenskaper i en grupp för anslutningsprogram kan endast ha en (1) funktionell profil.
1. Om du vill skjuta upp användning av funktionella profilen, ange **inaktivera** till **Ja**. Denna ändring påverkar endast aktuella kopplingsgruppen. Du kan fortsätta att använda samma funktionella profil i andra kopplingsgrupper.

### <a name="create-a-fiscal-registration-process"></a>Skapa process för räkenskapsregistrering

En process för räkenskapsregistrering definieras av ordningen på registreringsstegen och kopplingsgruppen som används i varje steg.

Följ dessa steg för att skapa en räkenskapsregistreringsprocess.

1. I Commerce headquarters, gå till sidan **Process för räkenskapsregistrering** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Process för räkenskapsregistrering**).
1. Skapa en ny post för varje unik räkenskapsregistreringsprocess.
1. Lägg till registreringssteg i processen genom att följa dessa steg:

    1. Markera **Lägg till**.
    1. Välj en typ av räkenskapskoppling:
    1. I fältet **gruppnummer** väljer du en grupp för räkenskapskoppling.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Tilldela entiteter för räkenskapsregistreringsprocess till kassaprofiler

Följ dessa steg för att tilldela entiteter för räkenskapsregistreringsprocess till kassaprofiler.

1. I Commerce headquarters, gå till sidan **Kassafunktionsprofiler** (**Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**). 
1. Tilldela räkenskapsregistreringsprocess till en funktionsprofil för kassa.
1. Välj **redigera** och klicka sedan på **Process för räkenskapsregistrering** i fältet **Processnummer** väljer du en process.
1. På fliken **Skattetjänster** väljer du tekniska profiler för anslutningsprogram med anslutningsprogramplatsen **Registrera**.
1. Gå till sidan **Maskinvaruprofil för kassa** (**Retail och Commerce \> Kanalinställning \> Kassainställning \> Kassaprofiler \> Hårdvaruprofil**).
1. Tilldela koppling tekniska profiler till maskinvaruprofil. 
1. Välj **Redigera** och lägg sedan till en rad på fliken **Kringutrustning för räkenskaper**. 
1. I fältet **Profilnummer** väljer du en profil för koppling.
1. På fliken **Skattetillbehör** väljer du tekniska profiler för anslutningsprogram med anslutningsprogramplatsen **Maskinvarustation**.

> [!NOTE]
> Du kan lägga till flera tekniska profiler till en maskinvaruprofil. En maskinvaruprofil eller kassafunktionalitetsprofil har dock endast en skärningspunkt med en grupp för räkenskapskoppling.

Räkenskapsregistreringsflöde har definierats av räkenskapsregistreringsprocessen samt av vissa parametrar för räkenskapsintegreringskomponenterna: tillägget CRT för providern av skattedokument och tillägg för maskinvarustation för räkenskapskopplingen.

- Prenumeration på händelser och transaktioner till räkenskapsregistreringen är fördefinierade i providern av skattedokument.
- Leverantören av skattedokument ansvarar för att identifiera räkenskapskopplingen som används för räkenskapsregistreringen. Den matchar kopplingens funktionella profiler som ingår i den grupp för räkenskapskoppling som har angetts för det aktuella steget för räkenskapsregistreringsprocessen med den tekniska profil för koppling som tilldelats maskinvaruprofilen för maskinvarustationen som POS är kopplad till.
- Leverantören av skattedokument använder data från konfiguration av leverantör av skattedokument för att omvandla transaktionshändelsen/data såsom skatter och betalningar medan skattedokument genereras.
- När providern av skattedokument genererar ett skattedokument kan räkenskapskopplingen antingen skicka den till räkenskapsenheten som den är, eller analysera den och omvandla den till en sekvens av kommandon i applikationsprogrammeringsgränssnittet (API) beroende på hur kommunikationen hanteras.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Ställa in register med skatteregistreringsrestriktioner

Du kan välja register där skatteregistrering är börbjuden, till exempel om du endast behöver tillhandahålla icke-skattemässiga åtgärder som till exempel sökning i produktkatalog, kundsökning eller skapande av transaktionsutkast på dessa enheter.

För mer information om hur du konfigurerar register med skatteregistreringsrestriktioner, följ dessa steg.

1. I Commerce headquarters går du till **Butik och handel \> Kanalinställningar \> Räkenskapsintegrering \> Processer för räkenskapsregistrering**.
1. Välj erforderlig process.
1. Markera fliken **Kassaregister med restriktioner rörande skatteprocess**.
1. Lägg till register med restriktioner rörande skatteprocess efter behov.

### <a name="validate-the-fiscal-registration-process"></a>Validera räkenskapsregistreringsprocessen

Du rekommenderas att validera räkenskapsregistreringsprocessen i följande fall:

- Du har slutfört alla inställningar för en ny registreringsprocess. De här inställningarna inkluderar tilldelning av registreringsprocesser till funktionsprofiler för kassan och maskinvaruprofiler.
- Du har gjort ändringar i en befintlig räkenskapsregistreringsprocess och dessa ändringar kan leda till att en annan räkenskapskoppling väljs vid körning. (Du har till exempel ändrat anslutningsgruppen för ett skatteregistreringsprocess, aktiverat en funktionsprofil för anslutning i en kopplingsgrupp eller lagt till en ny funktionell kopplingsprofil till en kopplingsgrupp.)
- Du har gjort ändringar i tilldelningen av tekniska profiler för koppling till maskinvaruprofiler.

Följ dessa steg för att validera en räkenskapsregistreringsprocess.

1. I Commerce headquarters, gå till sidan **Process för räkenskapsregistrering** (**Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Process för räkenskapsregistrering**).
1. Välj **Validera** om du vill validera räkenskapsregistreringsprocessen.
1. På sidan **Distributionsschema**, kör **1070** och **1090**-jobb för att överföra data till kanaldatabasen.

## <a name="set-up-fiscal-texts-for-discounts"></a>Ställ in räkenskapstexter för rabatter

I vissa fall kan måste en särskild text skrivas ut på en kvittoskrivare om en rabatt ska tillämpas. Du kan konfigurera räkenskapstexter för rabatter på sidan **Grupp för räkenskapskoppling** (**Butik och handel \> kanalinställning \> räkenskapsintegrering \> grupper för räkenskapskoppling**).

- För manuella rabatter som tillämpas i POS bör du konfigurera en räkenskapstext för den infokod eller infokodgrupp som anges som **produktrabatt**-infokod i funktionsprofil för kassa.

    1. På sidan **Grupp för räkenskapskoppling** anger du **Text för kvittoskrivaren**.
    1. På fliken **infokoder** väljer du **Lägg till** och välj en infokod eller infokodgrupp.
    1. I fältet **Infokodnummer** väljer du ett värde.
    1. I fältet **Delkodsnummer** väljer du ett värde om det krävs en delkod för valda infokoden.
    1. I fältet **Text för kvittoskrivare**, anger du en räkenskapstext som ska skrivas ut på en kvittoskrivare.
    1. Ange alternativet **Skriv ut användarens indata på kvittoskrivare** till **Ja** för att åsidosätta texten på en kvittoskrivare med information som användaren matar in manuellt i POS. Det här alternativet gäller bara för infokoder som har en indatatyp **Text**.

    > [!NOTE]
    > Du kan ange en räkenskapstext för flera infokoder för att stödja scenarier där infokodgrupper, länkade infokoder och utlösta infokoder används. I dessa fall innehåller kvittoskrivaren räkenskapstexter från alla infokoder som är kopplade till transaktionsraden där rabatten tillämpades.

- För kanalspecifika rabatter bör du definiera räkenskapstext för rabatt-ID.

    1. På sidan **Grupp för räkenskapskoppling** anger du **Text för kvittoskrivaren**.
    1. På fliken **rabatter**, välj **Lägg till**, och välj en rabatt-ID.
    1. I fältet **Text för kvittoskrivare**, anger du en räkenskapstext som ska skrivas ut på en kvittoskrivare.

    > [!NOTE]
    > Om flera rabatter tillämpas på samma transaktionsrad innehåller kvittoskrivaren räkenskapstexter från alla rabatter som är kopplade till transaktionsraden.

## <a name="set-error-handling-settings"></a>Ange inställningar för felhantering

Alternativ för felhantering som finns tillgängliga i räkenskapsintegrering ställs in i processen för räkenskapsregistrering. Mer information om felhantering i räkenskapsintegrering finns i [felhantering](fiscal-integration-for-retail-channel.md#error-handling).

Gör på följande sätt om du vill göra inställningar för felhantering.

1. På sidan **Process för räkenskapsregistrering** (**Butik och handel \> Kanalinställning \> räkenskapsintegrering \> process för räkenskapsregistrering**), kan du konfigurera följande parametrar för varje steg i processen för räkenskapsregistrering.

    - **Tillåt hoppa över** – den här parametern aktiverar alternativet **hoppa över** i dialogrutan för felhantering.
    - **Tillåt att markera som registrerad** – den här parametern aktiverar alternativet **Markera som registrerad** i dialogrutan för felhantering.
    - **Tillåt skjuta upp** – den här parametern aktiverar alternativet **skjuta upp** i dialogrutan för felhantering.
    - **Fortsätt vid fel** – om den här parametern är aktiverad kan räkenskapsregistreringen fortsätta på kassaapparater om räkenskapsregistreringen av en transaktioner eller händelser misslyckas. Annars om du vill köra räkenskapsregistreringen av nästa transaktion eller händelse måste operatorn göra om den misslyckade räkenskapsregistreringen, hoppa över den eller markera transaktioner eller händelser som registrerats. Mer information finns i [Valfri räkenskapsregistrering](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Om parametern **Fortsätt vid fel** är aktiverad kan parametrarna **Tillåt hoppa över** och **Tillåt markera som registrerad** inaktiveras automatiskt.

1. Alternativen **Hoppa över** och **Markera som registrerad** kräver behörigheten **Tillåt hoppa över registrering eller markera som registrerade** aktiveras. För att aktivera denna behörighet, gå till sidan **Behörighetsgrupper** (**Retail och Commerce \> Medarbetare \> Behörighetsgrupper**) och ange alternativet **Tillåt hoppa över registrering eller markera som registrerade** till **Ja**.
1. Alternativet **Skjuta upp** i dialogrutan för felhantering kräver att behörigheten **Tillåt skjuta upp** aktiveras. För att aktivera denna behörighet, gå till sidan **Behörighetsgrupper** (**Retail och Commerce \> Medarbetare \> Behörighetsgrupper**) och ange alternativet **Tillåt skjuta upp** till **Ja**.
1. Alternativen **hoppa över**, **markera som registrerad** och **skjuta upp** låter operatörer ange ytterligare information när räkenskapsregistreringen misslyckas. Om du vill göra funktionen tillgänglig bör du ange infokoderna **Hoppa över**, **Markera som registrerad** och **Skjuta upp** på en grupp för räkenskapskoppling. Informationen som operatörer anger sparas som en infokodtransaktion som kopplas till räkenskapstransaktionen. Mer information om infokoder finns i [Infokoder och infokodgrupper](../info-codes-retail.md).

    > [!NOTE]
    > Utlösarfunktionen **produkt** stöds inte för infokoder som används för **hoppa över** och **markera som registrerad** i grupper för räkenskapskoppling.

    - På sidan **Grupp för räkenskapskoppling** på fliken **Infokoder** väljer du infokoder eller infokodgrupper i fälten **hoppa över**, **markera som registrerad** och **skjuta upp**.

    > [!NOTE]
    > Ett skattedokument och ett icke skatte-dokument kan genereras på något steg i ett räkenskapsregistreringsprocessen. Tillägget för leverantör av skattedokument identifierar alla typer av transaktioner eller händelser som rör skatte- eller icke skattedokument. Funktionen för felhantering gäller endast skattedokument.
    >
    > - **Skattedokument** – ett obligatoriskt dokument som ska registreras korrekt (t.ex en kvittoskrivare).
    > - **Icke skattedokument** – ett kompletterande dokument för transaktionen eller händelsen (till exempel ett presentkortkvitto).

1. Om operatören ska kunna fortsätta att bearbeta aktuell åtgärd (till exempel skapa eller slutföra en transaktion) efter att ett hälsokontrollfel inträffar, bör du aktivera behörigheten **Tillåt hoppa över hälsokontrollfel** på sidan **Behörighetsgrupper** (**Butik och handel \> Medarbetare \> Behörighetsgrupper**). Mer information om hälsokontrollproceduren finns i [hälsokontroll av räkenskapsregistrering](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Ställ in räkenskapsrapporter X/Y från POS

För att aktivera räkenskapsrapporter X/Z att köras från POS, bör du lägga till nya knappar i kassalayouten.

- På sidan **knapprutnät**, följer du instruktionerna i [lägga till kassaåtgärder till kassalayouter med knappsatsdesigner](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) för att installera designern och uppdatera en kassalayout.

    1. Välj layout som ska uppdateras. 
    1. Lägg till en ny knapp och ange knappegenskapen **Skriv ut skatt X**.
    1. Lägg till en ny knapp och ange knappegenskapen **Skriv ut skatt Z**.
    1. På sidan **Distributionsschemaläggare** kör jobb **1090** för att överföra ändringar till kanaldatabasen.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Aktivera manuell körning av uppskjutna räkenskapsregistreringar

Om du vill aktivera manuell körning av en senarelagd räkenskapsregistrering bör du lägga till en ny knapp till en kassalayout.

- På sidan **knapprutnät**, följer du instruktionerna i [lägga till kassaåtgärder till kassalayouter med knappsatsdesigner](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) för att installera designern och uppdatera en kassalayout.

    1. Välj layout som ska uppdateras.
    1. Lägg till en ny knapp och ange knappegenskapen **Slutför räkenskapsregistreringsprocess**.
    1. På sidan **Distributionsschemaläggare** kör jobb **1090** för att överföra ändringar till kanaldatabasen.


## <a name="view-connection-parameters-and-other-information-in-pos"></a>Visa anslutningsparametrar och annan information i kassan

För att visa anslutningsparametrar och annan information i kassan, följ dessa steg.

1. Öppna Modern POS (MPOS) eller Cloud POS (CPOS).
1. Välj **inställningar**. Om skatteintegrering är aktiverad visas följande information i avsnittet **Räkenskapsintegrering** till höger:

    - Status för skatteregistrering
    - Tillståndet för den senaste skattetransaktionen
    - Antalet pågående granskningshändelser

1. Välj **Detaljer** om du vill visa följande information:

    - Steg för registreringsprocess
    - Anslutningsparametrar
    - Detaljer granskningshändelser
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
