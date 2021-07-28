---
title: Konfigurera ett experiment
description: I det här avsnittet beskrivs hur du ställer in ett experiment i en tredjepartstjänst.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7453f0780d46ec1b3a09fe122938c8729c35aef6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349242"
---
# <a name="set-up-an-experiment"></a>Konfigurera ett experiment

När du har [definierat en hypotes och bestämmer vilka mått du vill använda](experimentation-identify.md), måste du ställa in experimentet i tredjeparttjänsten. I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i olika avsnitt.

[ ![Experimentets användarresa – Konfiguration.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Ställa in experimentet i tredjepartstjänsten
Nu bör du ha valt att köra och övervaka din tredjepartstjänst och sedan ställa in experimentanslutningen. Dessa förutsättningar är listade vid [experiment i Dynamics 365 Commerce](experimentation-overview.md).

Följ de steg som krävs för att skapa experimentet i den tredjepartstjänsten. Om anslutningen är korrekt konfigurerad visas den fullständiga listan över experiment som du ställer in i tredjepartstjänst i Commerce webbplatsskaparen inom cirka 5 minuter.

## <a name="set-up-your-success-metrics"></a>Ställ in dina mätvärden för framgång
Varje experiment behöver mätvärden för att mäta effekterna av varianterna och för att validera hypotesen. Följ instruktionerna nedan för att aktivera beräkningen av mått i tjänsten från tredje part med hjälp av händelser för direkt telemetri från Dynamics 365 Commerce.

Följ dessa steg för att ställa in dina mätvärden för framgång.

1. I Commerce webbplatsskaparen väljer du fliken **Sidor** i det vänstra navigeringsfönstret och väljer sedan den sida som du vill samla in mått för. 
1. Gå till avsnittet **händelse-ID för att spåra** i egenskapsrutan till höger på den sida eller modul som du vill spåra.
1. Välj **Vy**. En lista över alla händelse-ID:n visas. Kopiera den händelse som du vill spåra och klistra in händelsenyckeln i den angivna platsen i tredjepartstjänsten. Om du behöver fler än en händelse kopierar du tangenterna en i taget. 
    - Mer information om hur du visar alla tillgängliga händelser och attribut, inklusive sidvyer och intäktsspårning, finns i [Commerce-komponenthändelser för diagnostik och felsökning](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Vidta alla andra steg för att följa upp mätvärden som krävs i tjänsten för tredje part.

## <a name="previous-step"></a>Föregående steg
[Identifiera en hypotes och fastställa mätvärden för ett experiment](experimentation-identify.md) 


## <a name="next-step"></a>Gå vidare
[Ansluta till och redigera ett experiment](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]