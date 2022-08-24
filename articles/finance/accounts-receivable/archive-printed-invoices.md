---
title: Arkivera utskrivna kundfakturor med hash-nummer
description: I den här artikeln beskrivs hur du aktiverar arkivering för att lagra utskrivna kundfakturor med hash-nummer.
author: mrolecki
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.custom: 539093
ms.search.form: ''
ms.openlocfilehash: 4c9bd7ead1615a4e6b0e8e672e858312ba518b56
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291682"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Arkivera utskrivna kundfakturor med hash-nummer

[!include [banner](../includes/banner.md)]

I vissa länder finns det ett juridiskt krav på att beräknade hash-nummer lagras i systemet tillsammans med utskrifter av vissa dokument. Hash-nummer kan användas för rapportering till myndigheter och under granskningar.

I den här artikeln beskrivs hur du konfigurerar arkivering för att lagra utskrivna kundfakturor med hash-nummer.

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

