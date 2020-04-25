---
title: Produktionsparametrar i Tillverkningskörning
description: Det här avsnittet innehåller information om inställningar av produktionsparametrar i Tillverkningskörning.
author: johanhoffmann
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e4d459fb516cca3825c0a1871797f83df4c1a7c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212536"
---
# <a name="production-parameters-in-manufacturing-execution"></a>Produktionsparametrar i Tillverkningskörning

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om inställningar av produktionsparametrar i Tillverkningskörning.

Modulen **Tillverkningskörning** är främst avsedd att användas av tillverkningsföretag. Den kan användas för att registrera tid och artikelförbrukning för produktionsjobb eller projekt. Innan du börjar använda Tillverkningskörning för jobbregistreringar måste du ställa in olika produktionsparametrar som definierar hur och när registreringar bokförs under produktionsprocessen. Inställningar av produktionsparametrar påverkar lagerhantering, produktionshantering och kostnadsberäkning.

Överväg noga alla inställningar på sidan **Produktionsparametrar** innan arbetare börjar göra registreringar på produktionsjobb. Klicka på **Produktionsstyrning** &gt; **Inställningar** &gt; **Tillverkningskörning** &gt; **Standarder för produktionsorder**. Om ditt företag använder multisitefunktionen kanske du vill ställa in olika produktionsparametrar för varje webbplats. Parametrarna för integration med modulen **Produktion** ställs in på följande flikar på sidan **Produktionsparametrar**.

- **Allmänt** – Allmänna parameterinställningar för produktionsjobb i Tillverkningskörning.
- **Start** – Parametrar som används när produktionsoperationer startar.
- **Operationer** – Parametrar som används för produktionsoperationer och återrapportering om operationer under produktionsprocessen.
- **Rapportera som färdigt** – Parametrar som används när artiklar rapporteras som färdiga i den sista operationen i en tillverkningsorder.
- **Kvantitetvalidering** – Parametrar som används för att validera start- och återrapporterade kvantiteter på produktionsorder.

## <a name="types-of-production-jobs"></a>Typer av produktionsjobb
På fliken **Operationer** väljer du vilken typ av produktionsjobb som måste registreras på sidan **Jobbregistrering**.

Vanligtvis gör anställda registreringar på inställningsjobb och processjobb. Om finplanering används kan du välja andra jobbtyper som arbetare måste göra registreringar på när en produktionsorder bearbetas. Du kan till exempel kräva registreringar på transportjobb.

> [!IMPORTANT]
> Se till att alla relevanta jobbtyper väljs. Annars kan inte jobb registreras på sidan **Jobbregistrering**. Inställningarna bör matcha valen i kolumnen **Jobbhantering** på fliken **Inställningar** för sidan **Flödesgrupper** (**Produktionskontroll** &gt; **Inställningar** &gt; **Flöden** &gt; **Flödesgrupper**).

Om **Jobbhantering** väljs för en viss jobbtyp i flödesgruppen, rapporteras det här jobbet som färdigt på tillverkningsordern när jobbet rapporteras som färdigt i Tillverkningskörning. När alla jobbtyper som **Jobbhantering** väljs för har rapporterats som färdiga på en operation kommer Tillverkningskörning att rapportera operationen som färdig.

> [!NOTE]
> Vissa jobbtyper kan rapporteras manuellt via produktionsjournaler. I det här fallet väljer du **Jobbhantering** för jobbtypen, men väljer inte jobbtypen för registrering på fliken **Operationer** på sidan **Produktionsparametrar** i Tillverkningskörning.

## <a name="bom-consumption-and-picking-list-journals"></a>Strukturlisteförbrukning och flödeskortjournaler
En konsekvent inställning för förbrukning av strukturlistor (BOM) är viktigt eftersom det hjälper till att garantera att lagerhanteringen är effektiv. Om exempelvis parametrarna för förbrukning av strukturlistor inte installerats korrekt i Tillverkningskörning kan material dras från lagret två gånger eller inte alls.

På sidan **Produktionsparametrar** ställs förbrukning av strukturlistor in i tre steg:

- I början av en produktion. Ställ in den här fasen på fliken **Starta**.
- Under tillverkningsprocessen när en åtgärd har slutförts. Ställ in den här fasen på fliken **Operationer**.
- När en produktionsorder är rapporterad som färdig. Ställ in den här fasen på fliken **Rapportera som färdig**.

För varje steg i fältet **Automatisk förbrukning av strukturlista** kan du välja någon av tre metoder för att plocka artiklar för en produktionsorder:

- **Avräkningsprincip** – Det här alternativet används i kombination med ett alternativ som definieras för strukturlistan i modulen **Produktion**. Klicka på **Produktionskontroll** &gt; **Allmänt** &gt; **Produktionsorder** &gt; **Alla produktionsorder**. På sidan **Alla produktionsorder**, välj en produktionsorder i listan och klicka sedan på **Strukturlista** i åtgärdsfönstret. På sidan **Strukturlista** på fliken **Inställningar** i fältet **Avräkningsprincip** ska du välja ett av följande alternativ:

  - **Starta**
  - **Avsluta**
  - **Manuell**
  - Tom (inget alternativ har valts).
  - **Tillgänglig på plats**

    Vid Tillverkningskörning, om **Avräkningsprincip** väljs i fältet **Automatisk förbrukning av strukturlista** på fliken **Starta**, dras allt material som är inställt på **Starta** i Strukturlista från lagret när operationen startas. Alternativet **Finns på plats** används för produkter som är aktiverade för avancerade lagerprocesser. Om du väljer denna avräkningsprincip töms material när lagerställearbete för plockning av råmaterial har slutförts. Material töms även när en strukturlisterad som använder denna avräkningsprincip frisläpps till ett lagerställe och material finns på platsen för produktionsinleverans.

    > [!NOTE]
    > Om fältet **Avräkningsprincip** ställs in på flien **Starta** vid tillverkningskörning måste du välja samma princip antingen på fliken **Åtgärder** eller fliken **Rapportera som färdig**. Detta krav bidrar till att säkerställa att material dras från lagret på strukturlistor med **Slutför** som en avräkningsprincip på tillverkningsordern. Om samma avräkningsprincip väljs, antingen på fliken **Operationer** eller fliken **Rapportera som färdig**, kan material dras av från lagret två gånger.

