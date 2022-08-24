---
title: Momsdeklaration (Danmark)
description: I denna artikel beskrivs hur du konfigurerar in och genererar en momsförskottsdeklaration för Danmark.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: a47b2b98d86daf50876c783f879362ec1addb579
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272153"
---
# <a name="vat-declaration-denmark"></a>Momsdeklaration (Danmark)

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar momsförskottsdeklarationen för Danmark och förhandsvisar den i Microsoft Excel.

Om du vill generera rapporten automatiskt måste du först skapa tillräckligt med momskoder för att hålla en separat momsredovisning för respektive ruta i momsförskottsdeklarationen. I de programspecifika parametrarna för det elektroniska rapporteringsformatet (ER) för förhandsdeklarationen för moms måste du dessutom koppla momskoder till sökresultatet för rutorna i momsdeklarationen.

För Danmark måste du konfigurera **Sökning i rapportfält**. Mer information om hur du konfigurerar programspecifika parametrar finns i avsnittet [Ställa in programspecifika parametrar för momsdeklarationsfält](#set-up-application-specific-parameters) längre fram i den här artikeln.

I följande tabell visar kolumnen Sökresultat det sökresultat som är förkonfigurerat för en viss momsdeklarationsrad i momsdeklarationsformatet. Använd den här informationen för att korrekt koppla momskoder till sökresultatet och sedan till raden i momsdeklarationen.

### <a name="vat-declaration-overview"></a>Momsdeklaration – översikt

Momsdeklarationen i Danmark innehåller följande information:

**Utgående VAT**

| Beskrivning                                                  | Momsbas/Momsbelopp | Sökningsresultat/Summa                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utgående moms                                                   | Skattebelopp          | **OutputVAT**</br> **DomesticVATUseTax** (även rapporterat i rutan "Ingående moms" )                                                                                                                                                                                                                                                                       |
| Moms på varor osv. Inköpt utomlands                           | Skattebelopp          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (även rapporterat i rutan "Ingående moms" )</br>**PurchaseGoodsEU** (momsbasen rapporteras i "Ruta A - anskaffning av varor.")</br>**PurchaseGoodsEUUseTax** (momsbeloppet även rapporterat i rutan "Ingående moms". Momsbasen rapporteras i "Ruta A - anskaffning av varor.")                   |
| Moms på tjänster köpta utomlands som omfattas av återfört tillägg | Skattebelopp          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (även rapporterat i rutan "Ingående moms" )</br>**PurchaseServicesEU** (Momsbasen rapporteras i "Ruta A - anskaffning av tjänster.")</br>**PurchaseServicesEUUseTax** (momsbeloppet även rapporterat i rutan "Ingående moms". Momsbasen rapporteras i "Ruta A - anskaffning av tjänster.") |
| Summa skulder                                                | Skattebelopp          | Summan av föregående tre rutor                                                                                                                                                                                                                                                                                                            |

**Avdrag**

| Beskrivning                                                                               | Momsbas/Momsbelopp | Sökningsresultat/Summa                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ingående moms                                                                                 | Skattebelopp          | **InputVAT**</br> **DomesticVATUseTax** (även rapporterat i rutan "Utgående moms" )</br>**PurchaseGoodsAbroadUseTax** (även rapporterat i rutan "Moms på varor osv. inköpta utomlands")</br>**PurchaseServicesAbroadUseTax** (rapporteras även i rutan "Moms på tjänster som köpts in utomlands och där omvänd moms gäller")</br>**PurchaseGoodsEUUseTax** (även rapporterat i rutan "Moms på varor osv. inköpta utomlands")</br> **PurchaseServicesEUUseTax** (rapporteras även i rutan "Moms på tjänster som köpts in utomlands och där omvänd moms gäller") |
| Skatt på olja och gastuber                                                                  | Skattebelopp          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Skatt på naturgas och stadsgas                                                             | Skattebelopp          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Kolskatt                                                                               | Skattebelopp          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Skattebelopp          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Vattenavgift                                                                              | Skattebelopp          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Totala avdrag                                                                          | Skattebelopp          | Summan av föregående sex rutor                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Totalt belopp för skatter (positivt belopp = betalas, negativt belopp = återbetalas) | Skattebelopp          | "Summa skuld" – "Summa avdrag"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Tilläggsinformation**

| Beskrivning                                                                                                                                                                                                                                | Momsbas/Momsbelopp | Sökningsresultat/Summa                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Ruta A - anskaffning av varor. Värdet utan moms för anskaffning av varor inom fackförening.                                                                                                                                                   | Momsbas            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Ruta A - anskaffning av tjänster. Värdet utan moms för anskaffning av tjänster inom fackförening.                                                                                                                                             | Momsbas            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Ruta B - varuleveranser - ska rapporteras till "EU-försäljning utan moms"/DK VIES. Värdet utan moms för leverans av varor inom fackförening                                                                                                           | Momsbas            | **SalesGoodsEU**                                |
| Ruta B - leveranser - ska inte rapporteras till "EU-försäljning utan moms"/DK VIES. Värdet utan moms för vissa fackföreningsinterna leveranser, t.ex. installation, montering, körsträcka, distansförsäljning och nya transportmedel för icke-momspliktiga personer. | Momsbas            | **SalesInstallationAssemblyEtcEU**              |
| Ruta B - Tillhandahållande av tjänster. Värdet utan moms för tjänster inom EU som inköparen är skyldig att betala momsen för i form av omvänd moms måste också rapporteras till "EU-försäljning utan moms"/DK VIES.                          | Momsbas            | **SalesServicesEU**                             |
| Ruta C - övriga leveranser. Värdet på leverans av andra varor och tjänster som tillhandahålls utan moms inom Danmarks gränser, till andra medlemsstater i EU samt till tredje land eller tredje territorier.                                     | Momsbas            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>Återfört tillägg för inköp

Om du konfigurerar momskoder i syfte att bokföra inkommande återförda tillägg med hjälp av importavgift ska du associera dina momskoder med det sökresultat för använd moms, ska du koppla momskoderna till det sökresultat i **Sökning i rapportfält** som innehåller "UseTax" i namnet.

Alternativt kan du konfigurera två separata momskoder: en för förfallen moms och en för momsavdrag. Koppla sedan varje kod till motsvarande sökresultat för **Sökning i rapportfält**.

För momspliktiga inomeuropeiska anskaffningar konfigurerar du exempelvis momskod **UT_S_EU** med importavgift och associerar den med sökresultatet **PurchaseGoodsEUUseTax** för **Sökning i rapportfält**. I det här fallet återspeglas momsbelopp som använder momskoden **UT_S_EU** i rutorna "Moms på varor osv. inköpta utomlands" och "Ingående moms". Momsbasen reflekteras i "Ruta A - anskaffning av varor."

Alternativt kan du konfigurera två momskoder:

- **VAT_S_EU**, som har ett momssatsvärde på -25 procent
- **InVAT_S_EU**, som har ett momssatsvärde på 25 procent

Därefter associerar du koderna med sökresultaten i **Sökning i rapportfält** på följande sätt:

- Associera **VAT_S_EU** med sökresultatet **PurchaseGoodsEU**.
- Associera **InVAT_S_EU** med sökresultatet **InputVAT**.

I det här fallet återspeglas momsbelopp som använder momskoden **VAT_S_EU** i rutorna "Moms på varor osv. inköpta utomlands" och "Ruta A - anskaffning av varor". Belopp som använder momskoden **InVAT_S_EU** återspeglas i rutan "Ingående moms".

Mer information om hur du konfigurerar återfört tillägg finns i [Omvänd moms](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Konfigurera systemparametrar

Om du vill skapa en momsdeklaration måste du konfigurera momsnumret.

1. Gå till **Organisationsadministration** > **Organisationer** > **Juridiska personer**.
2. Välj den juridiska personen och välj sedan **Registrerings-ID**.
3. Välj eller skapa adressen i Danmark innan du på snabbfliken **Registrerings-ID** väljer **Lägg till**.
4. I fältet **Registreringstyp** väljer du den registreringstyp som är särskilt avsedd för Danmark och som använder registreringskategorin **Moms-ID**.
5. I fältet **Registreringsnummer** anger du momsnummer.
6. På fliken **Allmänt**, i fältet **Giltighet** anger du det datum då numret börjar gälla.

För mer information om hur du ställer in registreringskategorier och registreringstyper, se [Registrerings-ID](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Skapa en förhandsversion för momsdeklaration för Danmark

### <a name="import-er-configurations"></a>Importera ER-konfigurationer

Öppna arbetsytan **Elektronisk rapportering** och importera ER-formatet **Excel för momsdeklaration (DK)**.

Mer information finns i [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Konfigurera programspecifika parametrar för momsdeklarationsfält

> [!NOTE]
> Vi rekommenderar att du aktiverar funktionen genom att **Använd appspecifika parametrar från tidigare versioner av ER-format** i arbetsytan **Funktionshantering**. När den här funktionen är aktiverad blir parametrar som är konfigurerade för den tidigare versionen av ett ER-format automatiskt tillämpliga för den senare versionen av samma format. Om den här funktionen inte är aktiverad måste du konfigurera programspecifika parametrar explicit för varje formatversion. Funktionen **Använd appspecifika parametrar från tidigare versioner av ER-format** är tillgänglig i arbetsytan **Funktionshantering** med början i Finance version 10.0.23. Mer information om hur du ställer in parametrarna för ett ER-format för varje juridisk person finns i [Ställa in parametrarna för ett ER-format per juridisk enhet](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Om du vill generera en momsdeklaration automatiskt, associerar du momskoder i programmet och sökningsresultaten i ER-konfigurationen.

Följ dessa steg för att definiera vilka momskoder som genererar vilka rutor i momsdeklarationen.

1. Gå till **Arbetsytor** > **Elektronisk rapportering** och välj **Rapporteringskonfiguration**.
2. Välj konfigurationen för **Excel för momsdeklaration (DK)** och sedan **Konfigurationer \> Programspecifik parameterkonfiguration**.
3. På sidan **Programspecifika parametrar** på snabbfliken **Uppslag**, välj **Rapportera fältuppslag**.
4. På snabbfliken **Villkor** ställer du in följande fält för att koppla momskoderna och rapportfälten.

    | Fält                  | Beskrivning                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Sökningsresultat          | Välj värdet i rapportfältet. Mer information om värdena och deras tilldelning till momsdeklarationsrader finns i [översiktsavsnittet för momsdeklarationen](#vat-declaration-overview) tidigare i den här artikeln.                                                                                               |
    | Momskod               | Välj den momskod som ska associeras med rapportfältet. Bokförda momstransaktioner med den valda momskoden samlas in i rätt deklarationsruta. Vi rekommenderar att du separerar momskoder på ett sådant sätt att en momskod bara genererar belopp i en deklarationsruta. |
    | Transaktionsklassificerare | Om du har skapat tillräckligt med momskoder för att bestämma en deklarationsruta väljer du **\*Inte tom\***. Om du inte skapat tillräckligt med momskoder så att en momskod bara genererar belopp i en deklarationsruta kan du ställa in en transaktionsklassificerare. Följande transaktionsklassifierare är tillgängliga:</br>-   **Inköp**</br>-   **PurchaseExempt** (momsbefriat inköp)</br>-   **PurchaseReverseCharge** (momsfordran från inköpsåterköpstillägg)</br>-   **Försäljning**</br>-   **SalesExempt** (momsbefriad försäljning)</br>-   **SalesReverseCharge** (skatt som ska betalas från en omvänd skattskyldighet eller en omvänd skattskyldighet)</br>-   **Importavgift**. </br>För varje transaktionsklassificerare finns det också en klassificerare för kreditfakturan. En av dessa klassificerare är till exempel **PurchaseCreditNote** (inköpskreditfaktura).</br>Se till att skapa två rader för varje momskod: en som har transaktionsklassens värde och en som har transaktionsklassen för kreditfakturavärde. |


    > [!NOTE]
    > Associera alla momskoder till sökresultaten. Om momskoder inte ska generera värden i momsdeklarationen associerar du dem med sökresultatet **Övrigt**.

    ![Sidan Programspecifika parametrar.](media/7db74920fad66a0db7fad60758698cc0.png)


5. I fältet **tillstånd** ändra värdet från **slutförd**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Ställa in momsrapporteringsformat för förhandsgranskning av belopp i Excel

1. I arbetsytan **Funktionshantering** söker du efter och väljer funktionen **Formatrapporter för momsutdrag** i listan, och väljer sedan **Aktivera nu**.
2. Gå till **Redovisning** > **Inställningar** > **Redovisningsparametrar**.
3. På fliken **Moms** > snabbfliken **Momsalternativ** > fältet **Formatmappning för momsutdrag** väljer du formatet **Excel för momsdeklaration (DK)**.

   Det här formatet skrivs ut när du kör rapporten **Rapportera moms för kvittningsperiod**. Den skrivs också ut när du väljer **Skriv ut** på sidan **Momsbetalningar**.

4. På sidan **Skattemyndigheter** väljer du skattemyndighet innan du i fältet **Rapportlayout** väljer **Standard**.

Om du konfigurerar momsdeklarationen i en juridisk person som omfattar [flera momsregistreringar](emea-reporting-for-multiple-vat-registrations.md), följer du dessa steg.

1. Gå till **Redovisning** \> **Inställningar** \> **Redovisningsparametrar**.
2. På fliken **Moms** > snabbfliken **Elektronisk rapportering för länder/regioner** > raden för **DNK** väljer du ER-formatet **Excel för momsdeklaration (DK)**.

## <a name="set-up-electronic-messages"></a>Konfigurera elektroniska meddelanden

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Hämta och importera datapaketet som har exempelinställningar för elektroniska meddelanden

Datapaketet innehåller inställningar för elektroniska meddelanden som används för att förhandsvisa momsdeklarationen i Excel. Du kan utöka dessa inställningar eller skapa egna. Mer information om hur du arbetar med elektroniska meddelanden och skapar egna inställningar finns i [Elektroniska meddelanden](../general-ledger/electronic-messaging.md).

1. I [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), i biblioteket för delade tillgångar, väljer du **Datapaket** som tillgångstyp och laddar sedan ned **DK Momsdeklarationspaket**. Den nedladdade filen heter **DK VAT declaration package.zip**.
2. I arbetsytan **Datahantering** i Finance väljer du **Importera**.
3. På snabbfliken **Importera**, i fältet **Gruppnamn**, anger du ett namn för jobbet.
4. På snabbfliken **Vald entiteter**, välj **Lägg till fil**.
5. I dialogrutan **Lägg till fil** ser du till att fältet **Källdataformat** anges som **Paket**, väljer **Ladda upp och lägg till** och väljer sedan den zipfil som du tidigare laddade ned.
6. Välj **Nära**.
7. När dataenheterna har förts över väljer du **Importera** i åtgärdsfönstret.
8. Gå till **Moms** > **Förfrågningar och rapporter** > **Elektroniska meddelanden** > **Elektroniska meddelanden** och validerar den elektroniska meddelandebearbetning som du importerat (**DK Momsdeklaration**).

### <a name="configure-electronic-messages"></a>Konfigurera elektroniska meddelanden

1. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden** > **Fyll i poståtgärder**.
2. Välj raden för **DK Fyll i returposter för moms** och sedan **Redigera fråga**.
3. Använd filtret om du vill ange den kvittningsperiod som ska inkluderas i rapporten.
4. Om du måste rapportera momstransaktioner från andra kvittningsperioder i en annan deklaration ska du skapa en ny åtgärd för **Fyll i poster** och välja lämpliga kvittningsperioder.

## <a name="preview-the-vat-declaration-in-excel"></a>Förhandsgranska momsdeklarationen i Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a>Förhandsgranska momsdeklarationen i Excel från den periodiska uppgiften Rapportera moms för kvittningsperiod

1. Gå till **Moms** > **Periodiska uppgifter** > **Deklarationer** > **Moms** > **Rapportera moms för kvittningsperiod**.
2. Välj ett värde i fältet **Kvittningsperiod**.
3. I fältet **Momsbetalningsversion**, välj ett att följande värden:

    - **Ursprunglig**: Generera en rapport för momstransaktioner för den ursprungliga momsbetalningen eller innan momsbetalningen genereras.
    - **Korrigeringar**: Generera en rapport för momstransaktioner för alla efterföljande momsbetalningar för perioden.
    - **Summor**: Generera en rapport för alla momstransaktioner för perioden, inklusive ursprungliga och alla korrigeringar.

4. Välj startdatum för rapporteringsperioden i fältet **Från datum**.
5. Välj **OK** och granska Excelrapporten.

### <a name="settle-and-post-sales-tax"></a>Kvitta och bokför moms

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

När du använder elektroniska meddelanden när du genererar rapporten kan du samla in momsdata från flera juridiska personer. Mer information finns i avsnittet [Kör en momsdeklaration för flera juridiska personer](#run-vat-declaration) senare i det här ämnet.

Följande procedur gäller för det exempel på elektronisk meddelandebearbetning som du tidigare importerade från LCS-biblioteket för delade tillgångar.

1. Gå till **Moms \> Förfrågningar och rapporter \> Elektroniska meddelanden \> Elektroniska meddelanden**.
2. I vänster navigeringsfönster väljer du **DK Momsdeklaration**.
3. På snabbfliken **Meddelanden** väljer du **Ny** och sedan, i dialogrutan **Kör bearbetning**, väljer du **OK**.
4. Markera meddelanderaden som skapas, ange en beskrivning och ange sedan start- och slutdatum för deklarationen.

   > [!NOTE]
   > Steg 5 till 7 är valfria.

5. Valfritt: På snabbfliken **Meddelanden** väljer du **Samla in data** och sedan **OK**. Momsbetalningar som genererats tidigare läggs till i meddelandet. Mer information finns i avsnittet [Kvitta och bokföra moms](#settle-and-post-sales-tax) tidigare i det här ämnet. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Deklaration** i dialogrutan **Parametrar för elektronisk rapport**.
6. Valfritt: På snabbfliken **Meddelandeartiklar** granskar du de momsbetalningar som överförs för bearbetning. Som standard ingår alla momsbetalningar för den valda perioden som inte ingår i något annat meddelande tillhörande samma bearbetning.
7. Valfritt: Välj **Ursprungligt dokument** för att granska momsbetalningarna, eller välj **Ta bort** för att exkludera momsbetalningar från bearbetning. Om du hoppar över det här steget kan du fortfarande generera en momsdeklaration genom att använda fältet **Deklaration** i dialogrutan **Parametrar för elektronisk rapport**.
8. På snabbfliken **Meddelanden** väljer du **Uppdatera status**. I dialogrutan **Uppdatera status** väljer du **Klar att genereras** och sedan **OK**. Kontrollera att meddelandestatusen har ändrats till **Klar att genereras**.
9. Välj **Generera rapport**. För att förhandsgranska momsdeklarationsbeloppen: I dialogrutan **Kör bearbetning** väljer du **Förhandsgranska rapport** och sedan **OK**.
10. I dialogrutan **Parametrar för elektroniska rapporter** ställer du in fälten som beskrivs i [Förhandsgranska momsdeklarationen i Excel från avsnittet Rapportera moms för periodisk uppgift för kvittningsperiod](#preview-vat-excel) tidigare i detta ämne och väljer **OK**.
11. Välj knappen **Bilagor** (gem-ikonen) i sidans övre högra hörn, och välj sedan **Öppna** för att öppna filen. Granska beloppen i Excel-dokumentet.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Kör en momsdeklaration för flera juridiska personer

Om du vill använda formaten för att rapportera momsdeklarationen för en grupp juridiska personer, måste du först ställa in de programspecifika parametrarna för ER-formaten för försäljnigsmomskoder från alla juridiska personer som krävs.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Konfigurera elektroniska meddelanden för insamling av momsdata från flera juridiska personer

Följ dessa steg för att konfigurera elektroniska meddelanden för insamling av data från flera juridiska personer.

1. Gå till **Arbetsytor** > **Funktionshantering**.
2. Sök efter och välj funktionen **Frågor mellan företag för åtgärd för postifyllande** i listan, och välj sedan **Aktivera nu**.
3. Gå till **Moms** > **Inställningar** > **Elektroniska meddelanden** > **Fyll i poståtgärder**.
4. På sidan **Åtgärd för postifyllande** väljer du raden **DK Fyll i momsreturposter**.

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
