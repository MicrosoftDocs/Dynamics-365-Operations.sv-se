---
title: Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format
description: I det här avsnittet beskrivs hur rapportformat som har utformats för att generera rapporter som Excel-arbetsböcker kan konfigureras för att generera rapporter som Word-dokument.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de8286c7612cd588b28cf4667340374906962dde
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2022
ms.locfileid: "8324072"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format

[!include [banner](../../includes/banner.md)]

För att generera rapporter som Microsoft Word-dokument kan du [konfigurera](../er-design-configuration-word.md) ett nytt [elektronisk rapportering (ER)](../general-electronic-reporting.md) format. Du kan också återanvända ett ER-format som ursprungligen utformats för att generera rapporter som Excel-arbetsböcker. I så fall måste du ersätta Excel-mallen med en Word-mall.

Följande procedurer visar hur en användare med rollen Systemadministratör eller Elektronisk rapporteringsutvecklare kan konfigurera ett ER-format för att generera rapporter som Word-filer genom att återanvända ett ER-format som har utformats för att generera rapporter som Excel-filer.

Dessa procedurer kan slutföras i GBSI-företaget.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra dessa procedurer måste du först följa stegen i uppgiftsguiden [Designa en konfiguration för att skapa rapporter i OPENXML-format](er-design-reports-openxml-2016-11.md).

Du måste också hämta och spara följande mallar lokalt för exempelrapporten:

