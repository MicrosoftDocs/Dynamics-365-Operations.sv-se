---
title: Konfigurera körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du skapar en eller flera konfigurationer för körningsgränssnittet för produktionsgolvet. När du öppnar körningsgränssnittet för produktionsgolvet läser det automatiskt in ett valt konfigurations- och jobbfilter som är specifikt för webbläsaren och enheten. I konfigurationen ställer du in de principer som måste tillämpas för en viss användning.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 083f5a30323cdc813116af7462563c3b8dd5e4f5
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644409"
---
# <a name="configure-the-production-floor-execution-interface"></a>Konfigurera körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Verkstadsarbetare använder körningsgränssnittet för produktionsgolvet för att registrera sitt dagliga arbete, till exempel när de börjar ett jobb, rapporterar feedback om jobb, registrerar indirekta aktiviteter och rapporterar frånvaro. Dessa registreringar är grunden för spårning av framsteg och kostnader på tillverkningsorder och för beräkning av grunden för arbetares lön.

När du öppnar körningsgränssnittet för produktionsgolvet läser det automatiskt in ett valt konfigurations- och jobbfilter som är specifikt för webbläsaren och enheten. I konfigurationen ställer du in de principer som måste tillämpas för en viss användning. Nedan följer några användningsexempel:

- På en enhet i företagsplatsen har medarbetarna stämplat in när de kommer in på kontoret och de stämplar ut när de går för dagen.
- På en enhet i verkstadsgolvet registreras maskinoperatörer när de startar och avslutar jobben. De registrerar också pauser och indirekta aktiviteter.

Det här avsnittet beskriver de olika alternativen för att konfigurera ett gränssnitt för produktionsgolv för varje enhet som används på din plats.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Aktivera gränssnittet för körning av produktionsstyrningen och tillhörande valfria funktioner

Själva gränssnittet för körning av produktionsstyrningen, plus flera av de valfria inställningar som beskrivs i det här avsnittet, måste aktiveras i systemet innan du kan använda dem. Använd sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) om du vill aktivera någon av eller alla funktioner som beskrivs i följande underavsnitt efter behov.

### <a name="the-production-floor-execution-interface"></a>Körningsgränssnittet för produktionsgolvet

Detta är den primära funktion som beskrivs i det här avsnittet och är en förutsättning för alla andra funktioner som nämns i det här avsnittet. Från och med version 10.0.25 av Supply Chain Management är obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Produktionsgolvskörning* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Generera registreringsskyltar

Dessa funktioner gör funktionen för registreringsskyltar tillgänglig för körningsgränssnittet för produktionsgolvet. Om du vill använda dem aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. *ID-nummer för rapportering som färdig har lagts till på jobbkortenheten*<br>(Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)
1. *Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)

### <a name="print-labels"></a>Skriv ut etiketter

Dessa funktioner gör funktionen för utskrift av etiketter tillgänglig för körningsgränssnittet för produktionsgolvet. Om du vill använda dem aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. *ID-nummer för rapportering som färdig har lagts till på jobbkortenheten*<br>(Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)
1. *Skriv ut etikett från jobbkortenhet*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk.)

### <a name="allow-locking-the-touch-screen"></a>Tillåt låsning av pekskärm

Med denna funktion går det att tillåta arbetare att låsa den så att de kan sanisera den.

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version äldre än 10.0.25 kan administratörer aktivera eller inaktivera denna funktion genom att söka efter *Funktion för att låsa jobbkortsenhet och jobbkortsterminal så att de kan rensas* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funktionen för tillgångshantering för körningsgränssnittet för produktionsgolvet

Den här funktionen lägger till en flik för tillgångshantering i produktionsstyrningsgränssnittet. Arbetare kan använda den här fliken för att välja en tillgång som är ansluten till en maskinresurs inom det valda filtret för jobblistan. För den valda maskintillgången kan arbetaren visa status och tillstånd för tillgången från räknarvärden i upp till fyra valda räknare. Om du vill använda denna funktion aktiverar du följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Funktionen för tillgångshantering för körningsgränssnittet för produktionsgolvet*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard.)

### <a name="enable-job-search"></a>Aktivera jobbsökning

Med denna funktion går det att lägga till ett sökfält i jobblistan. En arbetare kan hitta ett visst jobb genom att ange jobb-ID eller söka efter alla jobb för en viss order genom att ange order-ID:t. Arbetare kan ange ID:t med hjälp av ett tangentbord eller genom att skanna en streckkod. Om du vill använda den aktiverar du följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Jobbsökning för produktionsgolvets körningsgränssnitt*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard.)

### <a name="enable-reporting-on-co-products-and-by-products"></a>Aktivera rapportering av samprodukter och biprodukter

