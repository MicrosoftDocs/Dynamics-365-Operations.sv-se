---
title: Arkivera utskrivna kundfakturor med hash-nummer
description: I det här avsnittet beskrivs hur du aktiverar arkivering för att lagra utskrivna kundfakturor med hash-nummer.
author: ilyako
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: d502ec5d286573c72e207419b66f283183009c09
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557490"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Arkivera utskrivna kundfakturor med hash-nummer

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

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

![Bifogat hash-nummer](media/attach-hash-num.jpg)

