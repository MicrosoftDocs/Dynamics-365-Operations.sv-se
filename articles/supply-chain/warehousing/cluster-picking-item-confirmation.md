---
title: Produktbekräftelse för klusterplockning
description: Det här avsnittet beskriver hur du konfigurerar artikelverifiering tillsammans med klusterplockning.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272c3a13b68e2b862faf20cc269ca790322b61de
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367302"
---
# <a name="product-confirmation-for-cluster-picking"></a>Produktbekräftelse för klusterplockning

[!include [banner](../includes/banner.md)]

Klusterplockning kan du plockar artiklar för flera order samtidigt. När klusterplockning används, är objektbekräftelse avgörande för att kontrollera de objekt som läggs till ett kluster. Du kan kontrollera objekt i klusterplockning vid klusterplockningsprocessen.

## <a name="where-it-applies"></a>När det gäller

Objektverifiering för klusterplockning fungerar på samma sätt som när du kontrollerar objekt i en icke-klusterplockningsprocess. Inställningen är baserad på inställning av produktstreckkoder.

## <a name="set-up-item-verification-with-cluster-picking"></a>Ställa in objektverifiering med klusterplockning

1. På den mobila enhetens menyalternativ öppnar du inställningsformuläret för arbetsbekräftelse: **lagerstyrning** > **lagerstyrning** > **inställningar** > **mobil enhet** > **mobila enhetens menyalternativ**.
1. Från mobila enhetens menyalternativ öppnar du **Inställning av arbetsbekräftelse**.

|        Alternativ        |                                    beskrivning                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Produktbekräftelse | Låter dig kontrollera varje lagerenhet från den mobila enheten när du har skannat. |
