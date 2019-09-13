---
title: Kostnadskontroll för tillgångsfel
description: I det här avsnittet förklaras kostnadskontroll för tillgångsfel i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2fe75c327cdc2bdd76173430ed551895f5941c7b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918313"
---
# <a name="asset-fault-cost-control"></a>Kostnadskontroll för tillgångsfel

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du beräkna kostnader för tillgångsfelregistreringar att få en översikt över de faktiska kostnaderna jämfört med för fel. Faktiska kostnader baseras på bokförda transaktioner. Datumet är feldatumet då symptomen registrerades.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Kostnadskontroll för tillgångsfel**.

2. I dialogrutan **Kostnadskontroll för tillgångsfel** väljer du en ekonomisk dimensionsuppsättning som ska inkluderas i beräkningen om det behövs.

4. Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller kostnaden noll.

5. Du kan använda fältet **Nivå** för att indikera hur detaljerad kostnadskontrollraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla kostnadskontrollrader för tillgångsfel för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla kostnadskontrollrader för tillgångsfel på alla funktionsplatsnivåer som de är relaterade till.

6. Om du vill begränsa sökningen kan du välja specifika tillgångar, feldatum och felorsaker på snabbfliken **Poster som ska ingå**.

7. Klicka på **OK** för att starta beräkningen.

8. I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna i åtgärdsfönstret markeras. Klicka på en knapp för att aktivera och inaktivera den.

I bilden nedan visas ett exempel på en kostnadskontrollberäkning för tillgångsfel.

![Figur 1](media/05-controlling-and-reporting.png)

Information om hur ställer in fel finns i avsnittet [Felhantering](../setup-for-work-orders/fault-management.md).

>[!NOTE]
>I fältet **Ursprunglig budget** visas budgetkostnader från arbetsorderprognosen. I fältet **Faktisk kostnad** visas bokförda kostnader för arbetsorder. I fältet **Utfästa kostnader** visas det totala kostnaderna som ditt företag är förpliktigat att utföra i relation till arbetsorder.

