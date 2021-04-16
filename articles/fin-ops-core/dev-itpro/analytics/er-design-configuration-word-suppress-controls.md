---
title: Ignorera Word-innehållskontroller i genererade rapporter
description: I det här avsnittet beskrivs hur du konfigurerar ett ER-format (elektronisk rapportering) för att generera rapporter som Microsoft Word-filer där innehållskontroller utelämnas.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 8c99203110cfdc7f8123c30488611d55f48e8f67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753617"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Ignorera Word-innehållskontroller i genererade rapporter

[!include [banner](../includes/banner.md)]

Om du vill generera rapporter som Microsoft Word-dokument måste du designa en mall för rapporterna som ett Word-dokument. Den här mallen måste innehålla Word-innehållskontroll som platshållare för data som ska fyllas i när den körs. Om du vill använda Word-dokumentet som skapats som en mall för dina rapporter kan du [konfigurera](er-design-configuration-word.md) en ny [Elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md). Den här lösningen måste omfatta en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER [format](general-electronic-reporting.md#FormatComponentOutbound). ER-formatet måste konfigureras så att det använder den utformat mallen för att generera rapporter.

I version 10.0.6 och senare av Dynamics 365 Finance kan du konfigurera formler i ER-formatet för att ignorera vissa Word-innehållskontroller i genererade dokument.

I följande steg förklaras hur en användare som är tilldelad rollen Systemadministratör eller Elektronisk rapportering funktionell konsult kan konfigurera ett ER-format som genererar rapporter som Word-filer och utelämnar vissa av innehållskontrollerna i de genererade rapporter som har konfigurerats med en Word-mall.

Dessa steg kan slutföras i GBSI-företaget.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra dessa steg måste du först avsluta dessa steg i följande uppgiftsguider:

- [Utforma en konfiguration för rapportgenerering i OPENXML-format](./tasks/er-design-reports-openxml-2016-11.md)
- [Återanvänd ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format](./tasks/er-design-configuration-word-2016-11.md)

När du har slutfört stegen i dessa uppgiftsguider förbereds följande artiklar:

- Ett **Rapport över exempelkalkylblad** ER-format som är konfigurerat för att generera ett dokument i Word-format
- En [utkast](general-electronic-reporting.md#component-versioning) version av **Rapport över exempelkalkylblad** ER-format som är markerat som **körbart**
- En **elektronisk** betalningsmetod som är konfigurerad att använda **Rapport över exempelkalkylblad** ER-format för bearbetning av leverantörsbetalningar

Du måste också ladda ner och spara följande mall för exempelrapporten:

- [Bunden mall 2 för betalningsrapport (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Granska den hämtade Word-mallen

1. I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReportBounded2.docx** som du hämtat tidigare.
2. Kontrollera att mallfilen innehåller ett samlingsavsnitt som visar de totala betalningsbeloppen för varje valutakod som har uppfyllts i de bearbetade betalningarna.

    - Sammanfattningsavsnittet finns i ett separat register i Word-dokumentet.
    - Den första raden i registret innehåller tabellkolumnrubrikerna som avsnittsrubrik.
    - Den andra raden i registret innehåller kontroll av upprepat innehåll som avsnittsdetaljer.
    - Den här innehållskontrollen mappas till fältet **SummaryLines** på **Rapport** anpassade XML-delen.
    - Baserat på den här mappningen associeras innehållskontrollen med **SummaryLines** element i det redigerbara ER-formatet.

    > [!NOTE]
    > Den upprepade innehållskontrollen är taggad av **SummaryLines** nyckel som matchar fältet för den anpassade XML-delen som den har mappats till.

    ![Word-mall layout](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Markera den befintliga ER-rapportkonfigurationen

I följande steg återanvänder du den befintliga ER-konfiguration som du konfigurerade när du slutförde stegen i de tidigare nämnda uppgiftsguiderna.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. På sidan **konfigurationer** i konfigurationsträdet expanderar du **Betalningsmodell** och väljer sedan **Rapport över exempelkalkylblad**.
4. Välj **Designer** för att redigera utkastversionen för det valda ER-formatet.

## <a name="replace-the-current-template-with-the-new-template"></a>Byt ut den aktuella mallen mot den nya mallen

För närvarande används SampleVendPaymDocReportBounded.docx-filen som en mall för att skapa utdata i Word-format. I följande steg kommer du att ersätta den här Word-mallen med den nya Word-mallen, SampleVendPaymDocReportBounded2.docx, som du hämtade tidigare.

1. Välj **Formatdesigner** på sidan **Bilagor**.
2. På sidan **Bilagor** väljer du **Ta bort** om du vill ta bort den befintliga mallen.
3. Välj **Ja** för att bekräfta raderingen.
4. Välj **Ny** \> **Fil**.
5. Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReportBounded2.docx** som du hämtat tidigare.
6. Välj **OK**.
7. Stäng sidan **Bilagor**.
8. På sidan **Formatdesigner** i fältet **Mall**, ange eller välj filen **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Kör formatet för att skapa Word-utleverans

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.
2. På sidan **Leverantörsbetalningar** på fliken **Lista** markera alla betalningar.
3. Välj **betalningsstatus** \> **ingen**.
4. Välj **Generera betalningar**.
5. I fältet **Betalningsmetod** väljer du **Elektronisk**.
6. I fältet **Bankkonto** väljer du **GBSI OPER**.
7. Välj **OK**.
8. I dialogrutan **Elektroniska rapportparametrar**, välj **OK** och analysera det genererade resultatet.

    ![Betalningar för bearbetning på sidan Leverantörsbetalningar](./media/er-design-configuration-word-suppress-controls-image2.gif)

    Resultatet presenteras i Word-format och innehåller sammanfattningsavsnittet.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Konfigurera det redigerbara formatet om du vill ignorera sammanfattningsavsnittet

Om du vill ignorera samlingsavsnittet i ett genererat dokument, baserat på begäran av en användare som kör det här ER-formatet, måste du ändra det redigerbara ER-formatet.

1. Gå till **Organisationsadministration** \> **Arbetsplatser** \> **Elektronisk rapportering** och öppna utkastversionen av ER-formatet för redigering.
2. Välj **rapporteringskonfigurationer**. 
3. På sidan **Konfigurationer** i konfigurationsträdet expanderar du **Betalningsmodell** \> **Rapport över exempelkalkylblad**.
4. Välj **Designer**.
5. På sidan **Formatdesigner**, expandera **Word** och **SummaryLines**.
6. På fliken **Mappning**, lägg till en ny datakälla för att fråga användaren vid körning om sammanfattningsavsnittet ska undertryckas:

    1. Välj **Lägg till rot**.
    2. I dialogrutan **Lägg till datakälla**, välj **Allmän\Användarindataparameter** för att öppna dialogrutan **Användarinmatningsparametrarnas datakällegenskaper**.
    3. Skriv **statisk** i fältet **uipSuppress**.
    4. I fältet **Etikett**, ange **Avsluta sammanfattningsavsnittet**.
    5. I fältet **Åtgärdens datatypnamn**, välj eller ange **NoYes**.
    6. Välj **OK**.

7. Lägg till en ny datakälla av **NoYes** appens uppräkningstyp:

    1. Välj **Lägg till rot**.
    2. I dialogrutan **Lägg till datakälla**, välj **Dynamics 365 for Operations\Uppräkning** om du vill öppna dialogrutan **Uppräkningens datakällegenskaper**.
    3. Skriv **Dokument** i fältet **enumNoYes**.
    4. I fältet **Etikett**, ange **Undertryck alternativ**.
    5. I fältet **Åtgärdens datatypnamn**, välj eller ange **NoYes**.
    6. Välj **OK**.

8. För det valda formatelementet **SummaryLines**, konfigurera formeln för att ange när Word-innehållskontrollen som är associerad med det valda formatelementet ska undertryckas:

    1. PÅ fliken **Mappning** i avsnittet **Borttaget**, välj **Redigera** om du vill öppna sidan **[Formeldesigner](general-electronic-reporting-formula-designer.md)**.
    2. I fältet **Formel** anger du formeln `uipSuppress = enumNoYes.Yes`.
    3. Stäng sidan **Spara** och **Formeldesigner**.

        > [!NOTE]
        > Formeln tillämpas på ett genererat dokument när **alla andra formatelement har körts**. När du vill använda den här formeln hittas en Word-innehållskontroll som är taggad som ett formatelement som formeln är konfigurerad för (**SummaryLines** i det här fallet) hittas i ett genererat dokument. Den innehållskontrollen tas då bort helt och hållet, tillsammans med den rad i Word-registret som innehåller kontrollen. Detaljraden i sammanfattningsavsnittet tas bort från det genererade dokumentet.
        >
        > Vid designtid kan du konfigurera formeln **borttagen** för ett formatelement, även om ingen innehållskontroll i Word-mallen som du använder har en tagg som matchar namnet på ett formatelement som **borttagen** har konfigurerats för. När du validerar formatet vid designtid får du en [varning](er-components-inspections.md#i14) om denna inkonsekvens.
        >
        > Vid körning kastas ett undantag om ingen innehållskontroll i Word-mallen som du använder har en tagg som matchar namnet på ett formatelement som egenskapen **Borttaget** har konfigurerats för.

    4. Ställ in alternativet **Mappning** i avsnittet **Borttaget**, ange alternativet **Med överordnad** till **Ja**.

        > [!NOTE]
        > Du måste ställa in alternativet **Ja** om du vill ta bort hela Word-registret som överordnat objekt för raden som innehåller information om sammanfattningsavsnittet. Om du ställer in detta alternativ till **Nej**, finns avsnittsrubrikraden kvar i det genererade dokumentet.

9. Välj **Spara** om du vill ändra till redigerbart format.

    ![Genererad utdata i Word-format](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Kör det modifierade formatet för att skapa Word-utleverans

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.
2. Välj betalningsjournalen som du skapade och välj sedan **Rader**.
3. På sidan **Leverantörsbetalningar** markera alla rader och välj sedan **Betalningsstatus** \> **Ingen**.
4. Välj **Generera betalningar**.
5. I fältet **Betalningsmetod** väljer du **Elektronisk**.
6. I fältet **Bankkonto** väljer du **GBSI OPER**.
7. Välj **OK**.
8. I dialogrutan **Parametrar för elektroniska rapporter** i fältet **Avsluta sammanfattningsavsnittet**, välj **Ja**.
9. Välj **OK** och analysera det genererade resultatet.

    ![Genererad utdata i Word-format](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Lägg märke till att utdata inte innehåller sammanfattningsavsnittet eftersom det har utelämnats.

## <a name="additional-resources"></a>Ytterligare resurser

- [Utforma en konfiguration för rapportgenerering i OPENXML-format](./tasks/er-design-reports-openxml-2016-11.md)
- [Utforma en ny ER-konfiguration för att generera rapporter i Word-format](er-design-configuration-word.md)
- [Återanvänd ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format](./tasks/er-design-configuration-word-2016-11.md)
- [Granska den konfigurerade ER-komponenten för att förhindra körningsproblem](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]