---
title: Lagerställeapphändelser
description: Det här ämnet beskriver den bearbetning av apphändelse i distributionslagret som används för att bearbeta apphändelse meddelanden för lagerstället som en del av ett batchjobb.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 66a5ca8a679563b59ca23992f7e0b4ee6fab470b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993820"
---
# <a name="warehouse-app-event-processing"></a>Händelsebearbetning i distributionslagerappen

[!include [banner](../includes/banner.md)]

Batchjobb som körs i Supply Chain Management kan använda data från en kö för bearbetning av händelser som utfärdats av distributionslagerappen för att vid behov reagera på signalerade händelser. Den här funktionen lägger till relevanta händelser i kön som svar på vissa typer av åtgärder som utförs av medarbetarna som använder appen. Ett exempel: när du använder funktionen **Skapa och bearbeta överföringsorder från lagerställeappen** skapas och uppdateras överföringsorderrubriken och -raderna i servern när du kör batchjobbet **Bearbeta händelser för lagerställeapp**.

## <a name="enable-the-process-warehouse-app-events-feature"></a>Aktivera funktionen bearbeta händelser för lagerställeapp

Innan du kan använda den här funktionen måste du aktivera den i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen bearbeta händelser för lagerställeapp anges som:

- **Modul** – Lagerstyrning
- **Funktionsnamn** - Bearbeta händelser för lagerställeapp

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Ställ in ett batchjobb för att bearbeta händelser för lagerställeapp

### <a name="process-warehouse-app-events"></a>Bearbeta lagerställeapphändelser

Ställ in ett schemalagt batchjobb för bearbetning händelser för lagerställeapp för skapande av överförda order och raduppdateringar.

1. Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta händelser för lagerställeapp**.
1. Dialogrutan bearbeta händelser för lagerställeapp öppnas. Expandera snabbfliken **Kör i bakgrunden** ange **Batchbearbetning** till **Ja**.
1. På snabbfliken **kör i bakgrunden** väljer du **återkommande**.
1. Dialogrutan **Definiera återkommande** öppnas. Ange det körschema som behövs för ditt företag.
1. Välj **OK** om du vill återgå till dialogrutan **Bearbeta händelser för lagerställeapp**.
1. Välj **OK** i dialogrutan **Bearbeta händelser för lagerställeapp** för att lägga till batchjobbet i batchkön.

## <a name="query-warehouse-app-events"></a>Fråga händelser för lagerställeapp

Du kan visa den händelsekön och de händelsemeddelanden som har genererats av lagerställeappen genom att gå till **Hantering av distributionslager \> Frågor och rapporter \> Loggar för mobil enhet \> Lagerställeapp händelser**.

## <a name="the-standard-event-queue-process"></a>Standardkö för händelser för lagerställeapp

Kön för händelser för lagerställeapp används vanligtvis tillsammans med följande beskrivna flöde:

1. En händelse läggs till i kön med ett händelsemeddelande. Det nya meddelandet har inledningsvis händelsetillståndet **väntar**, vilket innebär att batch-jobbet **Bearbeta händelser för lagerställeapp** inte kommer att hämta och bearbeta meddelandet.
1. Så snart status för meddelandet har uppdaterats till **I kö** kommer händelsens batchjobb **Bearbeta händelser för lagerställeapp** hämtas och bearbeta händelsen.
1. När batch-jobbet körs uppdateras händelsetillstånden till antingen **slutförd** eller **misslyckad**, beroende på om den begärda processen var möjlig eller inte.
1. När alla relaterade händelsemeddelanden har **slutförts** tas händelsen bort från kön.

 Ett detaljerat exempel finns i [skapa överföringsorder från bearbetning av lagerställeapp](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Hantera händelsefel

Som en del av bearbetning av händelser för lagerställe kan den begärda meddelande aktiviteten inte ta emot processer från batchjobbet. I det här fallet ändras händelse meddelandet till **misslyckad**. Du kan använda **batch-logg** informationen om du vill veta varför och vidta nödvändiga åtgärder för att rätta till eventuella problem.

Ett detaljerat exempel finns i [skapa överföringsorder från lagerställeapp](create-transfer-order-from-warehouse-app.md).

Så här återställer du ett misslyckat meddelande för händelse för lagerställeapp:

1. Gå till **Lagerlager \> förfrågningar och rapporter \> loggar för mobila enheter \> händelser för lagerställeapp**.
1. På snabbfliken **meddelande för händelse för lagerställeapp**, hitta och välj en relevant händelse som visar **misslyckad** i kolumnen **händelsetillstånd**.
1. Välj **Återställ** från verktygsfältet **Meddelande om händelse för lagerställe**.
1. Fortsätt arbeta tills alla relevanta meddelanden har återställts.

Du kan också ta bort **misslyckat** händelsemeddelande genom att använda alternativet **ta bort** i verktygsfältet **meddelande om händelse för lagerställe**.
