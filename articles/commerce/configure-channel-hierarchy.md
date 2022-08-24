---
title: Konfigurera en kanal för att använda en kanalnavigeringshierarki
description: I denna artikel beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b15e6eee86880f0315f42b34056385f718cc6bf1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280404"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Konfigurera en kanal för att använda en kanalnavigeringshierarki


[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Navigeringshierarkier för kanal ordnar produkter till kategorier, så att du kan bläddra på en näthandelssajt i POS. Butiks- och onlinekanaler måste konfigureras med hierarkier för kanalnavigering.

## <a name="configure-the-channel"></a>Konfigurera kanalen

Om du vill konfigurera en kanal till att använda en navigeringshierarki för kanal följer du stegen nedan.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj kanal som ska konfigureras.
1. I åtgärdsfönstret, välj **ange attributmetadata**.
1. I listrutan **kategorihierarki** väljer du lämplig hierarki för kanalnavigering.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Under **attributgrupper**, lägg till alla attributgrupper som kommer att vara globala attribut för alla noder.

Följande bild visar hur du konfigurerar en kanal till att använda en navigeringshierarki för kanal.

![Exempel på kanalkonfiguration.](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Ställ in attributmetadata

Om du anger metadata för attributet kan attributens konfiguration konfigureras på varje nod.

Följ dessa steg för att konfigurera metadata för attribut.

1. I åtgärdsfönstret, välj **ange attributmetadata**.
1. Välj **kanalproduktattribut** för varje nod.
1. Ange **Visa attribut för kanal** till **Ja** och **Kan förfinas** till **Ja** för att aktivera förfinare på den kanalen.
1. När du har konfigurerat varje nod som önskas, i **åtgärdsfönstret**, välj knappen **spara** för att spara.
1. Välj **X** i det övre högra hörnet om du vill stänga fönstret på sidan **Kanalkategorier och produktattribut**.

Följande bild visar ett exempel på en uppsättning kanalproduktattribut som konfigurerats på en kanalkategorinod.

![Kanalattribut för en kanalkategorinod.](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publicera ändringar

För att ändringar ska träda i kraft måste du publicera ändringarna.

Gör så här om du vill publicera ändringarna.

1. I åtgärdsfönstret, välj **publicera kanaluppdateringar**.
1. I fönstret **publicera kanaluppdateringar** välj **OK**.

Följande bild visar hur du publicerar kanaluppdateringar.

![Publicera kanaluppdateringar.](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en kanalnavigeringshierarki](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
