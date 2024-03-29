---
title: Systemgruppering i en öppen arbetsuppgiftslista
description: Denna artikel beskriver hur du filtrerar den öppna arbetslistan på en mobil enhet.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42e5862392cff57886c36bcbe138e13a8ce7ef23
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849109"
---
# <a name="system-grouping-on-an-open-work-list"></a>Systemgruppering i en öppen arbetslista

[!include [banner](../includes/banner.md)]

Genom att använda ett systemgrupperingsfält kan de filtrera en öppen arbetslista utan att behöva redigera menyalternativet mobil enhet.
Där det går att tillämpa fungerar systemgrupperingen för att filtrera en arbetslista i ett fält för en enskild arbetsrubrik. Du kan inte använda systemgruppering för att filtrera på radnivåfält.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Ställa in systemgruppering i en öppen arbetslista
Använd dessa steg för att konfigurera systemgruppering i en öppen arbetslista.

-   Från ett menyalternativ för en mobil enhet, välj **Läge: indirekt** och **Aktivitetskod: Visa öppna arbetslista**. Följande alternativ blir tillgängliga: Dessa alternativ krävs för systemgruppering av en öppen arbetslista. 

|        Alternativ         |                                                                                                                                                                                                                                                                         beskrivning                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tillåta systemgruppering |                                                                                                                                                                                                                                                 Möjliggör systemgruppering för ett menyalternativ i en vald arbetslista.                                                                                                                                                                                                                                                  |
| Fält för systemgruppering | Endast tillgängligt om <strong>Tillåt systemarbete</strong> anges till <strong>Ja</strong>. Välj det fält som bestämmer hur plockningsarbete för arbetare ska grupperas. Om du till exempel väljer fältet <strong>ShipmentId</strong> kommer arbetstagare att skanna leverans-ID:t för att gruppera plockningsarbetet. Allt arbete för leveransen tilldelas sedan till arbetaren. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Använd fältet <strong>Etikett för systemgruppering</strong> för att informera arbetaren om vad denne ska skanna. |
| Etikett för systemgruppering |                       Endast tillgängligt om <strong>Tillåt systemarbete</strong> anges till <strong>Ja</strong>. Ange text för att informera arbetstagaren om vad som ska skannas när plockningsarbetet grupperas . Om du till exempel använder fältet <strong>ShipmentId</strong> för att gruppera plockningarbete efter leverans kan du ange Leverans-ID i fältet. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Du måste också välja fältet som du vill gruppera efter i fältet <strong>Systemgruppering</strong>.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]