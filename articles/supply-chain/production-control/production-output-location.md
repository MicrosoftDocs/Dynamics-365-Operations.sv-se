---
title: Plats för produktionsutleverans
description: Denna artikel beskriver den hierarki som används för att identifiera platsen för produktionsutleverans.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 130db343c4d09f2b8d31bf8acad3dcceec2be32e
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067954"
---
# <a name="production-output-location"></a>Plats för produktionsutleverans

[!include [banner](../includes/banner.md)]

Denna artikel beskriver den hierarki som används för att identifiera platsen för produktionsutleverans.

Produktionsutleveransplatsen är den plats där en färdig artikel lagras först när den produceras. Den här platsen är vanligen nära produktionsprocessen som tillverkar den färdiga varan. Produktionsutleveransplatsen används för materialet som transitlager innan den flyttas till försändelseområde, lagringsplats, en lagringsplats, en produktionsinleveransplats för efterföljande produktionsprocessen, osv. 

En standardplats produktionsutleverans anges när färdiga varor rapporteras för en produktionsorder eller batchorder. Följande hierarki används för att identifiera den här utdataplatsen:

1. Använd den utleveransplats som definieras i rubriken för produktionsordern eller batchordern.
2. Om ingen plats hittas där använder du den utleveransplats som definieras för en resurs som används av den sista åtgärden som definierats i produktionsflödet.
3. Om ingen plats hittas där använder du den utleveransplats som definieras för en resursgrupp som används av resursen för den sista åtgärden som definierats i produktionsflödet.
4. Om ingen plats hittas använder du utleveransplatsen som definieras i det lager som definierats för tillverkningsordern.

En standardplats för produktionsutleverans anges endast för produkter som har ställts in med hjälp av lagerstyrningsprocesser (WMS). När den här typen av artikel har rapporterats som färdig skapas lagerarbete av typen **Plats för slutförda varor** eller **Plats för samprodukt och biprodukt** . Den här typen av arbete använder produktionsutleveransplatsen som plockplats. Artikelinförselplatsen bestäms av platsdirektiv.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]