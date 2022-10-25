---
title: Momsdeklaration för (Tyskland)
description: I den här artikeln beskrivs hur du ställer in och genererar en förhandsdeklaration för moms (VAT) för Tyskland i det officiella XML-formatet.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 04c625b554d96f8ed28ceffef9647fe9cbf7fe2f
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689471"
---
# <a name="vat-declaration-germany"></a>Momsdeklaration för (Tyskland)

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in och genererar en förhandsdeklaration för moms (VAT) för Tyskland i det officiella XML-formatet. I den här artikeln beskrivs även hur du förhandsgranskar momsdeklarationen i Microsoft Excel.

Om du vill generera rapporten automatiskt skapar du tillräckligt med momskoder för att hålla en separat momsredovisning för respektive ruta i förhandsdeklarationen för moms. I de programspecifika parametrarna för det elektroniska rapporteringsformatet (ER) för förhandsdeklarationen för moms måste du dessutom koppla momskoder till sökresultatet för rutorna i momsdeklarationen.

För Tyskland måste du konfigurera **Sökning i rapportfält**. Mer information om hur du konfigurerar programspecifika parametrar finns i avsnittet [Ställa in programspecifika parametrar för momsdeklarationsfält](#set-up-application-specific-parameters-for-vat-declaration-fields) längre fram i den här artikeln.

I följande tabell visar kolumnen Sökresultat det sökresultat som är förkonfigurerat för en viss momsdeklarationsrad i momsdeklarationsformatet. Använd den här informationen för att korrekt koppla momskoder till sökresultatet och sedan till raden i momsdeklarationen.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Momsdeklaration – översikt

Förhandsdeklaration för moms i Tyskland innehåller följande information:

**AVSNITT – LEVERANSER OCH ANDRA TJÄNSTER**

**Skattepliktig försäljning**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                                                                                                                      | Sökningsresultat                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Utan kod     | Momspliktig försäljning med en momssats på 19 procent.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – med minustecken             |
| 21  | 86             | Utan kod     | Momspliktig försäljning med en momssats på 7 procent.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) – med minustecken               |
| 22  | 35             | 36               | Momspliktig försäljning till andra momssatser.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) – med minustecken      |
| 23  | 77             | *Inget momsbelopp*  | Leveranser från företag som ingår i verksamheten och som fungerar som det ska i enlighet med 24 i den tyska momsslagen (UStG) till kunder som har ett moms-ID-nummer. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – med minustecken |
| 24  | 76             | 80               | Försäljning som moms måste betalas för, enligt §24 i UStG (sågverksprodukter, drycker och alkoholhaltiga vätskor).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Momsbefriad försäljning med ingående momsavdrag**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                                                       | Sökningsresultat                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Inget momsbelopp*  | Inomeuropeiska leveranser till kunder som har ett moms-ID.                       | 26-EUSales                          |
| 27  | 44             | *Inget momsbelopp*  | Inomeuropeiska leveranser av nya fordon till inköpare som inte har ett moms-ID.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Inget momsbelopp*  | Inomeuropeiska leveranser av nya fordon utanför ett företag.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Inget momsbelopp*  | Annan skattefri försäljning som har ett avdrag för ingående moms, t.ex. exportleveranser. | 29-ExportOtherTaxFreeSales          |

**Momsbefriad försäljning utan ingående momsavdrag**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                            | Sökningsresultat                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Inget momsbelopp*  | Skattefri försäljning som inte har ett avdrag för ingående moms. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Inomeuropeiska anskaffningar**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                                                                                                   | Sökningsresultat                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Inget momsbelopp*  | Skattefria inomeuropeiska anskaffningar av vissa objekt och investeringsguld.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Utan kod     | Momspliktiga inomeuropeiska anskaffningar med en momssats på 19 procent.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Utan kod     | Momspliktiga inomeuropeiska anskaffningar med en momssats på 7 procent.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Momspliktiga inomeuropeiska anskaffningar med andra momssatser.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Momspliktiga inomeuropeiska anskaffningar av nya fordon från leverantörer som inte har något moms-ID-nummer till den allmänna momssatsen. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**AVSNITT – MOTTAGARE SOM GÄLDENÄR FÖR SKATTESKULDEN**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                                                        | Sökningsresultat                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Andra tjänster för en privat tjänst, baserade på resten av communityområdet.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Försäljning som faller under avsnitt 13b (2) nr. 3 av UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Andra tjänster som faller under avsnitt 13b (2) nr. 1, 2 och 4 till 12 i UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**AVSNITT – KOMPLETTERANDE INFORMATION OM FÖRSÄLJNING**

