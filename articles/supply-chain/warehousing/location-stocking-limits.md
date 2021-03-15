---
title: Lagringsbegränsningsplats
description: I det här avsnittet beskrivs funktionerna för lagerplatsgränser.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e0adb9d05f0db9bbfe6bfbe72564a4e5e839f163
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004586"
---
# <a name="location-stocking-limits"></a>Lagringsbegränsningsplats

[!include [banner](../includes/banner.md)]

Du kan använda sidan **Lagringsbegränsningsplats** (**Hantering av distributionslager \> Inställningar \> Lagerställe \> Lagringsbegränsningsplats**) för att styra lastkapaciteten på lagerplatser utan att behöva använda de mer avancerade processerna för volymberäkningar av fysiska produkter.

Syftet med lagringsgränser för plats är att utvärdera den högsta kvantiteten som en plats kan innehålla. Du kan ställa in funktionen på någon av tre nivåer, som var och en har sin egen flik på sidan **lagerplatsgränser**:

- Produkter
- Produktvarianter
- Behållartyper

För varje nivå kan du definiera olika fältvärden. Systemet kommer sedan att utvärdera kapaciteten för en viss plats, baserat på värden **kvantitet** och **enhet** för varje rad. Den mest detaljerade matchande posten kommer först att väljas. En rad som har ett värde i fältet **platsprofil-ID** kommer att utvärderas innan en rad som bara har ett värde i fältet **lagerställe**. Den återstående kapaciteten utvärderas också utifrån **kvantiteten** för den platsgränspost för lagerställe som används.

I avsnittet **produkter** på sidan kan du definiera följande fältvärden för sökningen efter lagerställegränser:

- Lagerställe
- Platsprofil-ID
- Plats
- Kategori-ID för packningsstorlek
- Artikelnummer
- Enhet

> [!NOTE]
> Du behöver inte definiera ett värde för **enhet** för varje lagerställegränspost. Beräkningarna av lagerställe kapacitet baseras på kvantiteterna i lagerenheten. Om ingen enhetskonvertering har definierats för ett värde som används, hoppas posten för lagringsplatsgränsen över, som om ett annat värde för **artikelnummer** har definierats för den.

## <a name="example--purchase-order-receiving"></a>Exempel - Inleverans av inköpsorder

Det här exemplet är baserat på en ren *USMF* demodatauppsättning, där följande värden anges på fliken **produktvarianter** på sidan **Lagringsbegränsningsplats**.

| Lagerställe | Platsprofil-ID | Artikelnummer | Storlek | Kvantitet | Enhet |
|-----------|---------------------|-------------|------|----------|------|
| 24        | VÅNING               | D0013       | M    | 300      | Ea   |
| 24        | VÅNING               | D0013       | L    | 240      | Ea   |
| 24        | VÅNING               | D0013       | L    | 360      | Ea   |

Olika måttenheter för produktvarianter ställs in för produkterna. Dessa varianter justeras mot platsens lagergränser för tre lastpallar (PL):

- **Storlek M:** 1 PL = 100 var (Ea)
- **Storlek L:** 1 PL = 80 Ea
- **Storlek S:** 1 PL = 120 Ea

Därför kan varje plats där värdet **Platsprofil-ID** är inställt på *VÅNING* kan innehålla *3* *PL* av artikelnumret *D0013*.

### <a name="prepare-for-the-example"></a>Förbereda exemplet

I det här exemplet ska du köra ett flöde för inköpsorder mottagning för två rader. Du måste dock först uppdatera demonstrationsdata på följande sätt för att se till att blandade artiklar kan transporteras, utan bara de tomma platserna *FL-002* till *FL-004* och det finns inget öppet, inkommande arbete.

1. För plats *FL-001* ändrar du värdet i fältet **Platsprofil** från *VÅNING* till *VÅNING-05*.
1. För platsprofilen *VÅNING* ange alternativet **Tillåt blandade artiklar** till *Ja*.
1. Skapa en inköpsorder som har följande två rader.

    | Lagerställe | Artikelnummer | Storlek | Kvantitet | Enhet |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | L    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Bearbeta exemplet

Du får först en kvantitet på *4* av enhet *PL* i storleken *S*, och sedan granska placeringsrad platserna för det arbete som skapas. Du får sen en kvantitet på *4* av enhet *PL* i storleken *L*, och sedan granska placeringsrad platserna för det arbete som skapas.

1. I distributionslagerappen, logga in med *24* som användar-ID och *1* som lösenord.
1. Välj **inkommande** \> **inleverans av inköp**.
1. Ta emot *4* *PL* av artikelnummer *D0013* i storlek *S*.
1. Granska det artikelinförselarbete som har skapats. Du bör se följande resultat:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Ta emot *4* *PL* av artikelnummer *D0013* i storlek *L*.
1. Granska det artikelinförselarbete som har skapats. Du bör se följande resultat:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

Utifrån resultaten kan du komma fram till att systemet inte kunde allokera rätt inlagringsplatsen. I annat fall lägger systemet bara till *1* *PL* med storleken *L* till platsen *FL-003* i det sista steget, inte *2* *PL*? Det vill säga varför finns det inte sammanlagt *3* *PL* för artikelinförsel till den platsen?

För att förklara felet måste du förstå urvalskriterierna för platsens lagergränser. Systemet väljer den mest detaljerade matchande posten. I det här exemplet är den mest detaljerade matchande posten raden där värdet för **Storlek** är *L*, värdet **Kvantitet** är *240* och värdet **Enhet** är *Ea*. Eftersom du redan har öppet arbete från föregående inleverans av en kvantitet på *120* *Ea* med storleken *S*, beräknas den återstående kapaciteten som *240* – *120* = *120* *Ea*. Den återstående kapaciteten kan därför bara ha *1* *PL* *80* *Ea*.

> [!NOTE]
> Du kan inte använda platslagergränser för att t.ex. styra påfyllningen av artiklar som har olika kvantiteter på samma plats. Använd i så fall en *återanskaffningsmall*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]