---
title: Källskatt i försäljningstransaktioner
description: Detta ämne innehåller en lista med steg för att undvika beräkning av källskatt för valda kunder. För kunder som anger källskatt i sina betalningar till dig kan du tilldela standardkällskattegruppen.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d659004a1f61b63d6a782ba6b45bb99030bae9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727438"
---
# <a name="withholding-tax-in-sales-transactions"></a>Källskatt i försäljningstransaktioner

Detta ämne innehåller en lista med steg för att undvika beräkning av källskatt för valda kunder. För kunder som anger källskatt i sina betalningar till dig kan du tilldela **Standardkällskattegruppen** på sidan **Kunder**. 

1. Gå till **Navigeringsfönster > Moduler > Kundreskontra > Kunder > Alla kunder**.

2. Klicka på respektive kundkonto och sedan på **Redigera**.

3. I fliken **Faktura och leverans** anger du fältet **Beräkna källskatt** som **Ja**.

   > [!NOTE] 
   > Källskatt beräknas inte om **Beräkna källskatt** inte aktiveras för denna kund i huvuddatan.

4. Välj en källskattegrupp i **Källskattegrupp**.

5. Klicka på **Spara**.

För artiklar/tjänster som är källskattepliktiga kan du tilldela **Standardkällskattegrupp för artiklar** under **Frisläppta produkter**.

1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.

2. Klicka på respektive artikelnummer och sedan på **Redigera**.

3. I fliken **Sälj** klickar du på **Beräkna säljskatt**.

   > [!NOTE] 
   > Källskatt beräknas inte om **Beräkna källskatt** inte anges som **Ja** för denna artikel i fliken **Sälj** på sidan **Frisläppt produkt**.

4. Välj en grupp för artikelkällskatt i listan **Källskattegrupp för artiklar**.

5. Klicka på **Spara**.

Källskattegrupper och artikelkällskattegrupper kan tilldelas på sidan **Försäljningsorder**. 

Standardkällskattegruppen och artikelkällskattegruppen används som standardposter på försäljningsorderrader när du skapar en ny försäljningsorder.

Källskatt beräknas och bokförs i **kundbetalningsjournalen**. Du kan manuellt justera den tillämpliga källskattekoden och det faktiska källskattebeloppet på fliken **Källskatt** på sidan **Kvitta transaktioner**.

Det beräknade källskattebeloppet dras av från kundbetalningen och bokförs på **motkontot för källskatt** i en relaterad verifikation.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
