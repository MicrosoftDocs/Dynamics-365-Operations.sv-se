---
title: Ändra format genom att återanvända Excel-mallar
description: För att slutföra dessa steg i denna procedur måste du först slutföra proceduren ER - designa en konfiguration för att skapa rapporter i OPENXML-format".
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24eb64679b458d14e30dc5b4365c7305d71cfc4c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754900"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>Ändra format genom att återanvända Excel-mallar

[!include [banner](../../includes/banner.md)]

För att slutföra dessa steg i denna procedur måste du först slutföra proceduren ER - designa en konfiguration för att skapa rapporter i OPENXML-format".

Den här proceduren beskriver hur du ändrar formatkonfigurationen i en elektronisk rapportering (ER) genom att omtillämpa en Microsoft Excel-mall som har ändrats. I den här proceduren ska du importera en modifierad Excel-mall i ER-formatkonfigurationer som har skapats för exempelföretaget Litware, Inc. och använd dem för att skapa elektroniska dokument. Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen GBSI. Innan du börjar, se till att ladda ner och spara filen SampleVendPaymWsReport2.xlsx som listas i hjälpavsnittet Ändra elektroniskt rapporteringsformat genom att återapplicera en Excel-mall (ändra-elektroniskt-rapporteringsformat-återapplicera-excel-mall/).

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.  

## <a name="select-the-er-format"></a>Välj ER-format
1. Klicka på Reporting configurations.
2. Expandera "Betalningsmodell" i trädet.
3. Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.
4. Klicka på Bilagor.
    * Observera att Excel-filen SampleVendPaymWsReport.xlsx används som mall för bearbetning av betalningsplansjournal.   
5. Klicka på Öppna.
    * Klicka på Öppna för att utforska layouten i Excel-mallen.  
    * Granska mallen. Observera att den innehåller följande uppgifter för varje betalningsrad: leverantörskontonummer, leverantörsnamn, bank, organisationsnummer, kontonummer, debet, kredit och valuta. Vi vill utöka listan genom att lägga till information om betalningsdatum.   
6. Stäng sidan.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Använd en ny Excel-mall på ER-format
1. Klicka på Designer.
    * Öppna utkastversionen av det valda ER-formatet för redigering.  
2. Klicka på Importera i åtgärdsfönstret.
3. Klicka på Uppdatera från Excel.
    * Klicka på "Uppdatera mall" och välj filen SampleVendPaymWsReport2.xlsx.  
    * Klicka på Uppdatera mall och bläddra om du vill komma till filen SampleVendPaymWsReport2.xlsx som hämtades tidigare.  
4. Klicka på OK.
    * Mallen SampleVendPaymWsReport2.xlsx används. Strukturen för ER-formatet synkroniseras med innehållet i mallen vars element läggs till i ER-formatet. De befintliga element i ER-formatet som inte finns i mallen tas bort från formatdefinitionen.  
5. Välj Excel i trädet.
    * Observera att fältet Mall nu innehåller en referens till den nya mallen.   
6. Klicka på Bilagor.
7. Klicka på Öppna.
    * Klicka på Öppna för att utforska den redigerade Excel-mallen.  
    * Granska mallen. Observera att den nu innehåller en rad för betalningsdatumet.   
8. Stäng sidan.
9. Expandera Excel i trädet.
10. Expandera "Excel\PaymLines" i trädet.
11. Välj Excel\PaymLines\PaymDate i trädet.
    * Observera att ER-formatet nu innehåller ett till objekt. En cell, PaymDate, har lagts till Excel-mallen.  
12. Klicka på fliken Mappning.
13. Expandera "modell" i trädet.
14. Expandera "modell\Betalningar" i trädet.
15. Välj "modell\Betalningar\Transaktionsdatum(TransactionDate)" i trädet.
16. Klicka på Bind.
    * Ange vilka data som läggs till i den nya cellen vid körning.  
17. Klicka på Spara.
18. Stäng sidan.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Aktivera den ändrade utkastversionen av ER-formatet så att den kan användas vid bearbetning av betalningsplansjournal
1. Klicka på Configurations i åtgärdsfönstret.
2. Klicka på User parameters.
3. Välj Yes i fältet Run settings.
4. Klicka på OK.
5. Klicka på Redigera.
6. Välj Yes i fältet Run Draft.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Använd den ändrade utkastversionen av ER-formatet för bearbetning av betalningsplansjournal

Granska det skapade kalkylbladet, inklusive den nya detaljen på betalningsraderna – betalningsdatum.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]