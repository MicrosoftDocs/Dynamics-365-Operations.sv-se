--- 
title: "ER designar domänspecifika datamodeller"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0debb7276c4f3e41c2e85ce6bc63b8df5bc159f8
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="er-design-domain-specific-data-model"></a>ER designar domänspecifika datamodeller

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en datamodell för elektroniska betalningsdokument. Den här datamodellen ska senare användas som en datakälla när du skapar formatet för betalningsdokumenten.



I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Välj konfigurationsleverantören för exempelföretaget, Litware, Inc. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.  
2. Klicka på Reporting configurations.
    * Du skapar en konfiguration som innehåller en datamodell för elektroniska betalningsdokument. Den här datamodellen ska användas senare som en datakälla när du skapar formatet för betalningsdokumenten.  

## <a name="create-a-new-data-model-configuration"></a>Skapa en ny datamodellskonfiguration
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Skriv "Betalningar (förenklad modell)" i fältet Namn.
    * Betalningar (förenklad modell)  
3. Skriv "Konfiguration av betalningsmodell" i fältet Beskrivning.
    * Konfiguration av betalningsmodell  
    * Den aktiva konfigurationsleverantören anges automatiskt här. Den här leverantören kommer att kunna underhålla konfigurationen. Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.  
4. Klicka på "Skapa konfiguration" om du vill slutföra skapandet av konfigurationsuppgiften

## <a name="create-a-data-model"></a>Skapa datamodell
    * Du skapar en ny datamodell för den valda konfigurationen. Den här konfigurationsversionen ska ha statusen Utkast.  
1. Klicka på Designer.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definiera strukturen för en part som deltar i en betalningsprocess
1. Klicka på Nytt om du vill öppna dialogrutan.
2. Ange "Part" i fältet Namn.
    * Part  
3. Klicka på Lägg till.
4. Klicka på Nytt om du vill öppna dialogrutan.
5. Skriv "Namn" i fältet Namn.
    * Namn  
6. Välj "Sträng" i fältet Artikeltyp.
7. Klicka på Lägg till.
8. Ange "Part" i fältet Sök.
    * Part  
9. Klicka på Sök föregående.

## <a name="define-the-bank-structure-for-this-model"></a>Definiera bankstrukturen för den här modellen
1. Klicka på Nytt om du vill öppna dialogrutan.
2. Skriv "Agent" i fältet Namn.
    * Handläggare  
3. Välj "Post" i fältet Artikeltyp.
4. Klicka på Lägg till.
5. Ange "Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär)" i fältet Beskrivning.
    * Finansinstitut (till exempel en bank) som tillhandahåller service av ett konto för parten (gäldenär/borgenär).  
6. Klicka på Nytt om du vill öppna dialogrutan.
7. Skriv "Namn" i fältet Namn.
    * Namn  
8. Välj "Sträng" i fältet Artikeltyp.
9. Klicka på Lägg till.
10. Klicka på Nytt om du vill öppna dialogrutan.
11. Skriv "SWIFT" i fältet Namn.
    * SWIFT  
12. Klicka på Lägg till.
13. Ange "Bankidentifieringskod" i fältet Beskrivning.
    * Bankens identifieringskod  
14. Klicka på Nytt om du vill öppna dialogrutan.
15. Skriv "RoutingNumber" i fältet Namn.
    * RoutingNumber  
16. Klicka på Lägg till.
17. Ange "Ruttnummer" i fältet Beskrivning.
    * Clearingnummer  
18. Klicka på Sök föregående.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definiera bankkontostrukturen för den här modellen
1. Klicka på Nytt om du vill öppna dialogrutan.
2. Skriv "Konto" i fältet Namn.
    * Konto  
3. Välj "Post" i fältet Artikeltyp.
4. Klicka på Lägg till.
5. Ange "Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank)" i fältet Beskrivning.
    * Identifiering av en redogörelse för en part i ett finansinstitut (t.ex. en bank).  
6. Klicka på Nytt om du vill öppna dialogrutan.
7. Skriv "Valuta" i fältet Namn.
    * Valuta  
8. Välj "Sträng" i fältet Artikeltyp.
9. Klicka på Lägg till.
10. Ange "Valutakod" i fältet Beskrivning.
    * Valutakod  
11. Klicka på Nytt om du vill öppna dialogrutan.
12. Skriv "Nummer" i fältet Namn.
    * Nummer  
13. Klicka på Lägg till.
14. Klicka på Nytt om du vill öppna dialogrutan.
15. Skriv "IBAN" i fältet Namn.
    * IBAN  
16. Klicka på Lägg till.
17. Ange "Internationellt bankkontonummer" i fältet Beskrivning.
    * Internationellt bankkontonummer  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definiera betalningsmeddelandestrukturen för kreditöverföringens betalningstyp
1. Klicka på Nytt om du vill öppna dialogrutan.
2. Ange "Modellrot" i fältet "Ny nod som ett fält...".
3. Skriv "CustomerCreditTransferInitiation" i fältet Namn.
    * CustomerCreditTransferInitiation  
