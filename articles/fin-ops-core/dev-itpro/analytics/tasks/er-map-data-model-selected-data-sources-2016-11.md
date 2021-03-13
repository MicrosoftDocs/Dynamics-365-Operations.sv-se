---
title: ER mappar datamodeller till utvalda datakällor
description: I det här avsnittet beskrivs hur du mappar en elektronisk rapporteringsmodell (ER) till valda Microsoft Dynamics 365 Finance-datakällor.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e2ba94c9ec3ecc33f0c697d9f18f763749e4ba1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093758"
---
# <a name="er-map-data-model-to-selected-data-sources"></a>ER mappar datamodeller till utvalda datakällor

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan mappa en datamodell för elektronisk rapportering (ER) till valda datakällor. Den här modellmappningen kommer senare att användas som en datakälla i en formatkonfiguration som ska användas för att hantera elektroniska betalningsdokument. I det här exemplet mappar du en datamodell för exempelföretaget Litware, Inc. till datakällor. Om du vill slutföra dessa steg måste du först slutföra stegen i proceduren "Välj datakällor för modellmappning".


## <a name="open-er-configurations-tree"></a>Öppna ER-konfigurationsträdet
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klientkonfigurationer.

## <a name="select-created-model-mapping"></a>Välj skapad modellmappning
1. Välj "Betalningar (förenklad modell)" i trädet.
    * Kontrollera att modellkonfigurationen "Betalningar (förenklad modell") har skapats i förväg. Annars avbryter du nu och återvänder när du har slutfört uppgiftsguiden "Skapa en ny konfiguration med datamodellen för den markerade domänen".  
2. Klicka på Modelldesigner.
3. Klicka på Mappa modell till datakälla.
4. Välj posten "CT-mappning".
    * CT-mappning  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Koppla skapade datakällor till datamodellelement
