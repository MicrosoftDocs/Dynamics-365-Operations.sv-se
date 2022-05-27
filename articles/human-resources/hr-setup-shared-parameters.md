---
title: Konfigurera delade parametrar
description: Detta ämne innehåller information om hur du konfigurerar personalparametrar för juridiska personer.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e59745e01905be50e6908fb9587b8afc17604382
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692126"
---
# <a name="configure-shared-parameters"></a>Konfigurera delade parametrar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du måste konfigurera delade parametrar för poster som delas av flera företag, till exempel poster för **Befattning**. Detta ämne innehåller information om hur du konfigurerar personalparametrar för juridiska personer.

Vissa typer av poster, exempelvis poster gällande **befattning**, delas mellan företag. För dessa poster måste du ställa in delad parametrar. Du kan till exempel använda sidan **Delade parametrar för personal** för att konfigurerar personalparametrar för flera olika juridiska personer. 

På **mänskliga resurser delade parametrar sidan** , parametrar är indelade i områden, baserade på deras funktionsduglighet. 

### <a name="settings"></a>Inställningar
På **fliken identifiering** , måste du välja id typer som representerar ID-nummer som finns på sidan. Du måste ställa in identifieringtyper innan du kan ange identifieringsinformation för anställd. Information om personnummer, försäkringsnummer, Alien-ID-nummer och personliga ID-kod bibehålls på **identifiering typ** page. För att definiera en ny typ av identifiering eller granska listan över befintliga typer, gå till **Personalhantering** &gt; **Länkar** &gt; **Inställningar** &gt; **Identifieringstyper**. Du kan ange en enkel kod och beskrivning. 

På fliken **Nummersekvenser** kan du välja de nummersekvenser som används för följande poster: **Personalnummer**, **Befattning**, **ID för användarbegäran**, **I-9-dokument**, **Sökande**, **Diskussion**, **Förmåns-ID** samt **Personalåtgärd** (om denna posttyp aktiverats). För att bibehålla nummersekvens referenser och koder, använd **nummersekvens** listsidan. För att hitta denna sida, använd sidan sökfunktionen. 

På **fliken positioner** , ange om nya positioner som är tillgängliga för tilldelning som standard:

- **Alltid** – Du kan tilldela arbetstagare till nya positioner när positioner skapas. När befattningar skapas kommer datum och tid för **Tillgänglig för tilldelningar** på fliken **Allmänt** på sidan **Position** anges automatiskt till skapandedatum och -tid.
- **Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas. Om du väljer det här alternativet måste du öppna sidan **Befattning** för varje ny befattning som blir tillgänglig. På fliken **Allmänt** anger du sedan datum för **Tillgänglig för tilldelning** för att aktivera medarbetstilldelningen.

På fliken **Avancerad åtkomst** kan du begränsa åtkomsten till viss information eller vissa länkar:

- **Begränsa åtkomsten till medarbetarinformation** – Välj den här funktionen om användarna bara ska kunna visa medarbetarinformation för de juridiska personer som de har tillgång till, samt för medarbetare som har anställning hos dessa juridiska personer.

    När denna funktion har valts måste du följa dessa steg för att ställa in lämpliga behörigheter för varje enskild användare vars vy måste begränsas:

    1. Markera en användare på sidan **Användare**.
    1. Välj en roll för användaren. Alternativet **Tilldela organisationer** blir tillgängligt.
    1. Markera **Tilldela organisationer**.
    1. På den nya sidan väljer du **Bevilja åtkomst till specifika organisationer enskilt** och välj sedan de organisationer som användaren ska få åtkomst till.
    1. Upprepa steg 2 till 4 för alla ytterlgiare roller som användaren har, inklusive systemanvändarrollen.

    > [!NOTE]
    > De företag som en användare har åtkomst till måste matcha alla användarens roller.

- **Aktivera kompensationsvy mellan företag** – Kompensation för medarbetare tilldelas per juridisk person för anställning. Ibland kan en medarbetare vara anställd hos flera juridiska personer samtidigt. När den här funktionen har valts visas kompensationen för varje juridisk person **Självbetjäning för medarbetare** och **Självbetjäning för chef** utan att du behöver ändra juridiska personer. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
