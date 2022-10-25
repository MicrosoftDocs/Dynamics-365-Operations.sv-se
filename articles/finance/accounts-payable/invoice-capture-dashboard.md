---
title: Instrumentpanel för lösningen Invoice Capture
description: I den här artikeln beskrivs instrumentpanelen för lösningen Invoice Capture.
author: sunfzam
ms.date: 10/15/2022
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
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690137"
---
# <a name="invoice-capture-solution-dashboard"></a>Instrumentpanel för lösningen Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I Invoice Capture innehåller instrumentpanelen diagram som ger en översikt över fakturor som har importerats. De här diagrammen kan hjälpa chefen för Leverantörsreskontra (AP) att analysera resultatet av fakturagenereringsprocessen. Chefen för AP kan visa status för fakturagenereringsprocessen och, genom att använda olika filter, kan du också visa information.

## <a name="available-charts"></a>Tillgängliga diagram

Följande diagram är tillgängliga på instrumentpanel:

- **Alla hämtade fakturor per status** – I det här diagrammet visas följande statusar för en hämtad faktura. Genom att välja en status kan användarna filtrera de fångade fakturorna i den detaljerade listan.

    - Hämta
    - Slutfört
    - Under granskning
    - Inaktuell 

- **Totalt hämtad fakturavolym** – I det här diagrammet visas antalet hämtade fakturor per period. Användarna kan ändra perioden genom att använda listrutan.
- **Samla in faktura från toppleverantörer** – I det här diagrammet visas totala antalet fakturor per leverantör. Högst upp visas de leverantörer som har mest fakturor.
- **Dagar att fylla i per faktura med undantag** – Detta diagram visar det genomsnittliga antalet dagar som krävs för att hämta en faktura. Den här informationen kan hjälpa AP-chefen att analysera tidpunkten för bearbetning av en faktura när manuell inblandning krävs. Om det finns en uppåtgående trend kan användarna granska processdetaljerna och justera inställningarna för att minska antalet dagar som behövs.
- **Ofullständiga fakturor genom väntande** – I det här diagrammet visas antalet dagar som en fångad faktura inte har genererats i ett ERP-system (resursplanering för företag). Ju större antal pågående dagar, desto längre tid tar det att generera fakturor. Chefen för AP kan gå nedåt till de detaljerade hämta fakturorna och generera fakturor i ERP-systemet.
