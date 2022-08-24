---
title: Designa ett ER-format i syfte att generera en rapport i Excel-format med inbäddade bilder i sidhuvuden eller sidfötter
description: I denna artikel beskrivs hur du använder Elektronisk rapportering (ER) för att generera affärsdokument som har bilder och figurer inbäddade i sidhuvuden eller sidfötter.
author: kfend
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.custom: ''
ms.assetid: ''
ms.search.form: EROperationDesigner, ERParameters
ms.openlocfilehash: 5b46d92094bb3f2dab67a5cb2f0e1a34b05d52f0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281825"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Designa ett ER-format i syfte att generera en rapport i Excel-format med inbäddade bilder i sidhuvuden eller sidfötter

[!include[banner](../includes/banner.md)]

Detta ämne förklarar hur en användare med rollen Systemadministratör eller Elektronisk funktionskonsult kan utföra dessa uppgifter:

- Konfigurera parametrar för ramverket för [elektronisk rapportering (ER)](general-electronic-reporting.md).
- Importera ER-[konfigurationer](general-electronic-reporting.md#Configuration) som [tillhandahålls](general-electronic-reporting.md#Provider) av Microsoft och används i syfte att generera [fritextfakturor](../../../finance/accounts-receivable/create-free-text-invoice-new.md) baserade på en [mall](er-fillable-excel.md#excel-file-component) i Microsoft Excel-format.
- Skapa en [anpassad (härledd)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) version av en ER-konfiguration i standardformat tillhandahållen av Microsoft.
- Ändra den anpassade konfigurationen för ER-format så att den genererar en fritextfakturarapport som har en bild av företagslogotypen i sidfoten.

Procedurerna i detta ämne kan slutföras i företaget **USMF**. Ingen kod behövs. Hämta och spara följande fil innan du börjar:

| beskrivning        | Filnamn |
|--------------------|-----------|
| Bild av företagslogotypen | [Företagslogotyp.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Innehåll

- [Konfigurera den juridiska personen](#ConfigureLegalEntity)
- [Konfigurera ER-ramverket](#ConfigureFramework)

    - [Konfigurera ER-parametrar](#ConfigureParameters)
    - [Aktivera en ER-konfigurationsleverantör](#ActivateProvider)

        - [Granska listan med ER-konfigurationsleverantörer](#ReviewProvidersList)
        - [Lägg till en ny ER-konfigurationsleverantör](#AddProvider)
        - [Aktivera den nya ER-konfigurationsleverantören](#ActivateAddedProvider)

- [Importera standardkonfiguration av ER-format](#ImportERSolution1)

    - [Importera ER-standardkonfiguration](#ImportERFormat)
    - [Granska importerade ER-konfigurationer](#ReviewImportedERSolution)

- [Skriv ut en fritextfaktura med hjälp av ER-standardformatet](#PrintInvoice1)

    - [Konfigurera utskriftshantering](#ConfigurePrintManagement1)
    - [Skriv ut en fritextfaktura](#ProcessInvoice1)

- [Anpassa ER-standardformatet](#CustomizeProvidedFormat)

    - [Skapa ett anpassat format](#DeriveProvidedFormat)
    - [Redigera anpassat format](#ConfigureDerivedFormat)
    - [Markera det anpassade formatet som körbart](#MarkFormatRunnable)

- [Skriv ut en fritextfaktura med hjälp av det anpassade ER-standardformatet](#PrintInvoice2)

    - [Konfigurera utskriftshantering](#ConfigurePrintManagement2)
    - [Skriv ut en fritextfaktura](#ProcessInvoice2)

- [Ytterligare resurser](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Konfigurera den juridiska personen

1. Gå till **Organisationsadministration** \> **Organisationer** \> **Juridiska personer**.
2. På sidan **Juridiska personer** på snabbfliken **Rapportföretagets logotyp** väljer du **Ändra**.
3. I dialogrutan **Välj den bildfil som ska laddas upp** väljer du **Bläddra** och sedan filen **Company logo.png** som du tidigare laddade ner.
4. Välj **Spara** och stäng sedan sidan **Juridiska personer**.

![Bilden av företagslogotypen som valdes på sidan Juridiska personer.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Konfigurera ER-ramverket

Som användare i rollen funktionell konsult för elektronisk rapportering måste du konfigurera den minsta uppsättningen ER-parametrar innan du kan börja använda ER-ramverket för att designa en anpassad version av ett vanligt ER-format.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Konfigurera ER-parametrar

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.
4. Ange följande parametrar på fliken **Bilagor**:

    - I fältet **Konfigurationer** välj typen **Fil** för **USMF**-företaget.
    - I fältet **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** och välj typen **Fil**.

Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Aktivera en ER-konfigurationsleverantör

Varje ER-konfiguration som läggs till markeras som ägd av en ER-konfigurationsleverantör. Den ER-konfigurationsleverantör för ER som aktiveras i arbetsytan **Elektronisk rapportering** används för det här syftet. Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.

> [!NOTE]
> En ER-konfiguration kan endast redigeras av konfigurationsägaren. Innan en ER-konfiguration kan redigeras måste lämplig ER-konfigurationsleverantör aktiveras i arbetsytan **Elektronisk rapportering**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Granska listan med ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. På sidan **Tabellen konfigurationsleverantörer** har varje leverantörspost ett unikt namn och en URL. Granska innehållet på den här sidan. Om det redan finns en post för **Litware, Inc.** (`https://www.litware.com`) hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Lägg till en ny ER-konfigurationsleverantör

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.
4. I fältet **Namn** anger du **Litware, Inc.**.
5. I fältet **Internetadress** anger du `https://www.litware.com`.
6. Välj **Spara**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktivera den nya ER-konfigurationsleverantören

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.

Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importera standardkonfiguration av ER-format

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importera ER-standardkonfiguration

Om du vill lägga till standard-ER-konfigurationer i din aktuella Dynamics 365 Finance-instansen måste du importera dem från [databasen](general-electronic-reporting.md#Repository) som har konfigurerats för den instansen.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfigurationer**, i avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft** och sedan **Lagringsplatser** om du vill se en lista över lagringsplatser för leverantören **Microsoft**.
3. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**. m du uppmanas att bevilja behörighet att ansluta till [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md) följer du instruktionerna för auktorisering.
4. På sidan **Konfigurationsdatabas** i konfigurationsträdet i det vänstra fönstret välj du formatkonfigurationen **Fritextfaktura (Excel)**.
5. På snabbfliken **Versioner** väljer du den senaste versionen (till exempel **240.112**) för vald ER-formatkonfiguration.
6. Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.

![Importera standardformatet för ER-betalning på sidan Konfigurationsdatabas.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från Microsoft Dynamics Lifecycle Services (LCS) istället.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Granska importerade ER-konfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell**.
4. Förutom det valda ER-formatet **Fritextfaktura (Excel)** har även andra krävda ER-konfigurationer importerats. Se till att följande ER-konfigurationer är tillgängliga i konfigurationsträdet:

    - **Fakturamodell** – Denna konfiguration innehåller den datamodell för ER-komponent som representerar datastrukturen för affärsdomänen för fakturering.
    - **Mappning av fakturamodell** – Denna konfiguration innehåller den modellmappning för ER-komponent som beskriver hur datamodellen fylls i med appdata under körning.
    - **Fritextfaktura (Excel)** – Denna konfiguration innehåller ER-komponenter för format och formatmappning. Formatkomponenten anger rapportlayouten baserat på en mall i Excel-format. Komponenten för formatmappning innehåller modelldatakällan och anger hur denna datakälla används för att fylla i rapportlayouten vid körning.

![Importerade ER-konfigurationer på sidan Konfigurationer.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Skriv ut en fritextfaktura med hjälp av ER-standardformatet

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Konfigurera utskriftshantering

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **Fritextfaktura** väljer du fakturan **FTI-00000002** och sedan, på fliken **Faktura** i åtgärdsfönstret, går du till gruppen **Utskriftshantering** och väljer **Utskriftshantering**.
3. På sidan **Utskriftshantering**, i trädet till vänster, visar du **Modul - kundreskontra \> Dokument \> Fritextfaktura** och sedan **Ursprunglig \<Default\>**.
4. I fältet **Rapportformat** väljer du **Fritextfaktura (Excel)**.
5. Välj knappen **Esc** för att lämna sidan **Konfiguration för utskriftshantering** och återgå till sidan **Fritextfaktura**.

![Inställningar för utskriftshantering för en fritextfaktura i ER-standardformatet på konfigurationssidan för utskriftshantering.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Skriv ut en fritextfaktura

1. På sidan **Fritextfaktura** ser du till att fakturan **FTI-00000002** fortfarande är vald innan du i Åtgärdsfönstret > fliken **Faktura** > gruppen **Dokument** väljer **Skriv ut** \> **Markerade**.
2. Hämta den genererade fakturan i Excel-format och öppna den för förhandsgranskning.
3. Notera att sidfoten på den genererade fakturan, i enlighet med strukturen för Excel-mallen för det angivna ER-formatet, innehåller information om det aktuella sidnumret och det totala antalet sidor i rapporten.

![Genererad fritextfaktura.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Anpassa ER-standardformatet

I exemplet i det här avsnittet kan du använda ER-konfigurationerna som tillhandahålls av Microsoft för att generera en fritextfaktura i Excel-format. Du måste emellertid lägga till en anpassning för att placera en bild av företagslogotypen i sidfoten på genererade fakturor.

Som representant för Litware, Inc. måste du i detta fall skapa (härleda) en ny ER-formatkonfiguration baserad på den av Microsoft tillhandahållna konfigurationen **Fritextfaktura (Excel)**.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Skapa ett anpassat format

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell** och väljer sedan **Fritextfaktura (Excel)**. Litware, Inc. kommer att använda den importerade versionen (t. ex. **240.112**) av denna ER-formatkonfiguration som bas för den anpassade versionen.
3. Välj **Skapa konfiguration** om du vill öppna dialogrutan. Använd denna dialogruta för att skapa en ny konfiguration för ett anpassat betalningsformat.
4. I fältgruppen **Ny** väljer du alternativet **Härled från namn: Fritextfaktura (Excel), Microsoft**.
5. I fältet **Namn** anger du **Fritextfaktura (Excel) anpassad**.
6. Välj **Skapa konfiguration**.

![Skapa en konfiguration för ett anpassat betalningsformat i dialoglistrutan Skapa konfiguration.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

Version 240.112.1 av ER-formatkonfigurationen **Fritextfaktura (Excel) anpassad** skapas. Den här versionen har status av **utkast** och kan redigeras. Det aktuella innehållet i det anpassade ER-formatet matchar innehållet i det format som tillhandahålls av Microsoft.

![Nya versioner av den ER-formatkonfiguration som skapats på sidan Konfigurationer.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Redigera anpassat format

Konfigurera ditt eget format så att en bild med företagslogotypen läggs i sidfoten på alla sidor i rapporten.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **Fritextfaktura (Excel) anpassad**.
3. På snabbfliken **Versioner** välj version **240.112.1** av den valda konfigurationen.
4. Välj **Designer**.
5. På sidan **Formatdesigner** väljer du **Visa information** om du vill visa mer information om formatelementen.
6. Expandera och granska följande element:

    - Elementet **Fritextfaktura** för typen **Excel**. Det här elementet används för att generera en faktura i Excel-arbetsboksformat.
    - Elementet **Fritextfaktura \\ Faktura** för typen **Ark**. Det här elementet används för att generera ett kalkylblad med den genererade Excel-arbetsboken.
    - Elementet **Fritextfaktura \\ Faktura \\ Sidfot** av typen **Sidfot**. Det här elementet används för att fylla i en fakturasidfot.

7. Markera elementet **Fritextfaktura \\ Faktura \\ Sidfot**.

    ![Sidfotselement i ER-funktionsdesignern.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Varje sidfot i en genererad faktura innehåller information om aktuellt sidnummer och totalt antal sidor i rapporten. Som du ser innehåller elementet **Fritextfaktura \\ Faktura \\ Sidfot** inga underordnade element. Därför konfigureras den Excel-mall som används till att visa sidindelningsdetaljer i mitten av varje rapports sidfot.

8. Välj **Lägg till** och välj sedan typen **Excel \\ Bild** för det formatelement som du vill lägga till:

    1. I fältet **Justering** väljer du **Höger**.
    2. I fältet **Anpassa höjden** väljer du **Relativ**.
    3. I fältet **Anpassa i procent** anger du **70**.
    4. Välj **OK**.

        > [!NOTE]
        > Elementet **Excel \\ Bild** används för att lägga till en företagslogotypbild och anpassa den till höger om sidfoten.

    ![Egenskaper för bildelementet i dialogrutan Komponentegenskaper.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. I formatstrukturträdet till vänster väljer du det element för **Bild** som du just lagt till innan du på fliken **Mappning** visar datakällan **modell**.
10. Visa **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo** och välj sedan fältet **model.InvoiceBase.CompanyInfo.Logo** för datakälla. Fältet för datakälla tillhörande typen [Behållare](er-formula-supported-data-types-composite.md#container) visar bilden av företagslogotypen som medieinnehåll.
11. Välj **bind**. Elementet **Bild** format är nu bundet med fältet **modellen.InvoiceBase.CompanyInfo.Logo** för datakälla. Vid körning placeras därför en bild av företagslogotypen i sidfoten på genererade fakturor.

    ![Elementet Bildformat bundet med fältet model.InvoiceBase.CompanyInfo.Logo för datakälla i ER-åtgärdsdesignern.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Välj **Spara** och stäng sedan sidan **Designer**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Markera det anpassade formatet som körbart

Eftersom den första versionen av det anpassade formatet har skapats och bär statusen **Utkast** kan du köra formatet i testsyfte. Om du vill köra rapporten måste du bearbeta en leverantörsbetalning genom att använda den betalningsmetod som refererar till det anpassade ER-formatet. Som standard, när du anropar ett ER-format från appen kan endast versioner som har status **slutförd** eller **delad** beaktas. Det här beteendet gör det enklare att använda ER-format som inte innehåller färdiga designer. För att testet ska kunna köras kan du dock tvinga appen att använda den version av ditt ER-format som har statusen **utkast**. På det här sättet kan du justera den aktuella formatversionen om du behöver göra ändringar. Mer information finns i [Tillämplighet](electronic-reporting-destinations.md#applicability).

Om du vill använda utkastversionen av ett ER-format måste du markera ER-format på tydligt sätt.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.
4. Om du vill göra den aktuella sidan redigerbar väljer du **Redigera** och sedan - i konfigurationsträdet i vänstra fönstret - väljer du **Fritextfaktura (Excel) anpassad**.
5. Ge alternativet **Kör utkast** värdet **Ja**.

![Markera det anpassade formatet som körbart på sidan Konfigurationer.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Skriv ut en fritextfaktura med hjälp av det anpassade ER-standardformatet

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Konfigurera utskriftshantering

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **Fritextfaktura** väljer du fakturan **FTI-00000002** och sedan, på fliken **Faktura** i åtgärdsfönstret, går du till gruppen **Utskriftshantering** och väljer **Utskriftshantering**.
3. På sidan **Konfiguration för utskriftshantering**, i trädet till vänster, visar du **Modul - kundreskontra** \> **Dokument** \> **Fritextfaktura** och väljer sedan artikeln **Ursprunglig** **\<Default\>**.
4. I fältet **Rapportformat** väljer du **Fritextfaktura (Excel) anpassad**.
5. Välj **Esc** för att lämna sidan **Konfiguration för utskriftshantering** och återgå till sidan **Fritextfaktura**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Skriv ut en fritextfaktura

1. På sidan **Fritextfaktura** ser du till att fakturan **FTI-00000002** fortfarande är vald innan du i Åtgärdsfönstret > fliken **Faktura** > gruppen **Dokument** väljer **Skriv ut** \> **Markerade**.
2. Hämta den genererade fakturan i Excel-format och öppna den för förhandsgranskning.
3. Lägg märke till att sidfoten för den genererade fakturan, i enlighet med strukturen för det anpassade ER-formatet, innehåller en bild av företagslogotypen, utöver information om rapportens sidindelning.

![Genererad fritextfaktura med en bild av företagslogotypen i sidfoten.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Ytterligare resurser

- [Skapa en konfiguration för att generera dokument i Excel-format](er-fillable-excel.md)
- [Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)
