---
title: Referenser till ursprungliga fakturor i kreditfakturor (leverantörsfakturor)
description: I den här artikeln beskrivs hur du skapar en referens till en ursprunglig faktura när du skapar en kreditfaktura.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: 39cf4eb7eef1a83abeb7bd44fa7b2abefee0806e
ms.sourcegitcommit: 8eb0cafe5ad20be2c4fff684e88d7d3f2249f820
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409675"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Referenser till ursprungliga fakturor i kreditfakturor (leverantörsfakturor)

[!include [banner](../includes/banner.md)]

I vissa länder och regioner finns det ett juridiskt krav på att utskrivna kreditfakturor eller rapporteringsrutiner inkluderar hänvisningar till originalfakturorna. I den här artikeln beskrivs hur du skapar en referens till en ursprunglig faktura när du skapar en kreditfaktura.

## <a name="prerequisites"></a>Förutsättningar

I arbetsytan **Funktionshantering** aktivera funktionen **Aktivera kreditfakturering för leverantörsfakturor**. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Funktionerna som beskrivs i detta ämne gäller för följande affärsdokument.

**Leverantörsreskontra:**

- Inköpsorder
- Fakturajournal
- Fakturaregister

**Redovisning:**

- Allmän journal

## <a name="define-a-reference-to-an-original-invoice"></a>Definiera referenser till en ursprunglig faktura

När du definierar en referens till en ursprunglig faktura ingår följande steg på hög nivå:
1. Skapa och bokföra en leverantörsfaktura.
2. Skapa en leverantörskreditfaktura.
3. Använd kreditfaktureringsraden om du vill koppla fakturan till en kreditfaktura.
4. Bokför kreditfaktura.

Använd följande procedurer för att definiera en referens till en originalfaktura i de angivna affärsdokumenttyperna.

### <a name="vendor-credit-note-purchase-order"></a>Leverantörskreditfaktura (inköpsorder)

1. Gå till **Leverantörsreskontra** > **Inköpsorder** > **Alla inköpsorder**.
2. Skapa en ny inköpsorder eller använd en befintlig för att skapa en kreditfaktura.
3. I åtgärdsfönstret på fliken **Faktura** i gruppen **Introducera** väljer du **Kreditfaktura**.
4. Ange referensen till den ursprungliga fakturan och välj orsaken till korrigeringen.

### <a name="vendor-credit-note-ledger-journals"></a>Leverantörskreditfaktura (redovisningsjournaler)

1. Gör något av följande:

    - Gå till **Leverantörsreskontra** \> **Fakturajournaler**.
    - Gå till **Leverantörsreskontra** \> **Fakturaregister**.
    - Gå till **Redovisning** \> **Journalposter** \> **Allmänna journaler**.

2. Skapa en ny journal och nya journalrad.
3. I åtgärdsrutan, välj **Funktioner** \> **Kreditfakturering**.
4. Ange referensen till den ursprungliga fakturan och välj orsaken till korrigeringen.

> [!NOTE]
> Kommandot **Kreditfakturering** visas i en allmän journalverifikation om fältet **Kontotyp** är inställt på **Leverantör**.
