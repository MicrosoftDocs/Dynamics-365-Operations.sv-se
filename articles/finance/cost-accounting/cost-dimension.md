---
title: Skapa dimensioner och importera dimensionsmedlemmar
description: Kostnadsredovisningen är en oberoende modul som kräver huvuddata från andra moduler.
author: twheeloc
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: twheeloc
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 19c49a3f069274a01741bb272065d17a912970ae
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734067"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Skapa dimensioner och importera dimensionsmedlemmar

[!include [banner](../includes/banner.md)]

Kostnadsredovisningen är en oberoende modul som kräver data från andra moduler. Denna data kategoriseras till följande:

-  Kostnadselement
-  Kostnadsobjekt
-  Statistikdimensioner

Ett **Kostnadselement** motsvarar en kostnadsrelevant artikel i kontolistan. Ett **kostnadsobjekt** motsvarar valfri ekonomisk dimensionstyp, till exempel produkter, kostnadsställen samt projekt som du vill beräkna, allokera kostnader till eller mäta direkt. En **statistisk dimension** och dess medlemmar används för att registrera icke-monetära poster. Statistiska dimensionsmedlemmar kan användas som allokeringsbas inom kostnadsdistribution och -allokering 

Följande diagram illustrerar de dimensioner som används inom kostnadsredovisningen.

[![Dimensioner i kostnadsredovisning.](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

När datan väl har importerats till kostnadsredovisningen kan du använda den för att skapa olika perspektiv som ger insikter till chefer på alla organisationsnivåer. Mer information om hur du skapar dimensioner och importerar dimensionsmedlemmar finns i följande avsnitt: 

-  [Dimensioner för kostnadselement](cost-elements.md)
-  [Skapa kostnadselement](./tasks/create-cost-elements.md)
-  [Kostnadsobjektdimensioner](cost-objects.md)
-  [Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar](map-cost-elements-dimension-members.md)
-  [Mappa dimension för kostnadselement](./tasks/map-cost-element-dimension.md)
-  [Providermallar för statistiska dimensionsmedlemmar och statistiska mätningar](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]
