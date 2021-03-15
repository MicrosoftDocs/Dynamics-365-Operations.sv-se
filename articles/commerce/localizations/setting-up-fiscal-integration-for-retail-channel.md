---
title: Ställ in räkenskapsintegration för handelskanaler
description: Det här avsnittet ger riktlinjer för att skapa funktionen för räkenskapsintegration för handelskanaler.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 889340c13d150ce8e3ad49a08b3d7f0c25a4b77a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017903"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Ställ in räkenskapsintegration för handelskanaler

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduktion

Det här avsnittet ger riktlinjer för att skapa funktionen för räkenskapsintegration för handelskanaler. Mer information om räkenskapsintegration finns i [översikt över räkenskapsintegration för handelskanaler](fiscal-integration-for-retail-channel.md).

Processen för att ställa in räkenskapsintegration inkluderar följande uppgifter:

1. Konfigurera räkenskapskopplingar som representerar räkenskapsenheter eller tjänster som används för räkenskapsregistrering såsom kvittoskrivare.
2. Konfigurera dokumentleverantörer som skapar skattedokument som registreras i räkenskapsenheter eller tjänster av räkenskapskopplingar.
3. Konfigurera räkenskapsregistreringsprocessen som definierar en uppsättning steg i räkenskapsregistrering och räkenskapskopplingar och skattedokumentleverantörer som används för varje steg.
4. Tilldela räkenskapsregistreringsprocess till funktionsprofiler för kassa.
5. Tilldela koppling tekniska profiler till maskinvaruprofiler.

## <a name="set-up-a-fiscal-registration-process"></a>Ställa in process för räkenskapsregistrering

Innan du använder funktionen räkenskapsintegrering bör du konfigurera följande inställningar.

1. Uppdatera handelsparametrar.

    1. På sidan **gemensamma handelsparametrar** på fliken **allmänna** anger du alternativet till **aktivera räkenskapsintegration** till **Ja**. På fliken **Nummerserier** definierar du nummerserier för följande referenser:

        - Nummer för teknisk profil för räkenskaper
        - Gruppnummer för räkenskapskoppling
        - Nummer för registreringsprocess

    2. På sidan **Handelsparametrar** definierar du nummerserier för funktionell profilnummer för räkenskap.

    > [!NOTE]
    > Nummerserier är valfria. Numren för alla entiteter för räkenskapsintegration kan genereras från nummerserier eller manuellt.

