---
title: ER Skapa en formatkonfiguration (november 2016)
description: I det här avsnittet beskrivs hur du skapar en formatkonfiguration för elektronisk rapportering (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9404d1e242c83d2103d1f24c42589c33b9f57f02
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092260"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Skapa en formatkonfiguration (november 2016)

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en formatkonfiguration för elektronisk rapportering (ER). Den här formatkonfiguration definierar formatet för elektroniska dokument som används för att bearbeta betalningar. I det här exemplet ska du skapa en konfigurering för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Mappa modellen till utvalda datakällor".


## <a name="create-a-new-format-configuration"></a>Skapa en ny formatkonfiguration
1. Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.
2. Klicka på **Rapporteringskonfiguration**.
3. I trädet väljer du **Betalningar (förenklad modell)**.
4. Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.

 > [!NOTE]
 > Om du inte ser **Skapa konfiguration** måste du aktivera designläge på sidan **Elektronisk rapportering parametrar**. 
 
5. I fältet **Nytt** anger du **Format som baseras på datamodellen PaymentModel**.
6. I fältet **Namn**, ange **BACS (fiktivt UK)**.
7. I fältet **Beskrivning** ange **BACS-leverantörsbetalningsformat (fiktivt UK)**.
    * Den aktiva konfigurationsleverantören anges automatiskt här. Den här leverantören kommer att kunna underhålla konfigurationen. Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.  
    * Ett visst format för elektroniska dokument kan definieras. Lämna det här fältet tomt om du vill välja ett format vid körning.  
8. I fältet **Definition av datamodell** ange eller välj ett värde.
9. Klicka på **Skapa konfiguration**. En ny konfiguration har skapats. Utkastversionen kan användas för att lagra designformatet för att hantera elektroniska dokument.  

## <a name="design-the-format-of-an-electronic-document"></a>Designa formatet för ett elektroniskt dokument
1. Klicka på **Designer**.
2. Klicka på **Lägg till rot** för att öppna dialogrutan.
3. I trädet, välj **Allmänt\Fil**.
4. I fältet **Namn** ange **Xml**.
5. I fältet **Kodning** ange **UTF-8**.
6. Klicka på **OK**.
7. Klicka på **Lägg till**.
8. I trädet, välj **XML\Element**.
9. I fältet **Namn** ange **Meddelande**.
10. Klicka på **OK**.
11. I fältet träd ange **Xml\Message**.
12. Klicka på **Lägg till element**.
13. I fältet **Namn** ange **ProcessingDate**.
14. Klicka på **OK**.
15. Klicka på **Lägg till element**.
16. I fältet Namne ange **MessageId**.
17. Klicka på **OK**.
18. Klicka på **Lägg till element**.
19. I fältet **Namn** ange **Betalningar**.
20. Klicka på **OK**.
21. I trädet, välj **Xml\Message\Payments**.
22. Klicka på **Lägg till element**.
23. I fältet **Namn** ange **Artikel**.
24. Klicka på **OK**.
25. I trädet välj **Xml\Message\Payments\Item**.
26. Klicka på **Lägg till**.
27. I trädet välj **XML\Attribute**.
28. I fältet Namn, ange **Id**.
29. Klicka på **OK**.
30. Klicka på **Lägg till**.
31. I trädet, välj **XML\Element**.
32. I fältet Namn, ange **Leverantör**.
33. Klicka på **OK**.
34. I trädet välj **Xml\Message\Payments\Item\Vendor**.
35. Klicka på **Lägg till element**.
36. I fältet Namn, ange **Namn**.
37. Klicka på **OK**.
38. Klicka på **Lägg till element**.
39. I fältet **Namn** ange **Bank**.
40. Klicka på **OK**.
41. I trädet ange **Xml\Message\Payments\Item\Vendor\Bank**.
42. Klicka på **Lägg till element**.
43. I fältet **Namn** ange **RoutingNumber**.
44. Klicka på **OK**.
45. Klicka på **Lägg till element**.
46. I fältet **Namn** ange **AccountNumber**.
47. Klicka på **OK**.
48. I trädet välj **Xml\Message\Payments\Item\Vendor**.
49. Klicka på **Kopiera**.
50. I trädet välj **Xml\Message\Payments\Item**.
51. Klicka på **Klistra in**.
52. I fältet **Namn** ange **Betalare**.
53. I trädet välj **Xml\Message\Payments\Item**.
54. Klicka på **Lägg till element**.
55. I fältet **Namn** ange **Valuta**.
56. Klicka på **OK**.
57. Klicka på **Lägg till element**.
58. I fältet **Namn** ange **Beskrivning**.
59. Klicka på **OK**.
60. Klicka på **Lägg till element**.
61. I fältet Nman ange **TransDate**.
62. Klicka på **OK**.
63. Klicka på **Lägg till element**.
64. I fältet Namn ange **Belopp**.
65. Klicka på **OK**.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Förbered formatkomponenter för att mappa till datamodellelement
1. I trädet ange **Xml\Message\ProcessingDate**.
2. Klicka på **Lägg till** för att öppna dialogrutan.
3. I trädet välj **Text\DateTime**.
4. I fältet **Format** ange **åååå-MM-dd**.
5. Klicka på **OK**.
6. I trädet ange **Xml\Message\Payments\Item\TransDate**.
7. Klicka på **Lägg till DateTime**.
8. I fältet **Format** ange **åååå-MM-dd**.
9. I fältet **DateTime** ange **Datum**.
10. Klicka på **OK**.
11. I trädet ange **Xml\Message\MessageId**.
12. Klicka på **Lägg till** för att öppna dialogrutan.
13. I trädet ange **Text\String**.
14. Klicka på **OK**.
15. I trädet ange **Xml\Message\Payments\Item\Vendor\Name**.
16. Klicka på **Lägg till sträng**.
17. Klicka på **OK**.
18. I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.
19. Klicka på **Lägg till sträng**.
20. Klicka på **OK**.
21. I trädet välj **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.
22. Klicka på **Lägg till sträng**.
23. Klicka på **OK**.
24. I trädet välj **Xml\Message\Payments\Item\Payer\Name**.
25. Klicka på **Lägg till sträng**.
26. Klicka på **OK**.
27. I trädet välj **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.
28. Klicka på **Lägg till sträng**.
29. Klicka på **OK**.
30. I trädet välj **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.
31. Klicka på **Lägg till sträng**.
32. Klicka på **OK**.
33. I trädet välj **Xml\Message\Payments\Item\Currency**.
34. Klicka på **Lägg till sträng**.
35. Klicka på **OK**.
36. I trädet välj **Xml\Message\Payments\Item\Description**.
37. Klicka på **Lägg till sträng**.
38. Klicka på **OK**.
39. I trädet välj **Xml\Message\Payments\Item\Amount**.
40. Klicka på **Lägg till sträng**.
41. Klicka på **OK**.
42. Klicka på **Spara**.
43. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]