---
title: API:er för Handel-prissättning
description: Denna artikel beskriver olika prissättnings-API:er som anges i Microsoft Dynamics 365 Commerce prissättningsmotor.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294133"
---
# <a name="commerce-pricing-apis"></a>API:er för Handel-prissättning

[!include [banner](../includes/banner.md)]

Denna artikel beskriver olika prissättnings-API:er som anges i Microsoft Dynamics 365 Commerce prissättningsmotor.

Prissättningsmotorn Dynamics 365 Commerce innehåller följande Retail Server-API:er som kan förbrukas av externa program som ett stöd för olika prissättningsscenarier:

- **GetActivePrices** – Detta API får en produkts beräknade pris, inklusive enkla rabatter.
- **CalculateSalesDocument** – Detta API beräknar priser och rabatter för produkter vid givna kvantiteter om de köps tillsammans.
- **GetAvailablePromotions** – Detta API får tillämpliga rabatter för produkter i vagnen. 
- **AddCoupons** – Detta API lägger till kuponger i en vagn.
- **RemoveCoupons** – Denna API tar bort kuponger från en vagn.

Mer information om hur du använder Retail Server-API:er i externa program finns i [Använda Retail Server API:er i externa program](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

API:et *GetActivePrices* finns i Commerce version 10.0.4. Detta API får en produkts beräknade pris, inklusive enkla rabatter. Det beräknas inte av flerradsrabatter och det förutsätter att varje produkt i en API-begäran har kvantiteten 1. Detta API kan också ta en lista över produkter som indata och fråga priset på enskilda produkter på en gång.

API *GetActivePrices* har stöd för Commerce-rollerna **Medarbetare**, **Kund**, **Anonym** och **Program**.

Det huvudsakliga användningsfallet för *GetActivePrices*-API :n är sidan för produktinformation (PDP), där återförsäljare vill få fram det bästa priset för en produkt, bland annat gällande rabatter.

Följande tabell visar indataparametrarna för API *GetActivePrices*.

| Namn                                    | Undernamn | Typ | Obligatorisk/valfri | Beskrivning |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Obligatoriskt | |
|                                         | ChannelId | lång | Obligatoriskt | |
|                                         | CatalogId | lång | Obligatoriskt | |
| productIds                              | | IEnumerable\<long\> | Obligatoriskt | Listan med produkter som priserna ska beräknas för. |
| activeDate                              | | DateTimeOffset | Obligatoriskt | Det datum då priserna beräknas. |
| customerId                              | | sträng | Valfritt | Kundkontonummer. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Valfritt | Anknytningsnivå och lojalitetsnivåer. |
|                                         | AffiliationId | lång | Obligatoriskt | Anknytnings-ID. |
|                                         | LoyaltyTierId | lång | Valfritt | ID för lojalitetsnivån. |
| includeSimpleDiscountsInContextualPrice | | bool | Valfritt | Ange att den här parametern ska vara **sann** om du vill inkludera enkla rabatter i prissättningsberäkningen. Standardvärdet är **falskt**. |
| includeVariantPriceRange                | | bool | Valfritt | Sätt denna parameter till **sant** för att få lägsta och högsta pris bland alla varianter av en huvudprodukt. Standardvärdet är **falskt**. |
| includeAttainablePricesAndDiscounts     | | bool | Valfritt | Ange denna parameter till **sant** för att få möjliga priser och rabatter. Standardvärdet är **falskt**. |

**Exempelbegärantext**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Exempelsvarstext**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

API:et *CalculateSalesDocument* finns i Commerce version 10.0.25. Detta API beräknar priser och rabatter för produkter vid givna kvantiteter om de köps tillsammans i en order. Prisberäkningen bakom API *CalculateSalesDocument* tar hänsyn till både enradsrabatter och flerradsrabatter.

Huvudanvändningen för *CalculateSalesDocument* API är prisberäkningen i scenarier där den fullständiga vagnen inte finns kvar (till exempel försäljningsofferter). Scenarier i kassan (POS) och Commerce e-handel kan också dra fördel av detta användningsfall. Ett lägre totalpris när artiklar i vagnen beräknas som en uppsättning (till exempel för diskreta buntar, länkade eller rekommenderade produkter eller produkter som redan har lagts till i kundvagnen) kan eventuellt hjälpa kunder att lägga till produkter i kundvagnen.

Datamodellen för både begäran och svaret från *CalculateSalesDocument* API är **kundvagn**. Inom detta API får dock datamodellen namnet **SalesDocument**. Eftersom de flesta egenskaper är valfria, och bara några av dem påverkar prissättningen, visas endast prissättningsrelaterade fält i följande tabell. Vi rekommenderar inte att andra fält används i API-begäran.

Omfattningen av API *CalculateSalesDocument* är bara beräkningen av priser och rabatter. Skatter och avgifter är inte inblandade.

I följande tabell visas indataparametrarna i objektet som kallas **salesDocument**.

| Namn             | Undernamn | Typ | Obligatorisk/valfri | Beskrivning |
|------------------|----------|------|-------------------|-------------|
| ID               | | sträng | Obligatoriskt | Identifierar för försäljningsdokument. |
| CartLines        | | IList\<CartLine\> | Valfritt | Listan med rader som priser och rabatter ska beräknas för. |
|                  | Produkt-ID | lång | Nödvändig inom CartLine | Produktpost-ID. |
|                  | ItemId | sträng | Valfritt | Artikelidentifierare. Om ett värde anges måste det matcha värdet för parametern **ProductId**. |
|                  | InventoryDimensionId | sträng | Valfritt | Identifierar lagerdimension. Om ett värde anges måste kombinationen av **ItemId**- och **InventoryDimensionId**-värden matcha värdet för parametern **ProductId** . |
|                  | Antal | decimal | Nödvändig inom CartLine | Kvantiteten för prodkten |
|                  | UnitOfMeasureSymbol | sträng | Valfritt | Produktens enhet. Om ett värde inte anges använder API:t som standard produktens försäljningsenhet. |
| CustomerId       | | sträng | Valfritt | Kundkontonummer. |
| LoyaltyCardId    | | sträng | Valfritt | Identifierare för bonuskortet. Alla kundkonto som är associerade med förmånskortet måste matcha värdet för **CustomerId**-parametern (om detta finns). Förmånskortet beaktas inte om det inte hittas eller om dess status är **Spärrad**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Valfritt | Anknytning lojalitetsnivårader. Om värdena **CustomerId** och/eller **LoyaltyCardId** tillhandahålls, kommer motsvarande anknytningslojalitetsnivåer att slås samman med rader som tillhandahålls i värdet **AffiliationLines**. |
|                  | AffiliationId | lång | Nödvändig inom AffiliationLoyaltyTier | Post-ID:t för anknytning. |
|                  | LoyaltyTierId | lång | Nödvändig inom AffiliationLoyaltyTier | Post-ID för lojalitetsnivån. |
|                  | AffiliationTypeValue | int | Nödvändig inom AffiliationLoyaltyTier | Ett värde som anger om anknytningsraden är av typen **allmän** (**0**) ekker typen **Förmån** (**1**). Om denna parameter är inställd på **0**, tar API:t **AffiliationId**-värdet som identifierare och ignorerar **LoyaltyTierId**-värdet . Om den är inställd på **1** tar API:t värdet **LoyaltyTierId** som identifierare och ignorerar värdet **AffiliationId**. |
|                  | ReasonCodeLines | Kollektion\<ReasonCodeLine\> | Nödvändig inom AffiliationLoyaltyTier | Orsakskodrader. Den här parametern påverkar inte prisberäkningen, utan krävs som en del av objektet **AffiliationLoyaltyTier**. |
|                  | CustomerId | sträng | Nödvändig inom AffiliationLoyaltyTier | Kundkontonummer. |
| Kuponger          | | IList\<Coupon\> | Valfritt | Kuponger som inte kan användas (inaktiva, utgångna eller inte) tas inte med i prissättningsberäkningen. |
|                  | Kod | sträng | Nödvändig inom kupong | Kupongkod. |
|                  | CodeId | sträng | Valfritt | Identifierare för kupongkod. Om ett värde anges måste det matcha värdet för parametern **Code**. |
|                  | DiscountOfferId | sträng | Valfritt | Rabattidentifieraren. Om ett värde anges måste det matcha värdet för parametern **Code**. |

**Exempelbegärantext**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

Hela vagnobjektet returneras som svarstext. Om du vill kontrollera priser och rabatter bör du fokusera på fälten i följande tabell.

| Namn           | Undernamn | Typ | Beskrivning |
|----------------|----------|------|--------------|
| NetPrice       | | decimal | Nettopriset för hela försäljningsdokumentet innan rabatter används. |
| DiscountAmount | | decimal | Det totala rabattbeloppet för hela försäljningsdokumentet. |
| TotalAmount    | | decimal | Det totala beloppet för hela försäljningsdokumentet. |
| CartLines      | | IList\<CartLine\> | Beräknade rader som omfattar pris- och rabattdetaljer. |
|                | Pris | decimal | Produktens enhetspris. |
|                | NetPrice | decimal | Radens nettopris före rabatter tillämpas (= *Pris* &times; *Antal*). |
|                | DiscountAmount | decimal | Rabattbeloppet. |
|                | TotalAmount | decimal | Det slutliga totala prisresultatet för raden. |
|                | PriceLines | IList\<PriceLine\> | Prisdetaljer, inklusive källan till priset (grundpris, prisjustering eller handelsavtal) och beloppet. |
|                | DiscountLines | IList\<DiscountLine\> | Rabattinformation. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Med en vagn som har flera vagnsrader returnerar *GetAvailablePromotions* API alla tillämpliga rabatter för vagnsraderna. 

Huvudanvändningen för *GetAvailablePromotions* API är kundvagnsidan, där återförsäljare vill använda rabatter eller tillgängliga kuponger för den aktuella vagnen.

Följande tabell visar indataparametrarna för API *GetAvailablePromotions*.

| Namn        | Typ | Obligatorisk/valfri | Beskrivning |
|-------------|------|-------------------|-------------|
| nyckel         | sträng | Obligatoriskt | Kundvagnens ID. |
| cartLineIds | IEnumerable\<string\> | Valfritt | Ställ in den här parametern om du bara vill returnera rabatter för valda vagnrader. |

**Exempelsvarstext**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

API *AddCoupons* API stöder att du lägger till en lista över kuponger i en kundvagn. Det returnerar kundvagnobjektet efter att kupongerna lagts till.

Följande tabell visar indataparametrarna för API *AddCoupons*.

| Namn                 | Typ | Obligatorisk/valfri | Beskrivning |
|----------------------|------|-------------------|-------------|
| nyckel                  | sträng | Obligatoriskt | Kundvagnens ID. |
| couponCodes          | IEnumerable\<string\> | Obligatoriskt | De kupongkoder som du vill lägga till i kundvagnen. |
| isLegacyDiscountCode | bool | Valfritt | Sätt denna parameter till **sant** för att indikera att kupongen är en äldre rabattkod. Standardvärdet är **falskt**. |

## <a name="removecoupons"></a>RemoveCoupons

API *RemoveCoupons* stöder borttagning av en lista med kuponger från en kundvagn. Det returnerar kundvagnobjektet efter att kupongerna tas bort.

Följande tabell visar indataparametrarna för API *RemoveCoupons*.

| Namn        | Typ | Obligatorisk/valfri | Beskrivning |
|-------------|------|-------------------|-------------|
| nyckel         | sträng | Obligatoriskt | Kundvagnens ID. |
| couponCodes | IEnumerable\<string\> | Obligatoriskt | De kupongkoder som du vill ta bort från kundvagnen. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