1. Klicka på Designer.
2. Välj "Datum för tid och bearbetning (ProcessingDateTime)" i trädet.
3. Välj "Bearbetningsdatum(ProcessingDateTime)" i trädet.
4. Klicka på Bind.
5. Välj "Identifiering av betalningsmeddelande(MessageIdentification)" i trädet.
6. Expandera "Transaktioner" i trädet.
7. Välj "Transaktioner\Journalbatchnummer(JournalNum)" i trädet.
8. Klicka på Bind.
9. Välj "Betalningar" i trädet.
10. Välj "Transaktioner" i trädet.
11. Klicka på Bind.
12. Expandera "Betalningar= Transaktioner" i trädet.
13. Expandera "Betalningar= Transaktioner\Betalningsmottagare" i trädet.
14. Expandera "Betalningar= Transaktioner\Betalningsmottagare\Konto" i trädet.
15. Välj "betalningar= Transaktioner\betalningsmottagare\Konto\Valutakod(Valuta)" i trädet.
16. Expandera "Transaktioner\vendBankAccountInTransactionCompany()" i trädet.
17. Välj "Transaktioner\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)" i trädet.
18. Klicka på Bind.
19. Välj "Betalningar= Transaktioner\Betalningsmottagare\Konto\IBAN-kod(IBAN)" i trädet.
20. Välj "Transaktioner\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)" i trädet.
21. Klicka på Bind.
22. Välj "Betalningar= Transaktioner\Betalningsmottagare\Konto\Nummer" i trädet.
23. Välj "Transaktioner\vendBankAccountInTransactionCompany()\Bankkontonummer(AccountNum)" i trädet.
24. Klicka på Bind.
25. Expandera "Betalningar= Transaktioner\Betalningsmottagare\Agent" i trädet.
26. Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\Namn" i trädet.
27. Välj "Transaktioner\vendBankAccountInTransactionCompany()\Namn" i trädet.
28. Klicka på Bind.
29. Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\Organisationsnummer(RoutingNumber)" i trädet.
30. Välj "Transaktioner\vendBankAccountInTransactionCompany()\Organisationsnummer(RegistrationNum)" i trädet.
31. Klicka på Bind.
32. Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\SWIFT-kod(SWIFT)" i trädet.
33. Välj "Transaktioner\vendBankAccountInTransactionCompany()\SWIFT-kod(SWIFTNo)" i trädet.
34. Klicka på Bind.
35. Välj "Betalningar= Transaktioner\Betalningsmottagare\Namn" i trädet.
36. Expandera "Transaktioner\findVendTable()" i trädet.
37. Välj "Transaktioner\hitta leverantörsregister ()\namn ()" i trädet.
38. Klicka på Bind.
39. Välj "Betalningar= Transaktioner\Valutakod(Valuta)" i trädet.
40. Expandera "Transaktioner\>Relationer" i trädet.
41. Expandera ”Transaktioner\>Relationer\Valutatabell(Valuta) i trädet.
42. Välj transaktioner ”Transaktioner\>Relationer\Valutatabell(Valuta)\Valutakod(CurrencyCodeISO) i trädet.
43. Klicka på Bind.
44. Expandera "Betalningar= Transaktioner\Betalare" i trädet.
45. Expandera "Betalningar= Transaktioner\Betalare\Konto" i trädet.
46. Välj "Betalningar= Transaktioner\Betalare\Konto\Valutakod(Valuta)" i trädet.
47. Välj "Bankkonto(BankAccount)" i trädet.
48. Expandera "Bankkonto(BankAccount)" i trädet.
49. Välj "Bankkonto(BankAccount)\Valuta(CurrencyCode)" i trädet.
50. Klicka på Bind.
51. Välj "Bankkonto(BankAccount)\IBAN" i trädet.
52. Välj "Betalningar= Transaktioner\Betalare\Konto\IBAN-kod(IBAN)" i trädet.
53. Klicka på Bind.
54. Välj "Betalningar= Transaktioner\Betalare\Konto\Nummer" i trädet.
55. Välj "Bankkonto(BankAccount)\Bankkontonummer(AccountNum)" i trädet.
56. Klicka på Bind.
57. Expandera "Betalningar= Transaktioner\Betalare\Agent" i trädet.
58. Välj "Betalningar= Transaktioner\Betalare\Agent\Namn" i trädet.
59. Välj "Bankkonto(BankAccount)\Namn" i trädet.
60. Klicka på Bind.
61. Välj "Betalningar= Transaktioner\Betalare\Agent\Organisationsnummer(RoutingNumber)" i trädet.
62. Välj "Bankkonto(BankAccount)\Organisationsnummer(RegistrationNum)" i trädet.
63. Klicka på Bind.
64. Välj "Betalningar= Transaktioner\Betalare\Agent\SWIFT-kod(SWIFT)" i trädet.
65. Välj "Bankkonto(BankAccount)\SWIFT-kod(SWIFTNo)" i trädet.
66. Klicka på Bind.
67. Välj "Betalningar= Transaktioner\Betalare\Namn" i trädet.
68. Välj "Företagsinformation(Företag)" i trädet.
69. Expandera "Företagsinformation(Företag)" i trädet.
70. Välj "Företagsinformation(Företag)\Namn" i trädet.
71. Klicka på Bind.
72. Välj "Betalningar= Transaktioner\Beskrivning" i trädet.
73. Välj "Transaktioner\Beskrivning(Txt)" i trädet.
74. Klicka på Bind.
75. Välj "Betalningar= Transaktioner\Slutpunkt till slutpunkt-identifieringskod(End2EndID)" i trädet.
76. Välj Transactions\$EndToEndID i trädet.
77. Klicka på Bind.
78. Välj "Betalningar= Transaktioner\Instruerat belopp(InstructedAmount)" i trädet.
79. Välj Transactions\$Amount i trädet.
80. Klicka på Bind.
81. Välj "Betalningar= Transaktioner\Transaktionsdatum(TransactionDate)" i trädet.
82. Välj "Transaktioner\Datum(TransDate)" i trädet.
83. Klicka på Bind.

## <a name="validate-created-mapping"></a>Validera skapad mappning
1. Klicka på Validera.
    * Bekräfta den nya mappningen för att säkerställa att alla bindningar är korrekta.  
2. Klicka på pilen för att Visa eller dölj avsnittet Fellista.
3. Klicka på Spara.
4. Stäng sidan.
5. Stäng sidan.
6. Stäng sidan.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Ändra status för den aktuella versionen av modellkonfigurationen
1. Klicka på Ändra status.
    * Ändra statusen för designad modellkonfiguration från Utkast till Slutfört för att göra den tillgänglig för utformning av betalningsformat.  
2. Klicka på Slutför.
    * Välj Slutför.  
3. Ange ett värde i fältet Beskrivning.
    * Till exempel "Version 1".  
4. Klicka på OK.
5. Välj den slutförda versionen av den aktuella konfigurationen.
    * Observera att den skapade konfigurationen sparas som slutförd version 1.  

