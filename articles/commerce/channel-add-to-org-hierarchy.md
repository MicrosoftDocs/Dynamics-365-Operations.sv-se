---
title: Lägga till kanal till organisationshierarkin
description: I det här avsnittet beskrivs hur du lägger till kanal till en organisatorisk hierarki i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7ff6d8ee7e526e45975cfa500b5e6d6079054dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800697"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Lägga till kanal till organisationshierarkin


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till kanal till en organisatorisk hierarki i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Kanaler måste vara kopplade till en eller flera organisatoriska hierarkier. Innan du skapar kanaler måste du bekräfta att dina organisatoriska hierarkier har ställts in.  

Se [organisationshierarkier](channels-org-hierarchies.md) för mer information om hur du skapar organisationshierarkier.

## <a name="select-a-hierarchy"></a>Välj en hierarki

Gör så här för att välja en hierarki:

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Organisationshierarkier**.
1. I listan väljer du den organisationshierarki som du vill lägga till kanalen i.
1. Välj **Visa** för att visa information om hierarkin i åtgärdsfönstret.

Följande bild visar information om organisationshierarkin för den valda hierarkin.

![Information om organisationshierarkin för den valda hierarkin](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Lägga till en kanal i en hierarkinod

Om du vill lägga till en kanal till en hierarkinod gör du följande.

1. Klicka på **Redigera** i åtgärdsfönstret.
1. Välj den hierarkinod som du vill lägga till kanalen i, välj sedan **Infoga** i listrutan och välj **butikskanal**. 
1. Välj kanal att lägga till och välj sedan **OK**-knappen.
1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **publicera** och ange **giltighetsdatum** som har passerat för att den här åtgärden ska börja gälla direkt.

Följande bild visar hur du väljer en kanal som ska läggas till i en hierarkinod.

![Välj en kanal för att lägga till en hierarkinod](media/channel-add-to-org-hierarchy-2.png)

Följande bild visar en hierarki med olika kanaler tillagda.

![En hierarki med olika kanaler tillagda](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planera en organisationshierarki](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Organisationshierarkier](channels-org-hierarchies.md)

[Ställa in en butikskanal](channel-setup-retail.md)
    
[Ställ in en onlinekanal](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]