| Rad | Ruta – momsbas  | Ruta – momsbelopp | Beskrivning                                                                                                | Sökningsresultat                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Inget momsbelopp*  | Leveranser av den första kunden vid inomeuropeiska trepartstransaktioner.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Inget momsbelopp*  | Momspliktig försäljning av att utföra en skatteskuld som tjänstemottagaren är skyldig skatt för. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Inget momsbelopp*  | Andra icke beskattningsbara tjänster.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Inget momsbelopp*  | Annan icke beskattningsbara försäljning när prestationsstället inte finns i Tyskland.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Inget momsbelopp* | *Inget momsbelopp*  | Moms.                                                                                                       | Rad 20 + Rad 21 + Rad 22 + Rad 24 + Rad 34 + Rad 35 + Rad 36 + Rad 37 + Rad 40 + Rad 41 + Rad 42 |

**AVSNITT – AVDRAGSGILL INGÅENDE MOMS**

| Rad | Ruta – momsbelopp | Beskrivning                                                                                                | Sökningsresultat                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Ange ingående momsbelopp för faktura från andra företag, tjänster och inomeuropeiska trepartstransaktioner.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – med minustecken                                                                   |
| 56  | 61               | Ingående momsbelopp från inomeuropeisk anskaffning av varor.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Importmoms som uppstått                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Ingående momsbelopp från tjänster enligt §13b i UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Ingående momsbelopp som beräknas enligt allmänna genomsnittssatser.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – med minustecken                                                                                    |
| 60  | 59               | Ingående momsavdrag för inomeuropeiska leveranser av nya fordon utanför ett företag och små företag. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – med minustecken                                                                  |
| 61  | 64               | Korrigering av inkommande momsavdrag.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | Resterande belopp.                                                                                      | Rad 52 – Rad 55 – Rad 56 – Rad 57 – Rad 58 – Rad 50 – Rad 60 – Rad 61                                                                                                        |

**AVSNITT – ANDRA MOMSBELOPP**

| Rad | Ruta – momsbelopp | Beskrivning                                                                                                                                                                                                                                                         | Sökningsresultat                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Moms på grund av en förändring i beskattningsformen och ytterligare moms på beskattad handpenning på grund av förändringar av momssatsen.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Felaktiga eller ej motiverade momsbelopp som framgår av fakturor och momsbelopp som är skyldiga att betalas enligt avsnitt 6a (4), mening 2, avsnitt 17 (1), mening 7 eller sektion 25b (2) i UStG, eller som är skyldig av ett entreprenadföretag eller lagerställeansvarig. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Avdrag av den fasta särskilda förskottsbetalningen för permanent tillägg. Vanligtvis fylls den här raden bara i med det sista förskottsmeddelandet om momsperioden.                                                                                                  | Parametern för användarindata i rapportdialogrutan |
| 68  | 83               | Återstående förskottsskattebetalning och återstående överstigande moms. Inkludera ett minustecken framför beloppet.                                                                                                                                                          | Rad 62 + Rad 64 – Rad 65 – Rad 66             |

**AVSNITT – KOMPLETTERANDE INFORMATION OM REDUCERING**

| Rad | Ruta – momsbas | Ruta – momsbelopp | Beskrivning                                                            | Sökningsresultat                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Reducering av skattebasen på raderna 20 till 24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Reducering av de avdragsgilla ingående momsbeloppen på raderna 55, 59 och 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>Återfört tillägg för inköp

