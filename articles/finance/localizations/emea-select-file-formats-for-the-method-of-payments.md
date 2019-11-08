---
title: Filformat för betalningsmetod
description: Det här avsnittet beskriver två metoder för att hämta de filformat som du kan använda för betalningsmetoder.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36f12fbc21fe782555c348f8a401e7aef6219f41
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183947"
---
# <a name="file-formats-for-methods-of-payment"></a>Filformat för betalningsmetod

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver två metoder för att hämta de filformat som du kan använda för betalningsmetoder.

Det finns två sätt att få filformat som du kan använda med betalningsmetoder, filformat för elektronisk rapportering (ER) eller X++ -filformat. När du anger en betalningsmetod för en kund eller leverantör anger du vilka filformat och standarder som ska användas för betalningar och hur betalningar ska bearbetas. Du kan välja mellan följande format:

-   Exportera
-   Importera
-   Retur
-   Remittering

### <a name="method-1-electronic-reporting-file-formats"></a>Metod 1: Filformat för elektronisk rapportering

För filformat som baseras på ER-konfigurationer måste du importera konfigurationer från Lifecycle Services (LCS). Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). När du importerar rapporteringskonfigurationer för dess filformat, blir importerade format tillgängliga för val på sidan **Betalningsmetoder**. Hur du importerar och väljer filformat för Europa liknar proceduren för Japan. Mer information finns i [Aktivera JBA-betalningsfilformat](tasks/jba-payment-file-format.md)

### <a name="method-2-x-file-formats"></a>Metod 2: X++ -filformat

Gör följande om du vill välja filformat som baseras på X++ -kod.

1.  Gå till sidan **Betalningsmetoder**.
2.  På snabbfliken **Filformat** klickar du på **Inställningar**.
3.  Välj den flik som motsvarar filformatet.
4.  Välj ett filformat i listan **Tillgänglig** listan och flytta det till listan **Markerat** med pilkontrollen.
5.  Stäng sidan **Filformat för betalningsmetoder**.
6.  På snabbfliken **Filformat** väljer du det filformat som ska användas för betalningsmetoden i motsvarande filformatsfält. De allmänna alternativen för elektronisk rapportering bör anges som **Nej** for X++ -filformat.



