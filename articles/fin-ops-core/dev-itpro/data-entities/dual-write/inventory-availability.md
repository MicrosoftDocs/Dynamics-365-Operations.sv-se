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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426992"
---
# <a name="inventory-availability"></a>Lagertillgänglighet

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Med hjälp av lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt i formulären **Offerter**, **Order** eller **Fakturor** i modellstyrda appar i Dynamics 365. Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md). Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser. Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.

## <a name="on-hand-inventory"></a>Lagerbehållning 

I rubriken på formulären **Offerter**, **Order** eller **Fakturor** i Dynamics 365 Sales läggs en ny knapp för **Lagerbehållning** till. När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för. Den returnerar lagerinformationen från Dynamics 365 Supply Chain Management och visar samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md). Informationen omfattar följande kvantiteter:

- **Lagerbehållning**
- **Reserverad lagerbehållning**
- **Tillgänglig lagerbehållning**
- **Orderkvantitet**
- **Kvantitet som har beställts**
- **Reserverad beställd kvantitet**
- **Total tillgänglig kvantitet**

## <a name="atp-information"></a>Information om ATP

Online artiklar i formulären **Offerter**, **Order** eller **Fakturor** i Dynamics 365 Sales läggs en ny knapp för **ATP-information** till. När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet. Den returnerar **ATP-information** från Supply Chain Management och visar inställningarna som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). Informationen innehåller **ATP-kvantitet**, **inleveranskvantitet**, **utleveranskvantitet** och **lagerbehållning**.
