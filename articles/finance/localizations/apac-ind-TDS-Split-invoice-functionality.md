---
title: Funktion för att dela upp faktura
description: I den här artikeln beskrivs inställning och funktionalitet för uppdelning av fakturor efter leveransadress och skattekontonummer (TAN).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7bbeb94429c2c69b7b8ea3089390db676a021b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874444"
---
# <a name="split-invoice-functionality"></a>Funktion för att dela upp faktura

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs inställning och funktionalitet för uppdelning av fakturor efter leveransadress och skattekontonummer (TAN).

På sidan **Leverantörsreskontraparametrar**, under fliken **Allmänt**, markerar du kryssrutan **Produktkvitto** eller **Faktura** för att bokföra och dela upp ett produktkvitto eller en faktura som har olika leveransadresser och TAN på sidan **Inköpsorder**. Den bokförda fakturan delas sedan upp efter leveransadress och TAN.

Under fliken **Sammanfattningsuppdatering**, under snabbfliken **Dela upp baserat på**, i raden **Leveransinformation**, ställer du in alternativet **Bekräftelse**, **Plocklista**, **Följesedel** eller **Faktura** på **Ja** för att bokföra och dela upp en bekräftelse, plocklista, följesedel eller faktura där olika leveransadressen och TAN har definierats för olika fakturarader på sidan **Försäljningsorder**. Fakturan delas upp först efter leveransadress och sedan efter TAN.

> [!IMPORTANT]
> - Om inga alternativ för **Leveransinformation** har ställts in på **Ja**, bokförs fakturan som en enkel faktura. Ingen fakturadelning sker.
> - Om du vill dela upp och bokföra en följesedel där fakturaraderna har olika leveransadresser och TAN måste du ställa in alternativet **Följesedel** för **Leveransinformation** på **Ja**.
> - Om du vill dela upp och bokföra en faktura där fakturaraderna har olika leveransadresser och TAN måste du ställa in alternativet **Faktura** för **Leveransinformation** på **Ja**.
> - Om du vill bokföra en faktura där fakturaraderna har olika leveransadresser men samma TAN ställer du in alternativet **Faktura** för **Leveransinformation** på **Nej**. Fakturan delas upp efter leveransadress.

## <a name="example"></a>Exempel

I det här exemplet har alternativet **Faktura** för **Leveransinformation** ställts in på **Ja** under fliken **Sammanfattningsuppdatering** på sidan **Leverantörsreskontraparametrar**. En inköpsfaktura bokförs med följande inställningar för leveransadresser och TAN på raderna:

- **Artikelrad 1:** Leveransadress 1, TAN-ABCD12345A
- **Artikelrad 2:** Leveransadress 1, TAN-ABCD12345A
- **Artikelrad 3:** Leveransadress 2, TAN-ABCE12345B
- **Artikelrad 4:** Leveransadress 3, TAN-ABCD12345A

I det här fallet delas den ursprungliga fakturan upp i två fakturor och bokförs på följande sätt:

- Faktura 1 bokförs för artikelrad 1 och artikelrad 2 eftersom båda raderna har samma leveransadress och TAN.
- Faktura 2 bokförs för artikelrad 3.
- Faktura 3 bokförs för artikelrad 4.