- [Mall för betalningsrapport (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Bunden mall för betalningsrapport (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

Procedurerna gäller för en funktion som lagts till Dynamics 365 for Operations i version 1611 (november 2016).

## <a name="select-the-existing-er-report-configuration"></a>Markera den befintliga ER-rapportkonfigurationen

1. I Dynamics 365 Finance, gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Kontrollera att konfigurationsleverantören **Litware, Inc.** har markerats som **aktiv**. Om den inte är det följer du stegen i uppgiftsguiden [Skapa konfigurationsleverantörer och markera dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).
3. Välj **rapporteringskonfigurationer**. Du kommer att återanvända den befintliga ER-konfigurationen som har skapats för att skapa rapportutdata i OPENXML-format.
4. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **Rapport över exempelkalkylblad**.

    > [!NOTE]
    > Utkastversionen av det valda ER-formatet kan redigeras på snabbfliken **Versioner**.

5. Välj **Designer**.
6. På sidan **Formatdesigner**, lägg märke till att titeln på rotformatelementet anger att en Excel-mall för närvarande används.

![Markera den befintliga konfigurationen.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Granska den hämtade Word-mallen

1. I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReport.docx** som du hämtat tidigare.
2. Verifiera att mallen endast innehåller layouten i det dokument som vi vill generera som ER-utdata.

![Layout för Word-mall i skrivbordsprogrammet.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Ersätt Excel-mallen med Word-mallen och lägg till en anpassad XML-kod

För närvarande används Excel-dokumentet som en mall för att skapa utdata i OPENXML-format. Du kommer att ersätta den här mallen med SampleVendPaymDocReport.docx Word-mallfil som du hämtade tidigare. Du vill också utöka Word-mallen genom att lägga till en anpassad XML-kod.

1. I Finance, på sidan **Formatdesigner** på fliken **Format**, välj **Bilagor**.
2. På sidan **Bilagor** väljer du **Ta bort** om du vill ta bort den befintliga Excel-mallen. Välj **Ja** för att bekräfta ändringen.
3. Välj **Ny** \> **Fil**.

    > [!NOTE]
    > Du måste välja en dokumenttyp som har [konfigurerats](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrarna för att ange minne för ER-formatmallar.

4. Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReport.docx** som du hämtat tidigare.
5. Välj **OK**.
6. Stäng sidan **Bilagor**.
7. På sidan **Formatdesigner** i fältet **Mall**, ange eller välj filen **SampleVendPaymDocReport.docx** som ska användas i Word-mallen istället för den Excel-mall som tidigare användes.
8. Välj **Spara**.

    Förutom att spara konfigurationsändringar, uppdaterar åtgärden **Spara** även den bifogade Word-mallen. Den hierarkiska strukturen hos det designade formatet läggs till det bifogade Word-dokumentet som en ny, anpassad XML-kod med namnet **Rapport**. Den bifogade Word-mallen innehåller layouten för dokumentet som kommer att genereras som ER-utdata och strukturen för data som ER kommer att ange i den mallen vid körning.

9. Observera att titeln på rotformatelementet anger att en Word-mall för närvarande används.

    ![Ersätta Excel-mallen med Word-mallen och lägga till en anpassad XML-del.](../media/er-design-configuration-word-2016-11-image03.gif)

10. Välj **bifogade filer** på fliken **format**.

Du kan nu mappa elementen i den anpassade **Rapport** XML-koden till innehållskontrollerna i Word-dokumentet.

Om du känner till processen att utforma Word-dokument som formulär som innehåller [innehållskontroll](/office/client-developer/word/content-controls-in-word) som är mappade till delar av [anpassade XML-koder](/visualstudio/vsto/custom-xml-parts-overview), slutföra alla steg i nästa procedur för att skapa dokumentet. Mer information finns i [Skapa formulär som användare fyller i eller skriver ut i Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). Hoppa annars över proceduren.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Hämta ett Word-dokument som har en anpassad XML-kod och mappa data

1. I Finance, på sidan **Bilagor** välj **Öppna** om du vill hämta den valda mallen från Finance och lagra den lokalt som ett Word-dokument.
3. Öppna dokumentet du just hämtat i Word-skrivbordsprogrammet.
4. På fliken **Utvecklare**, välj **fönstret för XML-mappning**.

    > [!NOTE]
    > Om fliken **Utvecklare** inte visas på menyfliken kan du anpassa den så att den lägger till den.

5. I fönstret **XML-mappning** i fältet **Anpassad XML-kod**, välj **Rapport** anpassad XML-kod.
6. Mappa elementen i den valda **Rapport** XML-koden till innehållskontrollerna i Word-dokumentet.
7. Spara det uppdaterade Word-dokumentet lokalt som **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Granska Word-mallen där den anpassade XML-koden mappas till innehållskontroller

1. I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReportBounded.docx**.
2. Verifiera att mallen innehåller layouten i det dokument som vi vill generera som ER-utdata. Innehållskontrollerna som används som platshållare för data som ER kommer att ange i den här mallen vid körning är baserade på mappningarna som är konfigurerade mellan elementen i den anpassade **Rapport** XML-koden och innehållskontrollerna i Word-dokumentet.

![Förhandsversin av Word-mall i skrivbordsprogrammet.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Överför Word-mallen där den anpassade XML-koden mappas till innehållskontroller

1. I Finance, på sidan **Bilagor** välj **Ta bort** för att ta bort Word-mallen som inte har några mappningar mellan elementen i den anpassade **Rapport** XML-koden och innehållskontroller. Välj **Ja** för att bekräfta ändringen.
2. Välj **Ny** \> **Fil** för att lägga till en ny mallfil som innehåller mappningar mellan elementen i anpassad **Rapport** XML-koden och innehållskontrollerna.

    > [!NOTE]
    > Du måste välja en dokumenttyp som har [konfigurerats](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrarna för att ange minne för ER-formatmallar.

3. Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReportBounded.docx** som du hämtat eller förberett genom att gå igenom proceduren i avsnittet [Hämta ett Word som har anpassad XML-kod till datamappning](#get-word-doc).
4. Välj **OK**.
5. Stäng sidan **Bilagor**.
6. På sidan **Formatdesigner** i fältet **Mall**, välj det dokument som du just laddade ner.
7. Välj **Spara**.
8. Stäng sidan **Formatdesigner**.

## <a name="mark-the-configured-format-as-runnable"></a>Markera det konfigurerade formatet som körbart

Om du vill köra utkastversionen för det redigerbara formatet måste du göra det [körbart](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. I Finance på sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
2. I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.
3. Välj **redigera** för att göra den aktuella sidan klar för redigering.
4. För den för närvarande valda konfigurationen **Rapport över exempelkalkylblad** ange alternativet **Kör utkast** till **Ja**.
5. Välj **Spara**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Kör formatet för att skapa utdata i Word-format

1. I Finance, gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.
2. Välj en betalningsjournal som du angav tidigare **Rader**.
3. På sidan **Leverantörsbetalningar** markera alla rader i rutnätet.
4. Välj **betalningsstatus** \> **ingen**.

    ![Betalningar för bearbetning på sidan Leverantörsbetalningar.](../media/er-design-configuration-word-2016-11-image05.png)

5. Välj **Generera betalningar** i åtgärdsfönstret.
6. Gör följande i dialogrutan som visas:

    1. I fältet **Betalningsmetod** väljer du **Elektronisk**.
    2. I fältet **Bankkonto** väljer du **GBSI OPER**.
    3. Välj **OK**.

7. I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.
8. De skapade utdata visas i Word-format och innehåller information om de behandlade betalningarna. Analysera den skapade utleveransen.

    ![Genererade utdata i Word-format.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Utforma en ny ER-konfiguration för att generera rapporter i Word-format](../er-design-configuration-word.md)
- [Bädda in bilder och former i dokument som du skapar med ER](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
