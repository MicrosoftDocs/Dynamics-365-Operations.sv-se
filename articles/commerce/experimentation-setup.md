---
title: Konfigurera ett experiment
description: I denna artikel beskrivs hur du konfigurerar ett experiment i en tredjepartstjänst.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946208"
---
# <a name="set-up-an-experiment"></a>Konfigurera ett experiment

När du har [definierat en hypotes och bestämmer vilka mått du vill använda](experimentation-identify.md), måste du konfigurera experimentet i tredjeparttjänsten. I bilden nedan visas alla steg som ingår när du konfigurerar och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar.

[ ![Experimentets användarresa – Konfiguration.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Ställa in experimentet i tredjepartstjänsten
Nu bör du ha valt att köra och övervaka din tredjepartstjänst och sedan konfigurera experimentanslutningen. Dessa förutsättningar är listade vid [experiment i Dynamics 365 Commerce](experimentation-overview.md).

Följ de steg som krävs för att skapa experimentet i den tredjepartstjänsten. Om anslutningen är korrekt konfigurerad visas den fullständiga listan över experiment som du konfigurerar i tredjepartstjänst i Commerce webbplatsskaparen inom cirka 5 minuter.

## <a name="set-up-your-success-metrics"></a>Ställ in dina mätvärden för framgång
Varje experiment behöver mätvärden för att mäta effekterna av varianterna och för att validera hypotesen. Följ instruktionerna nedan för att aktivera beräkningen av mått i tjänsten från tredje part med hjälp av händelser för direkt telemetri från Dynamics 365 Commerce.

Följ de här stegen om du vill konfigurera framgångsmått för färdiga moduler.

1. I Commerce webbplatsskaparen väljer du fliken **Sidor** i det vänstra navigeringsfönstret och väljer sedan den sida som du vill samla in mått för. 
1. Gå till avsnittet **händelse-ID för att spåra** i egenskapsrutan till höger på den sida eller modul som du vill spåra.
1. Välj **Vy**. En lista över alla klickhändelse-ID:n visas. Kopiera den händelse som du vill spåra och klistra sedan in händelsenyckeln på den angivna platsen i tredjepartstjänsten. Om du behöver fler än en händelse kopierar du tangenterna en i taget. 
1. För sidvyer kan du använda hashvärdet SHA-256 för sidnamnet i webbplatsverktyget där `.PageView` läggs till. Händelse-ID:t för `Homepage.PageView` skulle till exempel vara `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Vidta alla andra steg för att följa upp mätvärden som krävs i tjänsten för tredje part.

Följ stegen nedan om du vill instrumentera klickhändelser på en anpassad modul:

1. Förbered ett **TelemetryContent**-objekt för modulen med funktionen nedan. Den här funktionen använder sidnamn, modulnamn och SDK-tillhandahållet standardtelemeterobjekt som indata.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    Följande utgör ett exempel: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Skapa de nyttolastdata som innehåller information om vad som behöver läsas in. För knappar och andra statiska kontroller kan du inkludera **etext** som "Handla nu" eller "Sök". För komponenter med klick, till exempel klick på ett produktkort, kan du skicka det **recid** som är post-ID:t för produkten eller produkt-ID:t.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Som ett exempel på statiska kontroller skickar du knapptextsträngen enligt nedan:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Som ett exempel på produktklick skickar du recordId enligt nedan:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Anropa funktionen **OnClick** för att registrera händelsen.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    Följande utgör ett exempel:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Föregående steg
[Identifiera en hypotes och fastställa mätvärden för ett experiment](experimentation-identify.md) 


## <a name="next-step"></a>Gå vidare
[Ansluta till och redigera ett experiment](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
