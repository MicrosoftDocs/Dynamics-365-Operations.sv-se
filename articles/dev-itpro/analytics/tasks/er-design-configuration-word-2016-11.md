--- 
title: "Utforma en konfiguration för rapportgenerering i Microsoft Word-format för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) så att detta skapar rapporter som Microsoft Word-filer."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7f80dc8411d38d051b01d77e35635a920d8803a6
ms.openlocfilehash: 300cf6ed1a5a7098e71b812d682c1b51c2cf786c
ms.contentlocale: sv-se
ms.lasthandoff: 11/06/2017

---
# <a name="design-a-configuration-for-generating-reports-in-microsoft-word-format-for-electronic-reporting-er"></a>Utforma en konfiguration för rapportgenerering i Microsoft Word-format för elektronisk rapportering (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) så att detta skapar rapporter som Microsoft Word-filer. Dessa steg kan utföras i GBSI-företaget.

För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en ER-konfiguration för att skapa rapporter i OPENXML-format". Du måste också (i förväg) hämta och spara följande mallar lokalt för exempelrapporten:

[Mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266)

[Bunden mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266)

Denna procedur är avsedd för en funktion som lades till i Microsoft Dynamics 365 for Operations, version 1611.


## <a name="select-the-existing-er-report-configuration"></a>Markera den befintliga ER-rapportkonfigurationen
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören "Litware, Inc." är markerad som aktiv.  
2. Klicka på Reporting configurations.
    * Vi kommer att återanvända den befintliga ER-konfigurationen som ursprungligen har skapats för att generera rapportutdata i OPENXML-format.  
3. Expandera "Betalningsmodell" i trädet.
4. Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.
5. Klicka på Designer.

## <a name="replace-the-excel-template-with-the-word-template"></a>Byt ut Excel-mallen mot Word-mallen
    * För närvarande används Excel-dokumentet som en mall för att generera utdata i OPENXML-format. Vi kommer att importera rapportmallen i Word-format.  
1. Klicka på Bilagor.
    * Ersätt den befintliga Excel-mallen med den Word-mall som du hämtade förut, Mall för betalningsrapport. Observera att den här mallen endast innehåller layouten i det dokument som vi vill generera som ER-utdata.  
2. Klicka på Ta bort.
3. Klicka på Ja.
4. Klicka på Ny.
5. Klicka på Arkiv.
6. Klicka på Bläddra. Navigera till och välj SampleVendPaymDocReport.docx som du hämtade tidigare. Klicka på OK.
    * Välj mallen som du hämtade i det föregående steget.  
7. Ange eller välj ett värde i fältet Template.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Utöka Word-mallen genom att lägga till en anpassad XML-kod
1. Klicka på Spara.
    * Förutom att spara konfigurationsändringar, uppdaterar åtgärden Spara även den bifogade Word-mallen. Strukturen hos det designade formatet portas till det bifogade Word-dokumentet som en ny, anpassad XML-kod med namnet "Rapport". Lägg märke till att den bifogade Word-mallen inte bara innehåller layouten i det dokument som vi vill generera som ER-utdata, utan även den datastruktur som ER fyller den här mallen med under körning.  
2. Klicka på Bilagor.
    * Nu måste du binda elementen i den anpassade XML-koden "Rapport" till Word-dokumentets delar.  
    * Om du är bekant med Word-dokument som kan utformas som formulär med innehåll som avgränsas med elementen i anpassade XML-delar, spela då upp alla stegen i nästa underordnade uppgift för att skapa dessa dokument. Mer information finns via länken https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US. Annars hoppar du över alla steg i nästa underuppgift.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Få Word med anpassad XML-kod att utföra databindningar
    * Öppna detta dokument i Word och gör följande: - Öppna fliken Word-utvecklare (anpassa menyfliken om denna inte har aktiverats än).  - Välj fönstret för XML-mappning.  - Välj den anpassade XML-koden "Rapport" i sökningen.  - Utför mappningen av elementen i den markerade, anpassade XML-koden och Word-dokumentets innehållskontroller.  - Spara det uppdaterade Word-dokumentet på en lokal enhet.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Överför Word-mallen med anpassad XML-kod bunden till innehållskontroller
1. Klicka på Ta bort.
2. Klicka på Ja.
    * Lägg till ny mall. Markera det Word-dokument som du har skapat och sparat lokalt, om du har slutfört stegen i föregående underaktivitet. Annars väljer du MS Word-mallen SampleVendPaymDocReportBounded.docx som du hämtade tidigare.  
3. Klicka på Ny.
4. Klicka på Arkiv.
5. Klicka på Bläddra. Navigera till och välj SampleVendPaymDocReportBounded.docx som du hämtade tidigare. Klicka på OK.
6. I fältet Mall väljer du mallen som du hämtade i det föregående steget.
7. Klicka på Spara.
8. Stäng sidan.

## <a name="execute-the-format-to-create-word-output"></a>Kör formatet för att skapa Word-utleverans
1. Klicka på Configurations i åtgärdsfönstret.
2. Klicka på User parameters.
3. Välj Yes i fältet Run settings.
4. Klicka på OK.
5. Klicka på Redigera.
6. Välj Yes i fältet Run Draft.
7. Klicka på Spara.
8. Stäng sidan.
9. Stäng sidan.
10. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
11. Klicka på Rader.
12. Markera eller avmarkera alla rader i listan.
13. Klicka på Betalningsstatus.
14. Klicka på Ingen.
15. Klicka på Generera betalningar.
16. Klicka på OK.
17. Klicka på OK.
    * Analysera den genererade utleveransen. Observera att skapade utdata visas i Word-format och innehåller information om de behandlade betalningarna.  