2. Överför konfigurationer av räkenskapskopplingar och leverantörer av skattedokument.

    En leverantör av skattedokument ansvarar för generering av skattedokument som representerar transaktioner och händelser som har registrerats i POS i ett format som även används för interaktionen med en räkenskapsenhet eller tjänst. En leverantör av skattedokument kan generera en representation av en kvittoskrivare i XML-format.

    En räkenskapskoppling ansvarar för kommunikationen med en räkenskapsenhet eller tjänst. En räkenskapskoppling kan skicka en kvittoskrivare som en leverantör av skattedokument skapat i XML-format till en kvittoskrivare. Mer information om komponenter för räkenskapsintegration finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegration för kvittoskrivarenheter](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. På sidan **räkenskapskopplingar** (**Butik och handel \> Kanalinställning \> Räkenskapsintegration \> Räkenskapskopplingar**), ladda upp en XML-konfiguration för varje enhet eller tjänst som du tänker använda för räkenskapsintegration.

        > [!TIP]
        > Genom att markera **Visa**, kan du visa alla funktionella och tekniska profiler som är relaterade till aktuell räkenskapskoppling.

    2. På sidan **Leverantörer av skattedokument** (**Butik och handel \> Kanalinställning \> Räkenskapsintegration \> Leverantörer av skattedokument**), ladda upp en XML-konfiguration för varje enhet eller tjänst som du tänker använda.

        > [!TIP]
        > Genom att markera **Visa**, kan du visa alla funktionella profiler som är relaterade till aktuell leverantör av skattedokument.

    För exempel på konfigurationer av räkenskapskopplingar och leverantörer av skattedokument finns i [Exempel på räkenskapsintegration i Retail SDK](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > Datamappning betraktas som en del av skattedokumentleverantören. Om du vill ställa in olika datamappningar för samma typ av koppling (till exempel delstatsspecifika regler) bör du skapa olika leverantörer för skattedokument.

3. Skapa funktionella profiler för kopplingar profiler och tekniska profiler för kopplingar.

    1. På sidan **Funktionsprofiler för koppling** sida (**butik och handel \> kanalinställning \> räkenskapsintegration \> Funktionsprofiler för koppling**), skapa en funktionsprofil för koppling för varje kombination av en räkenskapskoppling och leverantör av skattedokument som är kopplad till den här räkenskapskopplingen.

        1. Välj namnet på en koppling.
        2. Välj en dokumentleverantör.

        Du kan ändra parametrarna för datamappning i en funktionsprofil för koppling. Återställ standardparametrar som är definierade i konfigurationen av leverantören av skattedokument, markera **uppdatering**.

        **Exempel**

        |   | Format | Exempel |
        |---|--------|---------|
        | **Inställning av momssatser** | värde: VATrate | 1 : 2000, 2 : 1800 |
        | **Mappning av momskoder** | VATcode : värde | vat20 : 1, vat18 : 2 |
        | **Mappning av betalningsmedelstyper** | TenderType : värde | Kontant: 1 kort: 2 |

        > [!NOTE]
        > Funktionsprofiler för koppling är företagsspecifika. Om du planerar att använda samma kombination av räkenskapskoppling och skattedokumentleverantör i olika företag, bör du skapa en funktionsprofil för koppling för varje företag.

    2. På sidan **Tekniska profiler för koppling** (**Butik och handel \> kanalinställning \> räkenskapsintegration \> teknisk profil för koppling**), skapa en funktionsprofil för koppling för varje räkenskapskoppling.

        1. Välj namnet på en koppling.
        2. Välj en kopplingstyp. För enheter som är anslutna till en maskinvarustation, välj **lokal**.

            > [!NOTE]
            > Endast lokala kopplingar stöds.

        Parametrarna på flikarna **enhet** och **inställningar** i en teknisk profil för koppling kan ändras. Återställ standardparametrar som är definierade i konfigurationen av räkenskapskoppling, markera **uppdatering**. När en ny version av en XML-konfiguration laddas får du ett meddelande om att aktuellt räkenskapskoppling eller leverantör av skattedokument används redan. Den här proceduren åsidosätter inte manuella ändringar som gjorts i tidigare funktionsprofiler för koppling och tekniska profiler för koppling. För att tillämpa standarduppsättningen med parametrar från en ny konfiguration, klicka på **uppdatering** på sidan **Funktionsprofiler för koppling** och **Uppdatera**.

4. Skapa grupper för räkenskapskoppling.

    En grupp för räkenskapskoppling kombinerar funktionella profiler med räkenskapskopplingar som utför identiska funktioner som används i samma fas inom en räkenskapsregistrering. Om flera kvittoskrivarmodeller kan användas i butik, räkenskapskopplingar för de kvittoskrivare kombineras i en grupp för räkenskapskoppling.

    1. På sidan **Grupp för räkenskapskoppling** (**Butik och handel \> kanalinställning \> räkenskapsintegration \> grupper för räkenskapskoppling**), skapa en ny grupp för räkenskapskoppling.
    2. Lägg till funktionella profiler till kopplingsgruppen. På sidan **Lägg till** på sidan **funktionella profiler** och välj ett profilnummer. Varje räkenskapskoppling i en kopplingsgrupp kan bara ha en funktionell profil.
    3. Om du vill skjuta upp användning av funktionella profilen, ange **inaktivera** till **Ja**. Denna ändring påverkar endast aktuella kopplingsgruppen. Du kan fortsätta att använda samma funktionella profil i andra kopplingsgrupper.

5. Skapa process för räkenskapsregistrering

    En process för räkenskapsregistrering definieras av ordningen på registreringsstegen och kopplingsgruppen som används i varje steg.

    1. På sidan **Process för räkenskapsregistrering** (**Butik och handel \> Kanalinställning \> räkenskapsintegration \> process för räkenskapsregistrering**), skapa en ny process för varje unik process i räkenskapsregistreringen.
    2. Lägg till registreringsteg i processen:

        1. Markera **Lägg till**.
        2. Välj en typ av räkenskapskoppling:
        3. I fältet **gruppnummer** väljer du en grupp för räkenskapskoppling.

6. Tilldela entiteter för räkenskapsregistreringsprocess till kassaprofiler.

    1. På sidan **Kassafunktionsprofiler** (**Butik och handel \> kanalinställningar \> kassainställningar \> kassaprofiler \> funktionsprofiler**), tilldela räkenskapsregistreringsprocessen till en kassafunktionsprofil. Välj **redigera** och klicka sedan på **Process för räkenskapsregistrering** i fältet **Processnummer** väljer du en process.
    2. På sidan **maskinvaruprofil för kassa** (**Butik och handel \> kanalinställning \> kassainställningar \> profiler för kassa \> maskinvaruprofiler**), tilldela tekniska profiler för kopplingar för en maskinvaruprofil. Välj **redigera** för att lägga till en rad på fliken **Kringutrustning för räkenskaper** på fliken och sedan, i **Profilnummer** väljer du en profil för koppling.

    > [!NOTE]
    > Du kan lägga till flera tekniska profiler till en maskinvaruprofil. En maskinvaruprofil eller kassafunktionalitetsprofil har dock endast en skärningspunkt med en grupp för räkenskapskoppling.

    Räkenskapsregistreringsflöde har definierats av räkenskapsregistreringsprocessen samt av vissa parametrar för räkenskapsintegrationskomponenterna: tillägget Commerce Runtime för leverantören av skattedokument och tillägg för maskinvarustation för räkenskapskopplingen.

    - Prenumeration på händelser och transaktioner till räkenskapsregistreringen är fördefinierade i leverantören av skattedokument.
    - Leverantören av skattedokument ansvarar för att identifiera räkenskapskopplingen som används för räkenskapsregistreringen. Den matchar kopplingens funktionella profiler som ingår i den grupp för räkenskapskoppling som har angetts för det aktuella steget för räkenskapsregistreringsprocessen med den tekniska profil för koppling som tilldelats maskinvaruprofilen för maskinvarustationen som POS är kopplad till.
    - Leverantören av skattedokument använder data från konfiguration av leverantör av skattedokument för att omvandla transaktionshändelsen/data såsom skatter och betalningar medan skattedokument genereras.
    - När leverantören av skattedokument genererar ett skattedokument kan räkenskapskopplingen antingen skicka den till räkenskapsenheten som den är, eller analysera den och omvandla den till en sekvens av kommandon i applikationsprogrammeringsgränssnittet (API) beroende på hur kommunikationen hanteras.

7. På sidan **Process för räkenskapsregistrering** (**Butik och handel \> Kanalinställning \> Räkenskapsintegration \> Process för räkenskapsregistrering**), välj **Validera** för att validera räkenskapsregistreringen.

    Vi rekommenderar att du använder den här typen av verifiering i följande fall:

    - När du har slutfört alla inställningar för en ny registreringsprocess, inklusive när du tilldelar registreringsprocesser till kassafunktionalitetsprofiler och hårdvaruprofiler.
    - När du har ändrat en befintlig räkenskapsregistreringsprocess, och de ändringar som kan göra att en annan räkenskapskontakt kan väljas vid körning (till exempel om du ändrar kontaktgruppen för ett räkenskapsregistreringsprocessteg, aktivera en funktionsprofil för koppling i en kopplingsgrupp eller lägg till en ny funktionsprofil för koppling till en kopplingsgrupp).
    - När du ändrar i tilldelningen av tekniska profiler för koppling till maskinvaruprofiler.

8. På sidan **Distributionsschema**, kör **1070** och **1090**-jobb för att överföra data till kanaldatabasen.

## <a name="set-up-fiscal-texts-for-discounts"></a>Ställ in räkenskapstexter för rabatter

I vissa fall kan måste en särskild text skrivas ut på en kvittoskrivare om en rabatt ska tillämpas. Du kan ställa in räkenskapstexter för rabatter på sidan **Grupp för räkenskapskoppling** (**Butik och handel \> kanalinställning \> räkenskapsintegration \> grupper för räkenskapskoppling**).

- För manuella rabatter som tillämpas i POS bör du konfigurera en räkenskapstext för den infokod eller infokodgrupp som anges som **produktrabatt**-infokod i funktionsprofil för kassa.

    1. På sidan **Grupp för räkenskapskoppling** anger du **Text för kvittoskrivaren**.
    2. På fliken **infokoder** väljer du **Lägg till** och välj en infokod eller infokodgrupp.
    3. I **Infokodnummer**, välj ett värde.
    4. I fältet **Delkodsnummer** väljer du ett värde om det krävs en delkod för valda infokoden.
    5. I fältet **Text för kvittoskrivare**, anger du en räkenskapstext som ska skrivas ut på en kvittoskrivare.
    6. Ange alternativet **Skriv ut användarens indata på kvittoskrivare** till **Ja** för att åsidosätta texten på en kvittoskrivare med information som användaren matar in manuellt i POS. Det här alternativet gäller bara för infokoder som har en indatatyp **Text**.

    > [!NOTE]
    > Du kan ange en räkenskapstext för flera infokoder för att stödja scenarier där infokodgrupper, länkade infokoder och utlösta infokoder används. I dessa fall innehåller kvittoskrivaren räkenskapstexter från alla infokoder som är kopplade till transaktionsraden där rabatten tillämpades.

- För kanalspecifika rabatter bör du definiera räkenskapstext för rabatt-ID.

    1. På sidan **Grupp för räkenskapskoppling** anger du **Text för kvittoskrivaren**.
    2. På fliken **rabatter**, välj **Lägg till**, och välj en rabatt-ID.
    3. I fältet **Text för kvittoskrivare**, anger du en räkenskapstext som ska skrivas ut på en kvittoskrivare.

    > [!NOTE]
    > Om flera rabatter tillämpas på samma transaktionsrad innehåller kvittoskrivaren räkenskapstexter från alla rabatter som är kopplade till transaktionsraden.

## <a name="set-error-handling-settings"></a>Ange inställningar för felhantering

Alternativ för felhantering som finns tillgängliga i räkenskapsintegration ställs in i processen för räkenskapsregistrering. Mer information om felhantering i räkenskapsintegration finns i [felhantering](fiscal-integration-for-retail-channel.md#error-handling).

1. På sidan **Process för räkenskapsregistrering** (**Butik och handel \> Kanalinställning \> räkenskapsintegration \> process för räkenskapsregistrering**), kan du ställa in följande parametrar för varje steg i processen för räkenskapsregistrering.

    - **Tillåt hoppa över** – den här parametern aktiverar alternativet **hoppa över** i dialogrutan för felhantering.
    - **Tillåt att markera som registrerad** – den här parametern aktiverar alternativet **Markera som registrerad** i dialogrutan för felhantering.
    - **Fortsätt vid fel** – om den här parametern är aktiverad kan räkenskapsregistreringen fortsätta på kassaregister om räkenskapsregistreringen av en transaktioner eller händelser misslyckas. Annars om du vill köra räkenskapsregistreringen av nästa transaktion eller händelse måste operatorn göra om den misslyckade räkenskapsregistreringen, hoppa över den eller markera transaktioner eller händelser som registrerats. Mer information finns i [Valfri räkenskapsregistrering](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Om parametern **Fortsätt vid fel** är aktiverad kan parametrarna **Tillåt hoppa över** och **Tillåt markera som registrerad** inaktiveras automatiskt.

2. Alternativen **Hoppa över** och **Markera som registrerad** kräver behörigheten **Tillåt hoppa över registrering eller markera som registrerade**. Därför på sidan **behörighetsgrupper** (**Butik och handel \> medarbetare \> behörighetsgrupper**), aktivera behörigheten **Tillåt hoppa över registrering eller markera som registrerad**.
3. Alternativen **hoppa över** och **markera som registrerad** låter operatörer ange ytterligare information när räkenskapsregistreringen misslyckas. Om du vill göra funktionen tillgänglig bör du ange infokoderna **hoppa över** och **markera som registrerad** på en grupp för räkenskapskoppling. Informationen som operatörer anger sparas som en infokodtransaktion som kopplas till räkenskapstransaktionen. Mer information om infokoder finns i [Infokoder och infokodgrupper](../info-codes-retail.md).

    > [!NOTE]
    > Utlösarfunktionen **produkt** stöds inte för infokoder som används för **hoppa över** och **markera som registrerad** i grupper för räkenskapskoppling.

    - På sidan **Grupp för räkenskapskoppling** på fliken **Infokoder** väljer du infokoder eller infokodgrupper i fälten **hoppa över** och **markera som registrerad**.

    > [!NOTE]
    > Ett skattedokument och ett icke skatte-dokument kan genereras på något steg i ett räkenskapsregistreringsprocessen. Tillägget för leverantör av skattedokument identifierar alla typer av transaktioner eller händelser som rör skatte- eller icke skattedokument. Funktionen för felhantering gäller endast skattedokument.
    >
    > - **Skattedokument** – ett obligatoriskt dokument som ska registreras korrekt (t.ex en kvittoskrivare).
    > - **Icke skattedokument** – ett kompletterande dokument för transaktionen eller händelsen (till exempel ett presentkortkvitto).

4. Om operatören ska kunna fortsätta att bearbeta aktuell åtgärd (till exempel skapa eller slutföra en transaktion) efter att ett hälsokontrollfel inträffar, bör du aktivera behörigheten **Tillåt hoppa över hälsokontrollfel** på sidan **Behörighetsgrupper** (**Butik och handel \> Medarbetare \> Behörighetsgrupper**). Mer information om hälsokontrollproceduren finns i [hälsokontroll av räkenskapsregistrering](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Ställ in räkenskapsrapporter X/Y från POS

För att aktivera räkenskapsrapporter X/Z att köras från POS, bör du lägga till nya knappar i kassalayouten.

- På sidan **knapprutnät**, följer du instruktionerna i [lägga till kassaåtgärder till kassalayouter med knappsatsdesigner](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) för att installera designern och uppdatera en kassalayout.

    1. Välj layout som ska uppdateras. 
    2. Lägg till en ny knapp och ange knappegenskapen **Skriv ut skatt X**.
    3. Lägg till en ny knapp och ange knappegenskapen **Skriv ut skatt Z**.
    4. På sidan **Distributionsschemaläggare** kör jobb **1090** för att överföra ändringar till kanaldatabasen.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Aktivera manuell körning av uppskjutna räkenskapsregistreringar

Om du vill aktivera manuell körning av en senarelagd räkenskapsregistrering bör du lägga till en ny knapp till en kassalayout.

- På sidan **knapprutnät**, följer du instruktionerna i [lägga till kassaåtgärder till kassalayouter med knappsatsdesigner](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) för att installera designern och uppdatera en kassalayout.

    1. Välj layout som ska uppdateras.
    2. Lägg till en ny knapp och ange knappegenskapen **Slutför räkenskapsregistreringsprocess**.
    3. På sidan **Distributionsschemaläggare** kör jobb **1090** för att överföra ändringar till kanaldatabasen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]