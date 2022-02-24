---
title: Utforma ER-konfigurationer för rapportgenerering i Word-format
description: I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering så att detta skapar rapporter som Microsoft Word-filer.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d4959b511022e1aa98544d23da6afcda1f6adf2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681935"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a>Utforma ER-konfigurationer för rapportgenerering i Word-format

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) så att detta skapar rapporter som Microsoft Word-filer. Dessa steg kan utföras i GBSI-företaget.

För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en ER-konfiguration för att skapa rapporter i OPENXML-format". Du måste också (i förväg) hämta och spara följande mallar lokalt för exempelrapporten:

- [Mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266)
- [Bunden mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266)


Denna procedur är avsedd för en funktion som lades till i Microsoft Dynamics 365 for Operations version 1611.


## <a name="select-the-existing-er-report-configuration"></a>Markera den befintliga ER-rapportkonfigurationen
1. I **navigeringsfönstret, gå till Moduler > Organisationsadministration > Arbetsytor > Elektronisk rapportering**. Kontrollera att konfigurationsleverantören "Litware, Inc." är markerad som aktiv.  
2. Klicka på **Rapporteringskonfiguration**. Vi kommer att återanvända den befintliga ER-konfigurationen som ursprungligen har skapats för att skapa rapportutdata i OPENXML-format.  
3. Expandera "Betalningsmodell" i trädet.
4. Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.
5. Klicka på Designer.

## <a name="replace-the-excel-template-with-the-word-template"></a>Byt ut Excel-mallen mot Word-mallen

För närvarande används Excel-dokumentet som en mall för att skapa utdata i OPENXML-format. Vi kommer att importera rapportmallen i Word-format.

1. Klicka på **Bilagor**. Ersätt den befintliga Excel-mallen med den Word-mall som du hämtade förut (SampleVendPaymDocReport.docx). Observera att den här mallen endast innehåller layouten i det dokument som vi vill generera som ER-utdata.  
2. Klicka på **Ta bort**.
3. Klicka på **Ja**.
4. Klicka på **Ny**.
5. Klicka på **Arkiv**.
6. Klicka på **Bläddra**. Navigera till och välj SampleVendPaymDocReport.docx som du hämtade tidigare. Klicka på **OK**. Välj mallen som du hämtade i det föregående steget.  
7. Ange eller välj ett värde i fältet **Mall**.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Utöka Word-mallen genom att lägga till en anpassad XML-kod
1. Klicka på **Spara**. Förutom att spara konfigurationsändringar, uppdaterar åtgärden Spara även den bifogade Word-mallen. Strukturen hos det designade formatet portas till det bifogade Word-dokumentet som en ny, anpassad XML-kod med namnet "Rapport". Lägg märke till att den bifogade Word-mallen inte bara innehåller layouten i det dokument som vi vill skapa som ER-utdata, utan även den datastruktur som ER fyller den här mallen med under körning.  
2. Klicka på **Bilagor**.
    + Nu måste du binda elementen i den anpassade XML-koden "Rapport" till Word-dokumentets delar.  
    + Om du är bekant med Word-dokument som kan utformas som formulär med innehåll som avgränsas med elementen i anpassade XML-delar, spela då upp alla stegen i nästa underordnade uppgift för att skapa dessa dokument. Mer information finns i [Skapa formulär som användare fyller i eller skriver ut i Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US). Annars hoppar du över alla steg i nästa underuppgift.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Få Word med anpassad XML-kod att utföra databindningar

Öppna dokumentet i Word och gör följande:  
1. Öppna fliken Word-utvecklare (anpassa menyfliken om denna inte har aktiverats än).
2. Välj fönstret för XML-mappning.
3. Välj den anpassade XML-koden "Rapport" i sökningen.
4. Utför mappningen av elementen i den markerade, anpassade XML-koden och Word-dokumentets innehållskontroller.  5. Spara det uppdaterade Word-dokumentet på en lokal enhet.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Överför Word-mallen med anpassad XML-kod bunden till innehållskontroller
1. Klicka på **Ta bort**.
2. Klicka på **Ja**. Lägg till ny mall. Markera det Word-dokument som du har skapat och sparat lokalt, om du har slutfört stegen i föregående underaktivitet. Annars väljer du MS Word-mallen SampleVendPaymDocReportBounded.docx som du hämtade tidigare.  
3. Klicka på **Ny**.
4. Klicka på **Arkiv**.
5. Klicka på **Bläddra**. Navigera till och välj SampleVendPaymDocReportBounded.docx som du hämtade tidigare. Klicka på **OK**.
6. I fältet **Mall** väljer du mallen som du hämtade i det föregående steget.
7. Klicka på **Spara**.
8. Stäng sidan.

## <a name="execute-the-format-to-create-word-output"></a>Kör formatet för att skapa Word-utleverans
1. Klicka på **Konfigurationer** i **åtgärdsfönstret**.
2. Klicka på **Användarparametrar**.
3. Välj Ja i fältet **Kör inställningar**.
4. Klicka på **OK**.
5. Klicka på **Redigera**.
6. Välj Ja i fältet **Kör utkast**.
7. Klicka på **Spara**.
8. Stäng sidan.
9. Stäng sidan.
10. I **navigeringsfönstret** går du till **Moduler > Leverantörsreskontra > Betalningar > Betalningsjournal**.
11. Klicka på **Rader**.
12. Markera eller avmarkera alla rader i listan.
13. Klicka på **Betalningsstatus**.
14. Klicka på **Ingen**.
15. Klicka på **Generera betalningar**
16. Klicka på **OK**.
17. Klicka på **OK**. Analysera den skapade utleveransen. Observera att skapade utdata visas i Word-format och innehåller information om de behandlade betalningarna.  

