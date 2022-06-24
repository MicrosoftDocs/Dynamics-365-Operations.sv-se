---
title: Momsspecifikation per redovisningstransaktion (rapport)
description: I den här artikeln beskrivs hur du använder rapporten Moms specifikation per redovisningstransaktion för att visa och skriva ut information om redovisningstransaktioner som moms beräknas för.
author: EricWang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: c96f457a0ea24aef1769f370c3c0657ada31eebf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898103"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Momsspecifikation per redovisningstransaktion (rapport)
[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du använder rapporten **Moms specifikation per redovisningstransaktion** för att visa och skriva ut information om redovisningstransaktioner som moms beräknas för.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Momskonton kontra icke-moms konton

Rapporten **Momsspecifikation per redovisningstransaktion** visas skattetransaktioner för både momskonton och icke-momskonton. Dessa konton kategoriseras på följande sätt:

- **Momskonto** – ett konto anses vara ett momskonto när en momstransaktion bokförs och huvudkontot på journalraden **moms** är ett momskonto, t.ex. ett konto för utgående moms eller ett konto för ingående moms.
- **Icke-momskonto** – ett konto anses vara ett icke-momskonto när en momstransaktion bokförs och huvudkontot på originaltransaktionen är ett journalraden icke-momskont, t.ex. ett intäktskonto eller ett utgiftskonto.

För skattekonton visar kolumnerna **Ursprung**, **Momsfordran** och **Momsskuld** på rapporten **0** (noll). För icke-momskonton visas belopp i dessa kolumner.

## <a name="filtering-the-data-on-the-report"></a>Filtrera data i rapporten.

När du genererar den här rapporten visas följande standardfält. Du kan använda dessa fält för att filtrera data som visas i rapporten.

| Fält                      | Beskrivning |
|----------------------------|-------------|
| Datum                       | Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett datumintervall för momstransaktionerna. |
| Huvudkonto               | Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett intervall för huvudkontona. |
| Momskod             | Använd fälten i avsnitten **Från** och **Till** om du vill definiera ett intervall för momskoder. |
| Gruppering                   | Välj om rapporten ska grupperas efter redovisningskonto eller momskod. |
| Delsumma efter momskod | Ställ in det här alternativet till **ja** om du vill visa delsummor efter momskod. |
| Endast summor                | Ställ in det här alternativet till **ja** om du endast vill visa summor. |
| Endast huvudkonton         | Ställ in det här alternativet till **ja** om du endast vill inkludera huvudkonton i rapporten. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Visa endast icke-momskonton i rapporten

Om du bara vill visa icke-momskonton i rapporten ställer du in ett filtervillkor, t.ex. en asterisk (\*), som visas på bilden nedan.

![Rapport som visar icke-momskonton.](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
