---
title: Konfigurera en kanal för att använda en kanalnavigeringshierarki
description: I det här avsnittet beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ceb6aa65c2ed5bc8d4224bdaf7095fba769181e8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220593"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Konfigurera en kanal för att använda en kanalnavigeringshierarki


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.

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

![Exempel på kanalkonfiguration](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Ställ in attributmetadata

Om du anger metadata för attributet kan attributens konfiguration konfigureras på varje nod.

Följ dessa steg för att ställa in metadata för attribut.

1. I åtgärdsfönstret, välj **ange attributmetadata**.
1. Välj **kanalproduktattribut** för varje nod.
1. Ange **Visa attribut för kanal** till **Ja** och **Kan förfinas** till **Ja** för att aktivera förfinare på den kanalen.
1. När du har konfigurerat varje nod som önskas, i **åtgärdsfönstret**, välj knappen **spara** för att spara.
1. Välj **X** i det övre högra hörnet om du vill stänga fönstret på sidan **Kanalkategorier och produktattribut**.

Följande bild visar ett exempel på en uppsättning kanalproduktattribut som konfigurerats på en kanalkategorinod.

![Kanalvärdena för en kanalkategorinod](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publicera ändringar

För att ändringar ska träda i kraft måste du publicera ändringarna.

Gör så här om du vill publicera ändringarna.

1. I åtgärdsfönstret, välj **publicera kanaluppdateringar**.
1. I fönstret **publicera kanaluppdateringar** välj **OK**.

Följande bild visar hur du publicerar kanaluppdateringar.

![Publicera kanaluppdateringar](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en navigeringshierarki för kanal](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]