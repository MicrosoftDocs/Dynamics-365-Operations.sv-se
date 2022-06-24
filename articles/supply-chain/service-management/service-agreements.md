---
title: Ta fram och upprätta avtal – översikt
description: Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf28619e66fa5d3e86bdbb3838dc7f711916bcec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905614"
---
# <a name="develop-and-establish-service-agreements-overview"></a>Ta fram och upprätta avtal – översikt

[!include [banner](../includes/banner.md)]

Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden.

Alla serviceavtal kopplas till ett projekt och transaktioner bokförs och faktureras via detta. Du kan dock även fakturera serviceordertransaktioner direkt genom projektet utan att först behöva koppla serviceordern till ett serviceavtal. Du kanske vill göra detta om serviceordern är för ett engångsbesök och behovet av att bearbeta tjänstetransaktionerna snabbt uppväger behovet av att bibehålla detaljinformation om serviceavtalet för kunden över tid.

## <a name="service-agreement"></a>Serviceavtal

I ett serviceavtal måste du ange ett projekt, ett serviceavtals-ID samt en serviceavtalsgrupp. Serviceavtalsgruppen kan användas för att sortera och organisera serviceavtal.

Rubriken i ett serviceavtal innehåller inställningar som används för alla kopplade avtalsrader:

-  Information om huruvida serviceavtalet är uppskjutet. Om avtalet är uppskjutet går det inte att skapa serviceorder från serviceavtalet.
-  Tidslängden för serviceavtalet.
-  Information om hur serviceorderrader ska kombineras till serviceorder.
-  Information om huruvida serviceavtalet är en mall.

I serviceavtalets rubrik ställer du också in serviceobjekt och serviceuppgifter som kan användas med serviceavtalet genom att ange specifika serviceuppgifter och serviceobjekt som ska kopplas till de olika raderna i avtalet.

Från avtalsrubriken kan du också kopiera serviceavtalsrader eller servicemallrader till det aktuella serviceavtalet.

Du kan skjuta upp serviceavtal och stoppa enskilda serviceavtalsrader.

Om du markerar kryssrutan **uppskjuten** på ett serviceavtal kan du inte göra något av följande:

-    Skapa serviceorder automatiskt eller manuellt från serviceavtalet.

Om du markerar kryssrutan **stoppad** för en serviceavtalsrad kan du inte göra något av följande:

-    Skapa serviceorder automatiskt eller manuellt från serviceavtalsraden.
-    Kopiera serviceavtalsraden till ett annat serviceavtal eller en annan serviceorder.


> [!NOTE]
> Om ett serviceavtal skjuts upp stoppas alla kopplade rader oavsett radernas enskilda status.

## <a name="service-agreement-lines"></a>Serviceavtalsrader

Varje serviceavtalsrad beskriver i detalj vad som ingår i det föreslagna servicearbetet. Raderna innehåller följande inställningar:

-  Transaktionstypen och en beskrivning av typen.
-  Den medarbetare som utför servicearbetet.
-  De objekt som service ska utföras för enligt serviceavtalet.
-  Den frekvens som arbete ska utföras med och som associerade artikel-, utgifts- och avgiftstransaktioner ska registreras med.
-  Det tidsfönster där serviceorderrader kan grupperas till en serviceorder.
-  De serviceuppgifter som används för att gruppera uppsättningar med avtalsrader till arbetsuppgifter och för att översiktligt beskriva för servicetekniker och kunder vilket servicearbete som ska utföras.
-  Information om huruvida en rad har stoppats. Om en rad har stoppats går det inte att skapa serviceorder för raden.
-  Projektinställningar, t.ex. kategori och radegenskaper.

## <a name="related-articles"></a>Relaterade artiklar

[Skapa serviceavtal](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]