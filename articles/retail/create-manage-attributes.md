---
title: Skapa och hantera attribut
description: "Det här avsnittet ger en beskrivning av attributen i Microsoft Dynamics 365 for Retail. Med attribut kan du beskriva en produkt och dess egenskaper genom eget fält."
author: pdp1207
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: EcoResAttributeType, EcoResAttribute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a98527d37040dfcc0e57b74d590802e8aa2cb0b6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="create-and-manage-attributes"></a>Skapa och hantera attribut

[!include[banner](includes/banner.md)]


Det här avsnittet ger en beskrivning av attributen i Microsoft Dynamics 365 for Retail. Med attribut kan du beskriva en produkt och dess egenskaper genom eget fält.

Med attribut kan du beskriva en produkt och dess egenskaper genom eget fält. Du kan till exempel ange produktens minnesstorlek och hårddiskkapaciteten och om produkten är energistjärnmärkt. Attribut som kan förknippas med olika retail enheter, såsom produktkategorier och butikskanaler och standardvärden kan ställas in för dem. Produkter ärva deras attribut och värden för de attribut som när de är associerade med produktkategorier eller butik. Standardvärdena kan åsidosättas på den enskilda produkten, vid butik nivå eller i en återförsäljare katalog.

#### <a name="examples"></a>Exempel

| Kategori   | Attribut                | Tillåtna värden          | Standardvärde |
|------------|--------------------------|-----------------------------|---------------|
| TV & Video | Märke                    | Några giltiga varumärkesvärden       | Inga          |
| TV         | Skärmstorlek              | 20″–80″                     | Inga          |
| TV         | Vertikal lösning      | 480i, 720p, 1080i, eller 1080p | 1080p         |
| TV         | Skärmuppdateringsfrekvens      | 60hz, 120hz, eller 240hz       | 60hz          |
| TV         | HDMI-ingångar              | 0–10                        | 3             |
| TV         | DVI-ingångar               | 0–10                        | 1             |
| TV         | Kompositingångar         | 0–10                        | 2             |
| TV         | Komponentingångar         | 0–10                        | 1             |
| LCD        | 3D Ready                 | Ja eller Nej                   | Ja           |
| LCD        | 3D aktiverat               | Ja eller Nej                   | Ingen            |
| Plasma     | Drifttemperatur från      | 32–110 grader              | 32            |
| Plasma     | Drifttemperatur till        | 32–110 grader              | 100           |
| Projektion | Projektionrörgaranti | 6, 12, eller 18 månader         | 12            |
| Projektion | antal projektionsrör    | 1–5                         | 3             |


## <a name="attribute-type"></a>Attributtyp
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) 
  
Attribut baseras på attributtyper. Attributtyper identifiera vilken typ av data som kan anges för ett visst attribut. För närvarande stöder Microsoft Dynamics 365 for Retail följande attributtyper:

-   **Valuta** – Denna attributtyp stöder valutavärden. Detta kan avgränsas (som kan stödja ett värde värde), eller det kan lämnas öppet.
-   **DatumTid** -– Denna attributtyp stödjer datum- och tidsinställningarna. Detta kan avgränsas (som kan stödja ett värde värde), eller det kan lämnas öppet.
-   **Decimal** – Denna attributtyp stöder numeriska värden som inkluderar decimaler. Den stöder dessutom måttenheter. Detta kan avgränsas (som kan stödja ett värde värde), eller det kan lämnas öppet.
-   **Heltal** – Denna attributtyp stöder siffervärden. Den stöder dessutom måttenheter. Detta kan avgränsas (som kan stödja ett värde värde), eller det kan lämnas öppet.
-   **Text** – Denna attributtyp stöder textvärden. Den stöder dessutom en fördefinierad uppsättning av möjliga värden (uppräkning).
-   **Boolesk** – Denna attributtyp stöder binära värden (**sant**/**falskt**).
-   **Referens**.

## <a name="attribute"></a>Attribut
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Utöver namn, egennamn, beskrivning och hjälptext, kan en eller flera av följande typer av information fångas i ett attribut:

-   Standardvärde
-   Attributmetadata, t.ex. metadata som anger huruvida egenskapen kan sökas, raffinerade eller sorteras

## <a name="attribute-group"></a>Attributgrupp
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) När attributen har definierats kan de grupperas i attributgrupper. Attributgrupper ger grupperingar av individuella egenskaper, och kan tilldelas butikskategorier eller butikskanaler.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Tilldela attributgrupper till butikskategorier
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) En eller flera attributgrupper som kan associeras med kategorinoder i butikskategorihierarkin. När produkterna har kategoriserats, de ärver de attribut som ingår i attributgrupper.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Tilldela attributgrupper till butiker
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) En eller flera attributgrupper kan associeras med en eller flera butiker i butikskategorihierarkin. När produkterna har förädlats för specifika butiker, de ärver de attribut som ingår i attributgrupper.

## <a name="overriding-attribute-values"></a>Åsidosätta attributvärden
### <a name="at-the-product-level"></a>På produktnivå

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Standardvärden för attribut kan åsidosättas på produktnivå (dvs. för enskilda produkter).

### <a name="in-a-retail-catalog"></a>I en återförsäljarkatalog

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Standardvärden för attribut kan åsidosättas för enskilda produkter i särskilda kataloger som är riktade till specifika butikskanaler.

### <a name="at-the-retail-channel-level"></a>På butiksnivå

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Standardvärden för attribut kan åsidosättas för enskilda produkter i särskilda kataloger som är riktade till specifika butikskanaler.




