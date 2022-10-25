---
title: Mottagna Invoice Capture-filer
description: I den här artikeln förklaras hur du samlar in fakturafiler från olika källor i Invoice Capture.
author: sunfzam
ms.date: 10/13/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3c55540d11a67d4d4c4c8477d51cb6f1f5777767
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690142"
---
# <a name="invoice-capture-received-files"></a>Mottagna Invoice Capture-filer

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I Invoice Capture är sidan **Mottagna filer** en central plats där fakturafiler tas emot från olika källor.

## <a name="upload-invoice-files"></a>Överför fakturafiler

Leverantörsreskontra (AP) kan skicka fakturabilder genom att välja **Ladda upp en fil** för att öppna dialogrutan **Ladda upp**. Efter att en ansvarig för leverantörsreskontra har valt en fil blir knappen **Ladda upp** blir tillgänglig.

## <a name="include-or-obsolete-invoice-files"></a>Ta med eller gamla fakturafiler

Användarna kan välja fakturor som har fel eller varningar och sedan antingen inkludera eller inaktuella fakturorna genom att välja motsvarande knapp i åtgärdsfönstret. En faktura som markerats som föråldrad visas inte i vyn **Mottagna filer (Inaktuell)**.

## <a name="view-captured-invoices"></a>Visa registrerade fakturor

När en mottagen fil har identifieras, returneras den fångade fakturans information av AI-modellen och anges i Microsoft Dataverse. Ansvarig för leverantörsreskontra kan sedan verifiera fakturauppgifterna genom att välja **Visa hämtad faktura**. Användarna kan hämta den ursprungliga fakturafilen efter behov.