Om du konfigurerar momskoder i syfte att bokföra inkommande återförda tillägg med hjälp av importavgift ska du associera dina momskoder med det sökresultat för använd moms, ska du koppla momskoderna till det sökresultat i **Sökning i rapportfält** som innehåller "UseTax" i namnet.

Alternativt kan du konfigurera två separata momskoder: en för förfallen moms och en för momsavdrag. Koppla sedan varje kod till motsvarande sökresultat för **Sökning i rapportfält**.

För momspliktiga inomeuropeiska anskaffningar till en standardsats konfigurerar du exempelvis momskod **UT_S_EU** med importavgift och associerar den med sökresultatet **34-UseTaxEUPurchaseStandard** för **Sökning i rapportfält**. I det här fallet återspeglas belopp som använder momskoden **UT_S_EU** i rutorna 089 och 061 (rader 34 och 56).

Alternativt kan du konfigurera två momskoder:

  - **VAT_S_EU**, som har ett momssatsvärde på -19 procent
  - **InVAT_S_EU**, som har ett momssatsvärde på 19 procent

Därefter associerar du koderna med sökresultaten i **Sökning i rapportfält** på följande sätt:

  - Associera **VAT_S_EU** med sökresultatet **34-EUPurchaseStandard**.
  - Associera **InVAT_S_EU** med sökresultatet **56-InputTaxEUPurchase**.

I det här fallet återspeglas belopp som använder momskoden **VAT_S_EU** i rutan 089 (rad 34). Belopp som använder momskoden **InVAT_S_EU** visas i rutan 061 (rad 56).

