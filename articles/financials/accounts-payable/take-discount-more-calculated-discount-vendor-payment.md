---
title: Ta en rabatt som är högre än den beräknade rabatten för en leverantörsbetalning
description: Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan. Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 730ea9bb23368d24c5a09f98fbf6bbb41d685702
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2019
ms.locfileid: "896107"
---
# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>Ta en rabatt som är högre än den beräknade rabatten för en leverantörsbetalning

[!include [banner](../includes/banner.md)]

Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för ett belopp som är större än den rabatt som ursprungligen var tillgänglig för fakturan. Det här scenariot kan inträffa om en organisation sluter ett avtal med leverantören om att betala ett lägre belopp på fakturan. 

Leverantör 3051 ger Fabrikam en kassarabatt på 4 procent, om en faktura betalas inom 7 dagar. Den 29 juni anger den en faktura på 1 000,00. Leverantören låter April göra en rabatt på 60,00 istället för den standardinställda rabatten på 40,00 som är tillgänglig för fakturan. April registrerar en enstaka betalning genom att använda betalningsjournalen för Leverantörsreskontra. Hon registrerar leverantören för betalningen och öppnar sedan sidan **Kvitta transaktioner**. Hon markerar fakturan och ändrar värdet i fältet **Kassarabattbelopp** till **60,00**.

| Markera     | Använd kassarabatt | Verifikation   | Konto | Datum      | Förfallodatum  | Faktura | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Markerad | Normal            | Fakt-10040 | 3051    | 29/6/2015 | 29/7/2015 | 10040   | 1 000,00                       | USD      | 940,00           |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 12/7/2015 |
| Kassarabattbelopp         | 60,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | 60,00     |

April bokför sedan betalningsjournalen. Fakturan kvittas fullständigt med hjälp av en betalning på 940,00 och en rabatt på 60,00.



