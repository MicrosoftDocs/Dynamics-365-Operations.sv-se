---
title: Använd streckkodsdatakällor för att generera streckkodsbilder
description: I det här avsnittet beskrivs hur du använder streckkodsdatakällor för att generera streckkodsbilder.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: 3fb754267de1120bc3c086d49cb7c63028183bda
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681434"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Använd streckkodsdatakällor för att generera streckkodsbilder

[!include[banner](../includes/banner.md)]

Du kan använda ramverket [Elektronisk rapportering (ER)](general-electronic-reporting.md) för att utforma [ER-formatkomponenter](general-electronic-reporting.md#FormatComponentOutbound) som du kan köra för att generera elektroniska och utskrivbara utgående dokument som du behöver. Om du vill generera ett utgående dokument i Microsoft Office format måste du ange rapportens layout genom att använda antingen ett Microsoft Excel-dokument eller ett Microsoft Word-dokument som rapportmall. Med [ER Operations designer](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) kan du bifoga ett Excel- eller Word-dokument som en mall för ett ER-format. Följande namngivna element i den kopplade mallen associeras med elementen i den konfigurerade formatkomponenten:

- Innehållskontroller i Word
- Namngivna blad, områden, celler, former och bilder i Excel

Dessa namngivna element används som platshållare för data som anges i ett genererat dokument när ett ER-format körs. ER-formatelement är bundna till datakällor. Dessa datakällor anger de data som ska anges i de genererade dokumenten under körning. För mer information om [Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)

ER har nu stöd för **streckkod** datakällans typ. Därför kan du nu generera en bild som representerar streckkoden för angiven text. När du konfigurerar ett ER-format kan du ange datakällor av typen **streckkod** för att generera streckkodsbilder. Du kan sedan lägga till dessa bilder i genererade affärsdokument, t.ex. order, fakturor, följesedlar och inleveranser. Du kan också lägga till dem på olika typer av etiketter, till exempel produkt- och hylletiketter samt etiketter för förpackning och leverans.

Följande platshållare kan användas i rapportmallar för att ange bilder av streckkoder:

- [Bild](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) innehållskontroll för Word
- [Bild](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) objekt i Excel

Genom att använda en datakälla för typen **streckkod** kan du generera streckkoder i följande format:

- Endimensionell streckkod:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligent post
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Tvådimensionell streckkod:

    - Aztec
    - Datamatris
    - QR-kod

När du konfigurerar en datakällan **streckkod** kan du definiera särskilda återgivningsparametrar som används för att generera en avbildning:

- **Bredd** – Ange streckkodens bredd i bildpunkter. Värdet **0** (noll) anger att standardbredden används. Innebörden kan variera i olika format.
- **Höjd** – Ange streckkodens höjd i bildpunkter. Värdet **0** (noll) anger att standardhöjden används. Innebörden kan variera i olika format.
- **Marginal** – Ange storleken på streckkodens marginal i bildpunkter. Marginalen är området på varje sida av streckkoden som måste hållas klar (tyst zon). Värdet **0** (noll) anger att standardmarginalen används. Innebörden kan variera i olika format.
- **Utgående innehåll** – Ställ in värdet på **Ja** för att generera en streckkodsbild som innehåller den kodade informationen som text. Standardvärdet är **Nej**.
- **Kodning** – anger vilken typ av tecken som ska kodas i den genererade streckkodsbilden. Som standard används **UTF-8**-kodning.

> [!IMPORTANT]
> När du lägger till en ny **streckkod** datakälla måste du lägga den under ett annat objekt (behållare) som ett kapslat element.
>
> När du binder en **streckkod** datakälla till ett cellelement i ett format och cellelementet representerar antingen en Word-kontroll eller en Excel-bild, visas datakällan i bindningen som en funktion med en parameter av typen **sträng**. Du måste använda den här parametern om du vill ange texten som ska omvandlas till en streckkodsbild och läsas när en genererad streckkod skannas.

Om du vill veta mer om den här funktionen fyller du i exemplet i det här avsnittet.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Exempel: generera en betalningscheck som innehåller en streckkod som kodar det utgående beloppet

Det här exemplet visar hur en användare i rollen **Systemadministratör** eller **Elektronisk rapportering** kan konfigurera ett ER-format som innehåller en mall som används för att generera ett utgående dokument i Excel-format som innehåller en streckkod. Här följer en översikt över de steg som ingår.

1. [Slutför förutsättningarna](#ExamplePrerequisites).
2. [Aktivera en konfigurationsprovider](#ExampleProvider).
3. [Importer den medföljande ER-lösningen](#ExampleImportSolution).
4. [Generera en betalningscheck](#ExampleGenerateCheque).
5. [Granska den genererade betalningschecken](#ExampleReviewGeneratedCheque).
6. [Ändra formatet för den angivna ER-lösningen](#ExampleModifyFormat).

    1. [Använd en ny kontrollmallen](#ExampleModifyFormatApplyTemplate).
    2. [Lägg till en ny streckkoddatakälla](#ExampleModifyFormatAddDataSource).
    3. [Binda ett nytt formatelement](#ExampleModifyFormatBindFormatElement).
    4. [Gör den ändrade versionen tillgänglig för testkörningar](#ExampleModifyFormatMakeVersionAvailable).

        1. [Slutför den ändrade formatversionen](#CompleteToRun).
        2. [Göra det utkast som versionen kan användas](#MarkToRun).

7. [Generera en betalningscheck](#ExampleGenerateCheque2).
8. [Konvertera den genererade kontrollen till en PDF](#ExampleConvertToPDF).

I det här exemplet ska du använda den angivna den ER-lösningen som har konfigurerats för att generera betalningschecken. Den här lösningen genererar betalningschecker där det utgående beloppet skrivs både som ett tal och som text. Du kommer att ändra den här ER-lösningen så att checken även innehåller en genererad streckkod där skuldbeloppet är kodat och kan läsas med hjälp av en streckkodsskanner.

Dessa steg kan slutföras i **USMF**-nivå i Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Slutför förutsättningarna

För att slutföra detta exempel måste du ha åtkomst till USMF företag i ekonomi för en av följande roller:

- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Om du inte redan har fyllt i exemplet i avsnittet om [Bädda in bilder och former i dokument som du genererar med ER](electronic-reporting-embed-images-shapes.md), ladda ned följande konfigurationer av ER-lösningen.

| Beskrivning av innehåll         | Filnamn                   |
|-----------------------------|-----------------------------|
| Exempel på konfiguration av ER-datamodell. | Modell för checkar.xml       |
| Konfiguration för ER-fomat     | Checkar utskriftsformat.xml |

Hämta dessutom följande Excel-fil som innehåller den ändrade mallen för den angivna ER-lösningen.

| Beskrivning av innehåll | Filnamn                 |
|---------------------|---------------------------|
| Rapportmall     | Kontrollera mall Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Aktivera en konfigurationsprovider

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** kontrollerar du att [konfigurationsprovidern](general-electronic-reporting.md#Provider) för **Litware, Inc.** exempelföretaget är listat och att det är markerat som aktivt. Om den inte finns i listan eller är markerad som aktiv, följer du [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md) markerar den som ett aktivt ämne.

![Konfigurera exempelföretaget att aktiveras på sidan lokaliseringskonfiguration](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importera den medföljande ER-lösningen

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer**, om konfigurationen **Modell för checkar** inte är tillgänglig i konfigurationsträdet, följ dessa steg för att importera konfigurationen för ER-datamodell:

    1. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
    2. I dialogrutan, välj **Bläddra**, hitta och välj filen **Modell för checkar.xml** och välj sedan **OK**.

4. Om konfigurationen **Checkar utskriftsformat** inte är tillgänglig i konfigurationsträdet, följ dessa steg för att importera ER-formatkonfigurationen:

    1. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
    2. I dialogrutan, välj **Bläddra**, hitta och välj filen **Checkar utskriftsformat.xml** och välj sedan **OK**.

5. I konfigurationsträdet expanderar du **modell för checkar**.
6. Granska listan över importerade ER-konfigurationer i konfigurationsträdet.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Generera en betalningscheck

1. Gå till **Kassa- och bankhantering** \> **Bankkonton** \> **Bankkonton**.
2. På sidan **Bankkonton** väljer du **USMF OPER**-konto.
3. På sidan bankkontoinformation, på åtgärdsfönstret, fliken **Konfigurera** i **Layout** väljer du **Check**.
4. På sidan **Checklayout** välj **Redigera**.
5. På snabbfliken **Allmänt** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.
6. I fältet **Konfiguration av exportformat**, välj det ER-format för **Checkar utskriftsformat** som du importerade tidigare.
7. Välj **Testutskrift** i åtgärdsfönstret.
8. I dialogrutan ställer du in alternativet **Överlåtbart checkformat** till **Ja** och väljer sedan **OK**.

    ![Checklayout – dialogrutan skriv ut test](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Granska den genererade betalningschecken

- Öppna den genererade checken i Excel.
2. Granska den genererade checken.

    ![Genererad betalningscheck i Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Ändra formatet för den angivna ER-lösningen

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Använd en ny kontrollmall

Du kan använda Excel-skrivbordsprogrammet för att öppna filen **Check mallen Excel.xlsx** som du importerade tidigare. Observera att den här mallen skiljer sig från mallen som du använde för att generera en betalningscheck i den angivna ER-lösningen. Dessutom innehåller ett element för **AmountBarcode** för streckkodsbilden.

![AmountBarcode-element i Excel-mallen](./media/er-barcode-data-source-cheque2.png)

Du måste nu ändra ER-lösningen och sedan [använda](modify-electronic-reporting-format-reapply-excel-template.md) den modifierade mallen igen.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet expanderar du **Modell för checkar** och väljer **Utskriftsformat för checkar**.
4. Klicka på **Designer** i åtgärdsfönstret.
5. I ER Operations designer väljer du fliken **Mappning** till höger på sidan och väljer sedan **Visa/Dölj** i formatträdrutan till vänster.
6. Observera att alla cellformatelement är bundna till lämpliga datakällor.

    ![Bindning av cellformatelement till datakällor i ER Operations designer](./media/er-barcode-data-source-cells-bound.png)

7. Välj fliken **Format** på sidans högra sida.
8. I åtgärdsfönstret, välj ellipsen (**...**) och sedan **Importera**.
9. I gruppen **Importera**, välj **Uppdatera från Excel** och välj sedan **Uppdatera mall**.
10. I dialogrutan, bläddra till filen **Checkmall.xlsx** som har sparats på datorn i dialog rutan, markera den och välj sedan **OK** för att bekräfta att den valda mallen ska användas.
11. Välj fliken **Mappning** till höger på sidan och väljer sedan **Visa/Dölj** i formatträdrutan till vänster.
12. Observera att cellelementet **AmountBarcode** har lagts till i formatet. Det här elementet är associerat med elementet **AmountBarcode** som har lagts till i den ändrade Excel-mallen som en platshållare för en streckkodsbild.

    ![AmountBarcode cellelement tillagt i formatet i ER Operations designer](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Lägg till en ny streckkoddatakälla

Sedan måste du lägga till en ny datakälla för typen **streckkod**.

1. I ER Operations designer på fliken **Mappning** till höger om sidan, välj datakällan **skriv ut**.
2. Välj **Lägg till** och sedan i gruppen **Funktioner** väljer du datakälltypen **streckkod**.

    ![Välja typ av streckkodsdatakälla](./media/er-barcode-data-source-add.png)

3. I dialogrutan i fältet **Namn**, ange **streckkod**.
4. I **Streckkodsformat**, välj **Kod 128**.
5. I fältet **Bredd**, ange **500**.
6. Välj **OK**.

    ![Dialogrutan databasegenskaper](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Binda ett nytt formatelement

Därefter måste du binda det nya formatelementet till den datakälla som du just har lagt till.

1. I ER Operations designer på fliken **Mappning** till höger om sidan, välj datakällan **skriv ut\\streckkod**.
2. Välj formatet trädfönster till vänster, välj cellelement **AmountBarcode** och välj sedan **Bind**.
3. Klicka på **Visa detaljer** i åtgärdsfönstret.
4. Observera att eftersom datakällan **streckkod** representeras i bindningen som en funktion som innehåller en enda parameter, har namnet på det bundna formatelementet automatiskt ett argument för den parametern.

    ![Information om streckkods datakällan i ER Operations designer](./media/er-barcode-data-source-bind1.png)

5. Välj **Redigera formel** om du vill justera bindningen.

    Du vill inte att namnet på det cellelement som ska returneras. Du måste därför konfigurera ett uttryck som returnerar text som innehåller det utgående beloppet för den aktuella checken. Eftersom det överordnade intervallet **ChequeLines** är bundet till datakällan **model.cheques** är den aktuella checkens betalningsbelopp tillgängligt i fältet **model.cheques.attributes.amount** i datatypen **Verklig**.

6. I fältet **Formel** ange **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Välj **Spara** och stäng sedan [ER formeldesigner](general-electronic-reporting-formula-designer.md).
8. Observera att bindningen har justerats.

    ![Justerad bindning i ER Operations designer](./media/er-barcode-data-source-bind2.png)

9. Välj **Spara** och stäng sedan ER Operations designer.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Gör den ändrade versionen tillgänglig för testkörningar

Som standard används de enda versionerna som har statusen **slutförd** och **delad** när du kör ett ER-format.

Om du har slutfört ändringarna kan du slutföra arbetet med den aktuella utkastversionen och göra dina ändringar tillgängliga för användning. Instruktioner finns i avsnittet [Slutför den ändrade formatversionen](#CompleteToRun) som följer.

Om du vill fortsätta arbeta med det aktuella utkastet, men måste använda det för att generera checkar, måste du uttryckligen ange att du vill använda utkastversionen av formatet som ska köras. Instruktioner finns i avsnittet [Gör utkastversionen tillgänglig för användning](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Slutför den ändrade formatversionen

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet expanderar du **Modell för checkar** och väljer **Utskriftsformat för checkar**.
4. På snabbfliken **Versioner** väljer du den post som har statusen **Utkast**.
5. Välj **Ändra status** och välj sedan **Slutför**.
6. I dialogrutan, välj **OK**.

Status för den aktuella versionen ändras från **utkast** till **slutfört** och en ny version som har statusen **utkast** skapas. Du kan använda den nya utkastversionen om du vill lägga till fler ändringar.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Göra det utkast som versionen kan användas

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du **Rapporteringskonfiguration**.
3. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
4. I dialogrutan ställer du in alternativet **körinställningar** till **Ja** och väljer sedan **OK**.
5. På konfigurationsträdet expanderar du **Modell för checkar** och väljer **Utskriftsformat för checkar**.
6. Ge alternativet **Kör utkast** värdet **Ja**.
7. Välj **Spara**.

Utkastversionen av det valda formatet markeras som tillgänglig för användning när det valda formatet körs.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Generera en betalningscheck

1. Gå till **Kassa- och bankhantering** \> **Bankkonton** \> **Bankkonton**.
2. På sidan **Bankkonton** väljer du **USMF OPER**-konto.
3. På sidan bankkontoinformation, på åtgärdsfönstret, fliken **Konfigurera** i **Layout** väljer du **Check**.
4. På sidan **Checklayout** i åtgärdsrutan, välj **Skriv ut test**.
5. I dialogrutan ställer du in alternativet **Överlåtbart checkformat** till **Ja**.
6. Välj **OK**.
7. Granska den genererade checken. Observera att en streckkod har genererats för att koda skuldbeloppet för checken.

    ![Genererad betalningscheck med streckkoder i Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Ett undantag erhålls om argumentet för en **streckkod** datakälla inte uppfyller de tillämpliga kraven som är specifika för streckkodsformatet. Om till exempel datakällan **streckkod** anropas för att generera en streckkod [EAN-8](https://wikipedia.org/wiki/EAN-8) för den angivna texten, genereras ett undantag om textlängden överstiger sju tecken.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Konvertera den genererade kontrollen till en PDF

Enligt beskrivningen i avsnittet [generera utskrivbara FTI-formulär](er-generate-printable-fti-forms.md#finland) kan du använda ett särskilt teckensnitt för att skapa streckkoder i ett genererat dokument. I det här fallet kan ytterligare omvandlingar av det genererade dokumentet vara beroende av tillgängligheten för det teckensnittet i omvandlingsmiljön. Om du till exempel försöker konvertera ett dokument till PDF-format eller förhandsgranska det i en miljö där teckensnittet saknas, återges inte streckkoder korrekt.

När datakällan **streckkod** används för att producera streckkoder beror det dock på något teckensnitt för återgivningen av streckkoderna. Därför kan du enkelt konvertera dokument som innehåller streckkoderna till PDF-format. Följande bild visar förhandsgranskningen av en genererad betalningscheck som har [konverterats](electronic-reporting-destinations.md#OutputConversionToPDF) till ett PDF-dokument, baserat på inställningen för det konfigurerade ER [målet](electronic-reporting-destinations.md).

![Förhandsgranskning av PDF-filen för en betalningscheck](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Begränsningar

> [!NOTE]
> Vissa typer av streckkoder som genereras har ett fast förhållandet mellan bredd och höjd. Detta är ett bra sätt om du har aktiverat funktionen **Aktivera användning av EPPlus bibliotek i ramverket för elektronisk rapportering** för att arbeta med Excel-dokument i ER. I så fall anges en bild i en platshållare som har ett låst förhållande mellan bredd och höjd. När dimensionerna för en platshållare i en mall motsvarar förhållandet mellan en bild som anges, kan därför en riktig bild i ett genererat dokument ändra storlek för att bevara det önskade proportionerna. Du kan förhindra att bilder ändrar storlek genom att använda en platshållare med förväntat proportioner.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering](electronic-reporting-destinations.md)
- [Formelspråk i elektronisk rapportering](er-formula-language.md)
- [Funktionen NUMBERFORMAT](er-functions-text-numberformat.md)
