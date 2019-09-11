---
title: Skapa ett autogiromedgivande för en kund
description: Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ca5ff2290df2179004ca1cebd11f67fbb7a724e
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916379"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Skapa ett autogiromedgivande för en kund

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.


## <a name="create-a-bank-account"></a>Skapa ett bankkonto
1. I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.
2. Välj en post i listan. Välj till exempel US-001
3. Klicka på **Kund** i åtgärdsfönstret.
4. Klicka på **Bankkonton**.
5. Klicka på **Ny**.
6. Ange ett värde i fältet **Bankkonto**.
7. Skriv ett värde i fältet **Namn**.
8. Ange ett värde i fältet **IBAN**.
9. Ange ett värde i fältet **Valuta**.
10. Klicka på **Spara**.
11. Stäng sidan.
12. I **Navigeringsfönstret**, gå till **Moduler > Kassa- och bankhantering > Bankkonton > Bankkonton**.
13. Hitta och markera önskad post i listan.
14. Klicka på länken på den valda raden i listan.
15. Klicka på **Redigera**.
16. Expandera snabbfliken **Ytterligare identifiering**.
17. Ange ett värde i fältet **ID för direktdebitering**.
18. Ange ett värde i fältet **IBAN**.
19. Stäng sidan.
20. Stäng sidan.

## <a name="define-the-electronic-payment-method"></a>Definiera den elektroniska betalningsmetoden
1. I **navigeringsfönstret**, gå till **Moduler > Kundreskontra > Betalningsinställning > Betalningsmetoder**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Betalningsmetod**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj "Elektronisk betalning" i fältet **Betalningstyp**. Betalningstypen för en betalningsmetod med autogiromedgivande måste vara elektronisk betalning.
6. Välj Ja i fältet **Kräv medgivande**.
7. Stäng sidan.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Lägg till ett autogiromedgivande till en kund.
1. I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.
2. Välj en post i listan. Välj till exempel US-001
3. Klicka på **Redigera**.
4. Expandera snabbfliken **Standardvärden för betalningar**.
5. I fältet **Betalningsmetod** anger du eller väljer ett värde.
6. Expandera snabbfliken **Standardvärden för betalningar**.
7. Expandera snabbfliken **Autogiromedgivanden**.
8. Klicka på **Lägg till**.
9. I fältet **Bankkonto** anger du eller väljer ett värde.
10. Ange eller välj ett värde i fältet **Betalningsmottagarens bankkonto**.
11. I fältet **Betalningsfrekvens**, ange det antal betalningar som du förväntar dig att bearbeta för detta medgivande.
12. Klicka på **OK**.
13. Klicka på **Skriv ut**.
14. Klicka på **Medgivanderapport**.
15. Stäng sidan.
16. Klicka på **Redigera**.
17. Ange ett datum i fältet **Datum för undertecknande**.
18. Klicka på **Ja**.
19. Ange platsen där medgivandet signerades.
20. Klicka på **OK**.
21. Stäng sidan.

## <a name="create-a-free-text-invoice-with-mandate"></a>Skapa en fritextfaktura med fullmakt
1. I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Fakturor > Alla fritextfakturor**.
2. Klicka på **Ny**.
3. Välj kunden som du lagt till medgivande för.
4. Ange eller välj ett värde i fältet **Autogiromedgivande-ID**.