Den här funktionen låter arbetare använda gränssnittet för exekvering av produktionsgolvet för att rapportera framsteg på batchorder. Denna rapportering inkluderar rapportering om biprodukter och biprodukter. För att använda den här funktionen, aktivera följande funktion i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Rapport om sam- och biprodukter från produktionsgolvets körningsgränssnitt*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>Aktivera visning av fullständiga serie-, batch- och ID-nummer

Funktionen ger en förbättrad upplevelse av att visa listor med serie-, batch- och ID-nummer i gränssnittet för körning på produktionsgolv. Visningen ändras från en kortvy som anger ett begränsat antal tecken till en listvy som har tillräckligt utrymme för att visa de fullständiga värdena. Du kan också söka efter särskilda nummer i listan.

Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Administratrörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Visa fullständigt serie-, batch- och ID-nummer i körningsgränssnittet för produktionsgolv* i arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) .

### <a name="enable-registering-of-material-consumption"></a>Aktivera registrering av materialförbrukning

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Med denna funktion kan arbetare använda gränssnittet för produktionsgolvkörning för att registrera materialförbrukning, batchnummer och serienummer. Vissa tillverkare, särskilt de som finns i bearbetningsindustrier, måste explicit registrera hur mycket material som förbrukas för varje batch eller tillverkningsorder. Medarbetare kan till exempel använda en våg för att väga hur mycket material som förbrukas medan de arbetar. För att garantera fullständig spårbarhet av material måste dessa organisationer också registrera vilka batchnummer som förbrukades när varje produkt produceras.

Det finns två versioner av denna funktion. Den ena stöder artiklar som *inte* aktiverats för att använda avancerade lagerställeprocesser (WMS). Den andra stöder artiklar som *är* aktiverade för att använda WMS. Om du vill använda den här funktionen ska du aktivera en av eller båda följande funktioner i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (i den här ordningen), beroende på om du har artiklar som är aktiverade för WMS:

- *(Förhandsversion) Registrera materialförbrukning i körningsgränssnittet för produktionsgolv (inte WMS)*
- *(Förhandsversion) Registrera materialförbrukning i körningsgränssnittet för produktionsgolvet (WMS-aktiverat)*

> [!IMPORTANT]
> Du kan använda enbart versionen utan WMS. Om du använder WMS måste du emellertid aktivera båda funktioner.

### <a name="enable-reporting-on-catch-weight-items"></a>Aktivera rapportering av artiklar med nominell vikt

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Medarbetare kan använda gränssnittet för exekvering av produktionsgolvet för att rapportera framsteg rörande batchorder för artiklar med nominell vikt. Batchorder skapas från formler, vilkar kan definieras så att de har artiklar med nominell vikt som formelartiklar, samprodukter och biprodukter. En formel kan också definieras till att ha formelrader för ingredienser som är definierade för nominell vikt. Artiklar med nominell vikt använder två måttenheter för att spåra lager: nominell viktkvantitet och lagerkvantitet. Inom till exempel livsmedelsindustrin kan förpackat kött definieras som en nominell viktartikel, där den nominella viktkvantiteten används för att spåra antalet kartonger och lagerkvantiteten används för att spåra kartongerna.

För att använda den här funktionen, aktivera följande funktion i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *(Förhandsversion) Rapport med fångstviktartiklar från körningsgränssnittet för produktionsgolvet*

### <a name="enable-the-my-day-dialog"></a>Aktivera dialogrutan "Min dag"

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

I dialogrutan **Min dag** får medarbetare en översikt över sina dagliga registreringar och aktuella saldon för betald tid, betald övertid, frånvaro och betald frånvaro.

För att använda den här funktionen, aktivera följande funktion i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Vyn Min dag i körningsgränssnittet för produktionsgolvet*

### <a name="enable-teams"></a>Aktivera team

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

När flera arbetare tilldelas samma produktionsjobb kan de ingå i ett team. Teamet kan utnämna en arbetare till ledare. De återstående arbetarna blir automatiskt medhjälpare till ledare. För det resulterande teamet måste bara ledaren registrera jobbstatus. Tidsposter gäller för alla gruppmedlemmar.

För att använda den här funktionen, aktivera följande funktion i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Produktionsteam i körningsgränssnittet för produktionsgolvet*

### <a name="enable-additional-configuration-in-the-production-floor-execution-interface"></a>Aktivera ytterligare konfiguration i körningsgränssnittet för produktionsgolvet

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

Den här funktionen lägger till inställningar för följande funktioner på sidan **Konfigurera körning på produktionsgolv**:

- Öppna dialogrutan **Startjobb** automatiskt när en sökning har slutförts.
- Öppna dialogrutan **Rapportförlopp** automatiskt när en sökning har slutförts.
- Förfyllning av resterande kvantitet i dialogrutan **Rapportförlopp**.
- Aktivera materialförbrukningsjusteringar från dialogrutan **Rapportförlopp**. (För denna funktion krävs även *Registrera materialförbrukning i gränssnittet för produktionsgolvskörning (ej WMS)* .)
- Aktivera sökning med projekt-ID.

