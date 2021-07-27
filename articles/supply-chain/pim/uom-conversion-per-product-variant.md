---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur du konfigurerar måttenhetskonvertering för produktvarianter. Den innehåller ett exempel på inställningarna.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 03c9406d295fb0dbd22e8072c2695dbef419b706
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353550"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Måttenhetskonvertering per produktvariant

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du konfigurerar måttenhetskonverteringar för diverse produktvarianter.

I stället för att skapa flera enskilda produkter som måste underhållas kan du använda produktvarianter för att skapa varianter av en enskild produkt. En produktvariant kan till exempel vara en T-shirt med given storlek och färg.

Tidigare kunde enhetskonverteringar endast ställas in i produktmallen. Därför hade alla produktvarianter samma enhetskonverteringsregler. När funktionen *Måttenhetskonverteringar för produktvarianter* är aktiverad, dina T-shirtar säljs i kartonger och antalet T-shirtar som kan förpackas i en och samma kartong beror på storleken på T-shirtarna, kan du nu ställa in enhetskonverteringar mellan olika tröjstorlekar och de kartonger som används för paketering.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om du inte redan ser funktionen i systemet går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Måttenhetskonverteringar för produktvarianter*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Konfigurera en produkt för enhetskonvertering per variant

Produktvarianter kan bara skapas för produkter som är produktmallar. Mer information finns i [Skapa en produktmall](tasks/create-product-master.md). Funktionen *Måttenhetskonverteringar för produktvarianter* är inte tillgänglig för produkter som har ställts in för faktiska viktprocesser.

Så här konfigurerar du en produktmall till stöd för enhetskonvertering per variant:

1. Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.
1. Skapa eller öppna en produktmall om du vill gå till sidan **Produktinformation**.
1. Ställ in alternativet **Aktivera måttenhetskonverteringar** som *Ja*.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Enhetskonverteringar**.
1. Sidan **Enhetskonverteringar** öppnas. Välj en av följande flikar:

    - **Konverteringar inom klasser** – Välj den här fliken om du vill konvertera mellan enheter som tillhör samma enhetsklass.
    - **Konverteringar inom klasser** – Välj den här fliken om du vill konvertera mellan enheter som tillhör olika enhetsklasser.

1. Klicka på **Ny** om du vill lägga till en ny enhetskonvertering.
1. Ställ in fältet **Skapa konvertering för** på ett av följande värden:

    - **Produkt** – Om du väljer detta värde kan du ange en enhetskonvertering för produktmallen. Den enhetskonverteringen kommer att användas som reserv för alla produktvarianter som ingen enhetskonvertering definieras för.
    - **Produktvariant** – Om du väljer detta värde kan du ange en enhetskonvertering för en specifik produktvariant. Använd fältet **Produktvariant** för att välja varianten.

    ![Lägga till en ny enhetskonvertering.](media/uom-new-conversion.png "Lägga till en ny enhetskonvertering")

1. Använd de andra fälten som tillhandahålls för att ställa in din enhetskonvertering.
1. Klicka på **OK** om du vill spara den nya enhetskonverteringen.

> [!TIP]
> Du kan öppna sidan **Enhetskonverteringar** för en produkt eller en produktvariant från någon av följande sidor:
> 
> - Produktdetaljer
> - Information om släppt produkt
> - Frisläppta produktvarianter

## <a name="example-scenario"></a>Exempelscenario

I detta scenario säljer ett företag T-shirts i storlekarna Small, Medium, Large och Extra large. T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av den produkten. Tröjorna förpackas i kartonger. För storlekarna Small, Medium och Large kan det finnas fem tröjor per kartong. För storleken Extra stor finns emellertid plats för endast fyra tröjor per kartong.

Företaget vill spåra de olika varianterna i enheten *Stycken*, men man säljer dem i enheten *kartonger*. För storlekarna Small, Medium och Large är konverteringsförhållandet mellan lagerenhet och försäljningsenhet 1 kartong = 5 stycken. För storleken Extra large är konverteringen 1 kartong = 4 stycken.

1. På sidan **Information om frisläppt produkt** för produkten **T-shirt** öppnar du sidan **Enhetskonvertering**.
1. På sidan **Enhetskonverteringar** anger du följande enhetskonvertering för produktvarianten **X-Large**.

    | Fält                 | Inställning                 |
    |-----------------------|-------------------------|
    | Skapa konvertering för | Produktvariant         |
    | Produktvariant       | T-Shirt : : X-Large : : |
    | Från enhet             | Lådor                   |
    | Faktor                | 4                       |
    | Till enhet               | Antal                  |

1. Eftersom produktvarianterna **Small**, **Medium** och **Large** samtliga har samma enhetskonvertering mellan enheterna *Kartong* och *Stycken* kan du definiera följande enhetskonvertering för dem i produktmallen.

    | Fält                 | Inställning |
    |-----------------------|---------|
    | Skapa konvertering för | Produkt |
    | Produkt               | T-shirt |
    | Från enhet             | Lådor   |
    | Faktor                | 5       |
    | Till enhet               | Antal  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Uppdatera enhetskonverteringarna med Excel

Om en produkt har många produktvarianter som har olika enhetskonverteringar är det en god idé att exportera enhetskonverteringarna till en Microsoft Excel-arbetsbok, uppdatera dem och sedan publicera dem på nytt i Dynamics 365 Supply Chain Management.

Om du vill exportera enhetskonverteringar till Excel går du till sidan **Enhetskonverteringar** och väljer **Öppna i Microsoft Office** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera måttenheter](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]