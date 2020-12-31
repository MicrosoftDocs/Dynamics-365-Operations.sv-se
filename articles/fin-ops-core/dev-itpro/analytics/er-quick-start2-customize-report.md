---
title: Justera ett ER-format för att skapa ett anpassat elektroniskt dokument
description: Det här avsnittet innehåller information om hur du justerar ett "ER"-format (elektronisk rapportering) från Microsoft så att ett anpassat elektroniskt dokument skapas.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20e7a32ac5f6ab21f89ed3c11c64458286864c9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680180"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Justera ett ER-format för att skapa ett anpassat elektroniskt dokument

[!include[banner](../includes/banner.md)]

Procedurerna i det här avsnittet förklarar hur en användare i rollen systemadministratör eller elektronisk rapportering kan utföra dessa uppgifter:

- Konfigurera parametrar för [ramverket för elektronisk rapportering (ER)](general-electronic-reporting.md).
- Importera ER-konfigurationer som tillhandahålls av Microsoft och används för att generera en betalningsfil medan en [leverantörsbetalning](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) bearbetas.
- Skapa en anpassad version av en standardkonfiguration av ER-format som tillhandahålls av Microsoft.
- Ändra konfigurationen för det anpassade ER-formatet så att den genererar betalningsfiler som uppfyller kraven för en specifik bank.
- Anta ändringar som görs i standardkonfigurationen för ER-format i konfigurationen för anpassat ER-format.

Alla följande procedurer kan göras i **GBSI** företaget. Ingen kod behövs.

