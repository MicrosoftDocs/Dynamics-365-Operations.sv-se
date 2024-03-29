---
title: Ställa in klusterplockning
description: Denna artikel beskriver hur du konfigurerar klusterplockning och hur du tillämpar artikelbekräftelse med klusterplockning.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ec3de073def2ff63af3c04b5696cbcec4f09948
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014775"
---
# <a name="set-up-cluster-picking"></a>Ställa in klusterplockning

[!include[banner](../includes/banner.md)]

I denna artikel beskrivs hur du möjliggör för en arbetare att använda sin mobila enhet för att gruppera plockningarbete till kluster, så att de kan plocka artiklar från en enda plats för flera arbetsordrar samtidigt. Detta kallas *klusterplockning*.

## <a name="about-cluster-picking"></a>Om klusterplockning

När arbetsorder har frisläppts till lagerstället kan arbetare använda en mobil enhet för att tilldela order till ett kluster. Klustret ordnar plockningsarbetet för arbetaren. När en arbetsorder tilldelas ett kluster, måste arbetaren använda klusterplockning för att utföra plockningsarbetet för ordern. Arbetaren kan inte använda andra plockningsmetoder. Om en arbetsorder tilldelas ett kluster av misstag måste arbetaren bryta klustret och sedan återskapa det.

Om det behövs kan en anställd skicka ett kluster till en annan arbetare. Detta ändrar klusterstatus till Klarat. När arbetstagaren använder en mobil enhet för att ange att plockningen och det inlagrade arbetet är slutfört måste leveransen eller lasten bekräftas i klienten.

## <a name="enable-cluster-picking"></a>Aktivera klusterplockning

Om du vill aktivera klusterplockning måste du konfigurera följande:

- **Klusterprofiler** – Ange om kluster-ID:n ska genereras automatiskt, antalet positioner som ska användas, när kluster ska brytas och plockarbetet ska ordnas och verifieras.

- **Arbetsmallar** – Ange hur plockningsarbetet för klusterplockning ska skapas.

- **Platsdirektiv** – Ange var artiklar ska plockas ifrån och var du vill placera dem.

- **Menyalternativ på mobil enhet** – Konfigurera ett menyalternativ för mobila enheter för att använda befintligt arbete som dirigeras av klusterplockning. Du måste sedan lägga till menykommandot på en meny för mobil enhet så att det visas på mobila enheter.

- **Parametrar för lagerstyrning** – Ange nummerserien som ska användas, om du vill generera identifierare för kluster.

## <a name="set-up-a-cluster-profile"></a>Ställa in en klusterprofil

Så här ställer du in en klusterprofil:

1. Klicka på **Lagerstyrning** \> **Inställningar** \> **Mobil enhet** \>  **Klusterprofiler**.

1. Klicka på **Ny** om du vill skapa en ny profil.

1. Klicka på **Skapa kluster** och under **Klustersortering**, klickar du på **Ny** för att konfigurera sorteringskriterier för klustret. Sorteringskriteriet kontrollerar den följd i vilken arbetaren ska utföra plockningsarbetet. Du kan lägga till så många villkor du vill.

1. I fältet **Sekvensnummer** anger du ett värde som definierar i vilken ordning sorteringskriterierna ska bearbetas.

1. Markera fältet som fastställer sorteringen i fältet **Fältnamn**. Om du till exempel väljer fältet **WMSLocationId** kommer arbetet att sorteras efter plats.

1. Välj ett av följande alternativ i fältet **Sortering**.

| **Alternativ**     | **Beskrivning**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Stigande**  | Plockningsarbete sorteras i en stigande ordning som baseras på sorteringskriteriet. Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 4 först. |
| **Fallande** | Plockningsarbete sorteras i en fallande ordning som baseras på sorteringskriteriet. Om du till exempel använder fältet **WMSLocationId** som sorteringsvillkor och dina plats-ID:n är 1, 2, 3 och 4 ska du plocka från plats 1 först. |

## <a name="item-confirmation"></a>Artikelbekräftelse

När klusterplockning används, är objektbekräftelse avgörande för att kontrollera de objekt som läggs till ett kluster. Du kan kontrollera objekt i klusterplockning vid klusterplockningsprocessen. Inställningen är baserad på inställning av produktstreckkoder.

### <a name="set-up-item-verification-with-cluster-picking"></a>Ställa in objektverifiering med klusterplockning

1. Gå till **Lagerstyrning** > **Inställningar** > **Mobil enhet** > **Menyalternativ på mobil enhet**.
1. I listrutan väljer du menyalternativet du vill ställa in.
1. I åtgärdsfönstret, välj **Inställningar för arbetsbekräftelse**.
1. Gör något av följande åtgärd:
    - Om det redan finns en rad för **arbetstypen** du vill ställa in väljer du den och sedan **Redigera** i åtgärdsfönstret.
    - Om det inte finns någon lämplig rad väljer du **Ny** i åtgärdsfönstret och ställer sedan in **arbetstypen** på lämplig typ.
1. Markera kryssrutan **Produkt bekräfta** för din nya eller valda rad. Detta gör det möjligt för arbetare att verifiera varje del av inventeringen med hjälp av den mobila enheten.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]