---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I den här artikeln finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 442486550d3a7c5132e26f663caaa7c2c02eeb6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289221"
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

## <a name="how-it-works"></a>Hur det fungerar

När du väljer knappen **Lagerbehållning** på sidan **Offerter**, **Order** eller **Fakturor** görs ett liveanrop med dubbel avskrivning till API för **Lagerbehållning**. API:t beräknar lagerbehållningen för den angivna produkten. Resultatet lagras i tabellerna **InventCDSInventoryOnHandRequestEntity** och **InventCDSInventoryOnHandEntryEntity** och skrivs sedan till Dataverse via dubbelriktad skrivning. Om du vill använda den här funktionen måste du köra följande mappningar: Hoppa över ursprunglig synkronisering när du kör kartorna.

- CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)
- CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Mallar

Följande mallar är tillgängliga för utsätter lagerdata.

Finance and Operations-appar | Kundengagemangsappar     | beskrivning
---|---|---
[CDS-lagerbehållningsposter](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[CDS-lagerbehållningsbegäranden](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
