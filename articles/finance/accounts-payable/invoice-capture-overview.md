---
title: Översikt av lösningen Invoice Capture
description: Den här artikeln innehåller information om den lösningen Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
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
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691207"
---
# <a name="invoice-capture-solution"></a>Lösningen Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Den här artikeln innehåller information om lösningen Invoice Capture som automatiskt skapar leverantörsfakturor från digitala fakturabilder.

Avdelningen för leverantörsreskontra (AP) hanterar och bearbetar fakturor för varor och tjänster som tas emot. Revisorn verifierar data på leverantörsfakturor av följande skäl:

- Undvik extra arbete om justeringar eller korrigeringar krävs under stängning av period
- Att betala leverantörsfakturor i rätt tid och förhindra ekonomisk förlust på grund av fel eller misstag

Optisk teckenigenkänning (OCR) har blivit allmänt använd av olika branscher under de senaste åren. Det är nu vanligt att tryckta texter digitaliseras så att de kan redigeras elektroniskt, sökas igenom, lagras mer vanligt och visas online. Den digitala texten kan användas i maskinprocesser, till exempel datorer, maskinöversättning, text till tal, nyckeldata och textutvinning.

Utvecklingen av tekniken för artificiell intelligens (AI) har gjort det möjligt för moderna OCR-lösningar att läsa olika fakturaformat från olika leverantörer utan att kräva mycket mänsklig inblandning. Fler företag inser att de kan spara pengar och göra fakturor mer korrekta genom att bearbeta fakturor via automation i stället för att bearbeta dem manuellt.

## <a name="system-landscape"></a>Systemlandskap

I följande bild visas huvudkomponenterna och stegen i lösningen Invoice Capture.

[![Komponenter och steg i lösningen Invoice Capture.](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Obligatoriska roller

I följande tabell visas vilka roller som krävs för att ställa in och använda lösningen Invoice Capture.

| Roll          | Åtgärder | System | Rollnamn |
|---------------|---------|---------|-----------|
| Administratör | <ul><li>Konfigurera miljöer i Microsoft Power Platform</li><li>Implementera lösningar i Microsoft Power Platform.</li><li>Ställ in anslutningar mellan Dynamics 365 och AI Builder.</li><li>Ställ in Azure Data Lake Storage platser.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Dynamics 365-administratör</li><li>Power Platform-administratör</li><li>Storage Blob Data-ägare</li></ul> |
| AI-skapare      | <ul><li>Hantera flöden.</li><li>Skapa anpassade AI-modeller.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Beslutsfattare för medborgare</li></ul> |
| Ansvarig för leverantörsreskontra      | <ul><li>Granska och vidta åtgärder i mellanlagringsområdet för leverantörsfaktura.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Ny ansvarig för leverantörsreskontra roll i Power Platform</li></ul> |
| Ansvarig för leverantörsreskontra      | <ul><li>Utföra dagliga operationer som ansvarig för leverantörsreskontra.</li><li>Navigera till mellanlagringsområdet för leverantörsfakturan.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Leverantörsreskontraansvarig</li></ul> |
  
Mer information om hur du installerar Invoice Capture finns i [Installera Invoice Capture](../accounts-payable/install-invoice-capture.md).  
