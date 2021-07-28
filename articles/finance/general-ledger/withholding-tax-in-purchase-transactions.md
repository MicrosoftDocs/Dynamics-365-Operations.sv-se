---
title: Källskatt i inköpstransaktioner
description: För leverantörer som ska betala källskatt kan du tilldela **Standardkällskattegruppen** på sidan **Alla leverantörer**.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: d605ac0b6e4190f0c0f576d402c9b101d754b347
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356686"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Källskatt i inköpstransaktioner

För leverantörer som ska betala källskatt kan du tilldela **Standardkällskattegruppen** på sidan **Alla leverantörer**.

1. Gå till **Navigeringsfönter > Moduler > Leverantörsreskontra > Leverantörer > Alla leverantörer**.

2. Klicka på respektive leverantörskonto och sedan på **Redigera**.

3. I fliken **Faktura och leverans** anger du fältet **Beräkna källskatt** som **Ja**.

   > [!NOTE] 
   > Källskatt beräknas inte om **Beräkna källskatt** inte aktiveras för denna leverantör i datan.

4. Välj en källskattegrupp i **Källskattegrupp**.

5. Klicka på **Spara**.

För artiklar/tjänster som är källskattepliktiga kan du tilldela **Standardkällskattegrupp för artiklar** under **Frisläppta produkter**.

1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.

2. Klicka på respektive artikelnummer och sedan på **Redigera**.

3. I fliken **Inköp** klickar du på **Beräkna källskatt**.

   > [!NOTE] 
   > Källskatt beräknas inte om **Beräkna källskatt** inte anges som **Ja** för denna artikel i fliken **Inköp** på sidan **Frisläppt produkt**.

4. Välj en grupp för artikelkällskatt i listan **Källskattegrupp för artiklar**.

5. Klicka på **Spara**.

Källskattegrupper och artikelkällskattegrupper kan tilldelas på sidorna: 

- **Inköpsorder**
- **Leverantörsfaktura**
- **Fakturajournal**

Standardkällskattegruppen och artikelkällskattegruppen förs in på raderna när du skapar **inköpsorder** och/eller **Väntande leverantörsfakturor**. För **Leverantörsfakturajournal** kan du aktivera **Beräkna källskatt** och sedan välja **Källskattegrupp för artiklar** i fliken **Allmänt** i journalen.

Det tillfälliga källskattebeloppet är tillgängligt i fältet **Justerad källskatt** i fliken **Summor** på sidan **Inköpsorder**.

![Källskatt inkluderas på inköpsordern.](media/withholding-tax-adjusted.png)

Källskatt som beräknats i **leverantörsbetalningsjournalen**. Du kan manuellt justera tillämpliga källskattekoder och de faktiska källskattebeloppen på fliken **Källskatt** på sidan **Kvitta transaktioner**.

![Källskatt kan justeras manuellt på sidan Kvitta transaktioner.](media/withholding-tax-vendor-payment-tab.png)

Det härledda källskattebeloppet dras av från leverantörsbetalningen och bokförs på **Källskattekontot** i en relaterad verifikation.

![Källskattekonto som visar en relaterad verifikation.](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]