---
title: Tilldela stegikoner och titlar för mobilappen för Warehouse Management
description: I det här avsnittet beskrivs hur du tilldelar stegikoner och titlar för nya eller anpassade uppgiftsflöden för mobilappen för Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d1d595e7f8ae3cf344c891844845738a4592328eecc326f11e9a2aa0e303785a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733358"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Tilldela stegikoner och titlar för mobilappen för Warehouse Management

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du tilldelar stegikoner och titlar för nya eller anpassade uppgiftsflöden för mobilappen för Warehouse Management.

Följande illustrationer visar hur stegikoner och titlar visas i mobilappen för Warehouse Management.

![Exempel på en stegikon och en stegrubrik i mobilappen för Warehouse Management.](media/step-icon-example.png "Exempel på en stegikon och en stegrubrik i mobilappen för Warehouse Management")

## <a name="turn-on-this-feature-in-your-system"></a>Aktivera funktionen i systemet

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen*

## <a name="standard-step-ids-classes-and-icons"></a>Standardstegs-ID, klasser och ikoner

Varje steg i ett uppgiftsflöde identifieras med ett steg-ID och varje steg-ID har en motsvarande stegklass. Stegikonen och rubriken anges i varje stegklass.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>Steg-ID och stegklasser

I följande register visas alla steg-ID som för närvarande är tillgängliga, och det är motsvarande stegklass. Kontrollnamnet för det primära indatafältet används som steg-ID.

