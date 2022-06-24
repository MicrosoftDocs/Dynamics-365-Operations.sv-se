---
title: Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: Det här ämnet beskriver hur du skapar konfigurationer för rapportering för att skapa elektroniska dokument som innehåller inbäddade bilder. (Del 1 - Ställa in parametrar).
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 365debc2713a7e3ef56b294bade07352fc2089b4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886626"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Gransa konfigurationer för att generera rapporter i Office-format med inbäddade bilder

[!include [banner](../../includes/banner.md)]

För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 1: Ställ in parametrar)".

Den här proceduren visar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel och Microsoft Word. I det här exemplet ska du granska ER-konfigurationer för exempelföretaget Litware, Inc.. 

Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen USMF.


## <a name="review-the-imported-data-model"></a>Granska den importerade datamodellen
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Välj "Modell för checkar" i trädet.
3. Klicka på Designer.
    * Den här modellen är utformad för betalningscheckar för företag och mappningen av den här modellen till programmets datakällor. Granska den här modellen av ER-verksamhetens designer. Observera attributen för modellelementen som visas: struktur, namn, beskrivning, datatyp och så vidare.   
4. Expandera root i trädet.
5. Välj root\cheques i trädet.
6. Expandera root\cheques i trädet.
7. Expandera root\cheques\attribute i trädet.
8. Expandera root\payer i trädet.
9. Välj root\istestrun i trädet.
10. Välj root\layout i trädet.
    * Layoutelementet för den här modellen representerar detaljerna i den utskrivna checkens formulärlayout för det valda bankkontot. Den innehåller också två noder för datatypen Behållare för att lagra bilder.   
11. Expandera root\layout i trädet.
12. Välj root\layout\company logo i trädet.
13. Expandera root\layout\company logo i trädet.
14. Välj root\layout\company logo\image i trädet.
15. Välj root\layout\company logo\isprinted i trädet.
16. Välj root\layout\signature i trädet.
17. Expandera root\layout\signature i trädet.
18. Välj root\layout\signature\image i trädet.
19. Välj root\layout\signature\isprinted i trädet.
    * Observera att två modellelement för bilddata är bundna till fälten i de register som innehåller bilder av företagets logotyp och den behöriga personens underskrift i binärt format.  
20. Expandera root\layout\watermark i trädet.
21. Klicka på Mappa modell till datakälla.
22. Klicka på Designer.
23. Expandera chequesselected i trädet.
24. Expandera "layout" i trädet.
25. Expandera layout\company logo i trädet.
26. Expandera "layout\signature" i trädet.
27. Expandera layout\watermark i trädet.
28. Ange "Visa detaljerad information" som PÅ.
    * Observera att datamodellelementet för checkar är kopplat till registret TmpChequePrintout som vid körning innehåller poster för checkar som användaren har valt för utskrift.   
29. Stäng sidan.
30. Stäng sidan.
31. Stäng sidan.

## <a name="review-the-imported-format"></a>Granska det importerade formatet
1. Expandera "Modell för checkar" i trädet.
2. Välj Model for cheques\Cheques printing format i trädet.
3. Klicka på Designer.
4. Klicka på Bilagor.
5. Klicka på Öppna.
    * Öppna den bifogade rapportens mall i Excel.  
    * Granska den bifogade rapportens Excel-mall som ska användas för att skriva ut checkar. Mallen är utformad för att skriva ut checkar på det förtryckta formuläret och innehåller två checkar per sida. Observera att två tomma bilder bäddas in. Dessa tomma bilder är till för företagets logotyp och underskriften av den person som auktoriserar en betalning. Kontrollera i Excel att bilderna har namnen CompLogo respektive SignatureImage.   
6. Stäng sidan.
7. Expandera Report i trädet.
8. Expandera Report\ChequeLines i trädet.
9. Välj Report\ChequeLines\CompLogo i trädet.
10. Ange "Visa detaljerad information" som PÅ.
    * Observera att CompLogo-formatets cellelement representerar det Excel-objekt som används för att fylla i företagets logotyp i rapporten. Det här formatelementet är bundet till bildens datamodellelement som under körning innehåller en logotyp för företaget i binärformat.   
11. Klicka på fliken Mappning.
12. Klicka på Redigering aktiverad.
    * Observera att du kan ändra formatet CompLogo-formatets cellelement så att det inte längre är aktiverat. Då döljer det associerade Excel-bildelement företagets logotyp i den skapade rapporten. Om det aktiverade uttrycket returnerar TRUE och den definierade bindningen inte hämtar någon bild, visar det associerade Excel-bildelementet en bild som har sparats i Excel-mallen.   
13. Stäng sidan.
14. Expandera "labels: Container" i trädet.
    * Vissa etiketter som visas i det förtryckta checkformuläret inkluderas i rapporten när den skapas i testsyfte. Dessa etiketter skrivs dock inte ut vid den verkliga utskriften eftersom det förtryckta formuläret redan innehåller dem.  
15. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]