---
title: Importera inkommande ASN:er via V3-datatabellen
description: I denna artikel beskrivs hur du hanterar import av inkommande avancerade leveransmeddelande (ASN) via inkommande ASN-dataentitet.
author: GalynaFedorova
ms.date: 05/11/2022
ms.topic: article
ms.search.form: WHSInboundASNV3Entity, WHSInboundASNEntity, DMFEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ac45e070d0473547c48da1380377de3d4bf60bd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907128"
---
# <a name="import-inbound-asns-through-the-v3-data-entity"></a>Importera inkommande ASN:er via V3-datatabellen

[!include [banner](../../includes/banner.md)]

Avancerade leveransmeddelanden (ASN) meddelar dig om leverantörsleveranser. De hjälper avsändaren att beskriva innehållet i en försändelse och ytterligare information om den, till exempel artiklar och förpackningar.

ASN kan hjälpa lagerarbetare att ta reda på vad som inkommer när. Därför kan de förbereda sig. Lagerarbetare kan dessutom använda ASN för att matcha detaljer för en försändelse med den relaterade inköpsorder som tidigare skapades.

I denna artikel finns en samling scenarier som med exempel visar hur du arbetar med ASN-filer.

> [!IMPORTANT]
> *Inkommande ASN*-import gäller bara för artiklar som är aktiverade för avancerad Warehouse management (WMS). Innan du får ett ASN måste en inköpsorder registreras i systemet mot leverantören som skickar detta ASN.

## <a name="inbound-asn-v3-entity"></a>Inkommande ASN V3-entitet

Du importerar inkommande ASN med hjälp av den *inkommande ASN V3* sammansatta dataentiteten. *Inkommande ASN V3* drar nytta av följande enheter:

- Rubrik för inkommande last
- Rubrik för inkommande leverans
- Inkommande beläggning av packningsstrukturer
- Kollin i packningsstruktur för inkommande last
- Rader med kollin i packningsstruktur för inkommande last
- Inkommande beläggning av packningsstrukturrader

*Inkommande ASN V3* sammansatta dataenhet är avsedd för asynkrona integreringsscenarier där XML-filbaserade importer används.

## <a name="xml-format-for-importing-asns"></a>XML-format för import av ASN

Microsoft Dynamics 365 Supply Chain Management stöder följande XML-format för import av ASN. Varje nod i XML-filen representerar ett attribut från en enskild enhet.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV3Entity>
                    </WHSInboundPackingStructureCaseLineV3Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV3Entity>
                </WHSInboundLoadPackingStructureLineV3Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a>Exempel

Följande delgrupper ger exempel på ASN XML-importfiler för leverantörsförsändelser.

### <a name="example-1"></a>Exempel 1

I följande exempel visas en XML-fil för import av leverantörsförsändelser för en inköpsorder när det inte finns några ärendedetaljer.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a>Exempel 2

I följande exempel visas en XML-fil för import av leverantörsförsändelser för en inköpsorder när det finns några ärendedetaljer.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLine3Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a>Exempel 3

I följande exempel visas en XML-fil för import av leverantörsförsändelser för flera inköpsorder när det finns några ärendedetaljer.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Inspektera resultaten av importen av en ASN-fil

Följ dessa steg om du vill kontrollera resultaten av importen av en ASN-fil.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Sök efter och öppna en inläsning som har skapats som en del av en ASN-import.
1. På snabbfliken **Last** ska du se värden som baseras på XML-filen.
1. På snabbfliken **Lastrader** bör du se inköpsordernummer och artikelinformation som baseras på XML-filen.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Ta emot**, välj **förpackningsstruktur** om du vill granska lastens förpackningsstruktur.
1. På snabbfliken **Lastpallar** ska du se ID-nummer som baseras på XML-filen.
1. På snabbfliken **Ärenden** ska du se ärenden som baseras på XML-filen.
1. På snabbfliken **Objekt** ska du se objekt och kvantiteter som baseras på XML-filen.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
