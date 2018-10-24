--- 
title: ER Skapa en formatkonfiguration (november 2016)
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 803ed4a1018d344f1b40fa1f2338fc066e784c3c
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Skapa en formatkonfiguration (november 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER). Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar. I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".


## <a name="create-a-new-format-configuration"></a>Skapa en ny formatkonfiguration
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Välj "Betalningar (förenklad modell)" i trädet.
4. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
5. Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.
6. Skriv "BACS (fiktivt UK) i fältet Namn.
    * BACS (fiktivt UK)  
7. Skriv "BACS-leverantörsbetalningsformat (fiktivt UK)" i fältet Beskrivning.
    * BACS-leverantörsbetalningsformat (fiktivt UK)  
    * Den aktiva konfigurationsleverantören anges automatiskt här. Den här leverantören kommer att kunna underhålla konfigurationen. Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.  
    * Ett visst format för elektroniska dokument kan definieras. Lämna det här fältet tomt om du vill välja ett format vid körning.  
8. Ange eller välj ett värde i fältet Data model definition.
9. Klicka på Skapa konfiguration.
    * En ny konfiguration har skapats. Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.  

## <a name="design-format-of-electronic-document"></a>Designa format för elektroniskt dokument
1. Klicka på Designer.
2. Klicka på Lägg till rot för att öppna dialogrutan.
3. Välj "Allmänt\Fil" i trädet.
4. Skriv "Xml" i fältet Namn.
    * Xml  
5. Skriv "UTF 8" i fältet Kodning.
    * UTF-8  
6. Klicka på OK.
7. Klicka på Lägg till för att öppna dialogrutan.
8. Välj "XML\Element" i trädet.
9. Skriv "Meddelande" i fältet Namn.
    * Meddelande  
10. Klicka på OK.
11. Välj "Xml\Message" i trädet.
12. Klicka på Add Element.
13. Skriv "ProcessingDate" i fältet Namn.
    * ProcessingDate  
14. Klicka på OK.
15. Klicka på Add Element.
16. Skriv "MessageId'" i fältet Namn.
    * MessageId  
17. Klicka på OK.
18. Klicka på Add Element.
19. Skriv "Betalningar" i fältet Namn.
    * Betalningar  
20. Klicka på OK.
21. Välj "Xml\Message\Payments" i trädet.
22. Klicka på Add Element.
23. Skriv "Artikel" i fältet Namn.
    * Artikel  
24. Klicka på OK.
25. Välj "Xml\Message\Payments\Item" i trädet.
26. Klicka på Lägg till för att öppna dialogrutan.
27. Välj "XML\Attribut" i trädet.
28. Skriv "Id" i fältet Namn.
    * ID  
29. Klicka på OK.
30. Klicka på Lägg till för att öppna dialogrutan.
31. Välj "XML\Element" i trädet.
32. Skriv "Leverantör" i fältet Namn.
    * Leverantör  
33. Klicka på OK.
34. Välj "Xml\Message\Payments\Item\Vendor" i trädet.
35. Klicka på Add Element.
36. Skriv "Namn" i fältet Namn.
    * Namn  
37. Klicka på OK.
38. Klicka på Add Element.
39. Skriv "Bank" i fältet Namn.
    * Bank  
40. Klicka på OK.
41. Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.
42. Klicka på Add Element.
43. Skriv "RoutingNumber" i fältet Namn.
    * RoutingNumber  
44. Klicka på OK.
45. Klicka på Add Element.
46. Skriv "AccountNumber" i fältet Namn.
    * Kontonummer  
47. Klicka på OK.
48. Välj "Xml\Message\Payments\Item\Vendor" i trädet.
49. Klicka på Kopiera.
50. Välj "Xml\Message\Payments\Item" i trädet.
51. Klicka på Paste.
52. Skriv "Betalare" i fältet Namn.
    * Betalare  
53. Välj "Xml\Message\Payments\Item" i trädet.
54. Klicka på Add Element.
55. Skriv "Valuta" i fältet Namn.
    * Valuta  
56. Klicka på OK.
57. Klicka på Add Element.
58. Skriv "Beskrivning" i fältet Namn.
    * beskrivning  
59. Klicka på OK.
60. Klicka på Add Element.
61. Skriv "TransDate" i fältet Namn.
    * TransDatum  
62. Klicka på OK.
63. Klicka på Add Element.
64. Skriv "Belopp" i fältet Namn.
    * Tid  
65. Klicka på OK.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Förbered formatkomponenter för att mappa till datamodellelement
1. Välj "Xml\Message\ProcessingDate" i trädet.
2. Klicka på Lägg till för att öppna dialogrutan.
3. Välj "Text\DateTime" i trädet.
4. Skriv "åååå-MM-dd" i fältet Format.
    * åååå/mm/dd  
5. Klicka på OK.
6. Välj "Xml\Message\Payments\Item\TransDate" i trädet.
7. Klicka på Lägg till DateTime.
8. Skriv "åååå-MM-dd" i fältet Format.
    * åååå/mm/dd  
9. Välj "Datum" i fältet DateTime-typ
10. Klicka på OK.
11. Välj "Xml\Message\MessageId" i trädet.
12. Klicka på Lägg till för att öppna dialogrutan.
13. Välj "Text\Sträng" i trädet.
14. Klicka på OK.
15. Välj "Xml\Message\Payments\Item\Vendor\Name" i trädet.
16. Klicka på Add string.
17. Klicka på OK.
18. Välj "Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber" i trädet.
19. Klicka på Add string.
20. Klicka på OK.
21. Välj "Xml\Message\Payments\Item\Vendor\Bank\AccountNumber" i trädet.
22. Klicka på Add string.
23. Klicka på OK.
24. Välj "Xml\Message\Payments\Item\Payer\Name" i trädet.
25. Klicka på Add string.
26. Klicka på OK.
27. Välj "Xml\Message\Payments\Item\Payer\Bank\RoutingNumber" i trädet.
28. Klicka på Add string.
29. Klicka på OK.
30. I trädet väljer du "Xml\Message\Payments\Item\Payer\Bank\AccountNumber".
31. Klicka på Add string.
32. Klicka på OK.
33. I trädet väljer du "Xml\Message\Payments\Item\Currency".
34. Klicka på Add string.
35. Klicka på OK.
36. I trädet väljer du "Xml\Message\Payments\Item\Description".
37. Klicka på Add string.
38. Klicka på OK.
39. I trädet väljer du "Xml\Message\Payments\Item\Amount".
40. Klicka på Add string.
41. Klicka på OK.
42. Klicka på Spara.
43. Stäng sidan.


