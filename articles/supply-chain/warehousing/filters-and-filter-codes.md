---
title: Konfigurera produktfilter för distributionslagertransaktioner
description: Denna artikel beskriver hur man konfigurerar produktfilter och filterkoder för att kategorisera lagerartiklar i ett lagerställe. Du kan också använda filter för att ange vilka kunder kan beställa en viss artikel och ange de artiklar som kan köpas från en viss leverantör.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: f3d6cd373699d374c019f0db7befaffc169f4f6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850450"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Konfigurera produktfilter för distributionslagertransaktioner

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur man konfigurerar produktfilter och filterkoder för att kategorisera lagerartiklar i ett lagerställe. Du kan också använda filter för att ange vilka kunder kan beställa en viss artikel och ange de artiklar som kan köpas från en viss leverantör.

Du kan även konfigurera och använda produktfilter för att automatiskt ordna lagerartiklar i ett lagerställe och kombinera filtrerade artiklar i filtergrupper. Filter kan användas för att lägga in artiklar i kategorier för hantering, inköp och försäljning av processer. Du kanske vill gruppera artiklar tillsammans eller separera dem från varandra när sättet att hantera dem baseras på vikt- eller hanteringsbegränsningar. Du kan också ange vilka kunder eller leverantörer en artikel kan köpas från eller säljas till.

## <a name="prerequisites"></a>Förutsättningar

Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

| Förutsättning | Instruktioner |
|---|---|
| Innan du börjar konfigurera produkter på sidan **Information om frisläppt produkt** måste du aktivera lagerbearbetning för produktens lagringsdimensiongrupp. | Gå till **Produktinformationshantering \> Installation \> Dimension och variantgrupper \> Dimensionsgrupper för lagring** och välj eller skapa en lagringsdimensionsgrupp där alternativet **Använd lagerstyrningsprocesser** anges till *Ja*. |
| Om du kommer att använda kundfilter och/eller leverantörsfilter måste du aktivera deras användning i Parametrar för lagerstyrning. | Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**. På fliken **Produktfilter** ange alternativet **Aktivera kundfilter** och/eller **Aktivera leverantörsfilter** till *Ja*. |

## <a name="set-up-product-filters"></a>Ställ in produktfilter

Produktfilter ger upp till 10 egenskaper **Filterrubrik** som är uppräkningsvärden (enum). Dessa enum-värden är tillgängliga för val när du skapar ett produktfilter. Enum-värdena *Kod 1* till *Kod 10* är systemdefinierade och representerar en specifik egenskap eller ett specifikt attribut för en artikel. Till exempel *Kod 1* kan representera objekt som har en klassificering av farligt material. *Kod 2* kanske representerar artiklar som endast leverantörer kan köpa. Produktfilter definierar sedan det specifika **Filterkod** som är kopplat till ett värde för **Filterrubrik**.

1. Gå till **Hantering av distributionslager \> Inställningar \> Produktfilter \> Produktfilter**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till ett produktfilter i rutnätet.
1. I fältet **Filterrubrik**, välj ett värde.
1. Ange ett värde i fältet **Filterkod**.

    ![Ställa in ett produktfilter.](media/Product_Filters10.png "Ställa in ett produktfilter")

