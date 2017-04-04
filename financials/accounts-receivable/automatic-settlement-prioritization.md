---
title: Automatisk kvittning och prioritering
description: "Den här artikeln beskriver hur transaktioner kvittas om du väljer Automatisk kvittning på sidan Kundreskontraparametrar. Den beskriver även hur automatisk kvittning kan användas i kombination med betalningsprioriteten."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: a751973b49febd6925267d00fb1d2c72114f86b0
ms.lasthandoff: 03/31/2017


---

# <a name="automatic-settlement-and-prioritization"></a>Automatisk kvittning och prioritering

Den här artikeln beskriver hur transaktioner kvittas om du väljer Automatisk kvittning på sidan Kundreskontraparametrar. Den beskriver även hur automatisk kvittning kan användas i kombination med betalningsprioriteten.

Du har två alternativ när du kvittar fakturor och betalningar mot andra transaktioner. Du kan manuellt välja vilka transaktioner som ska kvittas eller Microsoft Dynamics 365 för operationer kan välja transaktionerna automatiskt med funktionen Automatisk kvittning. Du kan också anpassa hur automatiska kvittningar bearbetas genom att använda alternativet **Prioritera kvittning**. De här alternativen ingår i kvittningen parametrarna som definieras i den **parametrar för kundreskontra** sida. Det sätt på vilket transaktioner automatiskt kvittas kan vara olika, beroende på vilken metod som du använder för automatisk kvittning. Följande metoder finns:

-   Användardefinierad kvittningsprioritet
-   Standardvald automatisk kvittning

Följande avsnitt beskriver hur transaktioner kvittas för varje metod.

## <a name="example-transactions"></a>Exempel på transaktioner
Exemplen på kvittningar senare i den här artikeln baseras på följande transaktioner. Alla transaktioner är för kund 2050.

| Transaktion   | Datum        | Belopp | Villkor för kassarabatt | Kassarabattdatum | Kommentarer                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faktura 1     | 15 augusti   | 100,00 | 2%14, Netto 30        | 29 augusti          |                                                                                                                                                                                               |
| Faktura 2     | 1 september | 250.00 | 2%14, Netto 30        | 15 september       |                                                                                                                                                                                               |
| Faktura 3     | 15 oktober  | 500.00 | 2% 14/Netto 30        | 29 oktober         |                                                                                                                                                                                               |
| Räntefaktura | 15 oktober  | 07:00   |                     |                    | Den här räntefakturan gäller fakturan 1 och 2 för fakturan. Beloppet beräknas som 2 % ränta på belopp som är mer eller 30 dagar efter förfallodatum. T.ex. 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="userdefined-settlement-priority"></a>Användardefinierade betalningsprioritet
Om du ställer in **Använd prioritet för automatiska betalningar** till **Ja** på sidan **Parametrar för kundreskontra** används den betalningsprioritet som du definierar på sidan **Kvittningprioritet** när transaktioner markeras för automatisk kvittning. För det här exemplet har följande kvittningprioritet definierats:

1.  transaktionstyp
    -   Betalningsavgifter
    -   Kravbrev
    -   Räntefakturor
    -   Fakturor

2.  Transaktionsdatum, stigande
3.  Verifikation

Om du bokför en betalning på 700,00 den 25 oktober kvittas betalingen för transaktionen i följande ordning.

| Verifikation       | Datum       | Faktura | Belopp i transaktionsvalutan | Belopp att kvitta | Saldo | Valuta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Räntefaktura | 2015/10/15 |         | 07:00                           | 07:00             | 0,00    | USD      |
| Faktura 1     | 2015/08/15  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Faktura 2     | 2015/09/01   | 10002   | 250.00                         | 250.00           | 0,00    | USD      |
| Faktura 3     | 2015/10/15 |         | 500.00                         | 343,00           | 157,00  | USD      |

## <a name="default-automatic-settlement"></a>Standardvald automatisk kvittning
Om det inte finns någon användardefinierad kvittningsprioritet, markeras automatiskt transaktioner för kvittning baserat på förfallodatumet. Transaktionerna som betalats måste ha samma valuta som transaktionen de ska kvittas mot. Om du bokför en betalning på 700,00 den 25 oktober väljs automatiskt följande transaktioner för kvittning.

| Verifikation       | Datum       | Faktura | Belopp i transaktionsvalutan | Belopp att kvitta | Saldo | Valuta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Faktura 1     | 2015/08/15  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Faktura 2     | 2015/09/01   | 10002   | 250.00                         | 250.00           | 0,00    | USD      |
| Faktura 3     | 2015/10/15 |         | 500.00                         | 350,00           | 150,00  | USD      |
| Räntefaktura | 2015/10/15 |         | 7,00                           | 0,00             | 0,00    | USD      |




