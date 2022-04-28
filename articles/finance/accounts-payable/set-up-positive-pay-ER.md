---
title: Konfigurera och generera filer för betalningskontroll med hjälp av elektronisk rapportering
description: Detta ämne innehåller information om hur du konfigurerar betalningskontroll med hjälp av elektronisk rapportering.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544518"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Konfigurera betalningskontrollfiler med hjälp av elektronisk rapportering

Ställa in betalningskontroll för att generera en elektrisk lista med checkar som ges till banken. När checken sedan visas för banken, jämför banken checken med listan med checkar. Om checken matchar en check i listan behandlar banken checken. Om checken inte matchar en check in listan kvarhåller banken checken för granskning.

## <a name="set-up-the-electronic-reporting-configuration"></a>Ställa in konfigurationen för elektronisk rapportering

1. Gå till **Arbetsytor \> Elektronisk rapportering**.
2. På panelen för **Microsoft**-konfigurationsprovidern väljer du **Databaser**.
3. Markera **Global** och välj sedan **Öppna**.
4. Om en anslutning till databasen måste upprättas väljer du den blå länken i dialogrutan.
5. I konfigurationslistan letar du upp och väljer **Modell för betalningskontroll \> Format för betalningskontroll**.
6. På snabbfliken **Versioner** väljer du den senaste versionen och sedan **Importera**.

## <a name="set-up-a-positive-pay-format"></a>Konfigurera ett format för betalningskontrollfil

1. Gå till **Kassa- och bankhantering \> Inställningar \> Format för betalningskontroll**.
2. Välj **Ny**.
3. Konfigurera fälten **Betalningsformat** och **Beskrivning**.
4. Markera kryssrutan **Allmänt elektroniskt exportformat**.
5. Ange fältet **Konfiguration för exportformat** som **Format för betalningskontroll**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Tilldela ett format för betalningskontroll till ett bankkonto

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna bankkontot.
3. På snabbfliken **Allmänt** anger du fältet **Format för betalningskontroll** till det format som skapades tidigare.
4. Ställ in fältet **Startdatum för betalningskontroll** på aktuellt datum.

## <a name="generate-a-positive-pay-file"></a>Skapa en betalningskontrollfil

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna ett bankkonto som betalningskontroll har ställts in för.
3. Välj **Hantera betalningar \> Betalningskontroll \> Betalningskontrollfil**.
4. Ställ in fältet **Slutdatum**. Checkar som genererats före detta datum kommer att inkluderas.

Den resulterande XML-filen hämtas.
