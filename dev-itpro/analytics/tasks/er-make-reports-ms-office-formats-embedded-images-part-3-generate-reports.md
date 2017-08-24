--- 
title: "Generera rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att generera elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4576d89923926971ab3ca30dc702baedf05f602a
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="generate-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er"></a>Generera rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att generera elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder.

I det här exemplet ska du använda skapade ER-konfigurationer för exempelföretaget, "Litware, Inc.".  För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 2: Granska konfigurationer)". Dessa steg kan utföras i USMF-företaget.


## <a name="run-format-with-initial-model-mapping"></a>Kör format med inledande modellmappning
1. Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.
2. Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".
3. Klicka på Ställ in i åtgärdsfönstret.
4. Klicka på Kontrollera.
5. Klicka på Testutskrift
    * Kör formatet i testsyfte.  
6. Välj Ja i fältet Överlåtbart checkformat.
7. Klicka på OK.
    * Granska den skapade utleveransen. Observera att företagets logotyp visas i rapporten samt den behöriga personens underskrift. Signaturbilden hämtas från fältet för datatypen Behållare i checklayoutposten som associeras med det valda bankkontot.  
8. Expandera avsnittet Kopior.
9. Klicka på Redigera.
10. Ange "Skriv ut vattenstämpel som annullerad" i fältet Vattenstämpel.
    * Ändra layoutinställningarna för vattenstämpel för att visa vattenstämpeln när dokument skapas i ett formatelement för Excel-kalkylblad.  
11. Klicka på Testutskrift
12. Klicka på OK.
    * Granska den skapade utleveransen. Kontrollera att vattenstämpeln visas i rapporten i enlighet med det valda alternativet.  
13. Stäng sidan.
14. Klicka på Hantera betalningar i åtgärdsfönstret.
15. Klicka på Checkar.
16. Klicka på Visa filter.
17. Använd följande filter: Ange filtervärdet 381, 385, 389 i fältet Checknummer med filteroperatorn "är någon av".
18. Markera alla rader i listan.
19. Klicka på Skriv ut checkkopia.
    * Kör formatet om du vill skriva ut valda checkar igen.  
    * Granska den skapade utleveransen. Observera att valda checkar har skrivits ut igen. Företagets logotyp och etiketter skrivs inte ut eftersom de visas på den förtryckta blanketten.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Ändra mappning av den importerade datamodellen
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
4. Välj "Modell för checkar" i trädet.
5. Klicka på Designer.
6. Klicka på Mappa modell till datakälla.
7. Klicka på Designer.
    * Vi vill ändra bindningen för datamodellens signaturobjekt för att hämta signaturbilden från filen som har kopplats till checklayoutposten som associeras med det valda bankkontot.  
8. Inaktivera Visa detaljer.
9. Expandera "layout" i trädet.
10. Expandera "layout\signature" i trädet.
11. Välj layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp i trädet.
12. Expandera chequesaccount i trädet.
13. Expandera "chequesaccount\<Relations" i trädet.
14. Expandera "chequesaccount\<Relations\BankChequeLayout" i trädet.
15. Expandera "chequesaccount\<Relations\BankChequeLayout\<Relations" i trädet.
16. Expandera chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents i trädet.
17. Välj "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()" i trädet.
18. Klicka på Bind.
19. Klicka på Spara.
20. Stäng sidan.
21. Stäng sidan.
22. Stäng sidan.
23. Stäng sidan.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Kör formatet med den justerade modellmappningen
1. Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Bankkonto med värdet på USMF OPER.
3. Klicka på Ställ in i åtgärdsfönstret.
4. Klicka på Kontrollera.
5. Klicka på Testutskrift
6. Klicka på OK.
    * Granska den skapade utleveransen. Observera att bilden från dokumenthanteringsbilagan visas som underskriften för en behörig person.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Använd Microsoft Word-dokument som en mall i det importerade formatet
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
4. Expandera "Modell för checkar" i trädet.
5. Välj Model for cheques\Cheques printing format i trädet.
6. Klicka på Designer.
7. Klicka på Bilagor.
8. Klicka på Ta bort.
9. Klicka på Ja.
10. Klicka på Ny.
11. Klicka på Arkiv.
    * Klicka på Bläddra och välj den i förväg hämtade Word.docx-filen för checkmall.  
12. Stäng sidan.
13. Ange eller välj ett värde i fältet Template.
14. Klicka på Spara.
15. Stäng sidan.
16. Klicka på Redigera.
17. Välj Yes i fältet Run Draft.
18. Stäng sidan.
19. Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.
20. Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".
21. Klicka på Kontrollera.
22. Klicka på Testutskrift
23. Klicka på OK.
    * Granska den skapade utleveransen. Observera att utdata har skapats som ett Microsoft Word-dokument med inbäddade bilder som innehåller företagslogotypen, underskrift av en behörig person och den markerade texten i vattenstämpeln.  


