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
ms.openlocfilehash: a7bfe998d2d787203a507a831c171fc43b03fedc
ms.sourcegitcommit: cc9921295f26804259cc9ec5137788ec9f2a4c6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "4839559"
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

Finance and Operations-appar | Kundengagemangsapp | beskrivning 
---|---|---
[CDS-lagerbehållningsposter](#145) | msdyn_inventoryonhandentries |
[CDS-lagerbehållningsbegäranden](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)

Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.

Finance and Operations-fält | Mappningstyp | Customer Engagement-fält | Standardvärde
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)

Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.

Finance and Operations-fält | Mappningstyp | Customer Engagement-fält | Standardvärde
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]