4. Klicka på Lägg till.
5. Ange "CustomerCreditTransferInitiation" i fältet Sök fält.
    * CustomerCreditTransferInitiation  
6. Klicka på Sök föregående.
7. Klicka på Nytt om du vill öppna dialogrutan.
8. Skriv "MessageIdentification" i fältet Namn.
    * MessageIdentification  
9. Klicka på Lägg till.
10. Ange "Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande" i fältet Beskrivning.
    * Point to Point-referens som tilldelats av den instruerande parten (och skickats till nästa part) för att identifiera ett meddelande.  
11. Klicka på Nytt om du vill öppna dialogrutan.
12. Skriv "ProcessingDateTime" i fältet Namn.
    * ProcessingDateTime  
13. Välj "DateTime" i fältet Artikeltyp.
14. Klicka på Lägg till.
15. Ange "Datum och tid då betalningsmeddelandet skapades" i fältet Beskrivning.
    * Datum och tid då betalningsmeddelandet skapades.  
16. Klicka på Nytt om du vill öppna dialogrutan.
    * Definiera betalningstransaktionsstrukturen för den här modellen.  
17. Skriv "Betalningar" i fältet Namn.
    * Betalningar  
18. Välj "Postlista" i fältet Artikeltyp.
19. Klicka på Lägg till.
20. Ange "Betalningsrader för det aktuella meddelandet" i fältet Beskrivning.
    * Betalningsrader för det aktuella meddelandet  
21. Klicka på Nytt om du vill öppna dialogrutan.
22. Skriv "Betalningsmottagare" i fältet Namn.
    * Betalningsmottagare  
23. Välj "Post" i fältet Artikeltyp.
24. Klicka på Lägg till.
25. Ange "Part till vilken ett penningbelopp ska betalas" i fältet Beskrivning.
    * Part till vilken ett penningbelopp ska betalas.  
26. Klicka på Byt artikelreferens.
27. Ange "Part" i fältet Sök.
    * Part  
28. Klicka på Sök nästa.
29. Klicka på OK.
30. Ange "Betalningar" i fältet Sök.
    * Betalningar  
31. Klicka på Sök nästa.
32. Klicka på Nytt om du vill öppna dialogrutan.
33. Skriv "Betalare" i fältet Namn.
    * Betalare  
34. Klicka på Lägg till.
35. Ange "Part som är skyldig den (slutliga) borgenären en viss summa pengar" i fältet Beskrivning.
    * Part som är skyldig den (slutliga) borgenären en viss summa pengar.  
36. Klicka på Byt artikelreferens.
37. Ange "Part" i fältet Sök.
    * Part  
38. Klicka på Sök nästa.
39. Klicka på OK.
40. Klicka på Sök nästa.
41. Klicka på Nytt om du vill öppna dialogrutan.
42. Skriv "Beskrivning" i fältet Namn.
    * beskrivning  
43. Välj "Sträng" i fältet Artikeltyp.
44. Klicka på Lägg till.
45. Klicka på Nytt om du vill öppna dialogrutan.
46. Skriv "Valuta" i fältet Namn.
    * Valuta  
47. Klicka på Lägg till.
48. Ange "Valutakod" i fältet Beskrivning.
    * Valutakod  
49. Klicka på Nytt om du vill öppna dialogrutan.
50. Skriv "TransactionDate" i fältet Namn.
    * TransactionDate  
51. Välj "Datum" i fältet Artikeltyp.
52. Klicka på Lägg till.
53. Ange "Transaktionsdatum" i fältet Beskrivning.
    * Transaktionsdatum  
54. Klicka på Nytt om du vill öppna dialogrutan.
55. Skriv "InstructedAmount" i fältet Namn.
    * InstructedAmount  
56. Välj "Realtal" i fältet Artikeltyp.
57. Klicka på Lägg till.
58. Ange "Det penningbelopp som ska flyttas mellan gäldenär och borgenär, före avdrag för avgifter"i fältet Beskrivning. Beloppet bör uttryckas i den valuta som har beställts av den initierande parten" i fältet Beskrivning.
    * Det penningbelopp som ska flyttas mellan betalaren och betalningsmottagaren, före avdrag för avgifter. Beloppet bör uttryckas i den valuta som har beställts av den initierande parten.  
59. Klicka på Nytt om du vill öppna dialogrutan.
60. Skriv "End2EndID" i fältet Namn.
    * End2EndID  
61. Välj "Sträng" i fältet Artikeltyp.
62. Klicka på Lägg till.
63. Ange "Den unika identifiering som tilldelats av den initierande parten" i fältet Beskrivning. Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan" i fältet Beskrivning.
    * Den unika identifiering som har tilldelats av den initierande parten. Denna identifiering överförs oförändrad i hela slutpunkt till slutpunkt-kedjan.  
64. Skriv "PaymentModel" i fältet Namn.
    * Namnet PaymentModel justeras med fördefinierade gränssnitt för betalningsformulär.  
65. Klicka på Spara.
66. Stäng sidan.