Mer information om hur du konfigurerar återfört tillägg finns i [Omvänd moms](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Konfigurera systemparametrar

Om du vill generera en momsdeklaration måste du konfigurera företagets momsnummer (Steuernummer).

1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
2. Välj den juridiska personen och välj sedan **Registrerings-ID**.
3. Välj eller skapa adressen i Tyskland och på snabbfliken **Registrerings-ID**, välj **Lägg till**.
4. På fältet **registreringstyp**, välj den registreringstyp som är dedikerad till Tyskland och som använder registreringskategorin **Företags-ID (COID)**.
5. I fältet **Registreringsnummer** anger du momsnummer.
6. På fliken **Allmänt**, i fältet **Giltighet** anger du det datum då numret börjar gälla.

För mer information om hur du ställer in registreringskategorier och registreringstyper, se [Registrerings-ID](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Skapa en momsdeklaration för Tyskland

### <a name="import-er-configurations"></a>Importera ER-konfigurationer

Öppna arbetsytan **Elektronisk rapportering** och importera följande versioner eller en senare version av dessa ER-format:

   - Momsdeklaration Excel (DE).version.101.16.12.xml
   - Momsdeklaration XML (DE).version.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Konfigurera programspecifika parametrar för momsdeklarationsfält

Om du vill generera en momsdeklaration automatiskt, associerar du momskoder i programmet och sökningsresultaten i ER-konfigurationen.

> [!NOTE]
> Vi rekommenderar att du aktiverar funktionen genom att **Använd appspecifika parametrar från tidigare versioner av ER-format** i arbetsytan **Funktionshantering**. När den här funktionen är aktiverad blir parametrar som är konfigurerade för den tidigare versionen av ett ER-format automatiskt tillämpliga för den senare versionen av samma format. Om den här funktionen inte är aktiverad måste du konfigurera programspecifika parametrar explicit för varje formatversion. Funktionen **Använd appspecifika parametrar från tidigare versioner av ER-format** är tillgänglig i arbetsytan **Funktionshantering** med början i Finance version 10.0.23. Mer information om hur du ställer in parametrarna för ett ER-format för varje juridisk person finns i [Ställa in parametrarna för ett ER-format per juridisk enhet](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Följ dessa steg för att definiera vilka momskoder som genererar vilka rutor i momsdeklarationen.

1. Gå till **Arbetsytor** > **Elektronisk rapportering** och välj **Rapporteringskonfiguration**.
2. Välj konfigurationen **Momsdeklaration XML (DE)** och välj sedan **Konfigurationer \> Programspecifika parameterinställningar**.
3. På sidan **Programspecifika parametrar** på snabbfliken **Uppslag**, välj **Rapportera fältuppslag**.
4. På snabbfliken **Villkor** ställer du in följande fält för att koppla momskoderna och rapportfälten.

    | Fält                  | Beskrivning                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Sökningsresultat          | Välj värdet i rapportfältet. Mer information om värdena och deras tilldelning till momsdeklarationsrader finns i [översiktsavsnittet för momsdeklarationen](#vat-declaration-overview) tidigare i den här artikeln.                                                                                               |
    | Momskod               | Välj den momskod som ska associeras med rapportfältet. Bokförda momstransaktioner med den valda momskoden samlas in i rätt deklarationsruta. Vi rekommenderar att du separerar momskoder på ett sådant sätt att en momskod bara genererar belopp i en deklarationsruta. |
    | Transaktionsklassificerare | Om du har skapat tillräckligt med momskoder för att bestämma en deklarationsruta väljer du **\*Inte tom\***. Om du inte skapat tillräckligt med momskoder så att en momskod bara genererar belopp i en deklarationsruta kan du ställa in en transaktionsklassificerare. Följande transaktionsklassifierare är tillgängliga:</br>-   **Inköp**</br>-   **PurchaseExempt** (momsbefriat inköp)</br>-   **PurchaseReverseCharge** (momsfordran från inköpsåterköpstillägg)</br>-   **Försäljning**</br>-   **SalesExempt** (momsbefriad försäljning)</br>-   **SalesReverseCharge** (skatt som ska betalas från en omvänd skattskyldighet eller en omvänd skattskyldighet)</br>-   **Importavgift**. </br>För varje transaktionsklassificerare finns det också en klassificerare för kreditfakturan. En av dessa klassificerare är till exempel **PurchaseCreditNote** (inköpskreditfaktura).</br>Se till att skapa två rader för varje momskod: en som har transaktionsklassens värde och en som har transaktionsklassen för kreditfakturavärde. |

    > [!NOTE]
    > Associera alla momskoder till sökresultaten. Om momskoder inte ska generera värden i momsdeklarationen associerar du dem med sökresultatet **Övrigt**.

    ![Sidan programspecifika parametrar](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. I fältet **tillstånd** ändra värdet från **slutförd**.
6. I åtgärdsfönstret, välj **Exportera** för att exportera inställningarna för de applikationsspecifika parametrarna.
7. Välj konfigurationen **Momsdeklaration Excel (DE)** och sedan på åtgärdsfönstret, välj **Importera** för att importera parametrarna du har konfigurerat för **Momsdeklaration XML (DE)**.
8. I fältet **Stat**, välj **Slutförd**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Ställa in momsrapporteringsformat för förhandsgranskning av belopp i Excel

1. I arbetsytan **Funktionshantering** söker du och aktiverar funktionen **Formatrapporter för momsutdrag**.
2. Gå till **Redovisning** > **Inställningar** > **Redovisningsparametrar**.
3. På fliken **Moms** på snabbfliken **Alternativ för skatt** i fältet **Formatmappning för momsutdrag**, välj **Momsdeklaration Excel (DE)**.

   Det här formatet skrivs ut när du kör rapporten **Rapportera moms för kvittningsperiod**. Den skrivs också ut när du väljer **Skriv ut** på sidan **Momsbetalningar**.

4. Om du måste rapportera korrigeringarna, på **Särskild rapport** ange **Inkludera korrigeringar** till **Ja**.
5. På sidan **Skattemyndigheter** väljer du skattemyndighet innan du i fältet **Rapportlayout** väljer **Standard**.

Om du konfigurerar momsdeklarationen i en juridisk person där det finns [flera momsregistreringar](emea-reporting-for-multiple-vat-registrations.md) följer du dessa steg.

1. Gå till **Redovisning** > **Inställningar** > **Redovisningsparametrar**.
2. På fliken **Moms** > snabbfliken **Elektronisk rapportering för länder/regioner** > raden för **DEU** väljer du formatet **Momsdeklaration Excel (DE)**.

## <a name="set-up-electronic-messages"></a>Konfigurera elektroniska meddelanden

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Hämta och importera datapaketet som har exempelinställningar för elektroniska meddelanden

Datapaketet innehåller inställningar för elektroniska meddelanden som används för att generera momsdeklarationen i XML-format och sedan kan du förhandsgranska den i Excel. Du kan utöka dessa inställningar eller skapa egna. Mer information om hur du arbetar med elektroniska meddelanden och skapar egna inställningar finns i [Elektroniska meddelanden](../general-ledger/electronic-messaging.md).

1. I biblioteket för delade tillgångar i [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), välj **Datapaket** som tillgångstyp och laddar sedan ned paketet **DE momsdeklaration EM-paket**. Den hämtade filen bär namnet **DE VAT declaration EM package.zip**.
2. I Dynamics 365 Finance i arbetsytan **Datahantering** väljer du **Importera**.
3. På snabbfliken **Importera**, i fältet **Gruppnamn**, anger du ett namn för jobbet.
4. På snabbfliken **Vald entiteter**, välj **Lägg till fil**.
5. I dialogrutan **Lägg till fil** ser du till att fältet **Källdataformat** anges som **Paket**, väljer **Ladda upp och lägg till** och väljer sedan den zipfil som du tidigare laddade ned.
6. Välj **Nära**.
7. När dataenheterna har förts över väljer du **Importera** i åtgärdsfönstret.
8. Gå till **Moms** > **Förfrågningar och rapporter** > **Elektroniska meddelanden** > **Elektroniska meddelanden** och validerar den meddelandebearbetning som du importerat.

### <a name="configure-electronic-messages"></a>Konfigurera elektroniska meddelanden

1. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden** > **Fyll i poståtgärder**.
2. Välj raden för **DE Fyll i returposter för moms** och välj sedan **Redigera fråga**.
3. Använd filtret om du vill ange den kvittningsperiod som ska inkluderas i rapporten.
4. Om du måste rapportera momstransaktioner från andra kvittningsperioder i en annan deklaration ska du skapa en ny åtgärd för **Fyll i poster** och välja lämpliga kvittningsperioder.

## <a name="preview-the-vat-declaration-in-excel"></a>Förhandsgranska momsdeklarationen i Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Förhandsgranska momsdeklarationen i Excel från den periodiska uppgiften Rapportera moms för kvittningsperiod

1. Gå till **Moms** > **Periodiska uppgifter** > **Deklarationer** > **Moms** > **Rapportera moms för kvittningsperiod**.
2. Välj ett värde i fältet **Kvittningsperiod**.
3. I fältet **Momsbetalningsversion**, välj ett att följande värden:

    - **Ursprunglig**: Generera en rapport för momstransaktioner för den ursprungliga momsbetalningen eller innan momsbetalningen genereras.
    - **Korrigeringar**: Generera en rapport för momstransaktioner för alla efterföljande momsbetalningar för perioden.
    - **Summor**: Generera en rapport för alla momstransaktioner för perioden, inklusive ursprungliga och alla korrigeringar.

4. Välj startdatum för rapporteringsperioden i fältet **Från datum**.
5. Välj **OK** och granska Excelrapporten.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Kvitta och bokför moms

1. Gå till **Moms** > **Periodiska uppgifter** > **Deklarationer** > **Moms** > **Kvitto och bokför moms**.
2. Välj ett värde i fältet **Kvittningsperiod**.
3. I fältet **Momsbetalningsversion**, välj ett att följande värden:

    - **Ursprunglig**: Generera den ursprungliga momsbetalningen för kvittningsperioden.
    - **Senaste korrigeringar**: Generera en momsbetalningskorrigering efter det att den ursprungliga momsbetalningen för kvittningsperioden har skapats.

4. Välj startdatum för rapporteringsperioden i fältet **Från datum**.
5. Välj **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Förhandsgranska momsdeklarationen i Excel från en momsbetalning

1. Gå till **Moms** > **Förfrågningar och rapporter** > **Momsförfrågningar** > **MOmsbetalningar** och välj en rad för momsbetalning.
2. Välj **Skriv ut rapport** och klicka sedan på **OK**.
3. Granska Excel-fil som genereras för den valda momsbetalningsraden.

    > [!NOTE]
    > Rapporten genereras bara för den valda raden i momsbetalningen. Om du till exempel måste generera en korrigeringsdeklaration som innehåller alla korrigeringar för perioden, eller en ersättningsdeklaration som innehåller ursprungliga data och alla korrigeringar, använder du den periodiska uppgiften **Rapportera moms för kvittningsperiod**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generera en momsdeklaration från elektroniska meddelanden

När du använder elektroniska meddelanden när du genererar rapporten kan du samla in momsdata från flera juridiska personer. Mer information finns i avsnittet [Kör en momsdeklaration för flera juridiska personer](#run-a-vat-declaration-for-multiple-legal-entities) senare i det här ämnet.

Följande procedur gäller för det exempel på elektronisk meddelandebearbetning som du importerade tidigare från LCS Shared Asset Library.

1. Gå till **Moms** > **Förfrågningar och rapporter** > **Elektroniska meddelanden** > **Elektroniska meddelanden**.
2. I vänster navigeringsfönster väljer du **Momsdeklaration DE**.
3. På snabbfliken **Meddelanden** väljer du **Ny** och sedan, i dialogrutan **Kör bearbetning**, väljer du **OK**.
4. Markera meddelanderaden som skapas, ange en beskrivning och ange sedan start- och slutdatum för deklarationen.

    > [!NOTE]
    > Steg 5 till 7 är valfria.

5. Valfritt: På snabbfliken **Meddelanden** väljer du **Samla in data** och sedan **OK**. Momsbetalningar som genererats tidigare läggs till i meddelandet. Mer information finns i avsnittet [Kvitta och bokföra moms](#settle-and-post-sales-tax) tidigare i det här ämnet. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Deklaration** i dialogrutan **Parametrar för elektronisk rapport**.
6. Valfritt: På snabbfliken **Meddelandeartiklar** granskar du de momsbetalningar som överförs för bearbetning. Som standard ingår alla momsbetalningar för den valda perioden som inte ingår i något annat meddelande tillhörande samma bearbetning.
7. Valfritt: Välj **Ursprungligt dokument** för att granska momsbetalningarna, eller välj **Ta bort** för att exkludera momsbetalningar från bearbetning. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Deklaration** i dialogrutan **Parametrar för elektronisk rapport**.
8. På snabbfliken **Meddelanden** väljer du **Uppdatera status**. I dialogrutan **Uppdatera status** väljer du **Klar att genereras** och sedan **OK**. Kontrollera att meddelandestatusen har ändrats till **Klar att genereras**.
9. Välj **Generera rapport**. För att förhandsgranska momsdeklarationsbeloppen: I dialogrutan **Kör bearbetning** väljer du **Förhandsgranska rapport** och sedan **OK**.
10. I dialogrutan **Parametrar för elektronisk rapportering** anger du följande fält och väljer sedan **OK**.

    | **Fält**                                   | **Beskrivning**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Kvittningsperiod                           | Välj kvittningsperiod. Om du valde **Samla in data** i steg 5 kan du lämna det här fältet tomt. Rapporten genereras för de momstransaktioner som ingår i de inkasserade momsbetalningarna. |
    | Momsdeklarationsversion                     | Välj ett av följande värden:</br>-   **Ursprunglig** – Generera en rapport för momstransaktioner för den ursprungliga momsbetalningen eller innan momsbetalningen genereras.</br>-   **Korrigeringar** – Generera en rapport för momstransaktioner för alla efterföljande momsbetalningar för perioden.</br>-   **Summor** – Generera en rapport för alla momstransaktioner för perioden, inklusive ursprungliga och alla korrigeringar.|
    | Momsrepresentant | Välj den part som ska vara momsrepresentant för momsdeklarationen, om det är tillämpligt. Information om den valda parten exporteras till **DatenLieferant** XML-element. |
    | Kontaktperson | Välj en person i organisationen som är dataleverantör. Information om den valda personen exporteras till **DatenLieferant** XML-element. |
    | Rättelseretur | Välj **Ja** om det här är en korrigeringsmomsdeklaration. I det här fallet har XML-elementet KZ10 värdet **1**.|
    | Kompletterande dokument | Välj **Ja** om du även skickar verifikationer. I det här fallet har XML-elementet KZ22 värdet **1**.|
    | Fullmakt för SEPA-autogiro återkallas som ett undantag| Välj **Ja** om SEPA-direktdebiterings mandatet återkallas som ett undantag för denna förregistreringsperiod. Till exempel på grund av motinställning av begäranden. Eventuellt resterande saldo ska betalas separat. I det här fallet har XML-elementet KZ26 värdet **1**. |
    | Motbetalning av det återbetalningsbelopp som önskas | Välj **Ja** om motinställning av återbetalningsbeloppet önskat eller om återbetalningsbeloppet har tilldelats. I det här fallet har XML-elementet KZ29 värdet **1**. |
    | Särskild förskottsbetalning – permanent tillägg | Efter avdragbeloppet av den fasta särskilda förskottsbetalningen för permanent tillägg. Detta avdragsbelopp slutförs vanligtvis endast i den sista förregistreringen av momsperioden. Beloppet exporteras på rad 67 (ruta 39) och XML-elementet KZ39 i momsdeklarationen. |

11. Markera **Bilagor** i det övre högra hörnet på sidan och välj **Öppna**.
12. Granska beloppen i Excel-dokumentet och välj sedan **Generera rapport**.
13. För att generera en momsdeklaration i XML-format: I dalogrutan **Kör bearbetning** väljer du **Generera rapport** och sedan **OK**.
14. I dialogrutan **Parametrar för elektronisk rapportering** anger du fälten som beskrivs i steg 10.
15. Välj **Bilagor** i sidans övre högra hör, ladda ned filen och använd den när du skickar in till skattemyndigheten.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Kör en momsdeklaration för flera juridiska personer

Om du vill använda formaten för att rapportera momsdeklarationen för en grupp juridiska personer, måste du först ställa in de programspecifika parametrarna för ER-formaten för försäljnigsmomskoder från alla juridiska personer som krävs.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Konfigurera elektroniska meddelanden för insamling av momsdata från flera juridiska personer

Följ dessa steg för att konfigurera elektroniska meddelanden för insamling av data från flera juridiska personer.

1. Gå till **Arbetsytor** > **Funktionshantering**.
2. Sök efter och välj funktionen **Frågor mellan företag för åtgärd för postifyllande** i listan, och välj sedan **Aktivera nu**.
3. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden \> Fyll i poståtgärder**.
4. På sidan **Åtgärd för postifyllande** väljer du raden **Fyll i momsreturposter DE**.

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
    | Användarfråga             | Kryssrutan väljs automatiskt när du definierar kriterier genom att välja **Redigera fråga**.                                 |

6. För varje ny rad väljer du **Redigera sökning** och anger sedan en relaterad kvittningsperiod för den juridiska person som angetts i fältet **Företag** på raden.

När inställningen har slutförts samlar funktionen **Samla in data** på sidan **Elektroniska meddelanden** in momsbetalningar från samtliga juridiska personer som du har definierat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
