--- 
title: "Skapa ett autogiromedgivande för en kund"
description: "Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Skapa ett autogiromedgivande för en kund

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.


## <a name="create-a-bank-account"></a>Skapa ett bankkonto
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Välj till exempel US-001
3. Klicka på Kund i åtgärdsfönstret.
4. Klicka på bankkonton.
5. Klicka på Ny.
6. I fältet Bankkonto, skriv ett värde.
7. Skriv ett värde i fältet Namn.
8. Ange ett värde i fältet IBAN.
9. Ange ett värde i fältet Valuta.
10. Klicka på Spara.
11. Stäng sidan.
12. Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.
13. Hitta och markera önskad post i listan.
14. Klicka på länken på den valda raden i listan.
15. Klicka på Redigera.
16. Expandera avsnittet Additional identification section.
17. I fältet för autogiro-ID anger du ett värde.
18. Ange ett värde i fältet IBAN.
19. Stäng sidan.
20. Stäng sidan.

## <a name="define-the-electronic-payment-method"></a>Definiera den elektroniska betalningsmetoden
1. Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder.
2. Klicka på Ny.
3. Skriv ett värde i fältet Betalningsmetod.
4. Ange ett värde i fältet Beskrivning.
5. Betalningstypen för en betalningsmetod med autogiromedgivande måste vara elektronisk betalning.
6. Välj Ja i fältet kräv medgivande.
7. Stäng sidan.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Lägg till ett autogiromedgivande till en kund.
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Välj till exempel US-001
3. Klicka på Redigera.
4. Expandera avsnittet Standardvärden för betalningar.
5. Ange eller välj ett värde i fältet Betalningsmetod.
6. Expandera avsnittet Standardvärden för betalningar.
7. Expandera avsnittet Autogiromedgivanden.
8. Klicka på Lägg till.
9. Ange eller välj ett värde i fältet Bankkonto.
10. Ange eller välj ett värde i fältet Creditor bank account.
11. Ange det antal betalningar som du förväntar dig att bearbeta för detta medgivande.
12. Klicka på OK.
13. Klicka på Skriv ut.
14. Klicka på Medgivanderapport.
15. Stäng sidan.
16. Klicka på Redigera.
17. I fältet Datum för undertecknande, ange ett datum.
18. Klicka på Ja.
19. Ange platsen där medgivandet signerades.
20. Klicka på OK.
21. Stäng sidan.

## <a name="create-a-free-text-invoice-with-mandate"></a>Skapa en fritextfaktura med fullmakt
1. Gå till Kundreskontra > Fakturor > Alla fritextfakturor.
2. Klicka på Ny.
3. Välj kunden som du lagt till medgivande för.
4. Ange eller välj ett värde i fältet Autogiromedgivande-ID.


