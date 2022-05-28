---
title: Uppskjuten bearbetning av manuell lagerrörelse
description: I detta ämne beskrivs hur du använder uppskjuten bearbetning av manuell lagerrörelse i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c2e7296d77332b665e5d618d39804216f4347ca2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670480"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Uppskjuten bearbetning av manuell lagerrörelse

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du använder uppskjuten bearbetning av manuell lagerrörelse i Microsoft Dynamics 365 Supply Chain Management.

Uppskjuten bearbetning låter lagerarbetare fortsätta att utföra annat arbete medan placeringsoperationen bearbetas i bakgrunden. Uppskjuten bearbetning är användbar när servern får tillfälliga eller oplanerade ökningar i bearbetningstid och den ökade bearbetningstiden kan påverka medarbetarens produktivitet. Arbetstypen *Lagerrörelse* har nu lagts till i den uppsättning arbetstyper som den här funktionen stöder.

Bakgrundsbearbetning uppnås genom att du använder [funktionen för att bearbeta apphändelser i lagerställe](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Aktivera funktionen i systemet

Om du vill göra denna funktion tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md): Du måste aktivera dem i följande ordning:

1. *Arbetsspärr för hela organisationen*<br>(Från och med version 10.0.21 av Supply Chain Management är den här funktionen obligatorisk, varför den är aktiverad som standard och inte kan stängas av igen.)
1. *Bearbeta lagerställeapphändelser*<br>(Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard.)
1. *Uppskjutna put-åtgärder*
1. *Uppskjuten bearbetning av manuell åtgärd för lagerrörelse*<br>(Från och med version 10.0.25 av Supply Chain Management är den här funktionen obligatorisk, varför den är aktiverad som standard och inte kan stängas av igen.)

## <a name="configure-the-work-processing-policies"></a>Konfigurera arbetsbearbetningspolicyer

Om du vill använda uppskjuten bearbetning måste du konfigurera och använda en policy för arbetsbearbetning. [Arbetsfunktionen Uppskjuten bearbetning av lagerställe](deferred-put.md) stöder följande arbetstyper: *Försäljningsorder*, *Utfärda överföringsorder* samt *Lagerpåfyllnad*. Funktionerna för *Uppskjuten bearbetning av manuella lagerrörelsefunktioner* lägger till en ny arbetstyp: *Lagerrörelse*.

Följ dessa steg för att konfigurera en policy för arbetsbearbetning:

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Policyer för arbetsbearbetning**.
1. Välj antingen en befintlig policy i listan eller skapa en ny policy genom att välja **Ny** i åtgärdsfönstret. Rubriken för varje policy har följande fält:

    - **Policynamn för arbetsbearbetning** – Namnet på policyn för arbetsbearbetning.
    - **Beskrivning:** – En beskrivning av policyn för arbetsbearbetning.

