---
title: Konfigurera ett menyalternativ för mobila enheter för att visa en översikt över plockrader
description: I det här avsnittet beskrivs hur du definierar när en lista med alla arbetsrader ska visas för lagerarbetare som bearbetar lagerarbetet på en mobil enhet. Den här funktionen kan vara användbar för lagerarbetare som ofta kräver en översikt över plockningsraderna i en arbetsorder så att de kan optimera sina plockserier.
author: MarkusFogelberg
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6eaba6da313f398c8d30f9a26c959ee971812e21
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818882"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Konfigurera ett menyalternativ för mobila enheter för att visa en översikt över plockrader

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar alternativ som är relaterade till översikten över plockningsraden för menyalternativ för mobila enheter som används för att bearbeta plockningsarbete. Plockningsradens översikt låter oss visa lagerarbetare och välja från en lista med alla arbetsrader som är kopplade till deras aktuella uppgift. Den här funktionen kan hjälpa arbetare att optimera sin plockserie. Funktionen innehåller alternativ som ersätter standardknappen **Hoppa över** som gör att arbetarna går igenom raderna en i taget, i en fast ordning. (Alternativet att använda knappen är dock fortfarande tillgängligt.)

Administratörer kan konfigurera varje menyalternativ enskilt för att styra hur, när och var mobilappen för distributionslagerhantering ska visa översikten över plockningsraden.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Aktivera funktionen översikt över arbetsraddetaljer

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** _Lagerstyrning_
- **Funktionsnamn:** _Översikt över arbetsraddetaljer_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Konfigurera menyalternativ för att visa en lista över alla arbetsrader

För att konfigurera ett menyalternativ för mobila enheter för att visa en översikt följer du dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj eller skapa ett menyalternativ som är relaterat till plockningsarbete och ange följande värden:

    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*
    - **Dirigeras av:** *Användardirigerad* eller *Systemdirigerad*

    Mer information om hur du skapar menyalternativ och använder de olika inställningar som finns på sidan **Menyalternativ på mobil enhet** finns i [Ställa in mobila enheter för lagerställe](configure-mobile-devices-warehouse.md).

1. På snabbfliken **Allmänt** konfigurerar du funktionen genom att ställa in fältet **Visa arbetsradlista** på något av följande värden:

    - **Visa endast på begäran** – arbetare kan välja att visa listan över plockrader genom att välja knappen **Hoppa till** i mobilappen för distributionslagerhantering.
    - **Visa i början av varje plockning** – arbetare ser listan varje gång de startar eller slutför en plockningsrad. De kan också visa listan igen genom att välja knappen **Hoppa till** i mobilappen för distributionslagerhantering.
    - **Visa endast i början av första plockningen** – Arbetare ser listan varje gång de påbörjar nytt plockningsarbete, men inte efter varje rad. De kan också visa listan igen genom att välja knappen **Hoppa till** i mobilappen för distributionslagerhantering.
    - **Visa aldrig** – standardknappen **Hoppa över** visas i mobilappen för distributionslagerhantering och visningen av arbetsradlistan är inaktiverad. Knappen **Hoppa över** låter arbetarna gå igenom raderna en i taget, i en fast ordning. De kan också gå igenom listan så många gånger de behöver, tills alla rader har bearbetats.

1. Klicka på **Spara** i åtgärdsfönstret.

    Om du ställer in fältet **Visa arbetsradlista** till ett värde utom *Visa aldrig* blir knappen **Fältlista** i åtgärdsfönstret tillgänglig.

1. Klicka på **Fältlista** i åtgärdsfönstret.
1. På sidan **Fältlista** konfigurerar du den information som ska visas för varje rad i listan för mobilappen för distributionslagerhantering.

    - Fältet **primära kontroll** är alltid inställt på *LineNum*. Därför börjar varje rad i listan med ett radnummer.
    - Använd de återstående fälten **Visa fält** för att lägga till upp till sju ytterligare visningsfält efter behov. I varje fält **Visningsfält** väljer du namnet på ett fält i arbetsraden. På varje rad visas sedan ett värde för det fältet. Värdena kommer att visas i den ordning du väljer här. Du kan lämna några av fälten **Visningsfält** tomma om du inte behöver alla sju värden.

1. I åtgärdsfönstret, välj **Spara** och stäng sedan sidan **Fältlista**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]