Information om hur du använder inställningarna finns senare i det här avsnittet.

För att använda den här funktionen, aktivera följande funktion i [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Ytterligare konfiguration i körningsgränssnittet för produktionsgolvet*


## <a name="work-with-production-floor-execution-configurations"></a>Arbeta med konfigurationer av körningsgränssnittet för produktionsgolvet

Om du vill skapa och underhålla konfigurationer av körning på produktionsgolv går du till **Produktionskontroll \> Inställning \> Tillverkningskörning \> Konfigurera för produktionsgolvet**. På sidan **Konfigurera för produktionsgolvet** visas en lista över befintliga konfigurationer. På den här sidan kan du utföra följande åtgärder:

- Välj en konfiguration av produktionsgolvet som visas i den vänstra kolumnen om du vill visa och redigera den.
- På åtgärdsfönstret, välj **Ny** för att lägga till en ny konfiguration i listan. Ange sedan ett namn i fältet **Konfiguration** för att identifiera den nya konfigurationen. Namnet som du anger här måste vara unikt bland alla konfigurationer och du kan inte redigera det senare. I fält **Beskrivning** kan du valfritt ange en beskrivning av konfigurationen.

Sedan konfigurerar du de olika inställningarna för den valda konfigurationen, enligt beskrivningen i följande delgrupper.

### <a name="the-general-fasttab"></a>Allmänt snabbfliken

Följande inställningar finns på snabbfliken **Allmänt**.

- **Endast för in- och utstämpling** – Ange det här alternativet *Ja* för att skapa ett förenklat gränssnitt som bara ger in- och urklockningsfunktionalitet. Då inaktiveras de flesta andra alternativ på den här sidan. Du måste ta bort alla rader från snabbflikarna **Flikmarkering** innan du kan aktivera det här alternativet.
- **Aktivera sökning** – Ange detta alternativ till *Ja* om du vill inkludera ett sökfält i jobblistan. En arbetare kan hitta ett visst jobb genom att ange jobb-ID eller söka efter alla jobb för en viss order genom att ange order-ID:t. Arbetare kan ange ID:t med hjälp av ett tangentbord eller genom att skanna en streckkod.
- **Aktivera sökning efter projekt-ID** – Ange det här alternativet till *Ja*, så att arbetare kan söka efter projekt-ID (utöver jobb-ID och order-ID) i sökfältet i körningsgränssnittet för produktionsgolvet. Du kan ange det här alternativet till *Ja* endast om alternativet **Aktivera sökning** är inställt på *Ja*.
- **Öppna dialogrutan Starta automatiskt** – När detta alternativet är inställt på *Ja*, dialogrutan **Startjobb** öppnas automatiskt när arbetare använder sökfältet för att hitta ett jobb.
- **Öppna dialogrutan Rapportförlopp automatiskt** – När detta alternativet är inställt på *Ja*, dialogrutan **Rapportförlopp** öppnas automatiskt när arbetare använder sökfältet för att hitta ett jobb.
- **Aktivera justering av material** – Ställ in det här alternativet till *Ja* för att aktivera knappen **Justera material** i dialogrutan **Rapportförlopp**. Arbetare kan välja den här knappen för att justera materialförbrukningen för jobbet.
- **Rapportera kvantitet vid utstämpling** – Ange detta alternativ till *Ja* för att be arbetare att rapportera återrapportering om pågående jobb när han eller hon stämplar ut. Om detta alternativ anges till *Nej* kommer medarbetarna inte att uppmanas.
- **Lås medarbetare** – när det här alternativet är inställt på *Nej* kommer arbetstagarna att loggas ut omedelbart efter att de har gjort en registrering (t.ex. ett nytt jobb). Gränssnittet kommer sedan tillbaka till inloggningssidan. När det här alternativet är inställt på *Ja* kommer varje medarbetare att vara inloggad på körningsgränssnittet för produktionsgolvet. En arbetare kan dock manuellt logga ut så att en annan arbetare kan logga in medan ett körningsgränssnitt för produktionsgolvet fortsätter att köras under samma systemanvändarkonto. Mer information om dessa typer av konton finns i [Tilldela användare](config-job-card-device.md#assigned-users).
- **Använd den faktiska tiden för registrering** – Ställ in detta alternativ på *Ja* att ställa in tiden för varje ny registrering till den exakta tidpunkt då arbetstagaren lämnade in registreringen. När alternativet är inställt på *Nej*, används inloggningstiden istället. Du vill vanligtvis ange alternativet till *Ja* om du anger **Lås medarbetare** och/eller **Enskild arbetare** till *Ja* i fall där arbetstagare ofta förblir inloggade under längre perioder.
- **En arbetare** – Ställ in det här alternativet på *Ja* om bara en av dem använder varje körningsgränssnitt för produktionsgolvet där denna konfiguration är aktiv. När det här alternativet är inställt på *Ja* alternativet **Lås medarbetare** automatiskt till *Ja*. Dessutom tar den här inställningen bort kravet (och möjligheten) för arbetaren att logga in med hjälp av ID-bricka (eller liknande ID). Istället loggar medarbetaren in Microsoft Dynamics 365 Supply Chain Management genom att använda ett systemanvändarkonto som är länkat till en *tidsregistrerad arbetare* (från tabellen *arbetaren*) och loggas in på körningsgränssnittet för produktionsgolvet samtidigt som medarbetaren.
- **Tillåt låsning av pekskärm** – Ange detta alternativ till *Ja* medarbetare ska kunna låsa pekskärmen på körningsgränssnittet för produktionsgolvet så att de kan sanera den. När det här alternativet är inställt på *Ja* läggs knappen **Låsskärm för sanering** läggs till på inloggningssidan. När en medarbetare väljer den här knappen, låser sig pekskärmen tillfälligt för att förhindra indata. En nedräkningstimer visas också. Arbetaren kan nu rensa enheten och skärmen på ett säkert sätt. När nedräkningen är klar låses pekskärmen upp automatiskt.
- **Tidslängd för skärmlåsning** – När alternativet **Tillåt låsning pekskärm** anges till *Ja*, använd det här alternativet för att ange antalet sekunder som pekskärmen ska vara låst för att desinficera. Längden måste vara mellan 5 och 120 sekunder.
- **Generera ID-nummer** – Ange det här alternativet *Ja* om du vill generera ett nytt ID-nummer varje gång en medarbetare använder körningsgränssnittet för produktionsgolvet för att rapportera som färdig. ID-numret genereras från en nummerserie som ställs in på sidan **parametrar för Warehouse management**. Om alternativet *Nej* måste arbetare ange ett befintligt ID-nummer när den rapporteras som färdig.
- **Skriv ut etikett** – Ställ in det här alternativet på *Ja* om du vill skriva ut ett ID-nummer när en medarbetare använder ett körningsgränssnitt för produktionsgolvet för att rapportera som färdig. Konfigurationen av etiketten ställs in i dokumentflödet som beskrivs i [Layout på dokumentflödet för ID-nummeretiketter](../warehousing/document-routing-layout-for-license-plates.md).

### <a name="the-tab-selection-fasttab"></a>Snabbfliken Flikval

Använd inställningarna på snabbfliken **Flikval** för att välja vilka flikar som produktionsgolvets gränssnitt ska visa när den aktuella konfigurationen är aktiv. Du kan utforma så många flikar du behöver och sedan lägga till och ordna dem enligt dina behov med hjälp av knapparna i snabbfliksverktygsfältet. Mer information om hur du utformar flikar och arbetar med inställningarna här finns i [utforma körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md).

### <a name="the-report-progress-fasttab"></a>Snabbflikarna Rapportförloppet

Följande inställningar finns på snabbfliken **Rapportförlopp**.

- **Aktivera justering av material** – Ställ in det här alternativet till *Ja* för att inkludera knappen **Justera material** i dialogrutan **Rapportförlopp**. Arbetare kan välja den här knappen för att justera materialförbrukningen för jobbet.
- **Standard för återstående kvantitet** – Ange alternativet *Ja* för att fylla i den förväntade återstående kvantiteten för ett produktionsjobb i dialogrutan **Rapportförlopp**.

## <a name="clean-up-job-configurations"></a>Rensa jobbkonfigurationerna

När arbetsstyrningen ställer in gränssnittet för körningsgränssnittet för produktionsgolvet väljer de en konfiguration och ett jobbfilter. Dessa val lagras i en referenstabell i Supply Chain Management och webbläsaren använder ett ID som lagras i en lokal cookie för att hitta rätt rad i registret. I tabellen loggas också det datum och den tidpunkt då en arbetare som senast loggade in på varje enhet.

Ett batchjobb rensar regelbundet poster i referensregistret för enheter som inte har loggat någon aktivitet under de senaste 60 dagarna. Du kan också manuellt rensa posterna genom att följa stegen nedan.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.
1. I åtgärdsfönstret, välj **Rensa klientkonfigurationer**.
1. I dialogrutan **Rensa klientkonfigurationer** ange fältet **Antal dagar** av inaktivitet (före idag). Du tar bort alla konfigurationer och inloggningsposter för enheter som inte har varit aktiva under den tiden.
1. Välj **OK** om du vill rensa de relevanta konfigurationerna, baserat på **Antal dagar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
