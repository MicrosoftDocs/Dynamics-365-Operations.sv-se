---
title: Planer som baseras på offerter och anbudsförfrågningar
description: I den här artikeln beskrivs hur du ställer in huvudplanering så att offerter och anbudsförfrågningar kan övervägs när planerade order genereras.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690104"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Planer som baseras på offerter och anbudsförfrågningar

[!include [banner](../../includes/banner.md)]

Offerter och anbudsförfrågningar representerar möjliga eller sannolika framtida order. Det är därför klokt att beakta dem under huvudplaneringen, så att extra leverans kan planeras utifrån befintliga anbudsförfrågningar och sannolikheten för att varje offert ska bli en faktisk order. I den här artikeln beskrivs hur du ställer in huvudplanering så att offerter och anbudsförfrågningar kan övervägs när planerade order genereras.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Ställ in huvudplanering när du vill ta hänsyn till försäljningsofferter och/eller anbudsförfrågningar

Gör på följande sätt när du vill ställa in huvudplanering så att försäljningsofferter och/eller anbudsförfrågningar övervägs.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en befintlig plan listvyn eller välj **ny** i åtgärdsfönstret för att skapa en ny.
1. På snabbfliken **Allmänt** ange följande fält:

    - **Inkludera försäljningsofferter** – Ställ in det här alternativet till *Ja* om du vill ta hänsyn till försäljningsofferter när den aktuella planen körs. Ställ in den till *Nej* om du vill ignorera dem.
    - **Sannolikhet %** – Ange det lägsta förtroende som krävs för att en offert ska kunna inkluderas i huvudplaneringen. Huvudplaneringsberäkningen omfattar alla offerter som har skapats utifrån affärsmöjligheter som har den här sannolikhetsprocenten eller högre. Om du vill inkludera alla offerter, inklusive offerter som inte har någon sannolikhet tilldelad, eller om ingen affärsmöjlighet associeras med dem, ställer du in det här fältet på *0* (noll). Mer information om sannolikheter för offerter regler finns i nästa avsnitt.
    - **Ta med anbudsförfrågningar** – Ställ in det här alternativet till *Ja* om du vill ta hänsyn till anbudsförfrågningar när den aktuella planen körs. Ställ in den till *Nej* om du vill ignorera dem. Om du väljer att ta hänsyn till en anbudsförfrågan skapas planerade inköpsorder för dem, men leverantören specificeras inte förrän anbudsförfrågan har lösts. Planerade inköpsorder som skapas för anbudsförfrågan kan påverka kvantiteterna för andra planerade order.

1. Fortsätt att ställa in huvudplanen på vanligt sätt.

## <a name="assign-and-view-probabilities-for-quotations"></a>Tilldela och visa verktyg för offerter

Som nämns i det föregående avsnittet innebär det att en huvudplan endast tar hänsyn till offerter som uppfyller eller överskrider sannolikhetströskeln som definieras för planen (om ett tröskelvärde har definierats). Sannolikheten ställs dock inte in direkt på varje offert. I stället ärvs det från affärsmöjligheten som används för att generera offerten. Därför offerter som skapas direkt på sidan **Alla offerter** kommer inte att ha en sannolikhet tilldelad dem eller en möjlighet kopplad till dem, och de kommer aldrig att beaktas av huvudplanering (såvida inte fältet **Sannolikhet %** anges till *0* \[noll\]). Om du vill tilldela en sannolikhet måste en offert genereras från en affärsmöjlighet.

### <a name="create-a-quotation-from-an-opportunity"></a>Skapa en offert från en möjlighet

Använd följande procedur om du vill tilldela en sannolikhet till en affärsmöjlighet och sedan skapa en offert från den affärsmöjligheten.

1. Gå till **Försäljning och marknadsföring \> Relationer \> Affärsmöjligheter \> Alla affärsmöjligheter**.
1. Välj en befintlig möjlighet eller välj **Ny** i åtgärdsfönstret för att skapa en ny.
1. Fyll i affärsmöjlighetssidan om du vill identifiera affärsmöjligheten. Se till att ställa in fältet **Sannolikhet** till ett lämpligt värde. Endast huvudplaner som har ställts in för att söka efter det här värdet eller högre tar hänsyn till offerter som har skapats från den här affärsmöjligheten.
1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, på fliken **Affärsmöjlighet** i grupp **Ny** välj **Försäljningsoffert** eller **Projektoffert**, beroende på vilken typ av offert som du vill skapa.
1. I dialogrutan **Skapa offert** anger du fälten och väljer sedan **OK**.
1. En ny offert skapas och öppnas. På snabbfliken **Rader** använder du verktygsfältet för att lägga till försäljningsrader eller projektrader som krävs för att definiera innehållet i offerten.
1. Klicka på **Spara** i åtgärdsfönstret. Stäng offert.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Se sannolikheten som tilldelas en offert

Det enda sättet att visa sannolikheten som tilldelas en offert är att öppna affärsmöjligheten som används för att skapa offerten på det sätt som beskrivs i proceduren nedan.

1. Gå till **Försäljning och marknadsföring \> Försäljningsofferter \> Alla offerter**.
1. Om kolumnen **Affärsmöjlighets-ID** inte visas (den är dold i en standardinstallation) följer du dessa steg för att tillfälligt visa den. (Alternativt för att behålla kolumnen **Affärsmöjlighets-ID** tillgänglig, skapa [sparad vy](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json) som innehåller den.)

    1. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Infoga kolumner**.
    1. I dialogrutan **Infoga kolumner** hitta raden där fältet **Fält** anges till *Affärsmöjlighet* och markera kryssrutan **Välj** för den raden.
    1. Välj **Uppdatera** om du vill lägga till den valda kolumnen på sidan **Alla offerter**.

1. Sök efter raden för den relevanta offerten i rutnätet. Välj sedan värdet för raden i kolumnen **Affärsmöjlighets-ID**.

    > [!NOTE]
    > Om du letar efter en projektoffert måste du kanske välja kolumnrubriken **Offerttyp** och rensa filtret. I en standardinstallation ställs det här filtret in så att endast försäljningsofferter visas.

1. Den relaterade affärsmöjligheten öppnas. Du kan nu visa och redigera **sannolikhet** värdet efter behov.
