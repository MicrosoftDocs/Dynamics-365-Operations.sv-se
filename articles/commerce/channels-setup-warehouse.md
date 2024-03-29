---
title: Ställ in ett lagerställen
description: I denna kanal beskrivs hur du konfigurerar ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: 476f78d7fe1bc61c2c9b783ed1f82bc660248b02
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273650"
---
# <a name="warehouse-set-up"></a>Inställning av lagerställe

[!include [banner](includes/banner.md)]

I denna kanal beskrivs hur du konfigurerar ett lagerställe som ska användas med en ny kanal i Microsoft Dynamics 365 Commerce.

Varje handelskanal kräver ett konfigurerat lagerställe för att det ska associeras med det. Följande procedurer ger den minsta konfiguration som krävs för att konfigurera ett lager ställe för en handelskanal. Mer information om inställningar för lagerställen finns i [Lagerstyrning – översikt](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Konfigurera en lagerställeplats

Innan du konfigurerar ett lagerställe måste du konfigurera en lagerställeplats.

Konfigurera en lagerställeplats enligt följande instruktioner.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Webbplatser**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Webbplatser** anger du ett värde.
1. I fältet **Namn** anger du ett värde.
1. I avsnittet **Allmänt** ange lämplig **Tidszon**.
1. I avsnittet **Adresser** ange en adress.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på lagerställeplats.

![Exempel på lagerställeplats.](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Ställ in ett lagerställen

Så här ställer du in ett lagerställe.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Lagerställe** ange ett värde.  Om detta är en 1:1-mappning till en butik bör du överväga att använda butiksnamnet eller namnet på ett regionalt distributionscenter.
1. I fältet **Namn** anger du ett värde.
1. I listrutan **Plats** väljer du den lagerställeplats som du skapade tidigare.
1. I fältet **Typ**, välj **Standard**.
    - Om du vill konfigurera ett **Karantänlagerställe** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Karantän**.
    - Om du vill konfigurera ett **Transitlager** måste du först följa stegen nedan för att skapa ett ytterligare lagerställe där **Typ** ställs in på **Transit**.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="set-up-inventory-aisles"></a>Ställ in lagergångar

Så här ställer du in lagergångar.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Platsinställning \> Lagergångar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **Lagerställe** väljer du det lagerställe som du skapade tidigare.
1. I fältet **Gång** anger du ett namn (till exempel "Def").
1. I fältet **Namn** anger du ett namn (till exempel "Standardgång").
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="set-up-warehouse-inventory-locations"></a>Konfigurera lagerplatser på lagerställen

Om du vill konfigurera lagerplatser för lagerställen för standard, skadat och returnerat lager följer du dessa steg.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.
1. Välj det lagerställe som du skapat tidigare.
1. Klicka på **Redigera** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Lagerställe** och välj sedan **lagerplats**.
1. Klicka på **Ny** i åtgärdsfönstret. Listrutan **Lagerställe** bör som standard vara ditt nya lager.
    1. I rutan **gång** ange namnet på gången du angav tidigare. 
    1. Ange **manuell uppdatering** till **Ja**
    1. I rutan **Plats** ange namnet på lagerstället.
    1. Klicka på **Spara** i åtgärdsfönstret.
 1. Klicka på **Ny** i åtgärdsfönstret.  Listrutan **Lagerställe** bör som standard vara ditt nya lager.
    1. I rutan **gång** ange namnet på gången du angav tidigare.  
    1. Ange **manuell uppdatering** till **Ja**
    1. I rutan **Plats** ange "Skadad".
    1. Klicka på **Spara** i åtgärdsfönstret.
 1. Klicka på **Ny** i åtgärdsfönstret.  Listrutan **Lagerställe** bör som standard vara ditt nya lager.
    1. I rutan **gång** ange namnet på gången du angav tidigare. 
    1. Ange **manuell uppdatering** till **Ja**
    1. I rutan **Plats** ange "Returer".
    1. Klicka på **Spara** i åtgärdsfönstret.
    
Följande bild visar inställningar av San Francisco-lagerplats.

![Exempel på konfiguration för lagerställe.](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Slutförd inställning av lagerställe

Om du vill slutföra inställning av lagerställe, följ dessa steg.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Lagerställen**.
1. Välj det lagerställe som du skapat tidigare.
1. Klicka på **Redigera** i åtgärdsfönstret.
1. Under **Hantering av lager och lagerstyrning**:
    1. Ange **Standardinleveransplats** till standardplatsen som skapades ovan.
    1. Välj **Standardutleveransplats** till standardplatsen som skapades ovan.
1. Under avsnittet **adresser** ange en adress till lagerstället.
1. Under avsnittet **butik**: 
    1. I rutan **Standardreturplats** ange den returplats som skapades tidigare.
    1. Ange **Butik** till **Ja**.
    1. Ange **Vikt** till **1,00**. 
    1. I rutan **Lagringsdimensioner** ange den standardplats som skapades tidigare.
1. Under avsnittet **lagerställe** ange **Fysiskt negativt lager** till **Ja**.
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar information om ett konfigurerat lagerställe.

![Exempel på konfigurerat lagerställe.](media/warehouse-sample.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Hantering av distributionslager – översikt](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att konfigurera kanaler](channels-prerequisites.md)

[Ställa in en butikskanal](channel-setup-retail.md)
    
[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
