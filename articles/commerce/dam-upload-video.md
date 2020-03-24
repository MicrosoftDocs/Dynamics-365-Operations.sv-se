---
title: Överför videor
description: I det här avsnittet beskrivs hur du överför videor i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98cb4f9049509dd700cf38a5d176447f86e9c824
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097087"
---
# <a name="upload-videos"></a>Överför videor

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du överför videor i Microsoft Dynamics 365 Commerce webbplatsskapare.

## <a name="overview"></a>Översikt

Med mediabiblioteket för Commerce webbplatsskapare kan du överföra videor. Du bör alltid överföra versionen av en video med högsta bithastighet och upplösning, eftersom videon omvandlas automatiskt för att vara lämplig för olika visningsportar och deras brytpunkter.

### <a name="video-information-specified-during-upload"></a>Videoinformation som anges under överföringen

När du överför en video kan du ange följande information.

- **Rubrik, beskrivning, nyckelord**: metadata för videon.
- **Generera automatiskt stängda bildtexter**: anger om dolda bildtexter ska genereras automatiskt för videon.
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
