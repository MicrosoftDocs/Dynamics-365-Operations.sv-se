---
title: Anpassa konfigurationer av elektronisk rapportering så att ett elektroniskt dokument skapas
description: Det här avsnittet innehåller information om hur du anpassar konfigurationer av elektronisk rapportering (ER) från Microsoft som används för att generera ett anpassat elektroniskt dokument.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: 47bb8a2a9adab4ec963a1d0b95e783299aab3819
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683031"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Anpassa konfigurationer av elektronisk rapportering så att ett elektroniskt dokument skapas

[!include[banner](../includes/banner.md)]

Med [ramverket för elektronisk rapportering (ER)](general-electronic-reporting.md) kan du överföra ER [konfigurationer](general-electronic-reporting.md#Configuration) som Microsoft tillhandahåller till din Microsoft Dynamics 365 Finance-instans. På så sätt kan de Microsoft-konfigurationer som tillhandahålls av Microsoft fungera som den återställningsmetod som används för att generera elektroniska kundfakturor (e-fakturor). Du kan använda den här ER-lösningen för att konfigurera din anpassade ER-lösning för att komma åt dina anpassade databasfält och skapa e-fakturor som är kompatibla med dina specifika behov, utan att du behöver redigera källkoden.

## <a name="overview"></a>Översikt

I exemplet i det här avsnittet måste du ange federal tax identification-kod som ett nytt eget attribut för varje kund som du fakturerar elektroniskt. Därför måste du anpassa strukturen för fakturan som för närvarande används genom att lägga till en ny artikel som måste fyllas med momskoden i alla e-fakturor som genereras.

Procedurerna i det här avsnittet förklarar hur en användare i rollen systemadministratör, utvecklare av elektronisk rapportering eller funktionell konsult för elektronisk rapportering kan utföra uppgifter i ekonomiinstansen:

- [Konfigurera den minimala uppsättningen ER-parametrar som krävs för att börja använda ER-ramverket](#ConfigureER).
- [Importera de ursprungliga versionerna av standard-ER-konfigurationerna som används för att generera e-fakturor](#ImportERConfigurations1).
- [Konfigurera Parametrar för kundreskontra så att de börjar använda standard-ER-konfigurationerna](#ConfigureAR1).
- [Konfigurera parametrar för juridisk person på fakturakunder](#ConfigureLE).
- [Förbered en kundpost för elektronisk fakturering](#ConfigureCustomer1).
- [Lägg till, bokför och skicka en kundfaktura med hjälp av standard-ER-konfigurationerna](#ProcessInvoice1).
- [Lägg till ett anpassat databasfält om du vill hantera en federal tax identification-kod för kunder](#AddCustomField).
- [Uppdatera ER-metadata för att aktivera databasändringar för ER-modellmappningsdesigner](#RefreshERMetadata).
- [Utforma de anpassade ER-konfigurationerna för att skapa e-fakturor som innehåller den nya momskoden](#DesignCustomERConfigurations).
- [Konfigurera Parametrar för kundreskontra så att de börjar använda anpassad ER-konfigurationerna](#ConfigureAR2).
- [Uppdatera en kundpost för elektronisk fakturering](#ConfigureCustomer2).
- [Lägg till, bokför och skicka en kundfaktura med hjälp av anpassade ER-konfigurationerna](#ProcessInvoice2).
- [Importera de nya versionerna av standard-ER-konfigurationerna som används för att generera e-fakturor](#ImportERConfigurations2).
- [Tillämpa ändringarna på de nya versionerna av standard-ER-konfigurationen i dina anpassade ER-konfigurationer](#RebaseCustomERConfigurations).
- [Lägg till, bokför och skicka en kundfaktura med hjälp av de nya versionerna av de anpassade ER-konfigurationerna](#ProcessInvoice3).

Alla dessa procedurer kan slutföras i **DEMF**-företaget.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Konfigurera ER-ramverket

Som användare i rollen funktionell konsult för elektronisk rapportering eller för utvecklare av elektronisk rapportering måste du konfigurera den minsta uppsättningen ER-parametrar. Du kan sedan börja använda ER-ramverket för att utforma anpassade versioner av standardkonfigurationerna för ER-lösningen som används för att generera e-fakturor.

### <a name="configure-er-parameters"></a>Konfigurera ER-parametrar

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.
4. På fliken **Bilagor** i fältet **Konfigurationer** välj **Fil**.
5. I fältet **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** och välj typen **Fil**.

Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Aktivera en ER-konfigurationsleverantör

Varje ER-konfiguration som läggs till markeras som ägd av en ER-konfigurationsleverantör. Den ER-konfigurationsleverantör för ER som aktiveras i arbetsytan **Elektronisk rapportering** används för det här syftet. Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.

> [!NOTE]
> Endast ägaren till en ER-konfiguration kan redigera den. Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Granska listan med ER-konfigurationsleverantörer

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

#### <a name="activate-an-er-configuration-provider"></a>Aktivera en ER-konfigurationsleverantör

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.

Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importera ursprungliga versioner av ER-standardkonfigurationer

Om du vill lägga till standard-ER-konfigurationer i din aktuella ekonomiinstansen måste du importera dem från [databasen](general-electronic-reporting.md#Repository) som har konfigurerats för den instansen.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.
3. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**. Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.
4. På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **Peppol-försäljningsfaktura**-formatkonfiguration.
5. På snabbfliken **Versioner**, välj version **11.2.2**.
6. Klicka på **Importera** för att hämta den valda versionen från Global lagringsplats.

![Sidan Konfigurationsdatabas](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Om du har problem med att komma åt den [Global databasen](er-download-configurations-global-repo.md), kan du [hämta konfigurationer](download-electronic-reporting-configuration-lcs.md) från Microsoft Dynamics Lifecycle Services (LCS) istället.

### <a name="review-the-imported-er-configurations"></a>Granska importerade ER-konfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **Konfigurationer** expanderar du snabbfliken **Konfigurationskomponenter**.
4. I konfigurationsträdet i det vänstra fönstret, expandera **Fakturamodell** och expandera sedan **UBL försäljningsfaktura**.

Observera att förutom det valda **Peppol-försäljningsfaktura** ER-format, har andra krävda ER-konfigurationer har importerats. Eftersom nya versioner av ER-konfigurationer ständigt publiceras i den globala databasen och LCS för att behålla motsvarande lösningar som är kompatibla med nya krav, importerades de senaste versionerna av den nödvändiga konfigurationen av [datamodellen](general-electronic-reporting.md#data-model-and-model-mapping-components) och dess konfigurationer av [modellmappnings](general-electronic-reporting.md#data-model-and-model-mapping-components).

![Sidan Konfigurationer](./media/er-quick-start3-imported-solution1a.png)

För att simulera tillståndet som ER-konfigurationer i den aktuella ekonomiinstansen skulle vara om du importerade versionen **11.2.2** av **Peppol-försäljningsfakturan** ER-format i det förflutna (t.ex. 7 augusti 2019) följer du dessa steg.

- I åtgärdsfönstret, välj **Ta bort** för att ta bort alla ER-konfigurationer som publicerades efter den 7 augusti 2019. Den enda **Fakturamodellen**, **Mappning av fakturamodell** (från början kallad **Modellmappning av kundfaktura**), **UBL försäljningsfaktura** och **Peppol-försäljningsfaktura**-konfigurationer måste finnas kvar.
- För de återstående ER-konfigurationerna, på snabbfliken **Versioner**, välj **Ta bort** för att ta bort alla versioner av ER-konfigurationer som publicerades efter den 7 augusti 2019.

Verifiera sedan att följande konfigurationer är tillgängliga i konfigurationsträdet:

- Konfiguration av **Fakturamodellen** ER-datamodell (från början kallad **Kundfakturamodell**):

    - Version 11 innehåller version 10 av [datamodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponent som representerar datastrukturen för företagsdomänen för fakturering. Den här ER-konfigurationen har importerats som en överordnad till ER-formatet **Peppol-försäljningsfakturan** som valdes för import.
    - Version 50 innehåller version 31 av ER-komponenten för datamodellen. Den här ER-konfigurationen har importerats som en föregångare till versionen från 7 augusti 2019 av konfiguration av ER-modellmappning **Mappning av fakturamodell**.

    ![Konfiguration av ER-datamodell av faktura modell på sidan konfigurationer](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Om version 50 av denna datamodell inte visas öppnar du den globala databasen och importerar version 50.19 av ER-konfigurationen **Mappning av fakturamodell**.

- Konfiguration och ER-modellmappning av **Mappning av fakturamodell** ER-datamodell (från början kallad **Mappning av kundfakturamodell**):

    - Version 50.19 har importerats som den senaste implementeringen av version 50 av konfiguration av ER-datamodell **fakturamodellen**. Den innehåller två [modellmappnings](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-komponenter som beskriver hur datamodellen fylls i med appdata vid körning.

    ![Konfiguration av mappning av fakturamodell, ER-modellmappning på sidan konfigurationer](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Om version 50.19 av denna modellmappning inte visas öppnar du den globala databasen och importerar version 50.19 av ER-konfigurationen **Mappning av fakturamodell**.

- **UBL försäljningsfaktura** Konfiguration av ER-format:

    - Version 11.2 innehåller [format](general-electronic-reporting.md#FormatComponentOutbound) och formatmappning för ER-komponenter. Formatkomponenten anger rapportlayouten. Komponenten för formatmappning innehåller modelldatakällan och anger hur denna datakälla används för att fylla i rapportlayouten vid körning. Det här ER-formatet har konfigurerats för att generera e-fakturor i UBL-format (Universal Business Language). Det har importerats som en överordnad till ER-formatet **Peppol-försäljningsfakturan** som valdes för import.

- **Peppol försäljningsfaktura** Konfiguration av ER-format:

    - Version 11.2.2 innehåller ERP-komponenter för format- och formatmappning som konfigurerades för att generera e-fakturor i formatet Pan-European Public Procurement OnLine (PEPPOL).

    ![Konfiguration av ER-datamodell av Peppol fakturamodell på sidan konfigurationer](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Konfigurera parametrar för kundreskontra

1. Gå till **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra**.
2. På fliken **Elektroniska dokument** på snabbfliken **Elektronisk rapportering** i fältet **Försäljnings- och fritextfaktura** välj **Peppol försäljningsfaktura**.
3. Välj **Spara**.

![Fliken elektroniska dokument på sidan Parametrar för kundreskontra](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Konfigurera parametrarna för den juridiska personen

1. Gå till **Organisationsadministration** \> **Organisationer** \> **Juridiska personer**.
2. För det valda **DEMF**-företaget på snabbfliken **Bankkontoinformation** i fältet **Clearingnummer** ange **1234**.
3. Välj **Spara**.
4. Stäng sidan **Juridiska personer**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Förbered en kundpost

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. På sidan **Alla kunder** välj länken **DE-014** kundkonto.

### <a name="add-a-customer-contact"></a>Lägg till en kundkontakt

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. I Åtgärdsfönstret, på fliken **kund**, i gruppen **konton**, markerar du **kontakter**.
3. Välj **Lägg till kontakter**.
4. På sidan **Kontakter** i fältet **Förnamn** öppnar du sökningen, väljer **Adam Carter** och väljer sedan **Välj** för att stänga sökningen.
5. Välj **Spara**.
6. Stäng sidan **Kontakter**.

### <a name="define-a-primary-contact"></a>Definiera en primär kontakt

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. På snabbfliken **Försäljningsdemografi** i fältet **Primär kontakt** välj **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Ställa in e-faktureringsalternativet

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. På snabbfliken **Faktura och leverans** ange alternativet **eInvoice** till **ja**.
3. Välj **Spara**.
4. Stäng sidan **alla kunder**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Behandla en kundfaktura med hjälp av standard-ER-konfigurationerna.

Du kan nu använda de ER-standardkonfigurationer som du importerade för att skicka en fritextfaktura till en kund elektroniskt.

### <a name="add-a-new-invoice"></a>Lägg till ny faktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **Fritextfaktura** välj **Ny**.
3. På snabbfliken **Fritextfakturahuvud** i fältet **Kundkonto** väljer du **DE-014**.
4. På snabbfliken **Fakturarader** läggs en fakturarad automatiskt till. Ställ in följande fält på denna rad:

    - I fältet **Beskrivning** anger du **Anteckningsbok**.
    - I fältet **Huvudkonto** väljer du **401100**.
    - I fältet **Enhetspris** ange **1000**.

5. Välj **Spara**.

![Sidan Fritextfakturor](./media/er-quick-start3-add-invoice.png)

Mer information finns i [Skapa fritextfaktura](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Bokför en ny faktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **Fritextfaktura** i åtgärdsfönstret, välj **bokför**.
3. I dialogrutan **Fritextfaktura** välj **OK**.

![Sidan Detaljer för fritextfaktura](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Skicka en bokförd faktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **fritextfaktura** i åtgärdsfönstret i gruppen **Dokument** välj **Skicka** \> **Ursprunglig**.

    ![Förhandsgranskning av den ursprungliga fakturan](./media/er-quick-start3-send-invoice.png)

3. Stäng sidan **Fritextfaktura**.

### <a name="analyze-a-generated-e-invoice"></a>Analysera en genererad e-faktura

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsjobb**.
2. På sidan **Elektroniska rapporteringsjobb** väljer du den första posten som har uppgiftsbeskrivningen **Skicka eInvoice XML**.
3. Välj **Visa filer** om du vill komma åt listan över genererade filer.

    ![Sidan Elektroniska rapporteringsjobb](./media/er-quick-start3-jobs-list.png)

4. Välj **Öppna** för att hämta den e-faktura-XML-fil som skapas.
5. Analysera XML-filen för e-fakturan. Observera att kundens skatteschema för närvarande representeras **schemeID** och **schemeAgencyID** XML-attributen. Observera också att **cbc:CustomizationID** XML-element innehåller för närvarande följande text: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Förhandsgranskning av den genererade XML-filen för e-fakturan](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Lägga till ett anpassat databasfält

Du kan använda funktionen [anpassat fält](../../fin-ops/get-started/user-defined-fields.md) för att utföra följande anpassning i den aktuella ekonomiinstansen:

- Anpassa databasstrukturen genom att lägga till ett nytt anpassat databasfält som lagrar en federal tax identification-kod för varje kund.
- Anpassa sidan **kund** genom att lägga till ett nytt fält för inmatning som kan användas för att ange ett momskodvärde i det nya anpassade databasfältet.

Utför anpassningarna enligt följande steg.

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. På sidan **Alla kunder** välj länken **DE-014** kundkonto.
3. På snabbfliken **Allmänt** högerklickar du på ett tomt område under fältet **Språk** och väljer sedan **Anpassa: UpperGroup**.

    Innehållet på snabbfliken **Allmänt** markeras och en **anpassa**-meny visas.

4. På **Anpassa**-menyn, välj **Lägg till ett fält**.
5. I dialogrutan **Lägg till kolumner** välj **Skapa nytt fält**.
6. I dialogrutan **Skapa nytt fält** i fält **Tabellnamn** välj **Kunder**.
7. I fältet **Namnprefix** anger du **FederalTaxID**.

    > [!NOTE]
    > Hela fältnamnet har definierats automatiskt som **FederalTaxID\_Anpassat**.

8. I fältet **Etikett** anger du **skatte-ID**.
9. I fältet **Typ**, välj **Text**.
10. I fältet **Längd** anger du **20**.
11. Välj **Spara**.
12. I meddelanderutan som visas väljer **Ja** för att bekräfta att du vill skapa en ny fältpost **FederalTaxID** för tabellen **Kunder**.
13. Välj **Infoga** till <a name="insert_custom_field"></a>lägg till fältet **FederalTaxID\_Anpassa** till den aktuella sidan.

    ![Sidan Alla kunder](./media/er-quick-start3-create-new-field.gif)

14. Stäng sidan **alla kunder**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Uppdatera ER-metadata

Du måste uppdatera ER-metadata för att göra det anpassade fältet som du har lagt till [synligt](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) i designer av ER-modellmappning.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Återskapa registerreferenser**.
2. I dialogrutan **Uppdatera datamodell** välj **OK**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Designa de anpassade ER-konfigurationerna

Du kan använda Microsofts ER-konfigurationer för att utforma dina anpassade ER-konfigurationer så att de genererar e-fakturor som innehåller den nya momskoden.

### <a name="customize-the-data-model-configuration"></a>Anpassa konfigurationen av datamodellen

Som användare i rollen funktionell konsult för elektronisk rapportering kan du designa din anpassade ER-datamodell.

#### <a name="add-a-custom-data-model-configuration"></a>Lägg till en anpassad konfiguration för datamodell

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Kundfakturamodell**.
3. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
4. I listrutan i fältet **Ny** välj **Härled från namn: kundfakturamodell, Microsoft** för att ange att din nya anpassade konfigurationen för ER-datamodell ska baseras på konfigurationen för ER-datamodellen.
5. I fältet **Namn** ange **fakturamodell (Litware)**.
6. Välj **Skapa konfiguration** för att lägga till den nya ER-konfigurationen.

Du kan nu använda designer för ER-datamodell designer för att redigera version 50.1 av **fakturamodell (Litware)** ER-konfiguration i **utkast** [status](general-electronic-reporting.md#component-versioning).

![Version 50.1 av ER-konfigurationen på sidan konfigurationer](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Konfigurera en anpassad datamodell

Du måste ändra din anpassad datamodell genom att lägga till ett nytt fält som anger värdet för en federal tax identification-kod. Den här koden är en del av kunddata för varje ER-format som kommer att använda den här datamodellen som en datakälla.

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Fakturamodell (Litware)**.
2. På snabbfliken **Versioner** välj version **50.1** av den valda ER-datamodellens konfiguration i **Utkast** status.
3. Välj **Designer** för den valda konfigurationsversionen i åtgärdsfönstret.
4. På sidan **Datamodell designer** i datamodellträdet, välj **Kundinformation (kund)**.
5. Välj **Ny**.
6. I dialogrutan i fältet **Ny nod som en** acceptera standardvärdet **Underordnad av en aktiv nod**.
7. I fältet **Namn** anger du **FederalTaxID\_Litware**.
8. I fältet **Artikeltyp** acceptera standardvärdet **Sträng**.
9. Välj **Lägg till** och välj sedan **Spara**.

    ![Sidan Datamodelldesigner](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > Fälten **Etikett** och **Beskrivning** beskriver syftet med det nya fältet. Du kan fylla i dessa fält på flera språk. Mer information finns i [Utforma flerspråkiga rapporter i elektronisk rapportering](er-design-multilingual-reports.md).

10. Stäng sidan **datamodelldesigner**.

#### <a name="complete-a-custom-data-model-configuration"></a>Slutför en anpassad konfiguration för datamodell

Du måste [slutföra](general-electronic-reporting.md#component-versioning) arbetet med version 50.1 av din konfiguration av din ER-datamodell för att göra den tillgänglig så att andra anpassade ER-konfigurationer kan läggas till.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell** och väljer sedan **Fakturamodell (Litware)**.
3. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 50.1 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 50.2, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i din anpassade konfiguration av ER-datamodell.

![Version 50.1 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Anpassa konfigurationen av modellmappning

Som användare i rollen funktionell utvecklare för elektronisk rapportering kan du designa din anpassade ER-modellmappning.

#### <a name="add-a-custom-model-mapping-configuration"></a>Lägg till en anpassad konfiguration för modellmappning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** och väljer sedan **Mappning av kundfakturamodell**.
3. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
4. I listrutan i fältet **Ny** välj **Härled från namn: mappning av kundfakturamodell, Microsoft** för att ange att din nya anpassade konfigurationen för ER-modellmappning ska baseras på konfigurationen för ER-modellmappning.
5. I fältet **Namn** ange **mappning av fakturamodell (Litware)**.
6. I fältet **Målmodell** väljer du **fakturamodell (Litware)**.

    > [!IMPORTANT]
    > Det här steget är mycket viktigt. Om du utelämnar den kan du inte använda din anpassade datamodell i den konfigurerade modellmappningen.

7. Välj **Skapa konfiguration** för att lägga till den nya ER-konfigurationen.

![Lägg till en anpassad konfiguration av modellmappning på sidan konfigurationer](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Konfigurera en anpassad modellmappning

Du måste ändra din anpassade modellmappning och ange hur det anpassade **FederalTaxID\_Litware**-fältet i den anpassade datamodellen ska fyllas i med programdata vid körning.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** \> **Mappning av kundfakturamodell** och väljer **Mappning av fakturamodell (Litware)**.
3. Klicka på **Designer** i åtgärdsfönstret.
4. På sidan **Modell till mappning av datakälla** i åtgärdsfönstret, välj mappning av **Kundfaktura**.

    ![Modell till mappning av datakälla](./media/er-quick-start3-select-customer-mapping.png)

5. Välj **Designer**.
6. På sidan **Modellmapping designer** i fönstret **Datakällor** expanderar du datakällan **CustInvoiceJour** som representerar appregistret **CustInvoiceJour**.
7. Under **CustInvoiceJour**, expandera **Relationer** för att granska relationerna av typen många till en (N:1) för tabellen **CustInvoiceJour**.
8. Under **CustInvoiceJour** \> **Relationer**, expandera **Kunder (CustTable)** för att komma åt fälten och relationerna i tabellen **Kunder (CustTable)**.
9. Välj datakällfältet **FederalTaxID\_Anpassa** som du implementerade [tidigare](#insert_custom_field).
10. I fönstret **Datamodell**, expandera **Kundinformation (kund)** och väljer datamodellfältet **FederalTaxID\_Litware**.
11. Välj **bind**.

    ![Modellmappningsdesigner](./media/er-quick-start3-customize-model-mapping.gif)

12. Välj **Spara**.
13. Stäng sidan **modellmappningsdesigner**.
14. Stäng sidan **modell till mappning av datakälla**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Slutför en anpassad konfiguration för modellmappning

Du måste [slutföra](general-electronic-reporting.md#component-versioning) arbetet med version 50.19.1 av din konfiguration av din ER-modellmappning för att göra den tillgänglig för användning.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** \> **Mappning av kundfakturamodell** och väljer **Mappning av fakturamodell (Litware)**.
3. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 50.19.1 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 50.19.2, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i din anpassade konfiguration av ER-modellmappning.

![Version 50.19.1 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> Den konfiguration som stöds [livscykel](general-electronic-reporting-manage-configuration-lifecycle.md) omfattar inte databasändringarnas livscykel. Om du exporterar version 50.19.1 av konfigurationen **mappning av fakturamodell (Litware)** från den aktuella ekonomiinstansen och försöker att importera den till en annan instans som inte innehåller det anpassade fältet **FederalTaxID\_Custom** i tabellen **CustTable** kommer ett undantag att uppstå. Undantaget kommer att ange att den importerade ER-konfigurationen inte är kompatibel med metadata för målekonomiinstansen.

### <a name="customize-the-format-configuration"></a>Anpassa formatkonfiguration

Som användare i rollen funktionell konsult för elektronisk rapportering kan du designa din anpassade ER-format.

#### <a name="add-a-custom-format-configuration"></a>Lägg till en anpassad formatkonfiguration

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** \> **UBL försäljningsfaktura** och väljer **Peppol försäljningsfaktura**.
3. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
4. I listrutan i fältet **Ny** välj **Härled från namn: Peppol försäljningsfaktura, Microsoft** för att ange att din nya anpassade konfigurationen för ER-format ska baseras på konfigurationen för ER-format.
5. I fältet **Namn** ange **Peppol försäljningsfaktura (Litware)**.
6. I fältet **Datamodell** väljer **Fakturamodell (Litware)** om du vill använda dina anpassade komponenter för datamodell och modellmappning.

    > [!NOTE]
    > Det här steget är mycket viktigt. Om du utelämnar den kan du inte använda din anpassade datamodell i den konfigurerade formatet.

7. I fältet **Datamodell** välj rotdefinitionen **InvoiceCustomer**.
8. Välj **Skapa konfiguration** för att lägga till den nya ER-konfigurationen.

![Lägg till en anpassad konfiguration av format på sidan konfigurationer](./media/er-quick-start3-adding-custom-format.png)

Du kan nu använda ER-åtgärdsdesigner för att redigera version 11.2.2.1 av **Peppol försäljningsfaktura (Litware)** ER-konfiguration i **utkast** [status](general-electronic-reporting.md#component-versioning).

![Version 11.2.2.1 av ER-konfigurationen på sidan konfigurationer](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Konfigurera ett anpassat format

Du måste ändra det anpassade formatet genom att lägga till ett nytt formatelement som fyller i värdet på en fakturerad kundens federal tax identification-kod.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** \> **UBL försäljningsfaktura** \> **Peppol försäljningsfaktura** och **Peppol försäljningsfaktura (Litware)**.
3. Klicka på **Designer** i åtgärdsfönstret.
4. I formatträdet, expandera **XMLHeader** \> **Faktura** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** och välj **cbc:ID**.
5. Välj **Lägg till** och välj sedan **XML** \> **Attribut**.
6. I dialogrutan **Komponentegenskap** i fältet **Namn** ange **FederalTaxID**.
7. Välj **OK** om du vill lägga till ett nytt formatelement för att skapa ett nytt **FederalTaxID** XML-attribut i en genererad XML-fil.
8. I formatträdet, under **XMLHeader** \> **Faktura** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID** välj **FederalTaxID**.
9. Välj **Flytta upp**.

![Nytt formatelement på sidan Formatdesigner](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Konfigurera en anpassad formatmappning

1. På sidan **Formatdesigner** på fliken **Mappning** expanderar du datakällan **Faktura** för typen **Modell**.
2. Under **Faktura**, expandera **kundinformation (kund)** och välj **FederalTaxID\_Litware**.
3. Välj **bind**.

    ![Formatdesignersida](./media/er-quick-start3-customized-format-mapping.png)

4. Markera datakällan **faktura** av typen **modell** och välj **Redigera**.
5. I fältet **Version**, välj version **1** av din anpassade datamodell och sedan **OK**.
6. Välj **Spara**.
7. Stäng sidan **Formatdesigner**.

#### <a name="complete-a-custom-format-configuration"></a>Slutför en anpassad formatkonfiguration

Du måste [slutföra](general-electronic-reporting.md#component-versioning) arbetet med version 11.2.2.1 av din konfiguration av din ER-format för att göra den tillgänglig för användning.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Kundfakturamodell** \> **UBL försäljningsfaktura** \> **Peppol försäljningsfaktura** och **Peppol försäljningsfaktura (Litware)**.
3. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 11.2.2.1 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 11.2.2.2, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i den anpassade konfigurationen ER-formatet.

![Version 11.2.2.1 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Konfigurera Parametrar för kundreskontra så att de börjar använda anpassad ER-konfigurationerna.

1. Gå till **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra**.
2. På fliken **Elektroniska dokument** på snabbfliken **Elektronisk rapportering** i fältet **Försäljnings- och fritextfaktura** välj **Peppol försäljningsfaktura (Litware)**.
3. Välj **Spara**.

![Sidan Parametrar för kundreskontra, fliken Elektroniska dokument, snabbfliken Elektronisk rapportering](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Uppdatera en kundpost genom att lägga till en federal tax identification-kod

1. Gå till **Leverantörsreskontra** \> **Kunder** \> **Alla kunder**.
2. På sidan **Alla kunder** välj länken **DE-014** kundkonto.
3. På snabbfliken **Allmänt** i fältet **skatte-ID** anger du **LITWARE-6789**.
4. Välj **Spara**.

    ![DE-014 sidan kundinformation](./media/er-quick-start3-added-tax-id-value.png)

5. Stäng sidan **alla kunder**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Behandla en kundfaktura med hjälp av anpassade ER-konfigurationerna.

### <a name="select-and-send-a-posted-invoice"></a>Välj och skicka en bokförd faktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **fritextfaktura** väljer du den faktura som du tidigare har lagt till och bokfört.
3. I åtgärdsfönstret i gruppen **Dokument** välj **Skicka** \> **Ursprunglig**.
4. Stäng sidan **Fritextfaktura**.

### <a name="analyze-a-generated-e-invoice"></a>Analysera en genererad e-faktura

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsjobb**.
2. På sidan **Elektroniska rapporteringsjobb** väljer du den senaste posten som har uppgiftsbeskrivningen **Skicka eInvoice XML**.
3. Välj **Visa filer** om du vill komma åt listan över genererade filer.
4. Välj **Öppna** för att hämta den e-faktura-XML-fil som skapas.
5. Analysera XML-filen för e-fakturan. Observera att i enlighet med din anpassning innehåller kundens skatteschema även det anpassade **FederalTaxID** XML-attributet förutom **schemeID** och **schemeAgencyID** XML-attributen. Värdet för det nya XML-attributet anges av skatte-ID **LITWARE-6789** federal tax ID som angavs för en fakturerad kund.

    ![Förhandsgranskning av den genererade XML-filen med dina anpassningar](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importera den senaste versioner av ER-standardkonfigurationer

Om du vill behålla standard-ER-konfigurationerna i din ekonomiinstans [uppdaterad](general-electronic-reporting-manage-configuration-lifecycle.md)måste du importera nya versioner av dem när de blir tillgängliga i ER [lagringsplats](general-electronic-reporting.md#Repository) som konfigurerades för den instansen.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Microsoft** och markera sedan **databaser** om du vill visa listan över databaser för Microsoft-leverantören.
3. På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typ och väljer sedan **Öppna**. Om du uppmanas att bevilja behörighet att ansluta till Regulatory Configuration Service följer du instruktionerna för auktorisering.
4. På sidan **Konfigurationsdatabas** i konfigurationsträdet i vänster fönster, välj den **Peppol-försäljningsfaktura**-formatkonfiguration.
5. På snabbfliken **Versioner** välj version **32.6.7** av den valda konfigurationen av ER-format som har släppts för att stödja kundens elektroniska fakturor i PEPPOL BIS 3-format. Mer information finns i [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.

![Version 32.6.7 markerad på sidan konfigurationsdatabas](./media/er-quick-start3-import-solution2.png)

Information om hur den här processen kan automatiseras finns i [importera uppdaterade versioner av ER-konfigurationer](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Granska importerade ER-konfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. Expandera snabbfliken **konfigurationskomponenter**.
4. I konfigurationsträdet i det vänstra fönstret, expandera **Fakturamodell**. Observera att namnet på **Kundfakturamodellen** har ändrats till **Fakturamodellen** i någon av de importerade konfigurationerna för ER-datamodell.
5. I konfigurationsträdet i det vänstra fönstret, expandera **Fakturamodellmappning**. Observera att namnet på **Mappning av kundfakturamodellen** har ändrats till **Fakturamodellmappning** i någon av de importerade konfigurationerna för ER-modellmappning.
6. Expandera **UBL försäljningsfaktura** \> **Peppol försäljningsfaktura**.

Observera att förutom det valda **Peppol-försäljningsfaktura** ER-format, de senaste versionerna av andra krävda ER-konfigurationer har importerats. Eftersom nya versioner av ER-konfigurationer ständigt publiceras i den globala databasen och LCS för att behålla motsvarande ER-lösningar som är kompatibla med nya krav, importerades de senaste versionerna av den nödvändiga konfigurationen av datamodellen och dess konfigurationer av modellmappnings.

Se till att följande ER-konfigurationer är tillgängliga i konfigurationsträdet:

- **Fakturamodell** Konfiguration av ER-datamodell:

    - Version 206 (eller senare) innehåller version 24 (eller senare) av datamodell ER-komponent som representerar datastrukturen för företagsdomänen för fakturering. Den här ER-konfigurationen har importerats som senast tillgänglig **mappning av fakturamodell** Konfiguration och ER-modellmappning.

    ![Version 206 på sidan konfigurationer](./media/er-quick-start3-imported-solution2b1.png)

- **Mappning av fakturamodell** konfiguration av ER-modellmappning:

    - Version 206.132 (eller senare) har importerats som den senaste implementeringen av version 206 av konfiguration av ER-datamodell **fakturamodellen**. Den innehåller flera modellmappnings ER-komponenter som beskriver hur datamodellen fylls i med appdata vid körning.

    ![Version 206.132 på sidan konfigurationer](./media/er-quick-start3-imported-solution2b2.png)

- **UBL försäljningsfaktura** Konfiguration av ER-format:

    - Version 32.6 innehåller format och formatmappning för ER-komponenter. Formatkomponenten anger rapportlayouten. Komponenten för formatmappning innehåller modelldatakällan och anger hur denna datakälla används för att fylla i rapportlayouten vid körning. Det här ER-formatet har konfigurerats för att generera e-fakturor i UBL-format. Det har importerats som en överordnad till ER-formatet **Peppol-försäljningsfakturan** som valdes för import.

- **Peppol försäljningsfaktura** Konfiguration av ER-format:

    - Version 32.6.7 innehåller ERP-komponenter för format- och formatmappning som konfigurerades för att generera e-fakturor i PEPPOL-format.

    ![Version 32.6.7 på sidan konfigurationer](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Tillämpa ändringarna på de nya standard-ER-konfigurationen i dina anpassade ER-konfigurationer

### <a name="adopt-your-custom-er-data-model"></a>Anta din anpassade ER-datamodell

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell** och väljer sedan **Fakturamodell (Litware)**.
3. På snabbfliken **Versioner** för utkastversion **50.2** av den valda ER-datamodellens konfiguration välj **Basera om**
4. I fältet **Målversion** bekräftar du valet av version **206** av konfigurationen för ER-basdatamodellen och väljer sedan **OK**.

    Utkastversionen av din konfiguration av din ER-datamodell numreras om från **50.2** till **206.2** för att ange att den nu innehåller din anpassning som slogs samman med ändringarna i den senaste versionen (206) av konfiguration av ER-basdatamodell.

    > [!NOTE]
    > Instruktionen för ombasering går att ångra. Om du vill avbryta den här ombaseringen väljer du version **50.1** av modellen **Fakturamodell (Litware)** på snabbfliken **Versioner** och välj sedan **Hämta denna version**. Version 206.2 kommer då att numreras tillbaka till **50.2** och innehållet i version 50.1 kommer innehållet i utkast version 50.2 att matchas.

5. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 206.2 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 206.3, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i din anpassade konfiguration av ER-datamodell.

![Version 206.2 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Anta din anpassade ER-modellmappning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **fakturamodell** \> **Mappning av fakturamodell** och väljer **Mappning av fakturamodell (Litware)**.
3. På snabbfliken **Versioner** för utkastversion **50.19.2** av den valda ER-modellmappning konfiguration välj **Basera om**
4. I fältet **Målversion** bekräftar du valet av version **206.132** av konfigurationen för ER-modellmappning och väljer sedan **OK**.

    Utkastversionen av din konfiguration av din ER-modellmappning numreras om från **50.19.2** till **206.132.2** för att ange att den nu innehåller din anpassning som slogs samman med ändringarna i den senaste versionen (206.132) av konfiguration av ER-modellmappning.

    Lägg märke till att vissa konflikter för ombasering upptäcktes. Du måste nu lösa konflikterna manuellt.

    ![Konfliktmeddelandet för basera om på sidan konfigurationer](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. I åtgärdsfönstret, välj **Designer** och välj sedan **Kundfaktura** i listan över mappningar.
6. För varje konflikt med ombasering, välj **Bibehåll eget värde**, eftersom du måste behålla versionsnumret för din anpassade datamodell för varje komponent som har nämnts.

    ![Konflikter för ombasering på sidan för modellmappningsdesigner](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Välj **Spara** och stäng sedan sidan **Modellmappningsdesigner**.
8. I listan över mappningar, välj **projektfaktura**.
9. För varje konflikt med ombasering, välj **Bibehåll eget värde**, eftersom du måste behålla versionsnumret för din anpassade datamodell för varje komponent som har nämnts.
10. Välj **Spara** och stäng sedan sidan **Modellmappning**.

    > [!NOTE]
    > Instruktionen för ombasering går att ångra. Om du vill avbryta den här ombaseringen väljer du version **50.19.1** av modellmappningen **Mappning av fakturamodell (Litware)** på snabbfliken **Versioner** och välj sedan **Hämta denna version**. Version 206.132.2 kommer då att numreras tillbaka till **50.19.2** och innehållet i version 50.19.1 kommer innehållet i utkast version 50.19.2 att matchas.

11. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 206.132.2 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 206.132.3, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i din anpassade konfiguration av ER-modellmappning.

![Version 206.132.2 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Anta det anpassade ER-formatet

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell** \> **UBL försäljningsfaktura** \> **Peppol försäljningsfaktura** och **Peppol försäljningsfaktura (Litware)**.
3. På snabbfliken **Versioner** för utkastversion **11.2.2.2** av den valda formatkonfiguration välj **Basera om**
4. I fältet **Mål** bekräftar du valet av version **32.6.7** av konfigurationen för ER-basformat och väljer sedan **OK**.

    Utkastversionen av din konfiguration av din ER-format numreras om från **11.2.2.2** till **32.6.7.2** för att ange att den nu innehåller din anpassning som slogs samman med ändringarna i den senaste versionen (32.6.7) av konfiguration av ER-basformat.

    Lägg märke till att vissa konflikter för ombasering upptäcktes. Du måste nu lösa konflikterna manuellt.

5. Klicka på **Designer** i åtgärdsfönstret.
6. För varje konflikt med ombasering, välj **Bibehåll eget värde**, eftersom du måste behålla versionsnumret för din anpassade datamodell för varje komponent som har nämnts.
7. Välj **Spara**.
8. På fliken **Mappning** välj datakällan **Faktura** av typen **Modell** och välj **Redigera**.
9. I fältet **Version**, välj version **2** av din anpassade datamodell och sedan **OK**.
10. Välj **Spara**.

    > [!NOTE]
    > Instruktionen för ombasering går att ångra. Om du vill avbryta den här ombaseringen väljer du version **11.2.2.1** av formatet **Peppol försäljningsfaktura (Litware)** på snabbfliken **Versions** och välj sedan **Hämta denna version**. Version 32.6.7.2 kommer då att numreras tillbaka till **11.2.2.2** och innehållet i version 11.2.2.1 kommer innehållet i utkast version 11.2.2.2 att matchas.

11. Stäng sidan **Formatdesigner**.
12. På snabbfliken **Versioner** välj **Ändra status** \> **Slutförd** och välj sedan **OK**.

Status för version 32.6.7.2 ändras från **utkast** till **slutfört** och versionen blir skrivskyddad. En ny redigerbar version, 32.6.7.3, har lagts till och har statusen **utkast**. Du kan använda den här versionen för att göra ytterligare ändringar i den anpassade konfigurationen ER-formatet.

![Version 32.6.7.2 slutförd på sidan konfigurationer](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Behandla en kundfaktura med hjälp av nya versioner av de anpassade ER-konfigurationerna.

### <a name="select-and-send-a-posted-invoice"></a>Välj och skicka en bokförd faktura

1. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
2. På sidan **fritextfaktura** väljer du den faktura som du tidigare har lagt till och bokfört.
3. I åtgärdsfönstret i gruppen **Dokument** välj **Skicka** \> **Ursprunglig**.

    > [!NOTE] 
    > Eftersom du nu har två versioner av **Peppol försäljningsfaktura Invoice (Litware)** konfiguration för ER-fomat och ingen av versionerna har ett [giltighetsdatum](general-electronic-reporting.md#component-date-effectivity)-värde används den senaste versionen för att generera en e-faktura.

4. Stäng sidan **Fritextfaktura**.

### <a name="analyze-a-generated-e-invoice"></a>Analysera en genererad e-faktura

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsjobb**.
2. På sidan **Elektroniska rapporteringsjobb** väljer du den senaste posten som har uppgiftsbeskrivningen **Skicka eInvoice XML**.
3. Välj **Visa filer** om du vill komma åt listan över genererade filer.
4. Välj **Öppna** för att hämta den e-faktura-XML-fil som skapas.
5. Analysera XML-filen för e-fakturan. Observera att i enlighet med din anpassning innehåller kundens skatteschema även det anpassade **FederalTaxID** XML-attributet förutom **schemeID** och **schemeAgencyID** XML-attributen. Eftersom ändringarna i den nya versionen av UBL för det grundläggande formatet **försäljningsfaktura** kombinerades med din anpassning, har texten för **CBC: CustomizationID** XML-element ändrats från `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` till `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Förhandsgranskning av den genererade XML-filen med anpassningar](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Ladda ned ER-konfigurationer från Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](er-download-configurations-global-repo.md)
- [Skapa en fritextfaktura](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new)
- [Skapa och arbeta med anpassade fält](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields)
