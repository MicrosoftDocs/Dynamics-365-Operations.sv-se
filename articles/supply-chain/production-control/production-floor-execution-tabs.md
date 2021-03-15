---
title: Designa körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du utformar innehållet i användargränssnittet för varje konfiguration.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 786ea9a3da98e9f1812b007d4301cb47680e6894
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "5077588"
---
# <a name="design-the-production-floor-execution-interface"></a>Designa körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Du kan utforma innehållet i användargränssnittet för varje konfiguration som används i gränssnittet för körning av produktionsstyrning. Arbetstagarna i en arbetsgrupp kan t.ex. behöva öppna jobbinstruktioner på produktionsgolvet, medan det i en annan arbetsgrupp inte behövs. I det fallet ska två konfigurationer skapas, en med en knapp för att öppna dokumentbilagor och en utan den här knappen.

## <a name="design-a-tab"></a>Utforma en flik

På sidan **Konfigurera körning av produktionsgolv** kan du skapa och konfigurera flikar genom att välja **Designa flikar** i åtgärdsfönstret.

Varje flik är uppdelad i fyra delar, som visas i bilden nedan.

![Fliklayout](media/pfe-tab-layout.png "Fliklayout")

Följande element visas i bilden:

1. Primärt verktygsfält
1. Sekundärt verktygsfält
1. Huvudvy
1. Detaljerad visning

Följ stegen nedan om du vill skapa och konfigurera en ny flik:

1. Gå till **Produktionskontroll &gt; Konfigurera &gt; Tillverkningskörning**.

1. Välj **Designa flikar** i åtgärdsfönstret för att **Designa flikar**.

    ![Sidan designa flikar](media/pfe-design-tabs.png "Sidan designa flikar")

1. Välj **Ny** i åtgärdsfönstret.

1. Gör följande inställningar i sidans rubrik:

    - **Fliknamn** - Ange ett namn på fliken.
    - **Huvudvisning** - Välj mellan de två fördefinierade jobblistorna (*aktiva jobb*, *alla jobb* eller *min maskin*).
    - **Detaljvy** - Välj mellan ett tomt värde eller **jobbinformation**. Om du väljer det tomma värdet visas ingen detaljerad vy på fliken. Om du väljer **jobbdetaljer** kommer den detaljerade vyn att innehålla en detaljerad beskrivning av det jobb som valts i jobblistan i huvudvyn.

1. I avsnittet för det **primära verktygsfältet** väljer du vilka knappar som ska vara tillgängliga i det primära verktygsfältet. I kolumnen **tillgängliga åtgärder** visas en lista över alla knappar som kan läggas till. I kolumnerna **Valda åtgärderna** visas en lista över alla knappar som ingår i den aktuella konfigurationen. Använd knapparna mellan kolumnerna för att flytta de markerade objekten mellan de kolumner som behövs. Använd knapparna upp och ned bredvid kolumnen **Valda åtgärder** om du vill styra i vilken ordning knapparna visas i användargränssnittet.

1. I avsnittet för det **sekundära** **verktygsfältet** väljer du vilka knappar som ska vara tillgängliga i det sekundära verktygsfältet. I kolumnen **tillgängliga åtgärder** visas en lista över alla knappar som kan läggas till. I kolumnerna **Valda åtgärderna** visas en lista över alla knappar som ingår i den aktuella konfigurationen. Använd knapparna mellan kolumnerna för att flytta de markerade objekten mellan de kolumner som behövs. Använd knapparna upp och ned bredvid kolumnen **Valda åtgärder** om du vill styra i vilken ordning knapparna visas i användargränssnittet.

## <a name="associate-a-tab-with-a-configuration"></a>Associera en flik med en konfiguration

När du har skapat alla flikar du behöver kan du koppla dem till en konfiguration.

1. Gå till **Produktionskontroll &gt; Inställningar &gt; Konfigurera för produktionsgolvet**.

    ![Konfigurera körning på produktionsgolv](media/pfe-config-prod-floor-execution.png "Konfigurera körning på produktionsgolv")

1. På snabbfliken **Val av flik** välj **Lägg till**.

1. En ny rad läggs till i rutnätet. Markera namnet på en flik som du vill lägga till i konfigurationen för den nya raden.

1. Fortsätt att lägga till ytterligare flikar om det behövs.

1. Använd knapparna **Flytta upp** och **Flytta ned** i verktygsfältet om du vill ordna flikarna efter behov. Flikarna visas från vänster till höger i den ordning som visas i ovanstående skärmdump (fliken längst upp visas till vänster).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]