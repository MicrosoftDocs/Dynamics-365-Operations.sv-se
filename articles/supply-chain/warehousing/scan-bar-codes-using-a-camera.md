---
title: Skanna streckkoder med hjälp av en kamera i lagerhållningsappen
description: Det här avsnittet beskriver hur du ställer in i lagerhållningsappen för att skanna streckkoder med en kamera på en mobil enhet.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530016"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a>Skanna streckkoder med hjälp av en kamera i lagerhållningsappen

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du ställer in i lagerhållningsappen för att skanna streckkoder med en kamera på en mobil enhet. 

## <a name="prerequisites"></a>Förutsättningar
Om du vill använda den här funktionen måste du ha version 1.2.0.0 av lagerhållningsappen installerat och enheten måste ha en kamera. När du öppnar programmet, efter att ha uppdaterat, uppmanas du att tillåta appen att använda kameran. Om enheten inte har någon kamera visas inte frågan och du kan inte använda en kamera som skanner. 

## <a name="setup"></a>Konfigurera
Du kan välja om kameran ska användas för skanning av streckkoder i visningsinställningar i lagerhållningsappen. Om du aktiverar **använda kameran som skanner** kan du använda kameran på alla inmatningsfält med inmatningsläget **skanning**. 

För att bestämma att ett indatafält ska vara skanningsbart, på sidan **Namnordning för lagerställeapp** anger du **önskat inmatningsläge** till **Skanning**. När det här alternativet väljs kan en kamera användas för skanning i lagerhållningsappen. Information om hur du konfigurerar app fältnamn i Warehousing finns i [konfigurera app fältnamn i lagerhållningsappen](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Streckkodsformat som stöds
De vanligaste formaten för streckkod stöds, inklusive kod 128, kod 39, kod 93, EAN-8, EAN-13, UPC-E, UPC-A och QR-koder. 

## <a name="navigation"></a>Navigering
Sidan för kamera initieras på varje sida där inmatningsfält har indataläge skanning. När du är på kamerasidan använd följande alternativ när du navigerar:
- Klicka på bakåt om du vill gå tillbaka till sidan Task and details. 
- Klicka på pennan på sidan Task and details för att gå till den sida där du kan skriva in data manuellt.
- Klicka på kameran på sidan Task and details för att gå tillbaka till kamerasidan. 

| Sidan Task and details | Kamerasida | 
| :---------------------: | :--------------------: |
| ![Sidan Kameraskanning exempelinformationssida](./media/camera-scanning-example-task-detail-page50.png)          | ![Kameraskanning exempel, kamerasida mindre](./media/camera-scanning-example-camera-page50.png)          |

När du klickar på knappen kamera på kamerasidan visas den nedtonad under identifiering av en streckkod. Om en streckkod inte identifieras inom 5 sekunder inaktiveras processen och kameraknappen blir tillgänglig igen. Du kommer sedan att kunna försöka skanna streckkoden igen.

För bästa resultat håller du kameran i linje när du riktar den över streckkoden. När en streckkod har skannats bearbetas informationen och du kommer till nästa steg. Om nästa steg innehåller ytterligare ett inmatningsfält med inmatningsläge skanning, startar kamerasidan igen. Om nästa steg inte är skanning, kommer kamerasidan inte att startas.