- **Alltid** – Om du väljer det här alternativet för en fas dras materialen alltid från lagret i den fasen. Exempelvis dras material för produktionen när tillverkningsordern startas. Den här inställningen kräver att **Aldrig** väljs på flikarna **Operationer** och **Rapportera som färdig**. Detta krav förhindrar att artiklar som dras från lagret två gånger.
- **Aldrig** – Om du markerar det här alternativet för en fas sker ingen strukturlisteförbrukning i den fasen. Om du exempelvis väljer **Aldrig** på alla de tre flikarna (**Starta**, **Operationer** och **Rapportera som färdig**) måste material dras manuellt från lagret.

> [!IMPORTANT]
> Inställningarna för produktionsparametrarna måste noga övervägas. Kontrollera att de parametrar som valts på de olika flikarna på sidan **Produktionsparametrar** inte motsäger varandra.

I följande exempel visas parameterinställningar som stöder olika principer för strukturlisteförbrukning. Parametrarna ställs in på sidan **Produktionsparametrar** i Tillverkningskörning.

### <a name="example-1-backflushing-on-operations"></a>Exempel 1: Backflushing i operationer

Använd följande inställningar om plocklistejournaler med förbrukning av strukturlisteartiklar måste genereras när artiklar rapporteras som färdiga i en operation.

| Flik                | Fält                          | Inställning                             |
|--------------------|--------------------------------|-------------------------------------|
| Starta              | Uppdatera start online           | **Status** eller **Status + kvantitet** |
| Starta              | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Operations         | Automatisk strukturlisteförbrukning      | **Alltid**                          |
| Rapportera som färdig | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Rapportera som färdig | Uppdatera färdig rapport online | **Status + kvantitet**               |

### <a name="example-2-backflushing-on-production"></a>Exempel 2: Backflushing i tillverkning

Använd följande inställningar om plocklistejournaler och förbrukning av strukturlisteartiklar måste genereras när artiklar rapporteras som färdiga på en tillverkningsorder.

| Flik                | Fält                          | Inställning                             |
|--------------------|--------------------------------|-------------------------------------|
| Starta              | Uppdatera start online           | **Status** eller **Status + kvantitet** |
| Starta              | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Operations         | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Rapportera som färdig | Automatisk strukturlisteförbrukning      | **Alltid**                          |
| Rapportera som färdig | Uppdatera färdig rapport online | **Status + kvantitet**               |

### <a name="example-3-flushing-principle"></a>Exempel 3: Avräkningsprincip

Använd följande inställningar om plocklistejournaler och förbrukning av strukturlisteartiklar ska genereras enligt avräkningsprincipen som är inställd för strukturlisteartiklarna.

| Flik                | Fält                          | Inställning                |
|--------------------|--------------------------------|------------------------|
| Starta              | Uppdatera start online           | **Status + kvantitet**  |
| Starta              | Automatisk strukturlisteförbrukning      | **Avräkningsprincip** |
| Operations         | Automatisk strukturlisteförbrukning      | **Avräkningsprincip** |
| Rapportera som färdig | Automatisk strukturlisteförbrukning      | **Aldrig**              |
| Rapportera som färdig | Uppdatera färdig rapport online | **Status + kvantitet**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Exempel 4: Avdrag av material under starten av en tillverkningsorder

Använd följande inställningar om plocklistejournaler och förbrukning av strukturlisteartiklar ska genereras när produktionen startas.

| Flik                | Fält                          | Inställning                             |
|--------------------|--------------------------------|-------------------------------------|
| Starta              | Uppdatera start online           | **Status + kvantitet**               |
| Starta              | Automatisk strukturlisteförbrukning      | **Alltid**                          |
| Operations         | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Rapportera som färdig | Automatisk strukturlisteförbrukning      | **Aldrig**                           |
| Rapportera som färdig | Uppdatera färdig rapport online | **Status** eller **Status + kvantitet** |

Baserat på de val som beskrivits tidigare i det här avsnittet bokförs plocklistejournaler i olika faser av tillverkningsorderprocessen:

- När en operation har startat.
- När kvantitetsåterkoppling rapporteras i en operation.
- När artiklar rapporteras som färdiga på tillverkningsordern.

### <a name="example-5-manual-bom-consumption"></a>Exempel 5: Manuell strukturlisteförbrukning

Du kan använda följande inställningar om materialen alltid ska dras av manuellt från lagret. I det här fallet bokförs plocklistejournalerna inte.


|        Flik         |             Fält              |         Inställning         |
|--------------------|--------------------------------|-------------------------|
|       Starta        |      Uppdatera start online      | <strong>Status</strong> |
|       Starta        |   Automatisk strukturlisteförbrukning    | <strong>Aldrig</strong>  |
|     Operations     |   Automatisk strukturlisteförbrukning    | <strong>Aldrig</strong>  |
| Rapportera som färdig |   Automatisk strukturlisteförbrukning    | <strong>Aldrig</strong>  |
| Rapportera som färdig | Uppdatera färdig rapport online | <strong>Status</strong> |