- [Konfigurera ER-ramverket](#ConfigureFramework)

    - [Konfigurera ER-parametrar](#ConfigureParameters)
    - [Aktivera en ER-konfigurationsleverantör](#ActivateProvider)

        - [Granska listan med ER-konfigurationsleverantörer](#ReviewProvidersList)
        - [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider)
        - [Aktivera en ER-konfigurationsleverantör](#ActivateAddedProvider)

- [Importera standardkonfiguration av ER-format](#ImportERSolution1)

    - [Importera ER-standardkonfiguration](#ImportERFormat1)
    - [Granska importerade ER-konfigurationer](#ReviewImportedERSolution)

- [Förbered en leverantörsbetalning för bearbetning](#PrepareVendorPayment)

    - [Lägga till bankinformation för ett leverantörskonto](#AddBankAccount)
    - [Ange en leverantörsbetalning](#EnterVendorPayment)

- [Bearbeta en leverantörsbetalning med hjälp av ER-standardformat](#ProcessVendorPayment1)

    - [Ange den elektroniska betalningsmetoden](#ConfigureMethodOfPayment1)
    - [Bearbeta en leverantörsbetalning](#ProcessPayment1)

- [Anpassa ER-standardformatet](#CustomizeProvidedFormat)

    - [Skapa ett anpassat format](#DeriveProvidedFormat)
    - [Redigera ett anpassat format](#ConfigureDerivedFormat)
    - [Markera ett anpassat format som körbart](#MarkFormatRunnable)

- [Bearbeta en leverantörsbetalning med hjälp av anpassat ER-format](#ProcessVendorPayment2)

    - [Ange den elektroniska betalningsmetoden](#ConfigureMethodOfPayment2)
    - [Bearbeta en leverantörsbetalning](#ProcessPayment2)

- [Importera nya versioner av standardkonfiguration av ER-format](#ImportERSolution2)

    - [Importera nya versioner av ER-standardkonfigurationer](#ImportERFormat2)
    - [Granska importerade ER-formatkonfigurationer](#ReviewImportedERFormat)

- [Tillämpa ändringarna i den nya versionen av ett importerat format i ett anpassat format](#AdoptNewBaseVersion)

    - [Slutför den nuvarande utkastversionen av ett anpassat format](#CompleteDerivedFormat)
    - [Basera ett anpassat format på en ny basversion](#RebaseDerivedFormat)
    - [Bearbeta en leverantörsbetalning med hjälp av ombaserat ER-format](#ProcessPayment3)

- [Ytterligare resurser](#References)

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
> Endast ägaren till en ER-konfiguration kan redigera den. Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Granska listan med ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. På sidan **Tabellen konfigurationsleverantörer** har varje leverantörspost ett unikt namn och en URL. Granska innehållet på den här sidan. Om det redan finns en post för **Litware, Inc.** (`https://www.litware.com`) hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Lägg till en ny ER-konfigurationsleverantör

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.
4. I fältet **Namn** anger du **Litware, Inc.**.
5. I fältet **Internetadress** anger du `https://www.litware.com`.
6. Välj **Spara**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktivera en ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.

Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importera standardkonfiguration av ER-format

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importera ER-standardkonfiguration

Om du vill lägga till standard-ER-konfigurationer i din aktuella instans av Microsoft Dynamics 365 Finance, måste du importera dem från ER [databasen](general-electronic-reporting.md#Repository) som har konfigurerats för den instansen.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.
3. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**. Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.
4. På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **BACS (UK)**-formatkonfiguration.
5. På snabbfliken **Versioner** välj version **1.1** av den valda ER-formatkonfigurationen.
6. Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.

![Sidan Konfigurationsdatabas](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från Microsoft Dynamics Lifecycle Services (LCS) istället.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Granska importerade ER-konfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell**.
4. Observera att förutom det valda **BACS (UK)** ER-format, har andra krävda ER-konfigurationer har importerats. Se till att följande ER-konfigurationer är tillgängliga i konfigurationsträdet:

    - **Betalningsmodell** – Den här konfigurationen innehåller den [datamodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponent för datamodellen som representerar data strukturen i betalningsaffärsdomänen.
    - **Mappning av betalningsmodell 1611** – Den här konfigurationen innehåller [modellmappningen](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponent som beskriver hur datamodellen fylls i med appdata under körning.
    - **BACS (UK)** – Den här konfigurationen innehåller [format](general-electronic-reporting.md#FormatComponentOutbound) och formatmappning för ER-komponenter. Formatkomponenten anger rapportlayouten. Komponenten för formatmappning innehåller modelldatakällan och anger hur rapportlayouten fylls i med hjälp av den här datakällan vid körning.

![Sidan Konfigurationer](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Förbered en leverantörsbetalning för bearbetning

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Lägga till bankinformation för ett leverantörskonto

Du måste lägga till bankinformation för ett leverantörskonto som kommer att refereras till senare i en registrerad betalning.

1. Gå till **Leverantörsreskontra** \> **Leverantörer** \> **Alla leverantörer**.
2. På sidan **Alla leverantörer**, välj **GB_SI_000001** leverantörskonto och sedan på åtgärdsfönstret, på fliken **Leverantör** i gruppen **Inställningar** väljer du **Bankkonton**.
3. På sidan **Leverantörsbankkonton**, välj **Ny** och ange sedan följande information:

    1. I fältet **Bankkonto** väljer du **GBP OPER**.
    2. I fältet **Bankgrupper** väljer du **BankGBP**.
    3. I fältet **Bankkontonummer** väljer du **202015**.
    4. I fältet **SWIFT-kod** ange <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. I fältet **IBAN** anger du **GB33BUKB20201555555555**.
    6. I fältet **Clearingnummer** behåll värdet <a id="DefineRoutingNumber"></a>**123456**.

    ![Sidan Leverantörsbankkonton](./media/er-quick-start2-bank-account.png)

4. Välj **Spara**.
5. Stäng sidan.
6. På sidan **Alla leverantörer** öppnar du **GB_SI_000001** leverantörskonto.
7. På sidan leverantörsinformation väljer du **Redigera** för att göra sidan redigerbar om det behövs.
8. På snabbfliken **Betalning** i fältet **Bankkonto** väljer du **GBP OPER**.

    ![Sidan Leverantörsinformation](./media/er-quick-start2-bank-account-reference.png)

9. Välj **Spara**.
10. Stäng sidan.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Ange en leverantörsbetalning

Du måste ange en ny leverantörsbetalning genom att använda [betalningsförslag](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. Välj **Leverantörsbetalningsjournal** på sidan **Leveranssätt**.
3. Välj **VendPay** i fältet **Namn**.
4. Markera **rader**
5. Välj **Betalningsförslag** \> **Skapa betalningsförslag**.
6. I dialogrutan **leverantörsbetalningsförslag** konfigurera villkor för att filtrera poster för endast leverantörskonto **GB_SI_000001** och välj sedan **OK**.
7. Markera raden för fakturan **00000007_Inv** och välj sedan **Skapa betalning**.

    ![Dialogrutan leverantörsbetalningsförslag](./media/er-quick-start2-payment-proposal.png)

8. Kontrollera att betalningen som anges har konfigurerats för användning av betalningsmetoden **elektronisk**.

    ![Sidan Leverantörsbetalningar](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Bearbeta en leverantörsbetalning med hjälp av ER-standardformat

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Ange den elektroniska betalningsmetoden

Du måste konfigurera den elektroniska betalningsmetoden så att den använder den importerade ER-formatkonfigurationen.

1. Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.
2. På sidan **Betalningsmetoder - leverantörer** välj metoden **Elektronisk** i det vänstra fönstret.
3. Välj **Redigera**.
4. På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.
5. I fältet **Exportformatkonfiguration** väljer du formatkonfigurationen **BACS (UK)**.

    ![Sidan Betalningsmetoder - leverantörer](./media/er-quick-start2-method-of-payment1.png)

6. Välj **Spara**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Bearbeta en leverantörsbetalning

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du lade till tidigare och väljer sedan **Rader**.
3. På sidan **Leverantörsbetalningar** välj **Generera betalningar**.
4. Ange följande information i dialogrutan **Generera betalningar**:

    - I fältet **Betalningsmetod** väljer du **Elektronisk**.
    - I fältet **Bankkonto** väljer du **GBSI OPER**.

5. Välj **OK**.
6. I dialogrutan **Elektroniska rapportparametrar** anger du alternativet **Skriv ut kontrollrapport** till **Ja** och väljer sedan **OK**.

    ![Sidan Dialog för elektroniska rapportparametrar](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > Förutom betalningsfilen kan du nu generera kontrollrapporten.

7. Hämta zip-filen och extrahera följande filer från den:

    - Kontrollrapporten i Excel-format
    - Betalningsfil i TXT-format

        Observera att i enlighet med [struktur](#PositionRoutingNumber) i den genererade filen börjar med det organisationsnummer som [definierats](#DefineRoutingNumber) för det konfigurerade bankkontot.

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Anpassa ER-standardformatet

För exemplet som visas i det här avsnittet vill du använda ER-konfigurationerna som tillhandahålls av Microsoft för att generera leverantörsbetalningsfiler i BACS-format, men du måste lägga till en anpassning för att stödja kraven för en specifik bank. Du vill också kunna uppgradera det anpassade formatet när nya versioner av ER-konfigurationer blir tillgängliga. Du vill dock kunna uppgradera till den lägsta kostnaden.

I det här fallet, som representant för Litware, Inc. måste du skapa (härledd) en ny ER-formatering genom att använda den **BACS (UK)** Microsoft-konfigurationen som bas.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Skapa ett anpassat format

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (UK)**. Litware, Inc. kommer att använda version 1.1 av den här ER-formatkonfigurationen som bas för den anpassade versionen.
3. Välj **Skapa konfiguration** om du vill öppna dialogrutan. Du kan använda denna dialogruta för att skapa en ny konfiguration för ett anpassat betalningsformat.
4. I fältgruppen **Ny** väljer du alternativet **Härled från namn: BACS (UK), Microsoft**.
5. I fältet **Namn** anger du **BACS (kund från Storbritannien)**.

    ![Den nedrullningsbara dialogrutan skapa konfiguration](./media/er-quick-start2-add-derived-format.png)

6. Välj **Skapa konfiguration**.

Version 1.1.1 av **BACS (kund från Storbritannien)** ER-formatkonfiguration har skapats. Den här versionen har [status](general-electronic-reporting.md#component-versioning) av **utkast** och kan redigeras. Det aktuella innehållet i det anpassade ER-formatet matchar innehållet i det format som tillhandahålls av Microsoft.

![Sidan Konfigurationer](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Redigera ett anpassat format

Du måste konfigurera det anpassade formatet så att det uppfyller de bankspecifika kraven. En bank kan t.ex. kräva att betalningsfiler som genereras inkluderar samhället i den globala SWIFT-koden (Financial Telecommunication Interbank) för en bank som tilldelas agentrollen i den bearbetade leverantörsbetalningen. SWIFT-koder är internationella bankkoder som identifierar specifika banker över hela världen. De är också kända som BIC (Bank Identifier Codes). SWIFT-koden måste vara 11 tecken lång och den måste anges i början av varje betalningsrad i en genererad betalningsfil.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (kund från Storbritannien)**.
3. På snabbfliken **Versioner** välj version **1.1.1** av den valda konfigurationen.
4. Välj **Designer**.
5. På sidan **Formatdesigner** väljer du **Visa information** om du vill visa mer information om formatelementen.
6. Expandera och granska följande element:

    - Elementet **BACSReportsFolder** av typen **Mapp**. Det här elementet används för att generera utdata i ZIP-format.
    - Elementet **fil** av typen **Fil**. Det här elementet används för att generera en betalningsfil i TXT-format.
    - Elementet **transaktioner** av typen **Sekvens**. Det här elementet används för att generera en enda betalningsrad i en betalningsfil.
    - Elementet **transaktion** av typen **Sekvens**. Det här elementet används för att generera individuella fält av en enda betalningsrad.

7. Välj elementet **transaktion**.

    ![Transaktionselement i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > Den angivna rapporten konfigureras så att <a id="PositionRoutingNumber"></a>varje betalningsrad inleds med bankens organisationsnummer. Formatelementet **vendBankRouteNum** används för detta syfte. 

8. Välj **Lägg till** och välj sedan typen **Text\\Sträng** för det formatelement som du vill lägga till:

    1. I fältet **Namn** anger du **vendBankSWIFT**.
    2. I fältet **Minsta längd** anger du **11**.
    3. I fältet **Maximal längd** anger du **11**.
    4. Välj **OK**.

    > [!NOTE]
    > Elementet **VendBankSWIFT** används för att ange SWIFT-koden för en leverantörsbank i genererade filer.

9. I formatstrukturträdet, välj **vendBankSWIFT**.
10. Välj **Flytta upp** om du vill flytta det valda format elementet en nivå uppåt. Upprepa det här steget tills elementet **vendBankSWIFT** är det <a id="PositionSWIFTCode"></a>första elementet under det överordnade elementet **transaktion**.

    ![VendBankSWIFT som första del under transaktionen i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format1.png)

11. När **vendBankSWIFT** fortfarande är markerat i formatstrukturträdet väljer du fliken **mappning** och expanderar sedan **modell** datakällan.
12. Expandera **model.Payment** \> **model.Payment.CreditorAgent** och välj fält **model.Payment.CreditorAgent.BICFI** för datakälla. Det här fältet i datakällan visar SWIFT-koden för en leverantörs bank som har tilldelats agentrollen i den bearbetade leverantörsbetalningen.
13. Välj **bind**. Formatelementet **vendBankSWIFT** är nu bundet med fältet **model.Payment.CreditorAgent.BICFI** för datakälla så att SWIFT-koder anges i den genererade betalningsfilen.

    ![vendBankSWIFT formatelement som är kopplat till model.Payment.CreditorAgent.BICFI fältet datakälla i ER-åtgärdsdesigner](./media/er-quick-start2-derived-format2.png)

14. Välj **Spara**.
15. Stäng designersidan.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Markera ett anpassat format som körbart

Nu när den första versionen av det anpassade formatet har skapats och har statusen **utkast** kan du köra den i testsyfte. Om du vill köra rapporten måste du bearbeta en leverantörsbetalning genom att använda betalningsmetoden som refererar till det anpassade ER-formatet. Som standard, när du anropar ett ER-format från appen kan endast versioner som har status **slutförd** eller **delad** [beaktas](general-electronic-reporting.md#component-versioning). Det här beteendet gör det enklare att använda ER-format som inte innehåller färdiga designer. För att testet ska kunna köras kan du dock tvinga appen att använda den version av ditt ER-format som har statusen **utkast**. På det här sättet kan du justera den aktuella formatversionen om du behöver göra ändringar. Mer information finns i [Tillämplighet](electronic-reporting-destinations.md#applicability).

Om du vill använda utkastversionen av ett ER-format måste du markera ER-format på tydligt sätt.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.
4. Välj **redigera** för att göra den aktuella sidan klar för redigering.
5. I konfigurationsträdet i det vänstra fönstret, välj **BACS (kund från Storbritannien)**.
6. Ge alternativet **Kör utkast** värdet **Ja**.

    ![Alternativet Kör utkast på sidan konfigurationer](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Bearbeta en leverantörsbetalning med hjälp av anpassat ER-format

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Ange den elektroniska betalningsmetoden

Du måste konfigurera den elektroniska betalningsmetoden så att ditt eget ER-format används för att bearbeta leverantörsbetalningar.

1. Gå till **Leverantörsreskontra** \> **Betalningsinställning** \> **Betalningsmetoder**.
2. På sidan **Betalningsmetoder - leverantörer** välj metoden **Elektronisk** i det vänstra fönstret.
3. Välj **Redigera**.
4. På snabbfliken **filformat** ställer du in alternativet **Allmänt elektroniskt exportformat** till **Ja**.
5. I fältet **Exportformatkonfiguration** väljer du formatkonfigurationen **BACS (kund från Storbritannien)**.

    ![Sidan Betalningsmetoder - leverantörer](./media/er-quick-start2-method-of-payment2.png)

6. Välj **Spara**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Bearbeta en leverantörsbetalning

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare.
3. Markera **rader**
4. På sidan **leverantörsbetalningar** ovanför rutnätet väljer du **betalningsstatus** \> **ingen**.
5. Välj **Generera betalning**.
6. Ange följande information i dialogrutan **Generera betalningar**:

    - I fältet **Betalningsmetod** väljer du **Elektronisk**.
    - I fältet **Bankkonto** väljer du **GBSI OPER**.

7. Välj **OK**.
8. I dialogrutan **Elektroniska rapportparametrar** anger du alternativet **Skriv ut kontrollrapport** till **Ja** och väljer sedan **OK**.

    > [!NOTE]
    > Förutom betalningsfilen kan du endast generera kontrollrapporten.

9. Hämta zip-filen och extrahera följande filer från den:

    - Kontrollrapporten i Excel-format
    - Betalningsfil i TXT-format

        Lägg märke till att betalningsraden i den genererade filen, i enlighet med strukturen i ditt anpassade ER-format, nu [startar](#PositionSWIFTCode) med SWIFT-kod som var [angav](#DefineSWIFTCode) för bankkontot för leverantören vars betalning har behandlats.

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importera nya versioner av standardkonfiguration av ER-format

För exemplet som visas i det här avsnittet får du ett meddelande om Knowledge Base-artikeln [KB 3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). I det här meddelandet får du information om den nya versionen av **BACS (UK)** ER-format som har publicerats av Microsoft. Förutom kontrollrapporten kan användarna skapa betalningsavirapporten och rapporten för notering av deltagande när en leverantörsbetalning bearbetas. Du vill börja använda den funktionen.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importera nya versioner av ER-standardkonfigurationer

Om du vill lägga till nya versioner av ER-konfigurationer i din aktuella Finance-instans måste du importera dem från ER [databasen](general-electronic-reporting.md#Repository) som du har konfigurerat.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.
3. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**. Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.
4. På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **BACS (UK)**-formatkonfiguration.
5. På snabbfliken **Versioner** välj version **3.3** av den valda ER-formatkonfigurationen.
6. Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.

![Sidan Konfigurationsdatabas](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från LCS istället.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Granska importerade ER-formatkonfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (UK)**.
4. På snabbfliken **Versioner**, välj version **3.3**.
5. Välj **Designer**.
6. På sidan **Formatdesigner** expandera **BACSReportsFolder** formatelement.
7.  Observera att version 3.3 innehåller det **PaymentAdviceReport** formatelement som används för att generera en betalningsavirapport när en leverantörsbetalning bearbetas.

    ![PaymentAdviceReport-formatelement i ER-åtgärdsdesigner](./media/er-quick-start2-imported-solution2.png)

8. Stäng designersidan.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Tillämpa ändringarna i den nya versionen av ett importerat format i ett anpassat format

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Slutför den nuvarande utkastversionen av ett anpassat format

Om du vill behålla det anpassade formatets aktuella status ska du fylla i utkast version 1.1.1 genom att ändra dess status från **utkast** till **slutförd**.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell**, expandera **BACS (UK)** och väljer sedan **BACS (kund från Storbritannien)**.
4. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 1.1.1 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 1.1.2, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i det anpassade ER-formatet.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Basera ett anpassat format på en ny basversion

Om du vill börja använda den nya funktionen i version 3.3 av **BACS (UK)** formatet i anpassningen måste du ändra baskonfigurationsversionen för den anpassade konfigurationen **BACS (kund från Storbritannien)**. Den här processen kallas för [ombasering](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). I stället för version 1.1 oav **BACS (UK)**, använd version 3.3.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **BACS (kund från Storbritannien)**.
3. På snabbfliken **Versioner** välj version **1.1.2** och välj sedan **Basera om**.
4. I dialogrutan **Basera om** i fältet **Målversion** välj version **3.3** av baskonfiguration att använda den som den nya basen och använda den för att uppdatera konfigurationen.

    ![Dialogrutan Basera om](./media/er-quick-start2-rebase1.png)

5. Välj **OK**.
6. Observera att numret på utkastversionen har ändrats från **1.1.2** till **3.3.2** för att avspegla ändringen i basversionen.

    När den anpassade versionen och en ny basversion slås samman kan vissa konflikter upptäckas på grund av formatändringar som inte kan slås samman automatiskt.

    ![Ombaserad konfiguration med konflikter på sidan konfigurationer](./media/er-quick-start2-rebase2.png)

    Om konflikter upptäcks måste de lösas manuellt i formatdesignern.

7. På snabbfliken **Versioner**, välj version **3.3.2**.
8. Välj **Designer**.
9. På sidan **Formatdesigner** på snabbfliken **Detaljer** välj posten ombasera konflikt och välj sedan **tillämpa basvärde**.

    ![Posten ombasera konflikt i ER-åtgärdsdesigner](./media/er-quick-start2-rebase3.png)

10. Välj **Spara**.

    Posten ombasera konflikt ska inte längre visas på snabbfliken **information**.

    ![Konflikt lösas i ER-åtgärdsdesigner](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Du har löst konflikten genom att bekräfta att version 3 av basmodellen måste användas i detta ER-format.

11. Expandera **BACSReportsFolder** \> **fil** \> **transaktioner** \> **transaktion**.
12. På fliken **Mappning** observera att version 3.3.2 av ditt anpassade ER-format innehåller både din anpassning (formatelementet **vendBankSWIFT** och dess bindning) och de nya funktionerna i version 3.3 av grundläggande ER-format som tillhandahölls av Microsoft (**PaymentAdviceReport** formatelement tillsammans med det är kapslade element och konfigurerade bindningar). Med bara några musklick kan du tillämpa ändringarna i en ny grundläggande version genom att koppla dem till dina anpassningar.

    ![Kopplat format i ER-åtgärdsdesigner](./media/er-quick-start2-rebase5.png)

13. Stäng designersidan.

> [!NOTE]
> Instruktionen för ombasering går att ångra. Om du vill avbryta den här ombaseringen väljer du version **1.1.1** av formatet **BACS (kund från Storbritannien)** på snabbfliken **Versioner** och välj sedan **Hämta denna version**. Version 3.3.2 kommer då att numreras om till och med innehållet i version 1.1.1 kommer innehållet i utkast version 1.1.2 att matchas.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Bearbeta en leverantörsbetalning med hjälp av ombaserat ER-format

1. Gå till **Leverantörsreskontra** \> **Betalningar** \> **Leverantörsbetalningsjournal**.
2. På sidan **Leverantörsbetalningsjournal** väljer du den betalningsjournal som du skapade tidigare.
3. Markera **rader**
4. På sidan **leverantörsbetalningar** ovanför rutnätet väljer du **betalningsstatus** \> **ingen**.
5. Välj **Generera betalning**.
6. Ange följande information i dialogrutan **Generera betalningar**:

    - I fältet **Betalningsmetod** väljer du **Elektronisk**.
    - I fältet **Bankkonto** väljer du **GBSI OPER**.

7. Välj **OK**.
8. I dialogrutan **Elektroniska rapportparametrar** ange följande information:

    - Ange alternativet **Skriv ut kontrollrapport** till **Ja**.
    - Ange alternativet **Skriv ut betalningsavi** till **Ja**.

    ![Dialogrutan Elektroniska rapportparametrar](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > Förutom betalningsfilen kan du nu generera både kontrollrapporten och betalningsavirapporten.

9. Välj **OK**.
10. Hämta zip-filen och extrahera följande filer från den:

    - Kontrollrapporten i Excel-format
    - Betalningsavirapporten i Excel-format

        ![Betalningsavirapporten i Excel-format](./media/er-quick-start2-payment-advice-report.png)

    - Betalningsfil i TXT-format

        Lägg märke till att betalningsraden i den genererade filen börjar med SWIFT-koden som anges för bankkontot för en leverantör vars betalning har behandlats.

        ![Betalningsfil i TXT-format](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Ladda ned ER-konfigurationer från Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](er-download-configurations-global-repo.md)
