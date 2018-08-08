---
title: "Ställa in klusterplockning"
description: "Det här avsnittet beskriver hur du konfigurerar klusterplockning och hur du tillämpar artikelbekräftelse med klusterplockning."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2ec0890963b2b01407acac8003453faf370894b4
ms.openlocfilehash: 1c23421ddfda8c5f6fa27a31831a00ead6094db9
ms.contentlocale: sv-se
ms.lasthandoff: 04/11/2018

---

[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a>Ställa in klusterplockning

I det här avsnittet beskrivs hur du möjliggör för en arbetare att använda sin mobila enhet för att gruppera plockningarbete till kluster, så att de kan plocka artiklar från en enda plats för flera arbetsordrar samtidigt. Detta kallas *klusterplockning*.

## <a name="about-cluster-picking"></a>Om klusterplockning

När arbetsorder har frisläppts till lagerstället kan arbetare använda en mobil enhet för att tilldela order till ett kluster. Klustret ordnar plockningsarbetet för arbetaren. När en arbetsorder tilldelas ett kluster, måste arbetaren använda klusterplockning för att utföra plockningsarbetet för ordern. Arbetaren kan inte använda andra plockningsmetoder. Om en arbetsorder tilldelas ett kluster av misstag måste arbetaren bryta klustret och sedan återskapa det.

Om det behövs kan en anställd skicka ett kluster till en annan arbetare. Detta ändrar klusterstatus till Klarat. När arbetstagaren använder en mobil enhet för att ange att plockningen och det inlagrade arbetet är slutfört måste leveransen eller lasten bekräftas i Dynamics 365 for Finance and Operations-klienten.

## <a name="set-up-cluster-picking"></a>Ställa in klusterplockning

Om du vill aktivera klusterplockning måste du ställa in följande:

-   **Klusterprofiler** – Ange om kluster-ID:n ska genereras automatiskt, antalet positioner som ska användas, när kluster ska brytas och plockarbetet ska ordnas och verifieras.

-   **Arbetsmallar** – Ange hur man skapar plockningsarbetet för klusterplockning.

-   **Platsdirektiv** – Ange var artiklar ska plockas från och var du vill placera dem.

-   **Menyalternativ på mobil enhet** – Konfigurera ett menyalternativ för mobila enheter för att använda befintligt arbete som dirigeras av klusterplockning. Du måste sedan lägga till menykommandot på en meny för mobil enhet så att det visas på mobila enheter.

-   **Parametrar för lagerstyrning** – Ange nummerserien som ska användas, om du vill generera identifierare för kluster.

## <a name="set-up-a-cluster-profile"></a>Ställa in en klusterprofil

Så här ställer du in en klusterprofil:

1.  Klicka på **lagerstyrning**\>**inställningar**\>**mobiltelefon**\>**klusterprofiler**.

2.  Klicka på **Ny** om du vill skapa en ny profil.

3.  Klicka på **Skapa kluster** och under **Klustersortering**, klickar du på **Ny** för att ställa in sorteringskriterier för klustret. Sorteringskriteriet kontrollerar den följd i vilken arbetaren ska utföra plockningsarbetet. Du kan lägga till så många villkor du vill.

4.  I fältet **Sekvensnummer** anger du ett nummer som definierar i vilken ordning som sorteringskriteriet ska bearbeta.

5.  Markera fältet som fastställer sorteringen i fältet **Fältnamn**. Om du till exempel väljer fältet **WMSLocationId** kommer arbetet att sorteras efter plats.

6.  Välj ett av följande alternativ i fältet **Sortering**.

| **Alternativ**     | **Beskrivning**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Stigande**  | Plockningsarbete sorteras i en stigande ordning som baseras på sorteringskriteriet. Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 4 först. |
| **Fallande** | Plockningsarbete sorteras i en fallande ordning som baseras på sorteringskriteriet. Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 1 först. |

## <a name="item-confirmation"></a>Artikelbekräftelse

När klusterplockning används, är objektbekräftelse avgörande för att kontrollera de objekt som läggs till ett kluster. Du kan kontrollera objekt i klusterplockning vid klusterplockningsprocessen. Inställningen är baserad på inställning av produktstreckkoder.

### <a name="set-up-item-verification-with-cluster-picking"></a>Ställa in objektverifiering med klusterplockning

1.  I den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: **Lagerstyrning** \> **Lagerstyrning** \> **Inställningar** \> **Mobil enhet** \> **Mobila enhetens menyalternativ**.

2.  Från mobila enhetens menyalternativ öppnar du **Inställning av arbetsbekräftelse**. Alternativet **Produktbekräftelse** låter dig kontrollera varje lagerenhet från den mobila enheten när du har skannat.

