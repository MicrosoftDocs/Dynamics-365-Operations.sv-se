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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c1739c9b50cb3f09696bf95730cd62fc9960ed5d
ms.sourcegitcommit: 908a85987b604a7782407da70fb70ef75c07989f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/19/2021
ms.locfileid: "6641090"
---
# <a name="configure-the-production-floor-execution-interface"></a>Konfigurera körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Verkstadsarbetare använder körningsgränssnittet för produktionsgolvet för att registrera sitt dagliga arbete, till exempel när de börjar ett jobb, rapporterar feedback om jobb, registrerar indirekta aktiviteter och rapporterar frånvaro. Dessa registreringar är grunden för spårning av framsteg och kostnader på tillverkningsorder och för beräkning av grunden för arbetares lön.

När du öppnar körningsgränssnittet för produktionsgolvet läser det automatiskt in ett valt konfigurations- och jobbfilter som är specifikt för webbläsaren och enheten. I konfigurationen ställer du in de principer som måste tillämpas för en viss användning. Nedan följer några användningsexempel:

- På en enhet i företagsplatsen har medarbetarna stämplat in när de kommer in på kontoret och de stämplar ut när de går för dagen.
- På en enhet i verkstadsgolvet registreras maskinoperatörer när de startar och avslutar jobben. De registrerar också pauser och indirekta aktiviteter.

I det här avsnittet beskrivs olika alternativ för att konfigurera jobbkorts enheten.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Aktivera gränssnittet för körning av produktionsstyrningen och tillhörande valfria funktioner

Själva gränssnittet för körning av produktionsstyrningen, plus flera av de valfria inställningar som beskrivs i det här avsnittet, måste aktiveras i systemet innan du kan använda dem. Använd sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) om du vill aktivera någon av eller alla funktioner som beskrivs i följande underavsnitt efter behov.

### <a name="the-production-floor-execution-interface"></a>Körningsgränssnittet för produktionsgolvet

Detta är den primära funktionen som beskrivs i detta ämne. Det lägger till körningsgränssnittet för produktionsgolvet till ditt system. Aktivera följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Körning av produktionsgolvet

### <a name="generate-license-plates"></a>Generera registreringsskyltar

Dessa funktioner gör funktionen för registreringsskyltar tillgänglig för körningsgränssnittet för produktionsgolvet. Om du vill använda dem aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten

### <a name="print-labels"></a>Skriv ut etiketter

Dessa funktioner gör funktionen för utskrift av etiketter tillgänglig för körningsgränssnittet för produktionsgolvet. Om du vill använda dem aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Skriv ut etikett från jobbkortenhet

### <a name="allow-locking-the-touch-screen"></a>Tillåt låsning av pekskärm

Den här funktionen lägger till en knapp i körningsgränssnittet för produktionsgolvet som gör att arbetare kan använda den för att sanera pekskärmen. Om du vill använda den aktiverar du följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Funktion för att låsa jobbkortsenhet och jobbkortsterminal för att anpassas till språk

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funktionen för tillgångshantering för körningsgränssnittet för produktionsgolvet

Den här funktionen lägger till en flik för tillgångshantering i produktionsstyrningsgränssnittet. Arbetare kan använda den här fliken för att välja en tillgång som är ansluten till en maskinresurs inom det valda filtret för jobblistan. För den valda maskintillgången kan arbetaren visa status och tillstånd för tillgången från räknarvärden i upp till fyra valda räknare. Om du vill använda denna funktion aktiverar du följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Funktionen för tillgångshantering för körningsgränssnittet för produktionsgolvet

### <a name="enable-job-search"></a>Aktivera jobbsökning

