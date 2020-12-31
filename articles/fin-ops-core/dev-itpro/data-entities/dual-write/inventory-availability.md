---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I det här avsnittet finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4457443"
---
# <a name="inventory-availability-in-dual-write"></a>Lagertillgänglighet vid dubbelriktad skrivning

[!include [banner](../../includes/banner.md)]

Genom lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt sida **Offerter**, **Order** eller **Fakturor** i Microsoft Dynamics 365 Sales. Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md).

Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser. Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.

## <a name="on-hand-inventory"></a>Lagerbehållning

I Dynamics 365 Sales, en ny knapp **Lagerbehållning** har lagts till i rubriken på sidorna **Offerter**, **Order** och **Fakturor**. När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för. I den här dialogrutan visas samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

Dialogrutan returnerar lagerinformationen från Dynamics 365 Supply Chain Management. I den här information beskrivs följande kvantiteter:

- Lagerbehållning
- Reserverad lagerbehållning
- Tillgänglig lagerbehållning
- Beställd kvantitet
- Kvantitet som har beställts
- Reserverad beställd kvantitet
- Total tillgänglig kvantitet

## <a name="atp-information"></a>Information om ATP

Vid försäljning har en ny knapp **ATP-information** har lagts till i radartikal på sidor **offerter**, **order** och **fakturor**. När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet. Den här dialogrutan har samma inställningar som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

Dialogrutan returnerar ATP-information från Supply Chain Management. I den här information beskrivs följande kvantiteter:

- Kvantitet för ATP
- Inleveranskvantitet
- Utleveranskvantitet
- Lagerbehållning
