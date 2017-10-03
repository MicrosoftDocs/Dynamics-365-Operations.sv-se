---
title: "Plats för produktionsutleverans"
description: "Det här avsnittet beskriver den hierarki som används för att identifiera produktionsutleveransplatsen."
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="production-output-location"></a>Plats för produktionsutleverans

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver den hierarki som används för att identifiera produktionsutleveransplatsen.

Produktionsutleveransplatsen är den plats där en färdig artikel lagras först när den produceras. Den här platsen är vanligen nära produktionsprocessen som tillverkar den färdiga varan. Produktionsutleveransplatsen används för materialet som transitlager innan den flyttas till försändelseområde, lagringsplats, en lagringsplats, en produktionsinleveransplats för efterföljande produktionsprocessen, osv. 

En standardplats produktionsutleverans anges när färdiga varor rapporteras för en produktionsorder eller batchorder. Följande hierarki används för att identifiera den här utdataplatsen:

1. Använd den utleveransplats som definieras i rubriken för produktionsordern eller batchordern.
2. Om ingen plats hittas där använder du den utleveransplats som definieras för en resurs som används av den sista operationen som definierats i produktionsflödet.
3. Om ingen plats hittas där använder du den utleveransplats som definieras för en resursgrupp som används av resursen för den sista operationen som definierats i produktionsflödet.
4. Om ingen plats hittas använder du utleveransplatsen som definieras i det lager som definierats för tillverkningsordern.

En standardplats för produktionsutleverans anges endast för produkter som har ställts in med hjälp av avancerade lagerprocesser. När den här typen av artikel har rapporterats som färdig skapas lagerarbete av typen **Plats för slutförda varor** eller **Plats för samprodukt och biprodukt** . Den här typen av arbete använder produktionsutleveransplatsen som plockplats. Artikelinförselplatsen bestäms av platsdirektiv.

