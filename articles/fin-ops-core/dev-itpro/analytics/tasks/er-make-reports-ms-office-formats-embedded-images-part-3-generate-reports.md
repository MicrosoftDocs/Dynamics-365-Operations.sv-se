---
title: Skapa rapporter i Office-format som omfattar inbäddade bilder
description: I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att skapa elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78dcdbd83dc717104d437662f7f451c9ecb714cf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684389"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Skapa rapporter i Office-format som omfattar inbäddade bilder

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att skapa elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder.

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
    * Granska den skapade utleveransen. Företagets logotyp visas i rapporten samt den behöriga personens underskrift. Signaturbilden hämtas från fältet för datatypen Behållare i checklayoutposten som är associerad med det valda bankkontot.  
8. Expandera avsnittet Kopior.
9. Klicka på Redigera.
10. Ange "Skriv ut vattenstämpel som annullerad" i fältet Vattenstämpel.
    * Ändra layoutinställningarna för vattenstämpel för att visa vattenstämpeln när dokument skapas i ett formatelement för Excel-kalkylblad.  
11. Klicka på Testutskrift
12. Klicka på OK.
    * Granska den skapade utleveransen. Vattenstämpeln visas i rapporten i enlighet med det valda alternativet.  
13. Stäng sidan.
14. Klicka på Hantera betalningar i åtgärdsfönstret.
15. Klicka på Checkar.
16. Klicka på Visa filter.
17. Använd följande filter: Ange filtervärdet 381, 385, 389 i fältet Checknummer med filteroperatorn "är någon av".
18. Markera alla rader i listan.
19. Klicka på Skriv ut checkkopia.
    * Kör formatet om du vill skriva ut valda checkar igen.  
    * Granska den skapade utleveransen. Valda checkar har skrivits ut igen. Företagets logotyp och etiketter skrivs inte ut eftersom de visas på den förtryckta blanketten.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Ändra mappning av den importerade datamodellen
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
4. Välj "Modell för checkar" i trädet.
5. Klicka på Designer.
6. Klicka på Mappa modell till datakälla.
7. Klicka på Designer.
    * Vi vill ändra bindningen för datamodellens signaturobjekt för att hämta signaturbilden från filen som har kopplats till checklayoutposten som är associerad med det valda bankkontot.  
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
    * Granska den skapade utleveransen. Bilden från dokumenthanteringsbilagan visas som underskrift för en behörig person.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Använd MS Word-dokument som en mall i det importerade formatet
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
    * Granska den skapade utleveransen. Utdata har genererats som ett Word-dokument med inbäddade bilder som innehåller företagslogotyp, underskrift av en behörig person och den markerade texten i vattenstämpeln.  

