---
title: Skriv ut skatteinformation på överföringsorderdokument
description: I det här avsnittet beskrivs hur skatteinformationen som bestäms av skatteberäkningstjänsten kan skrivas ut på överföringsorderdokument.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e74336270ab46fc19adb4c797745c9582028391a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687483"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Skriv ut skatteinformation på överföringsorderdokument

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du skriver ut skatteinformation i överföringsorderdokument. Du kan skriva ut proformafakturadokumentet för en överföringsorder för lageröverföringar som anses vara anskaffningar inom community och inomeuropeisk anskaffning enligt EU-regler (VAT). 

Följande skatterelevanta uppgifter läggs till i överföringsorderdokumenten:

- Namnen och avsändnings- och leveransadresserna för lageröverföringen
- Leverantörens och mottagarens skatte-ID
- Enhetspriset och beskattningsunderlaget för de levererade varorna
- Momskod, momssats, momsbelopp och skattedeklarationer

För att konfigurera dessa data måste du utföra följande huvudsteg.

1. [Aktivera och ställ in momsfunktionen för överföringsorder](tasks/Tax-feature-support-for-transfer-order.md).
2. [Skapa och ställ in flera momsregistreringsnummer för en juridisk person](emea-multiple-vat-registration-numbers.md).
3. Ställ in momsregistreringskod, beskrivning, skatte direktiv och utskriftskod i momskoder. För det här exemplet skapas och synkroniseras tre momskoder Microsoft Dynamics 365 Finance: **NL-Exempt**, **BE-RC-21** och **BE-RC+21**.

    1. I Finance går du till **Moms** \> **Inställningar** \> **Mom** \> **Momsbefrielsekoder**.
    2. Välj **Redigera** och ange en beskrivning av **EU**-momsregistreringskoden. Ange till exempel **momsfria EU-försändelser med momsregistreringsnummer**.
    3. Gå till **Moms** \> **Indirekta skatter** \> **Moms** \> **Momskoder**.
    4. Välj **BE-RC-21** momskod och välj **Skattedirektiv**.
    5. Välj **Ny**.
    6. I fältet **Språk** välj **EN-US**. Sedan i fältet **Text** ange **Dokument som fastställer överföring av varor i betydelsen artikel 138. 2. c) av EU momsdirektiv 2006/112/EC**.
    7. Stäng sidan.
    8. På snabbfliken **Allmänt** i fältet **Skriv ut**, välj **Momssats**.
    8. Välj momskoden **NL-undantagen** och sedan på snabbfliken **Allmänt** i fält **Skriv ut**, välj **Momssats**.

    > [!NOTE] 
    > Momskoden, momssatsen och skattebefriad beskrivning skrivs inte ut på överföringsorderdokument om ingen beskrivning av momsbefrielsekod eller skattedirektiv upprätthålls för momskoden.

## <a name="print-the-transfer-order---shipment-document"></a>Skriv ut överföringsorder - försändelsedokument

Efter att en överföring har levererats följer du dessa steg för att skriva ut överföringsordern - försändelsedokumentet.

1. Gå till **Lagerhantering** \> **Frågor och rapporter** \> **Överföringsorder** \> **Leverans**.
2. På fliken **Parametrar** i gruppen **Skriv ut** aktiverar du **Momsinformation**.
3. På fliken **Poster som ska inkluderas** välj **Filter**, välj överföringsordernumret och välj sedan **OK**.
4. Välj **OK** för att skriva ut överföringsorder - försändelsedokument.

## <a name="print-the-transfer-order---receipt-document"></a>Skriv ut överföringsorder - kvittodokument

Efter att en överföring har mottagits följer du dessa steg för att skriva ut överföringsordern - kvittodokument.

1. Gå till **Lagerhantering** \> **Frågor och rapporter** \> **Överföringsorder** \> **Ta emot**.
2. På fliken **Parametrar** i gruppen **Skriv ut** aktiverar du **Momsinformation**.
3. På fliken **Poster som ska inkluderas** välj **Filter**, välj överföringsordernumret och välj sedan **OK**.
4. Välj **OK** för att skriva ut överföringsorder - kvittodokument.

## <a name="print-the-transfer-overview-document"></a>Skriv ut överföringens översiktsdokument

Följ dessa steg för att skriva ut överföringens översiktsdokument.

> [!NOTE]
> Skatteinformation är bara tillgänglig när överföringsordern har levererats eller mottagits.

1. Gå till **Lagerhantering** \> **Frågor och rapporter** \> **Överföringsorder** \> **Överföringsöversikt**.
2. På fliken **Parametrar** i gruppen **Skriv ut** aktiverar du **Momsinformation**.
3. På fliken **Poster som ska inkluderas** välj **Filter**, välj överföringsordernumret och välj sedan **OK**.
4. Välj **OK** för att skriva ut överföringens översiktsdokument.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
