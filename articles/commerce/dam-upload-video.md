---
title: Överför videor
description: I det här avsnittet beskrivs hur du laddar upp videor i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f481e5d3f323b0c86d637b67c119d13b956d5714dc0d990004834e2be05b370e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735640"
---
# <a name="upload-videos"></a>Överför videor

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du laddar upp videor i Microsoft Dynamics 365 Commerce webbplatsskapare.

Med mediabiblioteket för Commerce webbplatsskapare kan du överföra videor. Du bör alltid överföra versionen av en video med högsta bithastighet och upplösning, eftersom videon omvandlas automatiskt för att vara lämplig för olika visningsportar och deras brytpunkter.

### <a name="video-information-specified-during-upload"></a>Videoinformation som anges under överföringen

När du överför en video kan du ange följande information.

- **Rubrik, beskrivning, nyckelord**: metadata för videon.
- **Generera underterxter automatiskt**: Anger om undertexter ska genereras automatiskt för videon (stöd finns endast för engelska). 
- **Dold textning**: anger den dolda textning som ska användas.
- **Vanligt ljud**: anger det vanliga ljudspår som ska användas.
- **Miniatyr**: anger miniatyrbilden för videon. Om den inte anges kommer den att genereras automatiskt.
- **Beskrivande ljud**: anger det beskrivande ljudspår som ska användas.

## <a name="upload-a-video"></a>Överför en video

Så här överför du en video i webbplatsskapare.

1. I vänstra navigeringsfönstret, välj **mediebibliotek**.
1. I kommandofältet, välj **Överför \> Överför medieartiklar**.
1. I fönstret Utforskaren navigerar du till och markerar en eller flera videofiler som ska överföras och väljer sedan **öppna**.
1. I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.
1. Ange valfri beskrivning och nyckelord och välj en kategori om du vill. 
1. Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**
1. Välj **OK**.

Om du överför flera typer av tillgångar samtidigt (t.ex. bilder och videor) i dialogrutan **överför medieobjekt** kan du bara ange nyckelord, om filerna ska publiceras direkt efter överföringen och om det ska genereras dolda bildtexter automatiskt för videofilerna. Alla tillgångar kommer att dela samma nyckelord.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av digital tillgångshantering](dam-overview.md)

[Överför bilder](dam-upload-images.md)

[Överför filer](dam-upload-files.md)

[Beskär bilder](dam-crop-images.md)

[Anpassa bildens fokuspunkter](dam-custom-focal-point.md)

[Ladda upp och betjäna statiska filer](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
