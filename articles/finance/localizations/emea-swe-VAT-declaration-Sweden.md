---
title: Momsdeklaration (Sverige)
description: I detta ämne beskrivs hur du konfigurerar in och genererar en momsdeklaration för Sverige.
author: anasyash
ms.date: 09/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Sweden
ms.author: anasyash
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3f24f810c310ff2ccc2c30c9ca098edb15e2f432
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647079"
---
# <a name="vat-declaration-sweden"></a>Momsdeklaration (Sverige)

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du konfigurerar in och genererar en momsdeklaration för Sverige. Du kan generera en förhandsgranskning av momsdeklarationen i Microsoft Excel. Du kan också generera en momsdeklaration i [dokumenttypsdefinitionsformat (DTD)](https://www.skatteverket.se/omoss/samverkan/forprogramkonstruktorer/dtdfil.4.65fc817e1077c25b83280000.html?q=dtd) och överföra den till [Skatteverkets officiella portal](https://www.skatteverket.se/foretag/moms/deklareramoms.4.7459477810df5bccdd480006935.html).

Om du vill generera rapporten automatiskt måste du först skapa tillräckligt med momskoder för att hålla en separat momsredovisning för respektive ruta i momsdeklarationen. I de programspecifika parametrarna för det elektroniska rapporteringsformatet (ER) för momsdeklarationen måste du dessutom koppla momskoder till sökresultatet för rutorna i momsdeklarationen.

För Sverige måste du konfigurera en (1) sökning: **Sökning i rapportfält**. Mer information om hur du konfigurerar programspecifika parametrar finns i avsnittet [Ställa in programspecifika parametrar för momsdeklarationsfält](#set-up-application-specific-parameters-for-vat-declaration-boxes) längre fram i det här avsnittet.

I följande tabell visar kolumnen **Sökresultat** det sökresultat som är förkonfigurerat för en viss momsdeklarationsrad i momsdeklarationsformatet. Använd den här informationen för att korrekt koppla momskoder till sökresultatet och sedan till raden i momsdeklarationen.

## <a name="vat-declaration-overview"></a>Momsdeklaration – översikt

Momsdeklarationen i Sverige innehåller följande information:

**Avsnitt A. Momspliktig försäljning eller självförsörjning**

| Rad | beskrivning                                             | XML-filelement | Sökningsresultat                                                                                                    |
|------|---------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------|
| 05   | Momspliktig försäljning, inte inkluderad i rutorna 06, 07 eller 08 | ForsMomsEjAnnan  | SalesLiableToVATStandard (05/10)</br>SalesLiableToVATReduced (05/11)</br>SalesLiableToVATReduced2 (05/12)                |
| 06   | Momspliktig självbetjäning                               | UttagMoms        | SelfSupplyLiableToVATStandard</br>(06/10) SelfSupplyLiableToVATReduced</br>(06/11) </br>SelfSupplyLiableToVATReduced2 (06/12) |
| 07   | Taxeringsgrund för vinstmarginalbeskattning         | UlagMargbesk     | TaxBaseProfitMarginStandard (07/10)</br>TaxBaseProfitMarginReduced (07/11) </br>TaxBaseProfitMarginReduced2 (07/12)       |
| 08   | Hyresinkomst – frivillig skattskyldighet                 | HyrinkomstFriv   | RentalIncomeStandard (08/10)</br>RentalIncomeReduced (08/11)</br>RentalIncomeReduced2 (08/12)                            |

**Avsnitt B. Utgående moms på försäljning i ruta 05 – 08**

| Rad | beskrivning     | XML-filelement | Sökningsresultat                                                                                                                           |
|------|-----------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| 10   | Utgående moms 25 % | MomsUtgHog       | SalesLiableToVATStandard (05/10)</br>SelfSupplyLiableToVATStandard (06/10)</br>TaxBaseProfitMarginStandard (07/10)</br> RentalIncomeStandard (08/10) |
| 11   | Utgående moms 12 % | MomsUtgMedel     | SalesLiableToVATReduced (05/11)</br>SelfSupplyLiableToVATReduced (06/11)</br>TaxBaseProfitMarginReduced (07/11)</br>RentalIncomeReduced (08/11)     |
| 12   | Utgående moms 6 %  | MomsUtgLag       | SalesLiableToVATReduced2 (05/12)</br>SelfSupplyLiableToVATReduced2 (06/12)</br>TaxBaseProfitMarginReduced2 (07/12)</br> RentalIncomeReduced2 (08/12) |

**Avdelning C. Momspliktiga inköp**

| Rad | beskrivning                                                        | XML-filelement   | Sökningsresultat                                                                                                                                                                                                                                                                        |
|------|--------------------------------------------------------------------|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 20   | Inköp av varor från ett annat EU-land                         | InkopVaruAnnatEg   | EUPurchaseGoodsStandard (20/30)</br>EUPurchaseGoodsReduced (20/31) </br>EUPurchaseGoodsReduced2 (20/32)</br>EUPurchaseGoodsStandardUseTax (20/30/48)</br>EUPurchaseGoodsReducedUseTax (20/31/48)</br>EUPurchaseGoodsReduced2UseTax (20/32/48)                                                             |
| 21   | Inköp av tjänster från ett annat EU-land enligt huvudregeln | InkopTjanstAnnatEg | EUPurchaseServicesStandard (21/30)</br>EUPurchaseServicesReduced (21/31)</br> EUPurchaseServicesReduced2 (21/32)</br>EUPurchaseServicesStandardUseTax (21/30/48)</br>EUPurchaseServicesReducedUseTax (21/31/48)</br>EUPurchaseServicesReduced2UseTax (21/32/48)                                           |
| 22   | Inköp av tjänster från ett land utanför EU                | InkopTjanstUtomEg  | PurchaseServicesOutsideEUStandard (22/30)</br>PurchaseServicesOutsideEUReduced (22/31)</br>PurchaseServicesOutsideEUReduced2 (22/32)</br>PurchaseServicesOutsideEUStandardUseTax (22/30/48)</br>PurchaseServicesOutsideEUReducedUseTax (22/31/48) </br>PurchaseServicesOutsideEUReduced2UseTax (22/32/48) |
| 23   | Inköp av varor i Sverige som köparen är ansvarig för          | InkopVaruSverige   | PurchaseGoodsDomesticRCStandard (23/30)</br>PurchaseGoodsDomesticRCReduced (23/31)</br>PurchaseGoodsDomesticRCReduced2 (23/32)</br>PurchaseGoodsDomesticRCStandardUseTax (23/30/48)</br>PurchaseGoodsDomesticRCReducedUseTax (23/31/48) </br>PurchaseGoodsDomesticRCReduced2UseTax (23/32/48)             |
| 24   | Övriga inköp av tjänster                                        | InkopTjanstSverige | OtherPurchaseGoodsRCStandard (24/30)</br>OtherPurchaseGoodsRCReduced (24/31) </br>OtherPurchaseGoodsRCReduced2 (24/32)</br>OtherPurchaseGoodsRCStandardUseTax (24/30/48)</br>OtherPurchaseGoodsRCReducedUseTax (24/31/48)</br>OtherPurchaseGoodsRCReduced2UseTax (24/32/48)                               |

**Avsnitt D. Utgående moms på inköp i ruta 20 – 24**

| Rad | beskrivning     | XML-filelement  | Sökningsresultat                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------|-----------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 30   | Utgående moms 25 % | MomsInkopUtgHog   | EUPurchaseGoodsStandard (20/30)</br>EUPurchaseGoodsStandardUseTax (20/30/48)</br>EUPurchaseServicesStandard (21/30) </br>EUPurchaseServicesStandardUseTax (21/30/48)</br>PurchaseServicesOutsideEUStandard (22/30)</br>PurchaseServicesOutsideEUStandardUseTax (22/30/48) </br>PurchaseGoodsDomesticRCStandard (23/30)</br>PurchaseGoodsDomesticRCStandardUseTax (23/30/48)</br>OtherPurchaseGoodsRCStandard (24/30)</br>OtherPurchaseGoodsRCStandardUseTax (24/30/48) |
| 31   | Utgående moms 12 % | MomsInkopUtgMedel | EUPurchaseGoodsReduced (20/31)</br>EUPurchaseGoodsReducedUseTax (20/31/48)</br>EUPurchaseServicesReduced (21/31) </br>EUPurchaseServicesReducedUseTax (21/31/48)</br>PurchaseServicesOutsideEUReduced (22/31)</br>PurchaseServicesOutsideEUReducedUseTax (22/31/48)</br>PurchaseGoodsDomesticRCReduced (23/31)</br>PurchaseGoodsDomesticRCReducedUseTax (23/31/48)</br>OtherPurchaseGoodsRCReduced (24/31)</br>OtherPurchaseGoodsRCReducedUseTax (24/31/48)           |
| 32   | Utgående moms 6 %  | MomsInkopUtgLag   | EUPurchaseGoodsReduced2 (20/32)</br>EUPurchaseGoodsReduced2UseTax (20/32/48)</br>EUPurchaseServicesReduced2 (21/32) </br>EUPurchaseServicesReduced2UseTax (21/32/48)</br>PurchaseServicesOutsideEUReduced2 (22/32)</br>PurchaseServicesOutsideEUReduced2UseTax (22/32/48) </br>PurchaseGoodsDomesticRCReduced2 (23/32)</br>PurchaseGoodsDomesticRCReduced2UseTax (23/32/48)</br>OtherPurchaseGoodsRCReduced2 (24/32)</br>OtherPurchaseGoodsRCReduced2UseTax (24/32/48) |

**Avsnitt H. Import**

| Rad | beskrivning             | XML-filelement | Sökningsresultat                                                                                                                                                      |
|------|-------------------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 50   | Beskattningsunderlag för import | MomsUlagImport   | ImportStandard (50/60)</br>ImportReduced (50/61)</br>ImportReduced2 (50/62)</br>ImportStandardUseTax (50/60/48) ImportReducedUseTax</br>(50/61/48)</br>ImportReduced2UseTax (50/62/48) |

**Avsnitt I. Utgående moms vid import i ruta 50**

| Rad | beskrivning     | XML-filelement   | Sökningsresultat                                          |
|------|-----------------|--------------------|--------------------------------------------------------|
| 60   | Utgående moms 25 % | MomsImportUtgHog   | ImportStandard (50/60)</br>ImportStandardUseTax (50/60/48) |
| 61   | Utgående moms 12 % | MomsImportUtgMedel | ImportReduced (50/61)</br>ImportReducedUseTax (50/61/48)   |
| 62   | Utgående moms 6 %  | MomsImportUtgLag   | ImportReduced2 (50/62)</br>ImportReduced2UseTax (50/62/48) |

**Avsnitt E. Momsbefriad försäljning osv.**

| Rad | beskrivning                                                             | XML-filelement      | Sökningsresultat                          |
|------|-------------------------------------------------------------------------|-----------------------|----------------------------------------|
| 35   | Försäljning av varor till ett annat EU-land                                    | ForsVaruAnnatEg       | EUSalesGoods                           |
| 36   | Försäljning av varor utanför EU                                           | ForsVaruUtomEg        | ExportSalesGoods                       |
| 37   | Mellanhand för inköp av varor vid triangulering                | InkopVaruMellan3p     | IntermediaryPurchaseGoodsTriangulation |
| 38   | Mellanhand för försäljning av varor vid triangulering                    | ForsVaruMellan3p      | IntermediarySalesGoodsTriangulation    |
| 39   | Försäljning av tjänster via transithandel i ett annat EU-land enligt huvudregeln | ForsTjSkskAnnatEg     | EUSalesServices                        |
| 40   | Övrig försäljning av tjänster som tillhandahålls utanför Sverige                      | ForsTjOvrUtomEg       | SalesServicesOutsideEU                 |
| 41   | Försäljning där köparen är momspliktig i Sverige                    | ForsKopareSkskSverige | SalesGoodsDomesticRC                   |
| 42   | Övrig försäljning o.s.v.                                                        | ForsOvrigt            | OtherSales                             |

**Avsnitt F. Ingående moms**

| Rad | beskrivning         | DTD-filelement | Sökningsresultat                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|------|---------------------|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 48   | Ingående moms att dra av | MomsIngAvdr      | InputVAT EUPurchaseGoodsStandardUseTax (20/30/48)</br>EUPurchaseGoodsReducedUseTax (20/31/48)</br>EUPurchaseGoodsReduced2UseTax (20/32/48)</br>EUPurchaseServicesStandardUseTax (21/30/48)</br>EUPurchaseServicesReducedUseTax (21/31/48)</br>EUPurchaseServicesReduced2UseTax (21/32/48) </br>PurchaseServicesOutsideEUStandardUseTax (22/30/48)</br>PurchaseServicesOutsideEUReducedUseTax (22/31/48)</br>PurchaseServicesOutsideEUReduced2UseTax (22/32/48) </br>PurchaseGoodsDomesticRCStandardUseTax (23/30/48)</br>PurchaseGoodsDomesticRCReducedUseTax (23/31/48)</br>PurchaseGoodsDomesticRCReduced2UseTax (23/32/48) </br>OtherPurchaseGoodsRCStandardUseTax (24/30/48)</br>OtherPurchaseGoodsRCReducedUseTax (24/31/48)</br>OtherPurchaseGoodsRCReduced2UseTax (24/32/48)</br>ImportStandardUseTax (50/60/48)</br>ImportReducedUseTax (50/61/48)</br>ImportReduced2UseTax (50/62/48) |

### <a name="purchase-reverse-charge-vat"></a>Återfört tillägg för inköp

Om du konfigurerar momskoder i syfte att bokföra inkommande återförda tillägg med hjälp av importavgift ska du associera dina momskoder med det sökresultat för använd moms, ska du koppla momskoderna till det sökresultat i **Sökning i rapportfält** som innehåller "UseTax" i namnet.

Alternativt kan du konfigurera två separata momskoder: en för förfallen moms och en för momsavdrag. Koppla sedan varje kod till motsvarande sökresultat för **Sökning i rapportfält**.

För inköp av varor till en standardsats i Sverige som köparen är ansvarig för, konfigurerar du exempelvis momskod **UT_S_RC** med importavgift och associerar den med sökresultatet **PurchaseGoodsDomesticRCStandardUseTax** för **Sökning i rapportfält**. I det här fallet återspeglas belopp som använder momskoden **UT_S_RC** i rutorna 23 (skatteunderlag), 30 (skuld) och 48 (skatteavdrag).

Alternativt kan du konfigurera två momskoder:

   - **VAT_S_RC**, som har ett momssatsvärde på -25 procent
   - **InVAT_S_RC**, som har ett momssatsvärde på 25 procent

Därefter associerar du koderna med sökresultaten på följande sätt:

   - Associera **VAT_S_RC** med sökresultatet **PurchaseGoodsDomesticRCStandard** i **Sökning i rapportfält**.
   - Associera **InVAT_S_RC** med sökresultatet **InputVAT** föri **Sökning i rapportfält**.

I det här fallet återspeglas belopp som använder momskoden **VAT_S_RC** i rutorna 23 (skatteunderlag) och 30 (skuld). Belopp som använder momskoden **InVAT_S_RC** återspeglas på rad 48.

Mer information om hur du konfigurerar återfört tillägg finns i [Omvänd moms](emea-reverse-charge.md).

## <a name="set-up-vat-declaration-for-sweden"></a>Konfigurera momsdeklaration för Sverige

### <a name="import-er-configurations"></a>Importera ER-konfigurationer

Öppna arbetsytan **Elektronisk rapportering** och importera följande versioner eller en senare version av dessa ER-format:

   - Momsdeklaration XML (SE) version 95.11
   - Momsdeklaration Excel (SE) version 95.11.13

Mer information om hur du importerar ER-format finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-boxes"></a><a name="set-up-application-specific-parameters-for-vat-declaration-boxes"></a>Konfigurera programspecifika parametrar för momsdeklarationsrutor

Om du vill generera en momsdeklaration automatiskt, associerar du momskoder i programmet och sökningsresultaten i ER-konfigurationen.

> [!NOTE]
> Vi rekommenderar att du aktiverar funktionen genom att **Använd appspecifika parametrar från tidigare versioner av ER-format** i arbetsytan **Funktionshantering**. När den här funktionen är aktiverad blir parametrar som är konfigurerade för den tidigare versionen av ett ER-format automatiskt tillämpliga för den senare versionen av samma format. Om den här funktionen inte är aktiverad måste du konfigurera programspecifika parametrar explicit för varje formatversion. Funktionen **Använd appspecifika parametrar från tidigare versioner av ER-format** är tillgänglig i arbetsytan **Funktionshantering** med början i Finance version 10.0.23. Mer information om hur du ställer in parametrarna för ett ER-format för varje juridisk person finns i [Ställa in parametrarna för ett ER-format per juridisk enhet](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

1. Gå till **Arbetsytor** > **Elektronisk rapportering** och välj **Rapporteringskonfiguration**.
2. Välj **Momsdeklaration XML (SE)** och välj sedan **Konfigurationer** > **Programspecifika parameterinställningar**.
3. På snabbfliken **Villkor** associerar du momskoderna och rapportfälten.

    > [!NOTE]
    >  Se till att associera alla momskoder till sökresultaten. Om momskoder inte ska generera värden i momsdeklarationen associerar du dem med sökresultatet **Övrigt**.
    >  
    >  Om du skapar tillräckligt med momskoder för att generera momsdeklarationsrutor som endast baseras på association till momskod, ska i kolumnen **Transaktionsklassifierare** välja **Ej tom**. Alternativt kan du, om du använder samma momskod för olika transaktionstyper, välja värde i kolumnen **Transaktionsklassifierare**. Om du till exempel använder samma momskod för försäljningar och inköp bör du ha minst fyra rader för samma momskod med värden för **Transaktionsklassifierare**: **Försäljning**, **SalesCreditNote**, **Inköp** samt **PurchaseCreditNote**.

      ![Sidan Programspecifika parametrar.](media/434c381f0f588abf84cd83518b51cf20.png)

4. I åtgärdsfönstret väljer du **Exportera** om du vill exportera inställningarna till en XML-fil. Stäng sidan.
5. Välj konfigurationen **Momsdeklaration Excel (SE)** och sedan **Konfigurationer** > **Programspecifika parameterinställningar**.
6. Välj **Importera** och markera den fil som du exporterade tidigare.

    > [!NOTE]
    > När du skapar en ny momskod justerar du inställningarna för programspecifika parametrar enligt sökresultatet för den nya momskoden.

    När du importerar en ny version av en ER-konfiguration, importerar du inställningarna för programspecifika parametrar till den nya versionen.

### <a name="set-up-the-vat-reporting-format"></a>Konfigurera momsrapporteringsformat

1. I arbetsytan **Funktionshantering** aktiverar du funktionen **Formatrapporter för momsutdrag**.
2. Gå till **Redovisning** > **Inställningar** > **Redovisningsparametrar**.
3. På fliken **Moms** > snabbfliken **Momsalternativ** > fältet **Formatmappning för momsutdrag** väljer du formatet **Momsdeklaration Excel (SE)**.

   Formatet skrivs ut när du kör rapporten **Rapportera moms för kvittningsperiod**, samt även när du väljer **Skriv ut** på sidan **Momsbetalningar**.

4. På sidan **Skattemyndigheter** väljer du skattemyndighet innan du i fältet **Rapportlayout** väljer **Standard**.

Om du konfigurerar momsdeklarationen i en juridisk person där det finns [flera momsregistreringar](emea-reporting-for-multiple-vat-registrations.md) följer du dessa steg.

1. Gå till **Redovisning** > **Inställningar** > **Redovisningsparametrar**.
2. På fliken **Moms** > snabbfliken **Elektronisk rapportering för länder/regioner** > raden för **SWE** väljer du formatet **Momsdeklaration Excel (SE)**.

### <a name="activate-the-capability-to-add-notes-to-the-vat-declaration-xml-se-report"></a>Aktivera möjligheten att lägga till noteringar i XML-rapporten för momsdeklaration (SE)

1. Gå till **Organisationsadministration** > **Dokumenthantering** > **Aktiva dokumenttabeller**.
2. Lägg till en rad och välj sedan tabellen **Momsbetalningar** i referensrutnätet.
3. Markera kryssrutan i kolumnen **Alltid aktiverad**.

    ![Aktiv dokumenttabell](media/15676877b8e3f578ca461da460bd7d87.png)

## <a name="settle-and-post-sales-tax-and-preview-the-vat-declaration-in-excel"></a>Kvitta och bokför moms och förhandsgranska momsdeklarationen i Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Förhandsgranska momsdeklarationen i Excel från den periodiska uppgiften Rapportera moms för kvittningsperiod

1. Gå till **Moms** > **Periodiska uppgifter** > **Deklarationer** > **Moms** > **Rapportera moms för kvittningsperiod**.
2. Ange följande fält.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Fält</strong></p>
    </td>
    <td>
    <p><strong>Beskrivning</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Kvittningsperiod</p>
    </td>
    <td>
    <p>Välj kvittningsperiod.</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Momsbetalningsversion</p>
    </td>
    <td>
    <p>Välj ett av följande värden:</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Ursprunglig</strong> &ndash; Generera en rapport för momstransaktioner för den ursprungliga momsbetalningen eller innan momsbetalningen genereras.</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Korrigeringar</strong> &ndash; Generera en rapport för momstransaktioner för alla efterföljande momsbetalningar för perioden.</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Summor</strong> &ndash; Generera en rapport för alla momstransaktioner för perioden, inklusive ursprungliga och alla korrigeringar.</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Från-datum</p>
    </td>
    <td>
    <p>Välj startdatum för rapporteringsperioden.</p>
    </td>
    </tr>
    </tbody>
    </table>

3. Välj **OK** och granska Excelrapporten.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Kvitta och bokför moms

1. Gå till **Moms** > **Periodiska uppgifter** > **Deklarationer** > **Moms** > **Kvitto och bokför moms**.
2. Ange följande fält.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Fält</strong></p>
    </td>
    <td>
    <p><strong>Beskrivning</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Kvittningsperiod</p>
    </td>
    <td>
    <p>Välj kvittningsperiod.</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Momsbetalningsversion</p>
    </td>
    <td>
    <p>Välj ett av följande värden:</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Ursprunglig</strong> &ndash; Generera den ursprungliga momsbetalningen för kvittningsperioden.</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Senaste korrigeringar</strong> &ndash; Generera en momsbetalningskorrigering efter det att den ursprungliga momsbetalningen för kvittningsperioden har skapats.</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Från-datum</p>
    </td>
    <td>
    <p>Välj första datum för rapporteringsperioden.</p>
    </td>
    </tr>
    </tbody>
    </table>

3. Välj **OK**.

### <a name="add-notes-to-the-sales-tax-payment"></a>Lägg till noteringar i momsbetalningen

1. Gå till **Moms** > **Förfrågningar och rapporter** > **Momsförfrågningar** > **Momsbetalningar**.
2. Markera raden för momsbetalning och välj sedan knappen **Bilagor** (gem-ikonen) i sidans övre högra hörn.
3. Lägg till en ny notering som ska exporteras till XML-rapporten för momsdeklaration (SE).

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Förhandsgranska momsdeklarationen i Excel från en momsbetalning

1. Gå till **Moms** > **Förfrågningar och rapporter** > **Momsförfrågningar** > **MOmsbetalningar** och välj en rad för momsbetalning.
2. Välj **Skriv ut rapport** och granska den Excel-fil som genereras för den valda momsbetalningsraden.

    > [!NOTE]
    > Rapporten genereras bara för den valda raden i momsbetalningen. Om du till exempel måste generera en korrigeringsdeklaration som innehåller alla korrigeringar för perioden, eller en ersättningsdeklaration som innehåller ursprungliga data och alla korrigeringar, använder du den periodiska uppgiften **Rapportera moms för kvittningsperiod**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generera en momsdeklaration från elektroniska meddelanden

Om du använder elektroniska meddelanden för att generera rapporten kan du generera rapporten i XML-format. Du kan även samla in momsdata från flera juridiska personer. Mer information finns i avsnittet [Kör en momsdeklaration för flera juridiska personer](#run-a-vat-declaration-for-multiple-legal-entities) senare i det här ämnet.

### <a name="set-up-electronic-messages"></a>Konfigurera elektroniska meddelanden

#### <a name="download-and-import-the-data-management-package-that-includes-example-settings-for-electronic-messages"></a>Hämta och importera datahanteringspaketet som innehåller exempelinställningar för elektroniska meddelanden

Datapaketet som innehåller exempelinställningarna innehåller inställningar för elektroniska meddelanden som används för att generera momsdeklarationen för Sverige. Du kan utöka dessa inställningar eller skapa egna. Mer information om hur du arbetar med elektroniska meddelanden och skapar egna inställningar finns i [Elektroniska meddelanden](../general-ledger/electronic-messaging.md).

1. I biblioteket för delade tillgångar i [LCS](https://lcs.dynamics.com/v2) väljer du **Datapaket** som tillgångstyp och laddar sedan ned paketet **SE Momsdeklaration EM**. Den hämtade filen bär namnet **EM Vat Declaration EM package.zip**.
2. I arbetsytan **Datahantering** i Finance väljer du **Importera**.
3. På snabbfliken **Importera**, i fältet **Gruppnamn**, anger du ett namn för jobbet.
4. På snabbfliken **Vald entiteter**, välj **Lägg till fil**.
5. I dialogrutan **Lägg till fil** ser du till att fältet **Källdataformat** anges som **Paket**, väljer **Ladda upp och lägg till** och väljer sedan den zipfil som du tidigare laddade ned.
6. Välj **Nära**.
7. När dataenheterna har förts över väljer du **Importera** i åtgärdsfönstret.
8. Gå till **Moms** > **Förfrågningar och rapporter** > **Elektroniska meddelanden** > **Elektroniska meddelanden** och validerar den meddelandebearbetning som du importerat (**paketet SE Momsdeklaration**).

#### <a name="configure-electronic-messages"></a>Konfigurera elektroniska meddelanden

1. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden** > **Fyll i poståtgärder**.
2. Välj raden **SE Fyll i returposter för moms** och välj sedan **Redigera fråga**.
3. Använd filtret om du vill ange den momskvittningsperiod som ska inkluderas i rapporten.
4. Om du måste rapportera momstransaktioner från andra kvittningsperioder i en annan deklaration ska du skapa en ny åtgärd för **Fyll i poster** och välja lämpliga kvittningsperioder.

### <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generera en momsdeklaration från elektroniska meddelanden

Följande procedur gäller för det exempel på elektronisk meddelandebearbetning som du importerade tidigare från LCS Shared Asset Library (**paketet SE Momsdeklaration EM**).

1. Gå till **Moms** > **Förfrågningar och rapporter** > **Elektroniska meddelanden** > **Elektroniska meddelanden**.
2. I vänster navigeringsfönster väljer du **Momsdeklaration SE**.
3. På snabbfliken **Meddelanden** väljer du **Ny** och sedan, i dialogrutan **Kör bearbetning**, väljer du **OK**.
4. Markera meddelanderaden som skapas, ange en beskrivning och ange sedan start- och slutdatum för deklarationsperioden.

    > [!NOTE] 
    > Steg 5 till 7 är valfria.

5. Valfritt: På snabbfliken **Meddelanden** väljer du **Samla in data** och sedan **OK**. Momsbetalningar som genererats tidigare läggs till i meddelandet. Mer information finns i avsnittet [Kvitta och bokföra moms](#settle-and-post-sales-tax) tidigare i det här ämnet. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Momsdeklarationsversion** i dialogrutan **Parametrar för elektronisk rapport**.
6. Valfritt: På snabbfliken **Meddelandeartiklar** granskar du de momsbetalningar som överförs för bearbetning. Som standard ingår alla momsbetalningar för den valda perioden som inte ingår i något annat meddelande tillhörande samma bearbetning.
7. Valfritt: Välj **Ursprungligt dokument** för att granska momsbetalningarna, eller välj **Ta bort** för att exkludera momsbetalningar från bearbetning. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Momsdeklarationsversion** i dialogrutan **Parametrar för elektronisk rapport**.
8. På snabbfliken **Meddelanden** väljer du **Uppdatera status**.
9. I dialogrutan **Uppdatera status** väljer du åtgärden **Klar att genereras** och sedan **OK**. Kontrollera att meddelandestatusen har ändrats till **Klar att genereras**.
10. Välj **Generera rapport**.
11. För att förhandsgranska momsdeklarationsbeloppen: I dialogrutan **Kör bearbetning** väljer du **Förhandsgranska rapport** och sedan **OK**.
12. I dialogrutan **Parametrar för elektronisk rapportering** anger du följande fält och väljer sedan **OK**.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Fält</strong></p>
    </td>
    <td>
    <p><strong>Beskrivning</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Kvittningsperiod</p>
    </td>
    <td>
    <p>Välj kvittningsperiod.</p>
    <p>Om du valde <strong>Samla in data</strong> i steg 5 kan du ignorera det här fältet. Rapporten genereras för de momstransaktioner som ingår i de inkasserade momsbetalningarna.</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Momsdeklarationsversion</p>
    </td>
    <td>
    <p>Välj ett av följande värden:</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Ursprunglig</strong> &ndash; Generera en rapport för momstransaktioner för den ursprungliga momsbetalningen eller innan momsbetalningen genereras.</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Korrigeringar</strong> &ndash; Generera en rapport för momstransaktioner för alla efterföljande momsbetalningar för perioden.</p>
    <p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Summor</strong> &ndash; Generera en rapport för alla momstransaktioner för perioden, inklusive ursprungliga och alla korrigeringar.</p>
    <p>Om du valde <strong>Samla in data</strong> i steg 5 kan du ignorera det här fältet. Rapporten genereras för de momstransaktioner som ingår i de inkasserade momsbetalningarna.</p>
    </td>
    </tr>
    </tbody>
    </table>

13. Välj knappen **Bilagor** (gem-ikonen) i sidans övre högra hörn, och välj sedan **Öppna** för att öppna Excelfilen. Granska beloppen i Excel-dokumentet.
14. Välj **Generera rapport**.
15. För att generera en rapport i XML-format: I dalogrutan **Kör bearbetning** väljer du **Generera rapport** och sedan **OK**.
16. Välj knappen **Bilagor** (gem-ikon) i sidans övre högra hörn, och ladda sedan ned den elektroniska fil som genererades. Du bör föra över den här filen manuellt till myndighetsportalen.
    
    > [!NOTE]
    > Du kan behöva lägga till följande rad manuellt i den genererade filen innan du överför filen till myndighetsportalen. Det bör vara den andra raden i filen: 
    >
    >  <!DOCTYPE eSKDUpload PUBLIC "-//Skatteverket, Sweden//DTD Skatteverket eSKDUpload-DTD Version 6.0//SV" "https://www1.skatteverket.se/demoeskd/eSKDUpload_6p0.dtd">
    

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Kör en momsdeklaration för flera juridiska personer

Om du vill använda formaten för att rapportera momsdeklarationen för en grupp juridiska personer, måste du först ställa in de programspecifika parametrarna för ER-formaten för försäljnigsmomskoder från alla juridiska personer som krävs.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-multiple-legal-entities"></a>Konfigurera elektroniska meddelanden för insamling av momsdata från flera juridiska personer

Följ dessa steg för att konfigurera elektroniska meddelanden för insamling av data från flera juridiska personer.

1. Gå till **Arbetsytor** > **Funktionshantering**.
2. Sök efter och välj funktionen **Frågor mellan företag för åtgärd för postifyllande** i listan, och välj sedan **Aktivera nu**.
3. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden** > **Fyll i poståtgärder**.
4. På sidan **Åtgärd för postifyllande** väljer du raden **Fyll i momsreturposter SE**.

   I rutnätet **Konfiguration av datakällor** blir ett nytt **Företag**-fält tillgängligt. För befintliga poster visar det här fältet identifieraren för den aktuella juridiska personen.

5. I rutnätet **Konfiguration för datakällor** lägger du till en rad för varje ytterligare juridisk person som måste inkluderas i rapporten. För varje ny rad anger du följande fält:

    | Fält                  | beskrivning                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Namn                   | Ange ett värde som hjälper dig att förstå varifrån den här posten kommer. Ange till exempel **Momsbetalning för dotterbolag 1**. |
    | Meddelandets artikeltyp      | Välj **Momsretur**. Detta värde är det enda värde som är tillgängligt för alla poster.                                    |
    | Kontotyp           | Markera **Alla**.                                                                                                               |
    | Namn på huvudregister      | Ange **TaxReportVoucher** för alla poster.                                                                             |
    | Dokumentnummerfält  | Ange **Verifikation** för alla poster.                                                                                      |
    | Dokumentdatumfält    | Ange **TransDate** för alla poster.                                                                                    |
    | Dokumentkontofält | Ange **TaxPeriod** för alla poster.                                                                                    |
    | Företag                | Välj ID för den juridiska personen.                                                                                            |
    | Användarfråga             | Kryssrutan väljs automatiskt när du definierar kriterier genom att välja **Redigera fråga**.                                  |

6. För varje ny rad väljer du **Redigera sökning** och anger sedan en relaterad kvittningsperiod för den juridiska person som angetts i fältet **Företag** på raden.

   När inställningen har slutförts samlar funktionen **Samla in data** på sidan **Elektroniska meddelanden** in momsbetalningar från samtliga juridiska personer som du har definierat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
