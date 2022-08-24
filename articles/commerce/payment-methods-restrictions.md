---
title: Begränsa betalsätt för returer utan kvitto
description: Denna artikel beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.
author: josaw1
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.industry: Retail
ms.search.form: RetailTenderTypeTable
ms.openlocfilehash: 9b14d7d8f6a2d9209ad6a12cd53bce4a9b50178d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281407"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Begränsa betalsätt för returer utan kvitto


[!include [banner](includes/banner.md)]

Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras. Denna artikel beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.

## <a name="set-up-payment-methods"></a>Ange betalsätt

Om du vill konfigurera betalsätten måste du göra följande.
1. Skapa de betalsätt som har godkänts för hela organisationen.
2. Skapa korttyper och kortnummer för hela organisationen. Om kreditkort eller betalkort tas emot måste du först skapa ett betalsätt för kort, och sedan skapa korttyper och kortnummer för hela organisationen.
3. Ställ in betalsätt för butiken. Associera betalsätten med varje butiker och ange sedan de butiksspecifika inställningarna för varje betalningsmetod.
4. Ställ in kortbetalsätt för butiker. Slutför kortinställningarna för alla kortbetalsätt som butiken godtar.

![Butikskonfiguration.](media/NoReceiptReturns1.png "Inställning av butik") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Begränsa betalningsmetoder för returer utan kvitto

Spara betalningsmetod, för var och en på sidan **Butikshantering** under **Returer utan kvitto** ange **Begränsa betalsätt för returer** till **Ja**. 

Standardvärdet för en alternativknapp är **Nej**, vilket innebär att betalsättet är tillåten för återbetalningar. 

När **Begränsa betalsätt för returer** anges till **Ja**, tillåter inte den valda betalsättet för återbetalningar. 

![Lagra betalningsmetod.](media/NoReceiptReturns3.png "Betalningsmetod för butik") 

> [!NOTE]
> När kassören väljer ett betalsätt som är begränsad till bidrag utan ett kvitto, visas ett meddelande för att kontrollera godtagbara betalsätt.

![Godkända betalningsmetoder.](media/NoReceiptReturns4.png "Godkända betalsätt") 

Om en transaktion har en retur med kvitto och en retur utan kvitto, upprätthålls begränsningsvillkoren inte eftersom transaktionen kommer att returnera arbetsflödet med ett kvitto. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
