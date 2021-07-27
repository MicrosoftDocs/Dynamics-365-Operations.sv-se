---
title: Konfigurera delade parametrar
description: Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7aff01bee8cadcf852ae32fd60447c68e2174a2a
ms.sourcegitcommit: 43962e6fedaf55aab2f28f53bc38a69d2ff58403
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2021
ms.locfileid: "6333006"
---
# <a name="configure-shared-parameters"></a>Konfigurera delade parametrar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du måste ställa in delade parametrar för poster som delas av flera företag, till exempel befattningsposter. Den här artikeln innehåller information om hur du ställer in personalparametrar för juridiska personer.

Vissa typer av poster, såsom läge, delas mellan företag. För dessa poster måste du ställa in delad parametrar. Du kan till exempel använda **mänskliga resurser delade parametrar** för att ställa in mänskliga resurser parametrar över juridiska personer. 

På **mänskliga resurser delade parametrar sidan** , parametrar är indelade i områden, baserade på deras funktionsduglighet. 

### <a name="settings"></a>Inställningar
På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan. Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd. Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page. För att definiera en ny typ av identifiering eller granska listan över befintliga typer, klicka på **Mänskliga resurser** &gt; **Länkflik** &gt; **Inställningar** &gt; **Identifieringstyper**. Du kan ange en enkel kod och beskrivning. 

På fliken **Nummersekvenser** kan du välja antalet sekvenser som används för följande poster: Anställningsnummer, befattning, användarens begärande-ID, 1-9 dokument, sökande, diskussion, förmåns-ID och personalåtgärd (om detta är aktiverat). För att bibehålla nummersekvens referenser och koder, använd **nummersekvens** listsidan. För att hitta denna sida, använd sidan sökfunktionen. 

På **fliken positioner** , ange om nya positioner som är tillgängliga för tilldelning som standard:

- **Alltid** – Du kan tilldela arbetstagare till nya positioner när positioner skapas. När befattningar skapas kommer datum och tid för **Tillgänglig för tilldelningar** på fliken **Allmänt** på sidan **Position** anges automatiskt till skapandedatum och -tid.
- **Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas. Om du väljer det här alternativet måste du öppna sidan **Befattning** för varje ny befattning som blir tillgänglig. På fliken **Allmänt** anger du sedan datum för **Tillgänglig för tilldelning** för att aktivera medarbetstilldelningen.

På fliken **Avancerad åtkomst** kan du begränsa åtkomsten till viss information eller vissa länkar:

- **Begränsa åtkomsten till medarbetarinformation** – Aktivera den här funktionen om användarna bara ska kunna visa medarbetarinformation för de juridiska personer som de har tillgång till, och för medarbetare som har anställning hos dessa juridiska personer.

    När denna funktion har aktiverats måste du följa dessa steg för att ställa in lämpliga behörigheter för varje användare vars vy måste begränsas:

    1. Markera en användare på sidan **Användare**.
    1. Välj en roll för användaren. Alternativet **Tilldela organisationer** blir tillgängligt.
    1. Markera **Tilldela organisationer**.
    1. På den nya sidan väljer du **Bevilja åtkomst till specifika organisationer enskilt** och välj sedan de organisationer som användaren ska få åtkomst till.
    1. Upprepa steg 2 till 4 för alla andra roller som användaren har, inklusive systemanvändarrollen.

    > [!NOTE]
    > De företag som en användare har åtkomst till måste matcha alla användarens roller.

- **Aktivera kompensationsvy mellan företag** – Kompensation för medarbetare tilldelas per juridisk person för anställning. Ibland kan en medarbetare vara anställd hos flera juridiska personer samtidigt. När den här funktionen aktiveras visas kompensationen för varje juridisk person i självbetjäningen för medarbetare respektive chef utan att du måste ändra juridiska personer. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
