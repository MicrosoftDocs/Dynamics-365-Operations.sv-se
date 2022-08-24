---
title: Konfigurera en produkt som ska köpas in gratis
description: I denna artikel beskrivs hur du konfigurerar en produkt så att den kan köpas in gratis i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88370085de047a5e0be773dde218770cfa242d14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280375"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Konfigurera en produkt som ska köpas in gratis

[!include [banner](includes/banner.md)]


I denna artikel beskrivs hur du konfigurerar en produkt så att den kan köpas in gratis i Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Konfigurera produkten

För att kunna sälja en produkt gratis i Dynamics 365 Commerce måste du konfigurera sitt pris på 0 (noll). Du måste dessutom konfigurera produktens **nollpris giltigt** inställning.

Konfigurera inställningen **Nollpris giltigt** i Commerce headquarters genom att följa dessa steg.

1. Gå till **Retail och Commerce \> Produkter och kategorier \> Frisläppta produkter efter kategori**.
1. Gå till den produkt som du vill sälja gratis. 
1. I avsnittet **Commerce** på produktsidan, ange alternativet **Nollpris giltigt** till **Ja**.

I bilden nedan visas ett exempel på en produkt där alternativet **Nollpris giltigt** är inställt på **Ja**.

![Exempel på en produkt där alternativet Nollpris giltigt är inställt på Ja.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Konfigurera funktionsprofilen för onlinebutiken

Innan gratistransaktioner kan bearbetas bör du konfigurera inställningen **Tillåt kassa utan betalning** i funktionsprofilen för din onlinebutik så att transaktioner utan betalningar tillåts. Information om hur du skapar funktionsprofiler finns i [Skapa en funktionsprofil online](online-functionality-profile.md).

Konfigurera inställningen **Tillåt kassa utan betalningar** i Commerce headquarters genom att följa dessa steg.

1. Gå till **Retail och Commerce \> Kanalinställningar \> Inställningen för onlinebutik**.
1. På sidan för din butiks funktionsprofil, under **Kassa**, ange **Tillåt kassa utan betalningar** till **Ja**.

I följande bild visas ett exempel på en onlinebutiksprofil där alternativet **Tillåt kassa utan betalningar** är inställt på **Ja**.

![Exempel på en onlinebutiksprofil där alternativet Tillåt kassa utan betalningar är inställt på Ja.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Prishantering för butiksförsäljning](price-management.md)

[Skapa en onlinefunktionsprofil](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
