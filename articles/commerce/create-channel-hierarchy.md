---
title: Skapa en kanalnavigeringshierarki
description: I denna artikel beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: c3b28dd29bf444a75e5aa0a2a105d8a03fcacb0d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270275"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Skapa en kanalnavigeringshierarki


[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En navigeringshierarki för kanal används för att gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller i POS.

## <a name="create-a-channel-navigation-hierarchy"></a>Skapa en navigeringshierarki för kanal

Följ stegen nedan om du vill skapa en navigeringshierarki för kanaler.

1. I Navigeringsfönstret, gå till **Moduler \> Retail and Commerce \> Produkter och kategorier \> Navigeringskategorier för kanal**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange sedan ett namn i rutan **Namn**.
1. Ange en beskrivning i rutan **beskrivning**.
1. Markera **Skapa**.
1. I åtgärdsfönstret, välj **Ny kategorinod** för att skapa en rotnod.
1. Ange sedan ett namn i rutan **Namn**.
1. Ange en beskrivning i rutan **beskrivning**.
1. I rutan **Eget namn** anger du ett eget namn.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en rotnod.

![Exempel på rotnod.](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Skapa navigeringskategorinoder

Om du vill skapa ytterligare navigeringskategorinoder som representerar produktkategorierna på kanalen följer du dessa steg.

1. I navigeringsfönstret väljer du den överordnade noden för att lägga till en kategori.
1. I åtgärdsfönstret klickar du på **Ny kategorinod**.
1. Ange sedan ett namn i rutan **Namn**.
1. Ange en beskrivning i rutan **beskrivning**.
1. I rutan **Eget namn** anger du ett eget namn.
1. I rutan **Visningsordning**, ange en visningsordning (valfritt).
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar ett exempel på en slutförd navigeringshierarkin för butikskanal.

![Exempel på kanalhierarki.](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Lägg till produkter i kategorinoder

Följ stegen nedan om du vill lägga till produkter till kategorinoder.

1. Välj en kategorinod.
1. Under **Produkter**, välj **Lägg till**.
1. Sök efter de nya produkter som du vill lägga till med produktnummer eller produktnamn och välj sedan **OK**.
1. Klicka på **Spara** i åtgärdsfönstret.

> [!NOTE]
> Det räcker inte att lägga till produkter i en nod i modulen för kanalnavigering för att produkterna ska visas på en vald kanal – produkterna måste också vara utvalda för en kanal. Mer information om urval finns i [Urvalshantering](assortments.md).

Följande bild visar en exempelnod med produkter som läggs till.

![Produkter i som lagts till i en kategorinod.](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Lägg till produktattributgrupper till kategorinoder

> [!NOTE]
> Attributgrupper måste skapas innan du kan lägga till dem i en nod i kanalnavigeringshierarkin.

För att lägga till en attributgrupp till en kategorinod, följ dessa steg.

1. Välj en kategorinod.
1. Under **Produktattributgrupper**, välj **Lägg till**.
1. Sök efter de attributgrupper du vill lägga till och klicka sedan på **OK**.
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar en exempelnod med produktattributgrupper som läggs till.

![Produktattributgrupper på en nod.](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in sortiment](set-up-assortments.md)

[Hantera attribut och attributsgrupper](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