För ett exempel som visar hur dessa steg-ID och klasser används, se implementeringen av metoden `WHSMobileAppStepInfoBuilder.stepId()` i avsnittet [Exempel: Tilldela stegikoner och titlar för ett anpassat flöde](#example) senare i det här ämnet.

| Steg-ID | Stegklass |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Transportföretag | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Bekräftelse | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| PONum | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Potens | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Placera | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Kvantitet | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Vikt | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Tillgängliga stegikoner

Systemet innehåller en samling standardstegsikoner som du också kan använda för dina anpassade steg. Det går inte att föra över anpassade stegikoner. Därför måste du alltid välja en av standardstegikonerna.

I följande tabell visas alla standardstegsikoner som för närvarande är tillgängliga, samt dess namn.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Om stegikon"><br>Om</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Lägg till licens- eller artikelstegsikon"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Stegikon för batchdisposition"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Stegikonen transportföretag"><br>Transportföretag</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Stegikonen tagg för faktisk/nominell vikt"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Stegikonen för vikt tagg för faktisk/nominell vikt"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Stegikonen kontrollsiffra"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Stegikonen checka in eller checka ut ID"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Stegikonen för underordnat ID-nummer"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Stegikon för kluster-ID"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Stegikon för klusterposition"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Stegikon för konfig-ID"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Stegikonen konfiguration av fält"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Stegikonen Con eller LP"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konsolidering från licens- eller ID-stegikonen"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konsolidering till licens- eller ID-stegikonen"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Stegikon för behållartyp"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Stegikonen inventering"><br>Inventering</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Stegikon för inventeringsorsakskoder"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Stegikon för kod för ursprungsland"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Stegikon för disposition"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Stegikonen klart"><br>Klart</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Stegikon för incheckning förare i bekräftelsesteg"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Stegikonen inchecknings-ID förare"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Stegikonen utchecknings-ID förare"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Stegikonen Utgångsdatum"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Stegikonen fält"><br>Fält</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Stegikon från batchdisposition"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Stegikonen lagerstatus"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Stegikon för ID-attribut"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Stegikon för batch-ID för lager"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Stegikon för färg-ID för lager"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Stegikon för lagerplats"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Stegikon för seriell-ID för lager"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Stegikon för storleks-ID för lager"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Stegikonen lagerstatus-ID"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Stegikon för storleks-ID för lager"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Stegikonen lagerversions-ID"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Stegikon för objekt-ID"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Stegikon för ITM behållar-ID"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Stegikon för ITM försändelse-ID"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Stegikon för Kanban-kort-ID"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Stegikon för Kanban eller kort-ID"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Stegikonen för ID-nummer"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Stegikon för last-ID"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Stegikon för position-ID-nummer"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Stegikon för plats- eller ID-nummer"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Stegikon för kontroll av plats- eller ID-nummer"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Stegikon från plats- eller ID-nummer"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Stegikon till plats- eller ID-nummer"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Stegikon för långt process slutförd"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Stegikon för LP-paus överordnad LP"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Stegikon för sammanslå behållar-ID"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Stegikon för blandat ID-radnummer"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Stegikon för utgående vikt"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Stegikon för ägare"><br>Ägare</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Stegikon för överordnat ID-nummer"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Stegikonen bekräfta"><br>Bekräfta gärna</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Stegikonen inköpsorderradnummer"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Stegikonen inköpsordernummer"><br>PONum</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Stegikon för position full"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Stegikon för potens"><br>Potens</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Stegikon för skrivarnamn"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Stegikon för prod-ID"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Stegikon för produktbekräftelse"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Stegikon för placera"><br>Placera</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Stegikon för kluster för artikelinförsel"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Stegikonen kvantitet"><br>Kvantitet</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Stegikonen kvantitetsjustering"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Stegikonen kvantitet kort"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Stegikon för kvantitet som ska förbrukas"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Stegikon för kvantitet som ska placeras"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Stegikon för kvantitet som ska kasseras"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Stegikon för kvantitetsbekräftelse"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Stegikon för rapportera som färdigt"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Stegikon för ta emot plats-ID"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Stegikon för ta bort behållar-ID"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Stegikon RMA-nummer"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Välj orderstegsikon"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Stegikon för orsak till kort plockning"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Stegikon för sorteringsposition"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Stegikonen för målnummer-ID"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Stegikon för radnummer"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Stegikon för till plats"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Stegikon för till nummer"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Stegikon för till lagerställe"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Stegikon för transportlast-ID"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Stegikon för leverantörs-ID för lager"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Stegikon för påfyllnadsetikett-ID"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Stegikon för påfyllnadsetikett kvantitet"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Stegikon för vikt"><br>Vikt</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Stegikon för vikt som ska förbrukas"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Stegikon för WHS-justeringstyp"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Stegikon för WHS-mottagningsundantag"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Stegikon för WMS-plats-ID"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Stegikon för arbets-ID"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Stegikon för arbets-ID för att avbryta"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Stegikon för arbets-ID-nummer"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Stegikon för arbets-ID-nummer för kluster för artikelinförsel"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Stegikon för arbetspool-ID"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Stegikon för zon-ID"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Exempel: Tilldela stegikoner och titlar för ett anpassat flöde

I det här exemplet förklaras hur du ställer in stegikoner och titlar för ett anpassat uppgiftsflöde. Scenariot bygger på ett exempel på ett anpassat uppgiftsflöde som visas och mer ingående i följande bloggpost: [Anpassa mobilappen för lagerhantering](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). Uppgiftsflödet fungerar på följande sätt:

1. I programmet visas en sida där arbetaren måste ange ett behållar-ID (till exempel genom att skanna en streckkod).
1. Om behållar-ID:t är giltigt öppnar programmet en ny sida där arbetaren uppmanas att ange vikten. (Om behållar-ID:t är ogiltigt, returneras arbetaren till första sidan.)
1. När arbetaren anger en giltig vikt lagrar systemet vikten och returnerar arbetaren till första sidan.

Illustrationen nedan visar detta uppgiftsflöde.

![Diagram för uppgiftsflöde.](media/step-icons-example-task-flow.png "Uppgiftsflödesdiagram")

### <a name="create-a-step-class-for-the-container-input-page"></a>Skapa en stegklass för inmatningssidan för behållare

På inmatningssidan för behållare kan arbetaren skanna eller ange ett behållar-ID.

![Inmatningssida för behållare.](media/step-icons-example-container-input.png "Inmatningssida för behållare")

På behållarens inmatningssida är kontrollnamnet för inmatningsfältet `ContainerId`. Eftersom det här kontrollnamnet inte finns i [listan med steg-ID](#step-ids-classes), hittar du inte ett befintligt steg som baseras på det. Därför måste du skapa en stegklass som representerar steget. Här är ett exempel:

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

Identifieraren för stegikonen lagras i `defaultStepIcon` klassmedlemmen och stegtiteln lagras i  `defaultStepTitle` klassmedlemmen.

Om du vill tilldela en stegikon ställer du in `defaultStepIcon` till ett av de ikon_ID som anges i avsnittet [Tillgängliga stegikoner](#step-icons) tidigare i det här ämnet.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Använd en standard- eller anpassad stegikon och rubrik för viktinmatning

På indatasidan för vikt kan arbetaren ange en vikt.

![Viktinmatningssida.](media/step-icons-example-weight-input.png "Viktinmatningssida")

På viktinmatningssidan är kontrollnamnet för inmatningsfältet `Weight`, som finns i [listan med steg-ID](#step-ids-classes). Därför, om stegikonen och titeln som definieras i `WHSMobileAppStepWeight` klass är acceptabelt för dig, du behöver inte ändra någonting för detta steg.

Om du föredrar att använda en annan ikon eller rubrik för det här steget kan du dock åsidosätta metoden `stepId()` eller metoden `stepInfo()` skaparklass. Varje uppgiftsflöde har ett eget steginfoskapare.

#### <a name="override-the-stepid-method"></a>Åsidosätt metoden stepId()

Följande exempel visar ett sätt att ändra en skaparklass genom att åsidosätta `stepId()` metoden.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Du skapar sedan en stegklass för `NewWeight` steget. Koden bör likna koden för `ContainerId` exempel som tidigare visades i det här avsnittet.

#### <a name="override-the-stepinfo-method"></a>Åsidosätt metoden stepInfo()

Följande exempel visar ett sätt att ändra en skaparklass genom att åsidosätta `stepInfo()` metoden.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Sedan skapar du ett `WHSMobileAppStepInfo` objekt och ställer in ikonen och/eller rubriken direkt.

## <a name="additional-resources"></a>Ytterligare resurser

- [Installera och ansluta mobilappen för distributionslagerhantering](install-configure-warehouse-management-app.md)
- [Användarinställningar för mobil enhet](mobile-device-user-settings.md)