1. I fältet **Beskrivning**, ange ett namn för koden. Till exempel kan *Kod 2* representera leverantörer. Du kan sedan skapa ett produktfilter för en viss leverantör eller grupp av leverantörer. Mer information finns i avsnittet [Ställ in leverantörsfilterkoder](#vendor-product-filters) senare i denna artikel.

    ![Uppsättning produktfilter.](media/Product_Filters.png "Ställ in produktfilter")

## <a name="set-up-product-filter-groups"></a>Ställa in produktfiltergrupper

Du kan använda filtergrupper för att gruppera filterkoder. Denna funktion är användbar när gruppen används i en fråga i ett platsdirektiv, och du vill söka efter gruppen i stället för en serie koder. Varje filtergrupp är associerad med en artikelgrupp.

> [!IMPORTANT]
> Alla produktfiltergrupper är inte tillgängliga för filterkoder som är högre än *Kod 4* (det vill säga *Kod 5* till och med *Kod 10*). För frisläppta produkter, även om alla produktfilterkoderna kommer att läggas till, uppdateras till exempel inte gruppering av filterkoder. Det här beteendet kanske uppdateras i senare versioner.

Så här ställer du in filtergrupper.

1. Gå till **Hantering av distributionslager \> Inställningar \> Produktfilter \> Produktfiltergrupper**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fälten **Grupp 1** och **Grupp 2** ange namnen som ska användas för att kategorisera objekt.
1. På snabbfliken **Detaljer**, klicka på **Ny** för att lägga till en rad.
1. I fälten **Startdatum/tid** och **Slutdatum/tid** anger du start- och slutdatum för filtergruppen.
1. I fältet **Artikelgrupp** välj den artikelgrupp som produktfiltret ska gälla för.
1. I fälten **Kod 1** till och med **Kod 10**, välj de filterkoder som ska inkluderas i gruppen efter behov.

    ![Artikelgrupp.](media/ProdFilterGroup.png "Artikelgrupp")

> [!NOTE]
> Om du får ett felmeddelande när du stänger sidan, kan en kodinställning saknas. På sidan **Artikelgrupper** kan du göra koder obligatoriska för en artikelgrupp genom att välja kryssrutan **Tilldela filterkod 1 för artikelgrupp**, **Tilldela filterkod 2 för artikelgrupp** och så vidare.

## <a name="set-up-filter-codes-on-item-groups"></a>Ställ in filterkoder i artikelgrupper

Genom att konfigurera filterkoder för en artikelgrupp kan du skapa de koder som krävs för produkter som är kopplade till den artikelgruppen.

Gör på följande sätt när du vill konfigurera filterkoder i artikelgrupper.

1. Gå till **Lagerhantering \> Inställningar \> Lager \> Artikelgrupper**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en artikelgrupp.
1. Ange ett namn i fältet **Artikelgrupp**.
1. Ange en beskrivning i fältet **Namn**.
1. På snabbfliken **Distributionslager** i avsnittet **Filter krävs** väljer du lämpliga kryssrutor för att definiera en eller flera filterkoder som måste anges för produkter,som associeras med artikelgruppen.

    För att uppdatera en släppt produkt, öppna dess sida **Information om frisläppt produkt** och sedan i åtgärdsfönstret väljer du **Redigera**. Filtren som är kopplade till koder blir sedan tillgängliga på snabbfliken **Lagerställe**.

    ![Artikelgrupper.](media/ItemGroup10.png "Artikelgrupper")

1. I avsnittet **Artikelgruppfilter** markera kryssrutorna för de filter som måste matcha för att filtergruppen ska vara standardfiltergrupp för en artikel.

    Om till exempel kryssrutorna **Använd filterkod 1** och **Använd filterkod 2** markeras måste både filterkod 1 och filterkod 2 för artikeln matcha inställningarna för filtergruppen för artikelgruppen innan filtergruppen kan väljas. När du skapar en ny artikel kommer den valda filtergruppen att vara standardfiltergruppen i fälten **Grupp 1** och **Grupp 2** på snabbfliken **Distributionslager** på sidan **Information om frisläppt produkt**.

> [!IMPORTANT]
> Produktfilterkoder aktiveras endast för artiklar som använder avancerad distributionslagerhantering.

## <a name="specify-filter-codes-for-released-products"></a>Ange filterkoder för släppta produkter

Gör på följande sätt för att ange filterkoder för frisläppta produkter. Du kan till exempel använda filterkoder för att gruppera farliga produkter som specifika leverantörer köper.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en produkt.
1. I dialogrutan **Ny släppt produkt** anger du de data som krävs för att skapa basen för en ny produkt och väljer sedan **OK**.

    Produktfilterkoder är inte aktiverade om inte artikelgruppen som är kopplad till produkten har konfigurerats för filterkoder.

    Mer information finns i [Skapa en ny produkt](../pim/tasks/create-new-product.md).

1. På snabbfliken **Distributionslager** i avsnittet **Produktfilterkoder**, välj filterkoder för fälten **Kod 1** till och med **KodCode 10** vid behov för att ange filterkoder för produkten.

## <a name="set-up-generally-available-items"></a>Ställa in allmänt tillgängliga artiklar

Du kan göra specifika lagerartiklar endast tillgängliga för kunder eller leverantörer eller för både kunder och leverantörer.

> [!NOTE]
> Kundfilter och leverantörsfilter gäller inte för artiklar som ställs in som allmänt tillgängliga.

Gör på följande sätt när du vill konfigurera allmänt tillgängliga artiklar.

1. Gå till **Hantering av distributionslager \> Inställningar \> Produktfilter \> Allmänt tillgängliga produkter**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en post.
1. I fältet **Kund eller leverantör**, välj *Kund*, *Leverantör* eller *Alla* för att göra artiklarna tillgängliga för kunder, leverantörer eller båda.
1. I fältet **Startdatum/starttid** anger du datum och tid då artikeln ska bli tillgänglig.
1. I fältet **artikelgrupp** väljer du artikelgruppen.
1. I fälten **Kod 1** till och med **Kod 10** väljer du filterkoderna som begränsar vilka artiklar som är tillgängliga i allmänhet.

    När du väljer en artikelgrupp anger du att den här gruppen av artiklar är allmänt tillgänglig. Genom att välja filterkoder i dessa fält begränsar du artiklarna som är tillgängliga.

## <a name="set-up-customer-product-filters"></a>Ställ in kundproduktfilter

Du kan använda denna valfria procedur för att visa hur du anger artiklar som ska vara tillgängliga för en kund utöver de artiklar som har gjorts tillgängliga via filterinställningar på sidan **Allmänt tillgängliga artiklar**. Du kan konfigurera filter för en enda kund.

Gör på följande sätt när du vill konfigurera kundfilterkoder.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Välj en kund.
1. I åtgärdsfönstret, på fliken **Kund** i gruppen **Konfigurering**, markerar du **Produktfilter**.
1. På sidan **Produktfilterkoder** i åtgärdssfönstret väljer du **Ny**.
1. I fälten **Startdatum/tid** och **Slutdatum/tid** anger du start- och slutdatum för valda artikelgruppen.
1. I fältet **artikelgrupp** väljer du artikelgruppen.
1. I fälten **Kod 1** till och med **Kod 10** väljer du de filterkoder som ska användas som villkor för att begränsa de artiklar som är tillgängliga för kunder i den valda artikelgruppen. Du måste göra ett val för varje filterkod som är inställd för artikelgruppen.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Ställ in leverantörproduktfilter

Du kan använda denna valfria procedur för att visa hur du anger artiklar som ska vara tillgängliga för en leverantör utöver de artiklar som har gjorts tillgängliga via filterinställningar på sidan **Allmänt tillgängliga artiklar**. Du kan konfigurera filter för en enda säljare.

Gör på följande sätt när du vill konfigurera leverantörsfilterkoder.

1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**.
1. Välj en leverantör.
1. I åtgärdsfönstret, på fliken **Leverantör** i gruppen **Konfigurering**, markerar du **Produktfilter**.
1. På sidan **Filterkoder** i åtgärdsfönstret väljer du **Ny**.
1. I fälten **Startdatum/tid** och **Slutdatum/tid** anger du start- och slutdatum för valda artikelgruppen.
1. I fältet **artikelgrupp** väljer du artikelgruppen.
1. I fälten **Kod 1** till och med **Kod 10** väljer du de filterkoder som ska användas som villkor för att begränsa de artiklar som är tillgängliga för leverantörer i den valda artikelgruppen. Du måste göra ett val för varje filterkod som är inställd för artikelgruppen.

> [!NOTE]
> Inställningarna för leverantörsproduktfilter gäller frisläppta produkter där distributionslagerhanteringsprocesser är aktiverade för den associerade lagringsdimensionsgruppen. Filterkoderna används för att avgöra om systemet kommer att tillåta användare att köpa en given artikel från en given leverantör när de skapar inköpsorderrader. Microsoft Dynamics 365 Supply Chain Management har två metoder för hantering av leverantörsgodkännande. Om en eller flera frisläppta produkter där fältet **Kontrollmetod för godkänd leverantör** är inställt på *Endast varning* eller *Tillåts inte* kan båda metoderna för leverantörsgodkännande aktiveras för dessa artiklar. Den här situationen kan orsaka problem när användare skapar inköpsorderrader.

## <a name="see-also"></a>Se även

[För mer information se blogginlägget WMS-filterkoder för lagerställe](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]