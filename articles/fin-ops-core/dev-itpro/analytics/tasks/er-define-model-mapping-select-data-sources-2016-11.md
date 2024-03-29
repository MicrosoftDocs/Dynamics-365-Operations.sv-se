---
title: Definiera ER-modellmappningar och välj datakällor för dem
description: Detta ämne beskriver hur en Systemadministratör eller Utvecklare för elektronisk rapportering kan välja datakällor för en datamodell för elektronisk rapportering.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
ms.openlocfilehash: afef2c22d7fa18a92ebad310d793a892f3496ec1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291157"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>Definiera ER-modellmappningar och välj datakällor för dem

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan välja datakällor för en datamodell för elektronisk rapportering (ER). Datakällorna kopplas till enskilda komponenter för den valda datamodellen vid designtidpunkten och datamodellen fylls i med affärsdata vid körning. I det här exemplet ska du skapa välja datakällor för en befintlig datamodell som har skapats för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Skapa en ny datamodell".


## <a name="open-the-electronic-reporting-configurations-tree"></a>Öppna trädet för elektroniska rapporteringskonfigurationer
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.

## <a name="insert-a-new-model-mapping"></a>Infoga en ny modellmappning
1. Välj "Betalningar (förenklad modell)" i trädet.
2. Klicka på Designer.
3. Klicka på Mappa modell till datakälla.
4. Klicka på Ny.
    * Då skapas en ny post som ska mappa datamodellen till datakällorna. I det här exemplet mappar du datamodellen till datakällorna för önskad betalningstyp: kreditöverföring.     Det går att utforma fler än en mappning för en särskild datamodell. Du kan till exempel skapa en mappning för olika typer av betalningar, till exempel för debet- eller kreditöverföringar. I det här exemplet skapar du en mappning för kreditöverföringar.  
5. Skriv "CT-mappning" i fältet Namn.
    * CT-mappning  
6. Skriv "Betalningsmodell som mappar CT" i fältet Beskrivning.
    * Betalningsmodell som mappar CT  
7. I fältet Definition anger du "CustomerCreditTransferInitiation".
    * CustomerCreditTransferInitiation  
8. ResolveChanges the Definition.
9. Klicka på Spara.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Definiera obligatoriska datakällor för den aktuella modellmappningen
1. Klicka på Designer.
2. Välj "Dynamics 365 for Operations\Table records" i trädet.
3. Klicka på Lägg till rot.
    * Ange den här datakällan för att komma åt betalningstransaktioner.  
4. Skriv "Transaktioner" i fältet Namn.
    * Transaktioner  
5. Ange "Transaktioner" i fältet Etikett.
    * Transaktioner  
6. Ange "Redovisningsjournalrader" i fältet Hjälp.
    * Redovisningsjournalrader  
7. Välj Ja i fältet Fråga efter fråga.
    * Välj Ja.  
8. Skriv "LedgerJournalTrans" i fältet Tabell.
    * LedgerJournalTrans  
9. Klicka på OK.
    * Välj tabellen LedgerJournalTrans som en datakälla för den aktuella datamodellen.  
10. Välj Funktioner/Beräknat fält i trädet.
11. Klicka på Lägg till.
    * Klicka på Lägg till för att lägga till ett nytt beräknat fält.  
12. Skriv "$EndToEndID" i fältet Namn.
    * $EndToEndID  
13. Klicka på Redigera formel.
14. Välj "Sträng\SAMMANFOGA" i trädet.
15. Klicka på funktionen Lägg till.
16. Expandera "Transaktioner" i trädet.
17. Välj "Transaktioner\Verifikation" i trädet.
18. Klicka på Lägg till datakälla.
19. I formelfältet anger du "CONCATENATE(Transactions.Voucher, "-", ".
    * Skriv [ , "-", ] i slutet av formeln.  
20. Välj "Sträng\TEXT" i trädet.
21. Klicka på funktionen Lägg till.
22. Välj "Transaktioner\Post-ID(RecId)" i trädet.
23. Klicka på Lägg till datakälla.
24. I formelfältet anger du "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".
    * Skriv [))] i slutet av formeln.  
25. Klicka på Spara.
    * Kontrollera att inga fel har upptäckts för den skapade formeln. Mer information finns i fliken FEL under formelredigeringskontrollen.  
26. Stäng sidan.
27. Klicka på OK.
    * Lägga till det beräknade fält till den här datakällan.  
28. Klicka på Lägg till.
    * Klicka på Lägg till för att lägga till ett nytt beräknat fält.  
29. Skriv "$Amount" i fältet Namn.
    * $Amount  
30. Klicka på Redigera formel.
31. Expandera "Transaktioner" i trädet.
32. Välj "Transaktioner\Debet(AmountCurDebit)" i trädet.
33. Klicka på Lägg till datakälla.
34. I formelfältet anger du "Transactions.AmountCurDebit - ".
    * Skriv[ - ] i slutet av formeln.  
35. Välj "Transaktioner\Kredit(AmountCurCredit)" i trädet.
36. Klicka på Lägg till datakälla.
37. Klicka på Spara.
38. Stäng sidan.
39. Klicka på OK.
    * Då läggs fältet Beräknat $Amount till den valda datakällan för den aktuella datamodellen.  
40. Välj Transactions\$Amount i trädet.
41. Expandera "Transaktioner" i trädet.
42. Expandera eller komprimera Transactions\$Amount i trädet.
43. Expandera eller komprimera "Transaktioner" i trädet.
44. Välj "Dynamics 365 for Operations\Table records" i trädet.
45. Klicka på Lägg till rot.
    * Ange den här datakällan för att komma åt företagets bankkontodetaljer.  
46. Skriv "BankAccount" i fältet Namn.
    * BankAccount  
47. Ange "Bankkonto" i fältet Etikett.
    * Bankkonto  
48. Ange "Bankkonto" i fältet Hjälp.
    * Bankkonto  
49. Välj Ja i fältet Fråga efter fråga.
    * Välj Ja.  
50. Skriv "BankAccountTable" i fältet Tabell.
    * BankAccountTable  
51. Klicka på OK.
    * Välj tabellen BankAccountTable som en datakälla för den aktuella datamodellen.  
52. Klicka på Lägg till rot.
    * Ange den här datakällan för att komma åt företagets förutsättningar.  
53. Skriv "Företag" i fältet Namn.
    * Företag  
54. Skriv ett värde i fältet Etikett.
    * Företagsupplysningar  
55. Ange "Företagsinformation" i fältet Hjälp.
    * Företagsupplysningar  
56. Välj Ja i fältet Fråga efter fråga.
    * Välj Ja.  
57. Skriv "CompanyInfo" i fältet Tabell.
    * CompanyInfo  
58. Klicka på OK.
    * Välj tabellen CompanyInfo som en datakälla för den aktuella datamodellen.  
59. Välj Funktioner/Beräknat fält i trädet.
60. Klicka på Lägg till rot.
    * Infoga ett beräknat fält som en ny datakälla.  
61. Skriv "ProcessingDateTime" i fältet Namn.
    * ProcessingDateTime  
62. Ange "Datum och tid för bearbetning" i fältet Etikett.
    * Bearbetar datum och tid  
63. Klicka på Redigera formel.
64. I trädet väljer du "Date/time\SESSIONNOW".
65. Klicka på funktionen Lägg till.
66. Klicka på Spara.
67. Stäng sidan.
68. Klicka på OK.
    * Lägg till fältet Beräknat ProcessingDateTime som en datakälla för den aktuella datamodellen.  
69. Klicka på Spara.
70. Stäng sidan.
71. Stäng sidan.
72. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
