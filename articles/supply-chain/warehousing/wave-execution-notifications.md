---
title: Meddelanden för påfyllnadskörning
description: Det här ämnet beskriver meddelande om påfyllnadskörning och förklarar hur du ställer in det.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 26810f6e21f9c8ba6e92621a8e1ddee17837b6048107b961afb0e428059051af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752594"
---
# <a name="wave-execution-notifications"></a>Meddelanden för påfyllnadskörning

[!include [banner](../includes/banner.md)]

Funktionen *Meddelande påfyllnadskörning* använder affärshändelser och åtgärdscenter för att leverera meddelanden som är relaterade till påfyllnadskörning. Där kan du ange vilka typer av händelser som genererar meddelanden, vilka lagerställen som genererar dem och vilka användare som tar emot dem.

Knappen **Visa meddelanden** (klocksymbol) till höger om navigeringsfältet anger när ett åtgärdscenter meddelande är tillgängligt för den aktuella användaren. Användaren kan välja knappen **Visa meddelanden** om du vill öppna Åtgärdscentret och granska meddelandena.

Affärshändelser inträffar när affärsprocesser körs. Affärsprocesser består av uppgifter. Under en affärsprocess utför de användare som deltar i den affärsåtgärder för att slutföra dessa uppgifter. Affärshändelser innehåller en mekanism som gör att externa system kan ta emot meddelanden från Finance and Operations-program. På det här sättet kan systemen utföra affärsåtgärder som svar på affärshändelser. Mer information finns i [Översikt över affärshändelser](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-on-the-wave-execution-notifications-feature"></a>Aktivera funktionen meddelande om påfyllnadskörning

Innan du kan använda funktionen *meddelande om påfyllnadskörning* den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *meddelande om påfyllnadskörning*

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Scenario: Skicka meddelanden för batchkörning för påfyllnad till åtgärdscentret

I det här scenariot visas det kompletta flödet för utskick av meddelanden om körningsfel för påfyllnadsbatchen till en viss roll via Åtgärdscentret.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Kontrollera att påfyllnader körs i batchläge

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. På snabbfliken **Påfyllnadsbearbetning**, ange alternativet **Behandla påfyllnader i batch** till *Ja*.

> [!NOTE]
> Om du vill inaktivera meddelanden om exekvering av påfyllnadsbatch, ställ in **Inaktivera batchmeddelanden för påfyllnadsbehandling** till *Ja*.

### <a name="configure-a-wave-notification-policy"></a>Konfigurera en policy för påfyllnadsmeddelanden

Policyer för påfyllnadsmeddelanden definierar vilka typer av meddelanden som skickas och vilka användare som meddelas.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Policyer för påfyllnadsmeddelanden**.
1. Skapa en post med följande inställningar:

    - **Policy påfyllnadsmeddelanden:** *24BatchError*
    - **Beskrivning:** *Batchfel för lagerställe 24*
    - **Skicka meddelande om:** *Endast fel*
    - **Till rollen:** *Systemadministratör*

        > [!NOTE]
        > Eftersom detta scenario använder demodata väljs rollen *Systemadministratör* för enkelhetens skull. Eftersom du är inloggad som systemadministratör får du därför meddelandena. I praktiken bör du dock vanligtvis välja en mer specifik roll för att meddela om körningsfel för påfyllnadsbatchen, t.ex. *Warehouse management*.

1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="configure-a-wave-template"></a>Konfigurera en påfyllnadsmall

Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmallar.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I listrutan, ange fältet **Malltyp för påfyllnad** till *Leverans* och väljer sedan påfyllnadsmallen *24 leveransstandard* för lagerställe 24.
1. På snabbfliken **Allmänt** ställer du in fältet **Policy påfyllnadsmeddelanden** till *24BatchError*.

### <a name="configure-a-work-template"></a>Konfigurera en arbetsmall

Arbetsmallar används under påfyllnadskörningen för att generera arbete. I det här scenariot ska ett fel utlösas av påfyllnadskörningen. Genom att ställa in arbetsmallfrågan till att använda ett lagerställe som inte finns, ser du till att påfyllnadskörningen misslyckas och skickar därför ett meddelande.

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.
1. I listrutan, ange fältet **Malltyp för arbete** till *Försäljningsorder* och väljer sedan arbetsmallen *24 SO steg* för lagerställe 24.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall** redigera följande rad (eller lägg till det om det inte finns):

    - **Tabell:** *Tillfälliga arbetstransaktioner*
    - **Härlett register:** *Tillfälliga arbetstransaktioner*
    - **Fält:** *lagerställe*
    - **Kriterier:** Ändra värdet från *24* till *Fel*.

1. Välj **OK** och bekräfta ändringen.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Skapa en försäljningsorder och släpp den på lagerstället

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *24*

1. På snabbfliken **försäljningsorderrader** lägger du till en försäljningsorderrad som har följande inställningar:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *10*

    > [!NOTE]
    > Dessa artiklar och kvantiteter är bara exempel. De måste ha lager i det angivna lagerstället.

1. Medan den nya raden fortfarande är markerad på snabbfliken **Försäljningsorderrader**, välj **Lager \> Reservation** i verktygsfältet.
1. På sidan **Reservation** i åtgärdssfönstret väljer du **Reservera parti**. Stäng sidan.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

### <a name="notifications-from-wave-batch-job-execution"></a>Meddelanden från körning av batchjobb för påfyllnad

Beroende på inställningarna för dina affärshändelser kommer du så småningom att få ett meddelande om fel vid påfyllnadskörningen. Meddelandet i åtgärdscenter liknar följande exempel och innehåller en länk till den påfyllnaden som misslyckades.

> **Fel under påfyllnadskörning**  
> Ett fel uppstod vid körning av påfyllnaden USMF-000000001.  
> De senaste meddelandena: Inget arbete skapades för påfyllnaden USMF-000000001.
>
> **STATUS**  
> Aktiva
>
> Öppna påfyllnadsinformation

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
