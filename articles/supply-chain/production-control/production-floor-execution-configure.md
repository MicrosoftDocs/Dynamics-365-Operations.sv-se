---
title: Konfigurera körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du skapar en eller flera konfigurationer för körningsgränssnittet för produktionsgolvet. När du öppnar körningsgränssnittet för produktionsgolvet läser det automatiskt in ett valt konfigurations- och jobbfilter som är specifikt för webbläsaren och enheten. I konfigurationen ställer du in de principer som måste tillämpas för en viss användning.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cf58a7d851577854d08bad70cff69794c3841a2d
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012510"
---
# <a name="configure-the-production-floor-execution-interface"></a>Konfigurera körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Verkstadsarbetare använder körningsgränssnittet för produktionsgolvet för att registrera sitt dagliga arbete, till exempel när de börjar ett jobb, rapporterar feedback om jobb, registrerar indirekta aktiviteter och rapporterar frånvaro. Dessa registreringar är grunden för spårning av framsteg och kostnader på tillverkningsorder och för beräkning av grunden för arbetares lön.

När du öppnar körningsgränssnittet för produktionsgolvet läser det automatiskt in ett valt konfigurations- och jobbfilter som är specifikt för webbläsaren och enheten. I konfigurationen ställer du in de principer som måste tillämpas för en viss användning. Nedan följer några användningsexempel:

- På en enhet i företagsplatsen har medarbetarna stämplat in när de kommer in på kontoret och de stämplar ut när de går för dagen.
- På en enhet i verkstadsgolvet registreras maskinoperatörer när de startar och avslutar jobben. De registrerar också pauser och indirekta aktiviteter.

I det här avsnittet beskrivs olika alternativ för att konfigurera jobbkorts enheten.

## <a name="turn-on-new-features-in-feature-management"></a>Aktivera nya funktioner i funktionshantering

Några av de inställningar som beskrivs i det här avsnittet måste vara aktiverade på ditt system innan de blir tillgängliga för dig. Använd sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) om du vill aktivera någon av eller alla följande funktioner efter behov.

### <a name="generate-license-plate"></a>Generera registreringsskylt

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Aktivera automatisk generering av ID-nummer när rapportering slutförts i jobbkortenheten

### <a name="print-label"></a>Skriv ut etikett

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. ID-nummer för rapportering som färdig har lagts till på jobbkortenheten
1. Skriv ut etikett från jobbkortenhet

### <a name="allow-locking-the-touch-screen"></a>Tillåt låsning av pekskärm

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Förhandsversion) Funktion för att låsa jobbkortsenhet och jobbkortsterminal för att anpassas till språk

## <a name="work-with-production-floor-execution-configurations"></a>Arbeta med konfigurationer av körningsgränssnittet för produktionsgolvet

Om du vill skapa och underhålla enhetskonfigurationen går du till **Produktionskontroll \> Inställning \> Tillverkningskörning \> Konfigurera för produktionsgolvet**. På sidan **Konfigurera för produktionsgolvet** visas en lista över befintliga konfigurationer. På den här sidan kan du utföra följande åtgärder:

- Välj en konfiguration av produktionsgolvet som visas i den vänstra kolumnen om du vill visa och redigera den.
- Välj **ny** i åtgärdsfönstret om du vill lägga till en ny enhetskonfiguration i listan. Ange sedan ett namn i fältet **Konfiguration** för att identifiera den nya konfigurationen. Namnet som du anger här måste vara unikt bland alla enhetskonfigurationer och du kan inte redigera det senare.

Konfigurera sedan de olika inställningarna för den valda enhetskonfigurationen. Följande fält är tillgängliga:

