---
title: Praxis
description: I det här avsnittet beskrivs hur du ställer in överenskommelser för att upprätta hur kostnader ska redovisas i global lagerredovisning.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d629b082b423edf417714b8362be3364bc861e78f62d430a4d7083b8c49611a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773427"
---
# <a name="conventions"></a>Praxis

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

En regel är en behållare för en uppsättning principer som påverkar systemets beteende. Baserat på dina affärsbehov måste du definiera konventioner genom att använda en kombination av olika principer som fastställer hur kostnader ska redovisas i global lagerredovisning. Du kan koppla varje konferens till en eller flera redovisningar för att säkerställa överensstämmelse i redovisningsprinciperna som tillämpas i hela redovisningen.

För att ställa in dina konventioner, gå till **Global lagerredovisning \> Inställning \> Konventioner**. För varje konvention anger du följande fält:

- **Namn** – Ange namnet på konvention.
- **Beskrivning** – Ange en beskrivning av konvention.
- **Policy för kostnadsobjekt** – Välj policy för kostnadsobjekt. Dessa principer bestämmer nivån av finvärden som systemet använder för att beräkna och underhålla lagervärdet. Följande fördefinierade alternativ är tillgängliga:

    - Produkt
    - Produkt – Webbplats
    - Produkt – Webbplats – Lagerställe

    Om du till exempel väljer *Produkt – Webbplats* för varje lagerrörelse (inflöde eller utflöde) beräknar och underhåller systemet lagerkostnaden för varje produkt på webbplatsnivå. Lagerrörelser på lägre nivåer, till exempel lagerställenivå, påverkar därför inte lagervärdet. (Ett exempel på en överföring på lagerställenivå är en artikelöverföring mellan två lagerställen på en webbplats.) Det går inte heller att visa lagerkostnaden på en lägre nivå, till exempel lagerställenivå.

- **Policy för inmatningsmåttbas** – Välj en policy för inmatningsmåttbas. Dessa principer bestämmer vilka kostnader som ska flöda in på lagerkontot och de kostnader som ska debiteras. Följande alternativ är relevanta för handelsföretag:

    - **Normal historisk** – Alla kostnadskomponenter förs in i lagerkontot.
    - **Standard – Standardkostnadsflöden** till lagerkontona och skillnaden mellan tillämpad kostnad och faktiska kostnader debiteras avvikelsekontona. Om du vill skapa en policy för mätningsunderlag för *standard* indata måste du först skapa en prislista där policyn kan söka efter artikelns standardkostnad.
    - **Prislistor** – Global lagerredovisning stöder hämtning av artikelpriser från flera juridiska personer. Du kan definiera en prislista som ska användas i policyn för indatamått. På det här sättet vet systemet var artikelpriset ska sökas. Följ dessa steg för att ställa in prislistor:

        1. Ange sedan ett namn i fältet **Namn**.
        1. Ange en beskrivning i fältet **beskrivning**.
        1. I fältet **kostnadstyp** välj en kostnadstyp (*Standardkostnad* eller *Planerad kostnad*).
        1. Välj en **pristyp** i fältet Pristyp (*Kostnad*, *Inköp* eller *Försäljningspris*).
        1. Lägg till kostnadsversioner.
        1. Välj **Pris** i åtgärdsfönstret om du vill validera artikelpriserna i prislistan.

- **Policy för antagande av kostnadsflöde** – Välj en policy för antagande för kostnadsflöde. Dessa principer bestämmer hur kostnader tas bort från lagret och rapporteras som kostnaden för sålda varor. Följande fördefinierade alternativ är tillgängliga:

    - Genomsnitt
    - Specifik – batch

    > [!NOTE]
    > Global lagerredovisning är ett lagersystem som används av lagerhantering. Därför spårar systemet lagervärdet för transaktioner.

- **Policy för kostnadselement** – Du kan definiera principer för kostnadselement och koppla dem till det här fältet. Ett *kostnadselement* är kostnaden för en resurs som förbrukas av en händelse. Du kan använda kostnadselement när du vill spåra och kategorisera kostnader. Om du vill skapa principer för kostnadselement anger du information på följande ställen:

    - Fältet **Namn**
    - Fältet **Beskrivning**
    - **Kostnadselement** lista
    - **Regler** rutnät

    Om du inte vill bryta ned lagervärdet ytterligare måste du fortfarande skapa en kostnadselementlista som har ett enda kostnadselement. Du måste sedan skapa en kostnadselementprincip för att mappa alla relevanta mätningstyper (kostnadskomponenter) till det kostnadselementet.