Med denna funktion går det att lägga till ett sökfält i jobblistan. En arbetare kan hitta ett visst jobb genom att ange jobb-ID eller söka efter alla jobb för en viss order genom att ange order-ID:t. Arbetare kan ange ID:t med hjälp av ett tangentbord eller genom att skanna en streckkod. Om du vill använda den aktiverar du följande funktion i för att aktivera den [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Jobbsökning för produktionsgolvets körningsgränssnitt

## <a name="work-with-production-floor-execution-configurations"></a>Arbeta med konfigurationer av körningsgränssnittet för produktionsgolvet

Om du vill skapa och underhålla enhetskonfigurationen går du till **Produktionskontroll \> Inställning \> Tillverkningskörning \> Konfigurera för produktionsgolvet**. På sidan **Konfigurera för produktionsgolvet** visas en lista över befintliga konfigurationer. På den här sidan kan du utföra följande åtgärder:

- Välj en konfiguration av produktionsgolvet som visas i den vänstra kolumnen om du vill visa och redigera den.
- Välj **ny** i åtgärdsfönstret om du vill lägga till en ny enhetskonfiguration i listan. Ange sedan ett namn i fältet **Konfiguration** för att identifiera den nya konfigurationen. Namnet som du anger här måste vara unikt bland alla enhetskonfigurationer och du kan inte redigera det senare.

Konfigurera sedan de olika inställningarna för den valda enhetskonfigurationen. Följande fält är tillgängliga:

- **Clock in and out only** - Ange det här alternativet *Ja* för att skapa ett förenklat gränssnitt som bara ger in- och urklockningsfunktionalitet. Då inaktiveras de flesta andra alternativ på den här sidan. Du måste ta bort alla rader från snabbflikarna **Flikmarkering** innan du kan aktivera det här alternativet.
- **Aktivera sökning** - Ange detta alternativ till *Ja* om du vill inkludera ett sökfält i jobblistan. En arbetare kan hitta ett visst jobb genom att ange jobb-ID eller söka efter alla jobb för en viss order genom att ange order-ID:t. Arbetare kan ange ID:t med hjälp av ett tangentbord eller genom att skanna en streckkod.
- **Rapportera kvantitet vid utstämpling** – Ange detta alternativ till *Ja* för att be arbetare att rapportera återrapportering om pågående jobb när han eller hon stämplar ut. Om detta alternativ anges till *Nej* kommer medarbetarna inte att uppmanas.
- **Lås medarbetare** – när det här alternativet är inställt på *Nej* kommer arbetstagarna att loggas ut omedelbart efter att de har gjort en registrering (t.ex. ett nytt jobb). Enheten kommer sedan tillbaka till inloggningssidan. När det här alternativet är inställt på *Ja* kommer varje medarbetare att vara inloggad på jobbkortsenheten. En arbetare kan dock manuellt logga ut så att en annan arbetare kan logga in medan en jobbkortsenhet fortsätter att köras under samma systemanvändarkonto. Mer information om dessa typer av konton finns i [Tilldela användare](config-job-card-device.md#assigned-users).
- **Använd den faktiska tiden för registrering** – Ställ in detta alternativ på *Ja* att ställa in tiden för varje ny registrering till den exakta tidpunkt då arbetstagaren lämnade in registreringen. När alternativet är inställt på *Nej*, används inloggningstiden istället. Du vill vanligtvis ange alternativet till *Ja* om du anger **Lås medarbetare** och/eller **Enskild arbetare** till *Ja* i fall där arbetstagare ofta förblir inloggade under längre perioder.
- **En arbetare** – Ställ in det här alternativet på *Ja* om bara en av dem använder varje jobbkortsenhet där denna konfiguration är aktiv. När det här alternativet är inställt på *Ja* alternativet **Lås medarbetare** automatiskt till *Ja*. Dessutom tar den här inställningen bort kravet (och möjligheten) för arbetaren att logga in med hjälp av ID-bricka (eller liknande ID). Istället loggar medarbetaren in Microsoft Dynamics 365 Supply Chain Management genom att använda ett systemanvändarkonto som är länkat till en *tidsregistrerad arbetare* (från tabellen *arbetaren*) och loggas in på jobbkortsenheten samtidigt som medarbetaren.
- **Tillåt låsning av pekskärm** – Ange detta alternativ till *Ja* medarbetare ska kunna låsa pekskärmen på jobbkortsenheten så att de kan sanera den. När det här alternativet är inställt på *Ja* läggs knappen **Låsskärm för sanering** läggs till på inloggningssidan för enheten. När en medarbetare väljer den här knappen, låser sig pekskärmen tillfälligt för att förhindra indata. En nedräkningstimer visas också. Arbetaren kan nu rensa enheten och skärmen på ett säkert sätt. När nedräkningen är klar låses pekskärmen upp automatiskt.
- **Tidslängd för skärmlåsning** – När alternativet **Tillåt låsning pekskärm** anges till *Ja*, använd det här alternativet för att ange antalet sekunder som pekskärmen ska vara låst för att desinficera. Längden måste vara mellan 5 och 120 sekunder.
- **Generera ID-nummer** – Ange det här alternativet *Ja* om du vill generera ett nytt ID-nummer varje gång en medarbetare använder jobbkortsenheten för att rapportera som färdig. ID-numret genereras från en nummerserie som ställs in på sidan **parametrar för Warehouse management**. Om alternativet *Nej* måste arbetare ange ett befintligt ID-nummer när den rapporteras som färdig.
- **Skriv ut etikett** – Ställ in det här alternativet på *Ja* om du vill skriva ut ett ID-nummer när en medarbetare använder en jobbkortsenhet för att rapportera som färdig. Konfigurationen av etiketten ställs in i dokumentflödet som beskrivs i [Layout på dokumentflödet för ID-nummeretiketter](../warehousing/document-routing-layout-for-license-plates.md).
- **Val av flik** – Använd inställningarna i det här avsnittet om du vill välja vilka flikar som ska visas av körningsgränssnittet för produktionsgolvet när den aktuella konfigurationen är aktiv. Du kan utforma så många flikar du behöver och sedan lägga till och ordna dem efter behov. Mer information om hur du utformar flikar och arbetar med inställningarna här finns i [utforma körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Rensa jobbkonfigurationerna

När arbetsstyrningen ställer in gränssnittet för körningsgränssnittet för produktionsgolvet väljer de en konfiguration och ett jobbfilter. Dessa val lagras i en referenstabell i Supply Chain Management och webbläsaren använder ett ID som lagras i en lokal cookie för att hitta rätt rad i registret. I tabellen loggas också det datum och den tidpunkt då en arbetare som senast loggade in på varje enhet.

Ett batchjobb rensar regelbundet poster i referensregistret för enheter som inte har loggat någon aktivitet under de senaste 60 dagarna. Du kan också manuellt rensa posterna genom att följa stegen nedan.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.
1. I åtgärdsfönstret, välj **Rensa klientkonfigurationer**.
1. I dialogrutan **Rensa klientkonfigurationer** ange fältet **Antal dagar** av inaktivitet (före idag). Du tar bort alla konfigurationer och inloggningsposter för enheter som inte har varit aktiva under den tiden.
1. Välj **OK** om du vill rensa de relevanta konfigurationerna, baserat på **Antal dagar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
