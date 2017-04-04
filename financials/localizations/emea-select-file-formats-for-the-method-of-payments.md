---
title: "Filformat för betalningsmetod"
description: "Det här avsnittet beskrivs två metoder för att hämta de filformat som du kan använda för betalningsmetoder."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262514
ms.assetid: 72ea2018-5a49-419c-93d0-755e5ff2722f
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 54af22f1f2ec779bf947ae584a3ae09c20e6a364
ms.lasthandoff: 03/31/2017


---

# <a name="file-formats-for-methods-of-payment"></a>Filformat för betalningsmetod

Det här avsnittet beskrivs två metoder för att hämta de filformat som du kan använda för betalningsmetoder.

Det finns två sätt att få filformat användas med betalningsmetoder, elektronisk rapportering (ER) format eller X ++-filformat. När du ställer in en betalningsmetod för en kund eller leverantör, anger du vilka filformat och standarder som ska användas för betalningar och hur betalningar ska bearbetas. Du kan välja mellan följande typer av format:

-   Exportera
-   Importera
-   Retur
-   Remittering

### <a name="method-1-electronic-reporting-file-formats"></a>Metod 1: Elektronisk rapportering filformat

För filformat som baseras på ER konfigurationer måste du importera konfigurationer från Lifecycle Services (LCS). Mer information finns i [hämta elektronisk rapportering konfigurationer från Lifecycle Services](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). När du har importerat rapporterande konfigurationer för de filformat importerade format går att välja på den **betalningsmetoder** sida. Hur du importerar och välja filformat för Europa liknar proceduren för Japan. <!---For more details, see [Enable the JBA payment file format](https://ax.help.dynamics.com/en/wiki/enable-the-jba-payment-file-format/).-->

### <a name="method-2-x-file-formats"></a>Metod 2: X ++-filformat

Gör följande om du vill välja filformat som baseras på X ++-kod.

1.  Gå till den **betalningsmetoder** sida.
2.  I den **filformat** på snabbfliken klickar du på **inställningar**.
3.  Välj fliken format för filtypen.
4.  Välj ett filformat från den **tillgängliga** listan och flytta den till den **markerade** lista med pilen kontrollen.
5.  Stäng den **filformat för betalningsmetoder** sida.
6.  I den **filformat** på snabbfliken Välj filformatet som ska användas för betalningsmetoden i formatfältet lämplig fil. Allmänna elektroniska rapportalternativen tilldelas **nr** X ++-filformat.



