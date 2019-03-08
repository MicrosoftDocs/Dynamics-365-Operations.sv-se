---
title: Begränsa betalningsmetoder för returer utan kvitto
description: Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "315922"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Begränsa betalningsmetoder för returer utan kvitto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras. Det här avsnittet beskriver hur vissa betalningstyper kan begränsas för återbetalning om returer görs utan ett kvitto.

## <a name="set-up-payment-methods"></a>Ange betalningsmetoder

Om du vill ställa in betalsätten måste du göra följande.
1. Skapa de betalningsmetoder som har godkänts för hela organisationen.
2. Skapa korttyper och kortnummer för hela organisationen. Om kreditkort eller betalkort tas emot måste du först skapa en betalningsmetod för kort, och sedan skapa korttyper och kortnummer för hela organisationen.
3. Ställ in betalningsmetoder för butiken. Associera betalningsmetoderna med varje butiker och ange sedan de butiksspecifika inställningarna för varje betalningsmetod.
4. Ställ in kortbetalningsmetoder för butiker. Slutför kortinställningarna för alla kortbetalningsmetoder som butiken godtar.

![Butiksinställningar](media/NoReceiptReturns1.png "Butiksinställningar") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Begränsa betalningsmetoder för returer utan kvitto

Spara betalningsmetod, för var och en på sidan **Butikshantering** under **Returer utan kvitto** ange **Begränsa betalningsmetoder för returer** till **Ja**. 

Standardvärdet för en alternativknapp är **Nej**, vilket innebär att betalningsmetoden är tillåten för återbetalningar. 

När **Begränsa betalningsmetoder för returer** anges till **Ja**, tillåter inte den valda betalningsmetoden för återbetalningar. 

![Betalningsmetod för butik](media/NoReceiptReturns3.png "Betalningsmetod för butik") 

> [!NOTE]
> När kassören väljer en betalningsmetod som är begränsad till bidrag utan ett kvitto, visas ett meddelande för att kontrollera godtagbara betalningsmetoder.

![Godtagbara betalningsmetoder](media/NoReceiptReturns4.png "Godtagbara betalningsmetoder") 

Om en transaktion har en retur med kvitto och en retur utan kvitto, upprätthålls begränsningsvillkoren inte eftersom transaktionen kommer att returnera arbetsflödet med ett kvitto. 

