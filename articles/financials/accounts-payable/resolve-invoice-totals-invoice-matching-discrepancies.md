---
title: Åtgärda avvikelser under matchning av fakturasummor
description: Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation.
author: abruer
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63f4747c13d70d45404069a200124336d6f54947
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2019
ms.locfileid: "896360"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Åtgärda avvikelser under matchning av fakturasummor

[!include [banner](../includes/banner.md)]

En typ av fakturakontroll validering är fakturasummor matchning. Ange att systemet ska utföra fakturasummor matchning på **leverantörsskulder parametrar sidan** , på **fakturan fliken validering** , **matchar fakturasummor** alternativet **Ja**. 

Du kan använda fakturasummor matchande, för att garantera att fakturans totala belopp inte avviker från förväntat belopp med mer än en acceptabel variation. Sex summorna kan jämföras på **fakturasummor matchande detaljer** . Om någon av summorna avviker från den förväntade motsvarande inköpsorder totalt, en matchande avvikelse flaggas. 

För att granska faktura som har summorna matchande avvikelser i **säljarens faktura** arbetsytan klickar du på den **väntande fakturor** panel. Sedan, på rutan åtgärd, på **fliken granskning** klickar du **matchande detaljer**. Om matchning skillnader har upptäckts, varningsikoner visas intill beloppet på fakturan. Du kan visa fler detaljer om summor på fakturasummor matchande detaljer. 

När du identifierar en avvikelse, kan du behöva kontakta säljaren om du tycker att informationen på fakturan är felaktig. Beroende på vilket avtal med säljaren kan du sedan ta någon av dessa åtgärder:

-   Acceptera prisskillnaden och Bokför faktura som har matchande avvikelser. Ditt system kan vara konfigurerat att kräva godkännande innan den kan posta om det finns motsvarande skillnader. I detta fall måste du godkänna matchningen avvikelse och kan även ange ett godkännande kommentar. Du kan sedan välja att kontera faktura.
-   Ändra fakturans belopp till det förväntade värdet och Bokför faktura.
-   Begära ett fullständigt erkännande och en ny korrigerad faktura från leverantören.

Mer information finns i [Undersöka eller lösa undantag](tasks/research-resolve-exceptions.md).