1. På snabbfliken **Bearbetningsregler** ställer du in en samling regler som policyn ska gälla för. Använd knappar i verktygsfältet om du vill lägga till och ta bort regler efter behov. För varje regel anger du följande fält:

    - **Arbetsordertyp** – Välj den arbetstyp som policyn gäller för.
    - **Funktion** – Välj den funktion som policyn ska bearbeta. Om du har valt *Lagerrörelse* i fältet **Arbetsordertyp** behöver du inte ställa in detta fälte eftersom både plock- och placeringsfunktioner bearbetas som en enda händelse.
    - **Bearbetningsmetod** – Välj den metod som används för att bearbeta arbetsraden. Om du väljer *Omedelbar* liknar beteendet det beteende när inga policyer för bearbetning av arbetsprocesser används för att bearbeta raden. Om du väljer *Uppskjuten* tillämpar systemet uppskjuten bearbetning som använder batchramverket.
    - **Uppskjuten bearbetningströskel** – Om du ställer in det här fältet som *0* (noll) finns det inget tröskelvärde. I det här fallet används *uppskjuten* bearbetning om möjligt. Om den specifika beräkningen av tröskelvärde ligger under tröskelvärdet används metoden *Omedelbar*. I annat fall används metoden *Uppskjuten* om möjligt. För försäljnings- och överföringsrelaterat arbete beräknas tröskelvärdet som antalet associerade källbeläggningsrader som bearbetas för arbetet. För lagerpåfyllnadsarbete beräknas tröskelvärdet som antalet arbetsrader som fylls på av arbetet. Genom att ange ett tröskelvärde på till exempel *5* för försäljning säkerställer du att mindre arbeten med färre än fem inledande källbeläggningsrader inte använder uppskjuten bearbetning, men större arbeten kommer att använda den. Tröskelvärdet har endast effekt om fältet **arbetsbearbetningsmetod** har ställts in på *Uppskjuten*.
    - **Uppskjuten bearbetning av batchgrupp** – Ange batchgruppen som används för bearbetning. Om du har valt *Lagerrörelse* i fältet **Arbetsordertyp** behöver du inte ställa in detta fält, detta eftersom batchgruppen har valts i dialogrutan **Bearbeta händelser i lagerprogram**.

## <a name="assign-the-work-creation-policy"></a>Tilldela policyn för skapande av arbete

Mer information om hur du tilldelar en policy för att skapa arbete finns i [Uppskjuten bearbetning av lagerställearbete](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Ställ in ett batchjobb för att bearbeta händelser för lagerställeapp

Om du vill använda processen *uppskjuten bearbetning av manuella lagerrörelsefunktioner* ställer du in ett tidsplanerat batchjobb.

1. Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta händelser för lagerställeapp**.
1. I dialogrutan **Bearbeta händelser i lagerprogram**, på snabbfliken **Kör i bakgrunden**, anger du alternativet **Batchbearbetning** som *Ja*.
1. Välj **Återkommande** och ställ in ett körningsschema som uppfyller företagets krav.
1. Markera **OK** i respektive dialogruta.

## <a name="inquire-about-the-warehouse-app-events"></a>Fråga om händelser i lagerställeprogram

Du kan visa den händelsekön och de händelsemeddelanden som lagerställeprogrammet genererar genom att gå till **Lagerhantering \> Frågor och rapporter \> Loggar för mobil enhet \> Händelser i lagerställeprogram**.

Händelsemeddelandet *Lagerrörelse* får statusen *I kö* när de föst skapas. Denna status indikerar att batchjobbet **Bearbeta händelser i lager-app** kommer att registrera händelsemeddelandena och bearbeta dem. När statusen uppdateras till *Slutförd* raderas samtliga relaterade händelser från kön.

Alla händelser avseende *lagerrörelser* ackumuleras under en enda samling per händelsetyp och lagerställe.

Batchjobbet bearbetar apphändelser för lagerställe enligt upprepningen som har ställts in i dialogrutan **Bearbeta händelser i lager-app**. Därför kan du hitta lager-ID:t i fältet **Identifierare** tills ett meddelande bearbetas.

Meddelandets detaljer innehåller förflyttningens detaljer (till exempel platserna "från" och "till").

Mer information finns i [händelsebearbetning för lagerställe](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Konfigurera menyn för mobila enheter för att hoppa över den uppskjutna bearbetningspolicyn

Mer information om hur du konfigurerar menyn för mobila enheter i syfte att hoppa över en uppskjuten bearbetningspolicy finns i [Uppskjuten bearbetning av lagerställearbete](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Påverkan på stängda arbetsdatum

Mer information om hur stängda arbetsdatum påverkas finns i [Uppskjuten bearbetning av lagerställearbete](deferred-put.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Uppskjuten bearbetning av lagerhållningsarbete](deferred-put.md)
- [Händelsebearbetning i distributionslagerappen](warehouse-app-events.md)
- [Ställa in mobila enheter för distributionslagerarbete](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
