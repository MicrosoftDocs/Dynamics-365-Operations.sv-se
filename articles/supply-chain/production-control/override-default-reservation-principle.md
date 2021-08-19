---
title: Åsidosätt standardreservationsprincipen för material i produktionen.
description: I det här avsnittet beskrivs hur du ställer in en standardreservationsprincip för varje artikelmodellgrupp, så att olika reservationsprinciper automatiskt kan användas för varje artikel som ingår i en strukturlista eller en batchorderformel.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 959b8b85fe55ed5e0a93b5b614c3f6166bbd2bb6ef07e9d0f0f4c2b1ea3c4659
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721329"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Åsidosätt standardreservationsprincipen för material i produktionen.

[!include [banner](../includes/banner.md)]

Med funktionen *Åsidosätt standardproduktionsreservation* kan du ange en standardreservationsprincip för varje artikelmodellgrupp. Därför kan olika reservationsprinciper användas automatiskt för varje artikel som ingår i en strukturlista eller en batchorderformel. Du kan välja om varje artikelmodellgrupp ska åsidosätta principen för standardreservation som är inställd för en order och vilken reservationprincip som ska användas iställe (*manuell*, *uppskattning*, *tidsplanering*, *frisläppning* eller *start*).

När du skapar en ny tillverkningsorder eller batchorder uppmanas du att välja den reservationsprincip som ska användas för ordern och alla dess strukturlisterader eller receptrader. När funktionen *Åsidosätt standardproduktionsreservation* används kan vissa eller alla strukturliste- eller formelrader åsidosätta reservationsprincipen och istället använda reservationsprincipen som är inställd för relevant artikelmodellgrupp.

Om du till exempel har råmaterial eller ingredienser som kräver plockarbete, strukturlista eller receptrader som skapas för dessa produkter måste reserveras fysiskt, eftersom fysisk reservation är en förutsättning för att lagerställe ska kunna skapas. Typically, ifOm du vill att reservationen ska ske automatiskt väljer du vanligtvis en av följande reservationsprinciper: *uppskattning*, *tidsplanering*, *frisläppning* eller *start*. Å andra sidan, om du har material eller ingredienser som inte kräver plockarbete, eftersom de konsumeras direkt från en plats, väljer du vanligtvis *manuell* reservationsprincip som inte gör några fysiska reservationer eller genererar plockarbete.

## <a name="turn-on-the-feature"></a>Aktivera en funktion

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *produktionskontroll*
- **Funktionsnamn:** *Åsidosätt standardproduktionsreservation*

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Tilldela en policy för produktionsreservation till en artikelmodellgrupp

1. Gå till **Kostnadshantering \> Policyinställningar för lagerredovisning \> Artikelmodellgrupper**.
1. Skapa eller välj en artikelmodellgrupp.
1. På snabbfliken **Lagerpolicyer**, markera kryssrutan **Åsidosätt artikelproduktionsreservation**.
1. I fältet **Reservation**, välj reservationsprincip för objekt som tillhör vald modellgrupp. (Dessa artiklar omfattar artiklar som finns på en strukturlista eller receptrad.)

    - **Manuell** - Artiklar i modellgruppen reserveras inte automatiskt för produktion. De kan dock fortfarande reserveras manuellt efter behov.
    - **Uppskattning** - Artiklar i modellgruppen reserveras fysiskt under uppskattningen av tillverkningsordern.
    - **Schemaläggning** - Artiklar i modellgruppen reserveras fysiskt under schemaläggningen av tillverkningsordern.
    - **Frisläppa** - Artiklar i modellgruppen reserveras fysiskt under frisläppning av tillverkningsordern.
    - **Start** - Artiklar i modellgruppen reserveras fysiskt under start av tillverkningsordern.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Exempel: Använda reservationsprinciper i ett scenario med bulk/paket

Ett material som tillverkats i bulk tillverkas i en 1 000 liters blandning. När bulkmaterialet är klart fylls det av i flera olika påfyllningsstorlekar, där man fyller på flaskor i olika storlekar. När påfyllningen är klar packas flaskorna i lådor. Lådorna packas sedan på lastpallar.

I det här scenariot skapas en batchorder som gör 1 000 liter bulkmaterial. (Den här ordern är bulkordern.) När batchordern är slutförd rapporteras den som färdig till materialindataplatsen för påfyllningen. En batchorder som fyller och paketar varje flaskstorlek skapas sedan. (Dessa order är packorder.) Förpackningsorder har en formel som består av bulkmaterialet, en tom flaska, en etikett och andra förpackningsmaterial. Eftersom bulkmaterialet flödar direkt från lagret till påfyllningen, behövs inget lagerställe arbete för att plocka denna ingrediens och bulkmaterialet förbrukas direkt från inleveransplatsen. Därför ställs reservationsprincipen in till *manuell*. Det andra materialet fasas till ifyllningen genom plockarbete. Därför ställs reservationsprincipen för dessa rader in för *frisläppning* så att reservationen automatiskt inträffar när förpackningsordern frisläpps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]