- **Rapportera kvantitet vid utstämpling** – Ange detta alternativ till *Ja* för att be arbetare att rapportera återrapportering om pågående jobb när han eller hon stämplar ut. Om detta alternativ anges till *Nej* kommer medarbetarna inte att uppmanas.
- **Lås medarbetare** – när det här alternativet är inställt på *Nej* kommer arbetstagarna att loggas ut omedelbart efter att de har gjort en registrering (t.ex. ett nytt jobb). Enheten kommer sedan tillbaka till inloggningssidan. När det här alternativet är inställt på *Ja* kommer varje medarbetare att vara inloggad på jobbkortsenheten. En arbetare kan dock manuellt logga ut så att en annan arbetare kan logga in medan en jobbkortsenhet fortsätter att köras under samma systemanvändarkonto. Mer information om dessa typer av konton finns i [Tilldela användare](config-job-card-device.md#assigned-users).
- **Använd den faktiska tiden för registrering** – Ställ in detta alternativ på *Ja* att ställa in tiden för varje ny registrering till den exakta tidpunkt då arbetstagaren lämnade in registreringen. När alternativet är inställt på *Nej* , används inloggningstiden istället. Du vill vanligtvis ange alternativet till *Ja* om du anger **Lås medarbetare** och/eller **Enskild arbetare** till *Ja* i fall där arbetstagare ofta förblir inloggade under längre perioder.
- **En arbetare** – Ställ in det här alternativet på *Ja* om bara en av dem använder varje jobbkortsenhet där denna konfiguration är aktiv. När det här alternativet är inställt på *Ja* alternativet **Lås medarbetare** automatiskt till *Ja*. Dessutom tar den här inställningen bort kravet (och möjligheten) för arbetaren att logga in med hjälp av ID-bricka (eller liknande ID). Istället loggar medarbetaren in Microsoft Dynamics 365 Supply Chain Management genom att använda ett systemanvändarkonto som är länkat till en *tidsregistrerad arbetare* (från tabellen *arbetaren* ) och loggas in på jobbkortsenheten samtidigt som medarbetaren.
- **Tillåt låsning av pekskärm** – Ange detta alternativ till *Ja* medarbetare ska kunna låsa pekskärmen på jobbkortsenheten så att de kan sanera den. När det här alternativet är inställt på *Ja* läggs knappen **Låsskärm för sanering** läggs till på inloggningssidan för enheten. När en medarbetare väljer den här knappen, låser sig pekskärmen tillfälligt för att förhindra indata. En nedräkningstimer visas också. Arbetaren kan nu rensa enheten och skärmen på ett säkert sätt. När nedräkningen är klar låses pekskärmen upp automatiskt.
- **Tidslängd för skärmlåsning** – När alternativet **Tillåt låsning pekskärm** anges till *Ja* , använd det här alternativet för att ange antalet sekunder som pekskärmen ska vara låst för att desinficera. Längden måste vara mellan 5 och 120 sekunder.
- **Generera ID-nummer** – Ange det här alternativet *Ja* om du vill generera ett nytt ID-nummer varje gång en medarbetare använder jobbkortsenheten för att rapportera som färdig. ID-numret genereras från en nummerserie som ställs in på sidan **parametrar för lagerstyrning**. Om alternativet *Nej* måste arbetare ange ett befintligt ID-nummer när den rapporteras som färdig.
- **Skriv ut etikett** – Ställ in det här alternativet på *Ja* om du vill skriva ut ett ID-nummer när en medarbetare använder en jobbkortsenhet för att rapportera som färdig. Konfigurationen av etiketten ställs in i dokumentflödet som beskrivs i [Layout på dokumentflödet för ID-nummeretiketter](../warehousing/document-routing-layout-for-license-plates.md).

## <a name="clean-up-job-configurations"></a>Rensa jobbkonfigurationerna

När arbetsstyrningen ställer in gränssnittet för körningsgränssnittet för produktionsgolvet väljer de en konfiguration och ett jobbfilter. Dessa val lagras i en referenstabell i Supply Chain Management och webbläsaren använder ett ID som lagras i en lokal cookie för att hitta rätt rad i registret. I tabellen loggas också det datum och den tidpunkt då en arbetare som senast loggade in på varje enhet.

Ett batchjobb rensar regelbundet poster i referensregistret för enheter som inte har loggat någon aktivitet under de senaste 60 dagarna. Du kan också manuellt rensa posterna genom att följa stegen nedan.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.
1. I åtgärdsfönstret, välj **Rensa klientkonfigurationer**.
1. I dialogrutan **Rensa klientkonfigurationer** ange fältet **Antal dagar** av inaktivitet (före idag). Du tar bort alla konfigurationer och inloggningsposter för enheter som inte har varit aktiva under den tiden.
1. Välj **OK** om du vill rensa de relevanta konfigurationerna, baserat på **Antal dagar**.
