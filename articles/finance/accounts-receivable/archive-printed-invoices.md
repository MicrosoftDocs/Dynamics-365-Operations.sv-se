---
title: Arkivera utskrivna kundfakturor med hash-nummer
description: I det här avsnittet beskrivs hur du aktiverar arkivering för att lagra utskrivna kundfakturor med hash-nummer.
author: ilkond
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 093b1b8c516c0c659e7970d17d3f84b2ed0ccf8f
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500537"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Arkivera utskrivna kundfakturor med hash-nummer

[!include [banner](../includes/banner.md)]

I vissa länder finns det ett juridiskt krav på att beräknade hash-nummer lagras i systemet tillsammans med utskrifter av vissa dokument. Hash-nummer kan användas för rapportering till myndigheter och under granskningar.

I det här avsnittet beskrivs hur du konfigurerar arkivering för att lagra utskrivna kundfakturor med hash-nummer.

## <a name="prerequisites"></a>Förutsättningar

- I arbetsytan **funktionshantering** aktivera funktionen, **Arkivera utskrivna kundfakturor med hashnummer**. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Konfigurera utskriftsbara formaten för de nödvändiga dokumenten i **Utskriftshantering**.

Den här funktionen kan användas i följande dokument.

**Kundreskontra**
- Kundfaktura
- Kundkreditfaktura
- Fritextfaktura
- Fritextkreditfaktura

**Projekthantering och redovisning**
- Projektfaktura
- Projekts kreditfaktura

## <a name="configure-customer-master-data"></a>Konfigurera kundhuvuddata
Gör på följande sätt om du vill konfigurera kunddata och aktivera möjligheten att spara utskrivna fakturor automatiskt som bilagor.

1. Gå till **Leverantörsreskontra** > **Alla kunder**. 
2. Markera en kund och på snabbfliken **Faktura och leverans** i avsnittet **E-FAKTURA** i fältet **eInvoice bilaga** välj **Ja**.

## <a name="print-invoices"></a>Skriv ut fakturor
Du kan bokföra och skriva ut fritext, kund och projektfaktura eller kreditfaktura för kunden som konfigurerats i föregående procedur.

Öppna sidan **Bilagor** för den utskrivna fakturan. På snabbfliken **Bilaga** i fältgruppen **Ytterligare detaljer** i fältet **Dokumentets hash-numret**, hitta det lagrade hash-numret beräknat för den utskrivna fakturan.

![Bifogat hash-nummer.](media/attach-hash-num.jpg)

