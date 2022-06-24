---
title: Skanna streckkoder med kamera i Warehouse Management-mobilappen
description: Denna artikel beskriver hur du konfigurerar i mobilappen Warehouse Management för att skanna streckkoder med en kamera på en mobil enhet.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8459ea6912328fa589b92f1731551f56df89c11b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862349"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Skanna streckkoder med kamera i Warehouse Management-mobilappen

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du konfigurerar i mobilappen Warehouse Management för att skanna streckkoder med en kamera på en mobil enhet.

## <a name="setup"></a>Ställ in

Du kan välja om kameran ska användas för skanning av streckkoder i visningsinställningar i mobilappen för distributionslagerhantering. Om du aktiverar **använda kameran som skanner** kan du använda kameran på alla inmatningsfält med inmatningsläget **skanning**.

För att bestämma att ett indatafält ska vara skanningsbart, på sidan **Namnordning för lagerställeapp** anger du **önskat inmatningsläge** till **Skanning**. När det här alternativet väljs kan en kamera användas för skanning i mobilappen för distributionslagerhantering. - Mer information finns i [Konfigurera fält för mobilappen för distributionslagerhantering](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Streckkodsformat som stöds

De vanligaste formaten för streckkod stöds, inklusive kod 128, kod 39, kod 93, EAN-8, EAN-13, UPC-E, UPC-A och QR-koder.

## <a name="navigation"></a>Navigering

Sidan för kamera initieras på varje sida där inmatningsfält har **föredraget indataläge** inställt på *skanning*. När du är på kamerasidan använd följande alternativ när du navigerar:

- Klicka på bakåt om du vill gå tillbaka till sidan **Uppgift och detaljer**.
- Klicka på pennan på sidan **Uppgift och detaljer** för att gå till den sida där du kan skriva in data manuellt.
- Klicka på kameran på sidan **Uppgift och detaljer** för att gå tillbaka till kamerasidan.

När du klickar på knappen kamera på kamerasidan visas den nedtonad under identifiering av en streckkod. Om en streckkod inte identifieras inom 5 sekunder inaktiveras processen och kameraknappen blir tillgänglig igen. Du kommer sedan att kunna försöka skanna streckkoden igen.

För bästa resultat håller du kameran i linje när du riktar den över streckkoden. När en streckkod har skannats bearbetas informationen och du kommer till nästa steg. Om nästa steg innehåller ytterligare ett inmatningsfält med inmatningsläge skanning, startar kamerasidan igen. Om nästa steg inte är skanning, kommer kamerasidan inte att startas.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]