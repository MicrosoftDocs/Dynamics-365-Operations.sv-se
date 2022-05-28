---
title: Konfigurera produktkvantitetsgränser på nätandelsplatser för B2B
description: I detta ämne beskrivs hur du ställer in produktkvantitetsgränser för B2B-näthandelssajter.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 18dc138693dc9fb0e8cf8727de77b5f8584cde79
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690206"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Konfigurera produktkvantitetsgränser på nätandelsplatser för B2B

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du ställer in produktkvantitetsgränser för B2B-näthandelssajter.

De flesta produkter har en måttenhet som definierar deras gruppering. Grupperingen påverkar hur produkterna kan säljas. För en del produkter kan det finnas en ytterligare gruppering för kvantiteter. Denna gruppering fastställer huruvida produkterna kan säljas som enskilda enheter eller multiplar, och om det finns en minsta eller högsta orderkvantitetsgräns som måste innehållas.

Funktionen för kvantitetsbegränsning säkerställer att de minsta, högsta, multipla och standardkvantiteter som konfigureras i Microsoft Dynamics 365 Commerce (i standardorderinställningarna eller webbplatsinställningarna för Commerce-webbplatsbyggaren) tillämpas på kundorder som placeras på en näthandelssajt. Produktkvantitetsgränserna stöds för närvarande inte för kassa (POS) och kundtjänst.

Många återförsäljare ger möjlighet till kundorder (även kallade specialorder) att uppfylla diverse produkt- och uppfyllandekrav. Här följer några vanliga scenarier:

- En kund vill att produkter av vissa varianter ska säljas i grupper om flera.
- En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna. Förpackningsstandarderna för butikerna skiljer sig dock från förpackningsstandarderna för onlineförsäljningsdistribution.
- En kund vill köpa en begränsad produkt ("limited edition") som har en maxkvantitetsgräns för artiklar som går att köpa.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Aktivera funktionen för standardinställningar för order i Commerce-administrationen

Innan du kan ställa in produktkvantitetsgränser måste funktionen för standardorderinställningar aktiveras i Commerce-administrationen.

Följ de här stegen för att aktivera funktionen för inställningar för standardorder.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Sök efter och välj funktionen **Stöd för inställningar för webbplats och standardorder i kundorder**.
1. Markera **Aktivera nu** längst ner i höger fönster. 

## <a name="define-quantity-settings"></a>Definiera kvantitetsinställningar 

Du kan definiera kvantitetsinställningarna på sidan **Standardorderinställningar**.

Gör på följande sätt om du vill definiera kvantitetsinställningarna. 

1. Gå till Produkt **Butik och Handel \> Produkter och kategorier \> Frisläppta produkter efter kategori**.
1. Välj en frisläppt produkt.
1. I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Orderinställningar**, väljer du **Standardorderinställningar**. 
1. På sidan **Standardorderinställningar**, på snabbfliken **Försäljningsorder** i avsnittet **Försäljningskvantitet**, anger du försäljningskvantiteterna för produkten:

    - **Multipel** – Den kvantitet som produkten kan köpas i multiplar av.
    - **Minsta orderkvantitet** – Det minsta antal produkter som måste köpas in.
    - **Högsta orderkvantitet** – Det högsta antal produkter som kan köpas in.
    - **Standardorderkvantitet** – Standardkvantiteten som anges automatiskt när produkten väljs.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Aktivera funktionen för B2B-orderkvantitetsgränser i Commerce-webbplatsbyggaren

Följ dessa steg om du vill aktivera funktionen för B2B-orderkvantiteter i Commerce-webbplatsbyggaren.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Under **Aktivera orderkvantitetsgeänser** väljer du **Aktiverat för B2B-kunder** i listrutan. 

> [!NOTE] 
> Uppdaterade inställningar för webbplatsbyggare gäller bara när filen app.settings.json har uppdaterats. Mer information finns i [SDK- och modulbiblioteksuppdateringar](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en näthandelsplats för B2B](set-up-b2b-site.md)

[Hantera B2B-affärspartners med hjälp av kundhierarkier](partners-customer-hierarchies.md)

[Hantera affärspartneranvändare på näthandelsplatser för B2B](manage-b2b-users.md)

[Konfigurera betalsätt för kundkonto för B2B-näthandelssajter](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
