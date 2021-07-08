---
title: Importera inkommande ASN via V2-dataenheten
description: I det här avsnittet beskrivs hur du hanterar import av inkommande avancerade leveransmeddelande (ASN) via inkommande ASN V2-dataenhet.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249171"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="3ce21-103">Importera inkommande ASN via V2-dataenheten</span><span class="sxs-lookup"><span data-stu-id="3ce21-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ce21-104">Avancerade leveransmeddelanden (ASN) meddelar dig om leverantörsleveranser.</span><span class="sxs-lookup"><span data-stu-id="3ce21-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="3ce21-105">De hjälper avsändaren att beskriva innehållet i en försändelse och ytterligare information om den, till exempel artiklar och förpackningar.</span><span class="sxs-lookup"><span data-stu-id="3ce21-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="3ce21-106">ASN kan hjälpa lagerarbetare att ta reda på vad som inkommer när.</span><span class="sxs-lookup"><span data-stu-id="3ce21-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="3ce21-107">Därför kan de förbereda sig.</span><span class="sxs-lookup"><span data-stu-id="3ce21-107">Therefore, they can prepare.</span></span> <span data-ttu-id="3ce21-108">Lagerarbetare kan dessutom använda ASN för att matcha detaljer för en försändelse med den relaterade inköpsorder som tidigare skapades.</span><span class="sxs-lookup"><span data-stu-id="3ce21-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="3ce21-109">I det här avsnittet finns en samling scenarier som kan visas, till exempel hur du arbetar med ASN-filer.</span><span class="sxs-lookup"><span data-stu-id="3ce21-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ce21-110">*Inkommande ASN*-import gäller bara för artiklar som är aktiverade för avancerad Warehouse management (WMS).</span><span class="sxs-lookup"><span data-stu-id="3ce21-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="3ce21-111">Innan du får ett ASN måste en inköpsorder registreras i systemet mot leverantören som skickar detta ASN.</span><span class="sxs-lookup"><span data-stu-id="3ce21-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="3ce21-112">Inkommande ASN V2-entitet</span><span class="sxs-lookup"><span data-stu-id="3ce21-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="3ce21-113">Du importerar inkommande ASN med hjälp av den *inkommande ASN V2* sammansatta dataenheten.</span><span class="sxs-lookup"><span data-stu-id="3ce21-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="3ce21-114">*Inkommande ASN V2* drar nytta av följande enheter:</span><span class="sxs-lookup"><span data-stu-id="3ce21-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="3ce21-115">Rubrik för inkommande last</span><span class="sxs-lookup"><span data-stu-id="3ce21-115">Inbound load header</span></span>
- <span data-ttu-id="3ce21-116">Rubrik för inkommande leverans</span><span class="sxs-lookup"><span data-stu-id="3ce21-116">Inbound shipment header</span></span>
- <span data-ttu-id="3ce21-117">Inkommande beläggning av packningsstrukturer</span><span class="sxs-lookup"><span data-stu-id="3ce21-117">Inbound load packing structures</span></span>
- <span data-ttu-id="3ce21-118">Kollin i packningsstruktur för inkommande last</span><span class="sxs-lookup"><span data-stu-id="3ce21-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="3ce21-119">Rader med kollin i packningsstruktur för inkommande last</span><span class="sxs-lookup"><span data-stu-id="3ce21-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="3ce21-120">Inkommande beläggning av packningsstrukturrader</span><span class="sxs-lookup"><span data-stu-id="3ce21-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="3ce21-121">*Inkommande ASN V2* sammansatta dataenhet är avsedd för asynkrona integrationsscenarier där XML-filbaserade importer används.</span><span class="sxs-lookup"><span data-stu-id="3ce21-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="3ce21-122">XML-format för import av ASN</span><span class="sxs-lookup"><span data-stu-id="3ce21-122">XML format for importing ASNs</span></span>

<span data-ttu-id="3ce21-123">Microsoft Dynamics 365 Supply Chain Management stöder följande XML-format för import av ASN.</span><span class="sxs-lookup"><span data-stu-id="3ce21-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="3ce21-124">Varje nod i XML-filen representerar ett attribut från en enskild enhet.</span><span class="sxs-lookup"><span data-stu-id="3ce21-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="3ce21-125">Exempel</span><span class="sxs-lookup"><span data-stu-id="3ce21-125">Examples</span></span>

<span data-ttu-id="3ce21-126">Följande delgrupper ger exempel på ASN XML-importfiler för leverantörsförsändelser.</span><span class="sxs-lookup"><span data-stu-id="3ce21-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="3ce21-127">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="3ce21-127">Example 1</span></span>

<span data-ttu-id="3ce21-128">I följande exempel visas en XML-fil för import av leverantörsförsändelser för en inköpsorder när det inte finns några ärendedetaljer.</span><span class="sxs-lookup"><span data-stu-id="3ce21-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="3ce21-129">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="3ce21-129">Example 2</span></span>

<span data-ttu-id="3ce21-130">I följande exempel visas en XML-fil för import av leverantörsförsändelser för en inköpsorder när det finns några ärendedetaljer.</span><span class="sxs-lookup"><span data-stu-id="3ce21-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="3ce21-131">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="3ce21-131">Example 3</span></span>

<span data-ttu-id="3ce21-132">I följande exempel visas en XML-fil för import av leverantörsförsändelser för flera inköpsorder när det finns några ärendedetaljer.</span><span class="sxs-lookup"><span data-stu-id="3ce21-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="3ce21-133">Inspektera resultaten av importen av en ASN-fil</span><span class="sxs-lookup"><span data-stu-id="3ce21-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="3ce21-134">Följ dessa steg om du vill kontrollera resultaten av importen av en ASN-fil.</span><span class="sxs-lookup"><span data-stu-id="3ce21-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="3ce21-135">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="3ce21-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="3ce21-136">Sök efter och öppna en inläsning som har skapats som en del av en ASN-import.</span><span class="sxs-lookup"><span data-stu-id="3ce21-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="3ce21-137">På snabbfliken **Last** ska du se värden som baseras på XML-filen.</span><span class="sxs-lookup"><span data-stu-id="3ce21-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="3ce21-138">På snabbfliken **Lastrader** bör du se inköpsordernummer och artikelinformation som baseras på XML-filen.</span><span class="sxs-lookup"><span data-stu-id="3ce21-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="3ce21-139">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Ta emot**, välj **förpackningsstruktur** om du vill granska lastens förpackningsstruktur.</span><span class="sxs-lookup"><span data-stu-id="3ce21-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="3ce21-140">På snabbfliken **Lastpallar** ska du se ID-nummer som baseras på XML-filen.</span><span class="sxs-lookup"><span data-stu-id="3ce21-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="3ce21-141">På snabbfliken **Ärenden** ska du se ärenden som baseras på XML-filen.</span><span class="sxs-lookup"><span data-stu-id="3ce21-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="3ce21-142">På snabbfliken **Objekt** ska du se objekt och kvantiteter som baseras på XML-filen.</span><span class="sxs-lookup"><span data-stu-id="3ce21-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
