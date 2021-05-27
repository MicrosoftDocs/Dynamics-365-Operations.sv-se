---
title: Lägga till en QR-kod eller streckkod i transaktions- och kvittomeddelanden
description: Det här avsnittet förklarar hur man infogar QR-koder och streckkoder som representerar order-ID i transaktions- och kvittomeddelanden i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 9eea69f9618d4387f5d6320620dfee5d74813fc0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019549"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Lägga till en QR-kod eller streckkod i transaktions- och kvittomeddelanden

[!include [banner](includes/banner.md)]

Det här avsnittet förklarar hur man infogar QR-koder och streckkoder som representerar order-ID i transaktions- och kvittomeddelanden i Microsoft Dynamics 365 Commerce.

Du kan enkelt ta med QR-koder och streckkoder i transaktionsmeddelanden om du vill påskynda orderprocessen i en butiksmiljö. För att infoga QR-koder och streckkoder i e-postmeddelanden använder du en HTML **\<img\>** tagg som begär en QR-kod eller streckkodsbild från en generation och återgivningstjänster. Microsoft tillhandahåller inte denna tjänst. Det finns emellertid många gratis- eller tjänstservicetjänster som kan servera QR-koder eller streckkoder som är dynamiskt genererade baserat på ett värde som överförs i en frågesträng.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Lägga till en QR-kod eller streckkod i transaktionsmeddelande via e-post

Om du vill infoga en QR-kod eller streckkod i ett transaktionsmeddelande via e-post som skickas som en del av ett e-handelsinköp, följer du dessa steg.

1. Öppna käll-HTML-koden för transaktionsmeddelande via e-post och lägg till en HTML-tagg **\<img\>** som pekar på din QR-kod eller streckkodstjänst. Här är ett exempel:

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Här är en förklaring av föregående exempel:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representerar domänen för din QR-kod eller din streckkodstjänst.
    - **data** representerar parametern som QR-koden eller streckkodstjänsten använder för att ta emot innehållet som ska återges som en QR-kod eller streckkod.

        Värdet **%salesid%** måste tilldelas den här parametern. Lägg märke till i det här exemplet att värdet även används som alt-text för bilden.

    - **param1** och **param2** representerar ytterligare valfria parametrar.

1. Gå till **Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar** och ladda upp den uppdaterade HTML-filen till lämplig transaktionsmall.

> [!NOTE]
> Parametrarna kan skilja sig mellan leverantörer av QR-kod och streckkodstjänster. Kontakta därför din serviceleverantör för att bekräfta de parametrar som du måste tilldela värden till.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Lägga till en QR-kod eller streckkod i kvittomeddelande 

Om du vill infoga en QR-kod eller streckkod i ett kvittomeddelande som kan skickas efter att ett inköp har gjorts i kassan (POS) följer du dessa steg.

1. Öppna käll-HTML-koden för kvittomeddelande via e-post och lägg till en HTML-tagg **\<img\>** som pekar på din QR-kod eller streckkodstjänst. Här är ett exempel.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Här är en förklaring av föregående exempel:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representerar domänen för din QR-kod eller din streckkodstjänst.
    - **data** representerar parametern som QR-koden eller streckkodstjänsten använder för att ta emot innehållet som ska återges som en QR-kod eller streckkod.

        Värdet **%receiptid%** måste tilldelas den här parametern. Lägg märke till i det här exemplet att värdet även används som alt-text för bilden.

    - **param1** och **param2** representerar ytterligare valfria parametrar.

1. Gå till **Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar** och ladda upp den uppdaterade HTML till e-postmallen som har e-post-ID **emailrecpt**.

> [!NOTE]
> Parametrarna kan skilja sig mellan leverantörer av QR-kod och streckkodstjänster. Kontakta därför din serviceleverantör för att bekräfta de parametrar som du måste tilldela värden till.

## <a name="additional-resources"></a>Ytterligare resurser

[Skicka e-postkvitton från Modern POS (MPOS)](email-receipts.md)

[Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md)
