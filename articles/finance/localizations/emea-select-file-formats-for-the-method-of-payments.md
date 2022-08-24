---
title: Filformat för betalningsmetod
description: Den här artikeln beskriver två metoder för att hämta de filformat som du kan använda för betalsätt.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 262514
ms.search.form: CustPaymMode, VendPaymMode
ms.openlocfilehash: eae21fba2499d819a146953e56f48a8f9d748582
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292222"
---
# <a name="file-formats-for-methods-of-payment"></a>Filformat för betalningsmetod

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver två metoder för att hämta de filformat som du kan använda för betalsätt.

Det finns två sätt att få filformat som du kan använda med betalsätt, filformat för elektronisk rapportering (ER) eller X++ -filformat. När du anger ett betalsätt för en kund eller leverantör anger du vilka filformat och standarder som ska användas för betalningar och hur betalningar ska bearbetas. Du kan välja mellan följande format:

-   Exportera
-   Importera
-   Retur
-   Remittering

### <a name="method-1-electronic-reporting-file-formats"></a>Metod 1: Filformat för elektronisk rapportering

För filformat som baseras på ER-konfigurationer måste du importera konfigurationer från Lifecycle Services (LCS). Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). När du importerar rapporteringskonfigurationer för dess filformat, blir importerade format tillgängliga för val på sidan **Betalsätt**. Hur du importerar och väljer filformat för Europa liknar proceduren för Japan. Mer information finns i [Aktivera JBA-betalningsfilformat](tasks/jba-payment-file-format.md)

### <a name="method-2-x-file-formats"></a>Metod 2: X++ -filformat

Gör följande om du vill välja filformat som baseras på X++ -kod.

1.  Gå till sidan **Betalsätt**.
2.  På snabbfliken **Filformat** klickar du på **Inställningar**.
3.  Välj den flik som motsvarar filformatet.
4.  Välj ett filformat i listan **Tillgänglig** listan och flytta det till listan **Markerat** med pilkontrollen.
5.  Stäng sidan **Filformat för betalsätt**.
6.  På snabbfliken **Filformat** väljer du det filformat som ska användas för betalsättet i motsvarande filformatsfält. De allmänna alternativen för elektronisk rapportering bör anges som **Nej** for X++ -filformat.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
