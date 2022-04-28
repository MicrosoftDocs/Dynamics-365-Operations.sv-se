---
title: Skapa avancerad bankavstämningsimport med hjälp av elektronisk rapportering
description: Detta ämne innehåller information om hur du använder elektronisk rapportering när du konfigurerar den avancerade importprocessen för bankavstämning för BA12-utdrag.
author: panolte
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544528"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Skapa avancerad bankavstämningsimport med hjälp av elektronisk rapportering

[!include [banner](../includes/banner.md)]

Funktionen för avancerad bankavstämning låter dig importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 Finance. Detta ämne innehåller en beskrivning av hur du konfigurerar importfunktionen för dina BA12-bankutdrag.

## <a name="set-up-the-electronic-reporting-configuration"></a>Ställa in konfigurationen för elektronisk rapportering

1. Gå till **Arbetsytor \> Elektronisk rapportering**.
2. På panelen för **Microsoft**-konfigurationsprovidern väljer du **Databaser**.
3. Markera **Global** och välj sedan **Öppna**.
4. Om en anslutning till databasen måste upprättas väljer du den blå länken i dialogrutan.
5. I konfigurationslistan söker du upp **Bankutdragsmodell \> BA12-bankutdragsmodell**.
6. Välj formatet **BAI2**.
7. På snabbfliken **Versioner** väljer du den senaste versionen och sedan **Importera**.

## <a name="set-up-the-bank-statement-format"></a>Konfigurera formatet för bankutdrag

1. Gå till **Kassa- och bankhantering \> Inställningar \> Inställningar för avancerad bankavstämning \> Bankutdragsformat**.
2. Välj **Ny**.
3. Konfigurera fälten **Utdragsformat** och **Namn**.
4. Markera kryssrutan **Allmänt elektroniskt importformat**.
5. Ange fältet **Konfiguration för importformat** som formatet **BA12**.

## <a name="set-up-the-bank-account"></a>Konfigurera bankkontot

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna bankkontot.
3. Pån snabbfliken **Avstämning** ställer du in alternativet **Avancerad bankavstämning** som **Ja**.
4. Ställ in fältet **Utdragsformat** på det **BAI2-format** som du skapade tidigare.

## <a name="import-the-bank-statement"></a>Importera bankutdrag

1. Gå till **Kassa- och bankhantering \> Avstämning av bankutdrag \> Bankutdrag**.
2. På sidan **Bankutdrag** väljer du **Importera utdrag**.
3. Ställ in fältet **Bankkonto** till det bankkonto som angetts i utdraget.
4. Ställ in fältet **Utdragsformat** på det **BAI2-format** som du skapade tidigare.
5. Välj **Bläddra** och välj filen **BAI**.
6. Välj **överför**.
7. Välj **OK** för att importera den valda filen.
