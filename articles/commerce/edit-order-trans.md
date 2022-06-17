---
title: Redigera och granska onlineorder och asynkrona kundordertransaktioner
description: Den här artikeln beskriver hur du redigerar och granskar transaktioner för onlineorder och asynkrona kundorder i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3c4219e082466bdfd1426710cecf25fd350d0767
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873070"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Redigera och granska onlineorder och asynkrona kundordertransaktioner

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du redigerar och granskar transaktioner för onlineorder och asynkrona kundorder i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Mellan Commerce-versionerna 10.0.5 och 10.0.6 har stöd lagts till för redigering av hämtköpstransaktioner (till exempel försäljning och returer) och transaktioner för kontanthantering (till exempel borttagning av växelpost och betalningsmedel). I Commerce version 10.0.7 har stöd för redigering av onlineordertransaktioner och asynkrona kundordertransaktioner lagts till.

## <a name="edit-and-audit-order-transactions"></a>Redigera och granska ordertransaktioner

Följ de här stegen om du vill redigera och granska ordertransaktioner i Commerce-administration.

1. Installera [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Gå till sidan **Butiksparametrar**, fliken **Kundorder** på snabbfliken **Order** och ange en spärrkod för **Spärrkod för ordersynkroniseringsfel**.
1. Öppna arbetsytan **Butiksekonomi**. På panelerna **Synkroniseringsfel för onlineorder** och **Synkroniseringsfel för kundorder** finns en förfiltrerad vy av sidan med butikstransaktioner. På var och en visas de transaktionsposter som inte kunnat synkroniseras för motsvarande ordertyp.
1. Öppna sidan **Synkroniseringsfel för onlineorder** eller sidan **Synkroniseringsfel för kundorder**. Välj en post för att visa information om synkroniseringsfelet. På snabbfliken **Synkroniseringsstatus** finns följande felinformation:

    - Status för väntande order
    - Information om orderfel
    - Datum och tid för ändring
    - Antal nya försök

1. Om felinformationen anger att posten måste åtgärdas väljer du **Office Add in** och välj sedan **Redigera vald transaktion**. En Excel-fil som visar detaljerna för den valda transaktionen öppnas.

    - Om transaktionen som redigeras är en onlineordertransaktion innehåller Excel-filen följande kalkylblad:

        - **Transaktion** – I det här kalkylbladet finns huvudinformation för transaktionen.
        - **Försäljningstransaktion** – I det här kalkylbladet finns radinformation för transaktionen.
        - **Betalningstransaktioner** – I det här kalkyl bladet finns detaljinformation om betalningsraderna för transaktionen.
        - **Rabattransaktioner** – I det här kalkylbladet finns rabattrelaterad information för transaktionen.
        - **Momstransaktioner** – I det här kalkylbladet finns momsrelaterad information för transaktionen.
        - **Avgiftstransaktioner** – I det här kalkylbladet finns avgiftsrelaterad information för transaktionen.

    - Om transaktionen som redigeras är en asynkron kundordertransaktion innehåller Excel-filen följande kalkylblad:

        - **Rader** – I det här kalkylbladet finns huvud- och radinformation för transaktionen.
        - **Betalningar** – I det här kalkyl bladet finns detaljinformation om betalningsraderna för transaktionen.
        - **Rabatter** – I det här kalkylbladet finns rabattrelaterad information för transaktionen.
        - **Moms** – I det här kalkylbladet finns momsrelaterad information för transaktionen.
        - **Avgifter** – I det här kalkylbladet finns avgiftsrelaterad information för transaktionen.

1. Ange **Redigering** i fältet **Status för väntande order** i Excel-filen och publicera sedan ändringen. På det här sättet förhindrar du jobbet **Synkronisera order** som körs i batchläge hoppar över den här posten under bearbetningen.
1. I Excel-filen ändrar du lämpliga fält och skickar tillbaka informationen till Commerce-administration med hjälp av publiceringsfunktionen i Dynamics Excel Add-in. När du har publicerat data visas ändringarna i systemet. Under publiceringen görs ingen validering av ändringar som användarna gör.
1. Du kan visa en fullständig granskningsspårning av ändringarna genom att välja **Visa redovisningsspårning** i rubriken för **Butikstransaktion** för ändringarna på rubriknivå och i det relevanta avsnittet och den relevanta posten på den aktuella transaktionssidan. Till exempel kommer alla ändringar som är relaterade till försäljningsrader att visas på sidan **Försäljningstransaktioner** och alla ändringar som är relaterade till betalningar kommer att visas på sidan **Betalningstransaktioner**. Följande granskningsinformation underhålls för ändringarna:

    - Datum och tid för ändring
    - Fält
    - Gammalt värde
    - Nytt värde
    - Ändrades av

1. När du har gjort och publicerat ändringarna väljer du **Synkronisera order** om du vill att synkroniseringsprocessen ska starta direkt. Du kan också vänta och bearbeta transaktionen genom att köra synkroniseringsprocessen batchläge.

När order har synkroniserats får de som standard en spärrstatus, baserat på spärrkoden som definierats i Commerce-parametrarna. Orderspärren måste tas bort innan dessa order kan bearbetas ytterligare för uppfyllelse eller andra åtgärder.

## <a name="additional-resources"></a>Ytterligare resurser

[Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering](edit-cash-trans.md)

[Redigera ekonomiska dimensioner för butikstransaktioner](edit-financial-dim.md)

[Skapa en Excel-arbetsbok för att redigera butikstransaktioner](create-excel-edit.md)

[Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]