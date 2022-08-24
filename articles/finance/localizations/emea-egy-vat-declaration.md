---
title: Momsdeklaration för Egypten
description: I den här artikeln beskrivs hur du konfigurerar och genererar formuläret retur av moms för Egypten.
author: AdamTrukawka
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.search.scope: ''
ms.openlocfilehash: c035c52d7d577a01f5903461548c0cb33f05045f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287834"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Momsdeklaration för Egypten (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in och genererar formuläret för momsretur och försäljnings- och inköpsböcker för juridiska personer i Egypten.

Formuläret för momsretur för Egypten är det officiella dokumentet som sammanfattar det totala beloppet för utgående moms, totalt belopp för ingående moms och den tillhörande momsskulden. Formuläret används för alla typer av skattebetalare och ska fyllas i manuellt via skattemyndighetsportalen. Formuläret för momsretur kallas vanligtvis för rapport om momsretur.

Formuläret momsretur i Dynamics 365 Finance innehåller följande rapporter:

- Formulärnummer 10 för momsretur, som visar en uppdelning av belopp, justeringar och momsbelopp per radartikel i momsreturformuläret enligt lagstiftningens beskrivning.
- Försäljningstransaktionsbok
- Inköpstransaktionsbok

## <a name="prerequisites"></a>Förutsättningar
Den primära adressen för den juridiska personen måste dock finnas i Egypten.
I arbetsytan **utgiftshantering** aktiverar du följande funktion:

   - (Egypten) Kategorihierarki för rapporten Skatt på försäljning och inköp.

Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

I arbetsytan **Elektroniskt rapportering**, importera följande elektroniskt rapporteringsformat från databasen:

- Momsdeklaration Excel (EG)

> [!NOTE]
> Formatet ovan är baserat på **Skattedeklarationsmodell** och använder **Mappning för skattedeklarationsmodell**. Ytterligare konfigurationer importeras automatiskt.

Mer information om hur du importerar konfigurationer för elektronisk rapportering finns i [Hämta konfigurationer för elektronisk rapportering från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Hämta konfigurationer för elektronisk rapportering

Implementeringen av momsreturformuläret för Egypten är baserad på konfigurationer av Elektronisk rapportering (ER). Mer information om möjligheterna med och koncepten med konfigurerbara rapporter finns i [Elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Information om hur du testar produktion och användares godkännande (UAT) finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Ladda upp följande konfigurationer för att generera momsdeklarationsformuläret och relaterade rapporter i en juridisk enhet i Egypten:

- Skattedeklarationsmodell.version.70.xml eller senare version
- Skattedeklarationsmodell mappning.version.70.120.xml eller senare version
- Skattedeklaration Excel (EG).version.70.32 eller en senare version

När du har hämtat ER-konfigurationerna från Lifecycle Services (LCS) eller den globala databasen gör du så här.

1. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
1. På sidan **Konfigurationer** på åtgärdspanelen väljer du **Exchange** > **Läs in från XML-fil**.
1. Överför filerna i den ordning de visas ovan. När alla konfigurationer har överförts ska konfigurationsträdet finnas med i Finance.

## <a name="set-up-application-specific-parameters"></a>Ställa in appspecifika parametrar

Med hjälp av de programspecifika parametrarna kan du ange kriterier för hur skattetransaktioner ska klassificeras och beräknas på varje rad när rapporten genereras. Bestämmandet baseras på konfigurationen av artikelmomsgruppen, momsgruppen, momskoden och andra kriterier som upprättats i sökdefinitionen.

Rapporterna för försäljnings- och inköpsbok för Egypten innehåller en uppsättning kolumner som motsvarar specifika transaktionsklassificeringar som typer av operationer, produkter och dokument som är specifika för Egypten. I stället för att inkludera dessa nya klassificeringar som ny postdata när transaktionerna publiceras kommer klassificeringarna att bestämmas baserat på olika uppslag som introducerades i **Konfigurationer** > **ställa in programspecifika parametrar** > **inställning** för att uppfylla kraven för momsrapporterna för Egypten. 

![Sidan Programspecifika parametrar.](media/egypt-vat-declaration-setup1.png)

Dessa följande sökkonfigurationer används för att klassificera transaktionerna i inköps- och momsboksrapporter:

- **PurchaseItemTypeLookup** > Kolumn O: Artikeltyp
- **VATRateTypeLookup** > Kolumn B: Momstyp
- **VATRateTypeLookup** > Kolumn C: Tabellartikeltyp
- **PurchaseOperationTypeLookup** > Kolumn A: Dokumenttyp
- **CustomerTypeLookup** > Kolumn A: Dokumenttyp
- **SalesOperationTypeLookup** > Kolumn N: Operationstyp
- **SalesItemTypeLookup** > Kolumn O: Artikeltyp

Gör på följande sätt om du vill ställa in de olika sökningar som används för att generera momsdeklarationer och relaterade redovisningsrapporter. 

1. I arbetsytan **Elektronisk rapportering**, välj **Konfigurations** > **Inställningar** för att ställa in reglerna för att identifiera skattetransaktionen i den relaterade rutan i momsdeklarationsformuläret.
2. Markera den aktuella versionen och på snabbfliken **Uppslag** markera söknamnet. Till exempel **SalesItemTypeLookup**. Vid den här sökningen identifieras den lista över klassificeringar i momsboken som krävs av skattemyndigheten.
3. På snabbfliken **Villkor** markerar du **Lägg till** och på den nya raden i kolumnen **Sökresultat** markerar du den relaterade rad som representerar klassificeringen i **Kolumn O**.
4. I kolumnen **Momsgrupp** väljer du den momsgrupp som används för att identifiera klassificeringen. Till exempel, **lokal försäljningsfaktura**. Du kan också använda artikelmomsgrupp, momskod eller kombinationen av trädattribut om konfigurationen har definierats på ett annat sätt. 
5. I kolumnen **Namn**, välj skattetransaktionsklassificering.
6. Upprepa steg 3–5 för alla tillgängliga sökningar.
7. Välj **Lägg till** för att inkludera den sista postraden och i kolumnen **Sökresultat** välj **Inte aktuellt**. 
8. Välj i de återstående kolumnerna **Ej tom**. 
9. I fältet **Stat**, välj **Slutförd**.
10. Välj **Spara** och stäng sidan **Programspecifika parametrar**.

> [!NOTE]
> När du lägger till den sista posten, **Inte aktuellt**, definierar du följande regel: När momsgrupp, artikelmomsgrupp, momskod och namn som passerats när ett argument inte uppfyller några av de föregående reglerna, inkluderas inte transaktionerna i momsboken. Även om denna regel inte används när rapporten genereras, bidrar regeln till att undvika fel vid generering av rapporter när en regelkonfiguration saknas.

Följande register ger ett exempel på den föreslagna konfigurationen för de beskrivna sökkonfigurationerna. 

**SalesItemTypeLookup**

| Sökningsresultat         | Rad | Momsgrupp    | Artikelmomsgrupp    | Skattekod (kod) | Namn                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Lokal              | 1    | VAT_LOCAL          | *Inte tom*             | *Inte tom*     | Försäljning                 |
| Lokal              | 2    | VAT_LOCAL          | *Inte tom*             | *Inte tom*     | SalesCreditNote       |
| Lokal              | 3    | VAT_FINALC         | *Inte tom*             | *Inte tom*     | Försäljning                 |
| Lokal              | 4    | VAT_FINALC         | *Inte tom*             | *Inte tom*     | SalesCreditNote       |
| Lokal              | 5    | VAT_PUBLIO         | *Inte tom*             | *Inte tom*     | Försäljning                 |
| Lokal              | 6    | VAT_PUBLIO         | *Inte tom*             | *Inte tom*     | SalesCreditNote       |
| Export                | 7    | VAT_EXPORT         | *Inte tom*             | *Inte tom*     | Försäljning                 |
| Export                | 8    | VAT_EXPORT         | *Inte tom*             | *Inte tom*     | SalesCreditNote       |
| Maskin och utrustning | 9    | *Inte tom*        | VAT_M&E                 | *Inte tom*     | Försäljning                 |
| Maskin och utrustning | 10   | *Inte tom*        | VAT_M&E                 | *Inte tom*     | SalesCreditNote       |
| Maskindelar        | 11   | *Inte tom*        | VAT_PARTS               | *Inte tom*     | Försäljning                 |
| Maskindelar        | 12   | *Inte tom*        | VAT_PARTS               | *Inte tom*     | SalesCreditNote       |
| Undantag            | 13   | VAT_EXE            | *Inte tom*           | *Inte tom*     | SaleExempt            |
| Undantag            | 14   | VAT_EXE            | *Inte tom*           | *Inte tom*     | SalesExemptCreditNote |
| Inte aktuellt        | 15   | *Tom*            | *Tom*                 | VAT_ADJ         | *Inte tom*           |
| Inte aktuellt        | 16   | *Inte tom*        | *Inte tom*             | *Inte tom*     | *Inte tom*           |

 **SalesOperationTypeLookup**

| Sökningsresultat  | Rad | Artikelmomsgrupp    | Skattekod    | Namn                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Varor          | 1    | VAT_GOODS               | *Inte tom* | Försäljning                 |
| Varor          | 2    | VAT_GOODS               | *Inte tom* | SalesCreditNote       |
| Varor          | 3    | VAT_GOODS               | *Inte tom* | SaleExempt            |
| Varor          | 4    | VAT_GOODS               | *Inte tom* | SalesExemptCreditNote |
| Tjänster       | 5    | VAT_SERV                | *Inte tom* | Försäljning                 |
| Tjänster       | 6    | VAT_SERV                | *Inte tom* | SalesCreditNote       |
| Tjänster       | 7    | VAT_SERV                | *Inte tom* | SaleExempt            |
| Tjänster       | 8    | VAT_SERV                | *Inte tom* | SalesExemptCreditNote |
| Modifieringar    | 9    | *Tom*                 | VAT_ADJ     | Försäljning                 |
| Modifieringar    | 10   | *Tom*                 | VAT_ADJ     | SalesCreditNote       |
| Inte aktuellt | 11   | *Inte tom*             | *Inte tom* | *Inte tom*           |

**PurchaseItemTypeLookup**

| Sökningsresultat          | Rad | Artikelmomsgrupp    | Skattekod    | Namn                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Varor                  | 1    | VAT_GOODS               | *Inte tom* | Inköp                 |
| Varor                  | 2    | VAT_GOODS               | *Inte tom* | PurchaseCreditNote       |
| Tjänster               | 3    | VAT_SERV                | *Inte tom* | Inköp                 |
| Tjänster               | 4    | VAT_SERV                | *Inte tom* | PurchaseCreditNote       |
| Maskin och utrustning  | 5    | VAT_M&E                 | *Inte tom* | Inköp                 |
| Maskin och utrustning  | 6    | VAT_M&E                 | *Inte tom* | PurchaseCreditNote       |
| Maskindelar         | 7    | VAT_PARTS               | *Inte tom* | Inköp                 |
| Maskindelar         | 8    | VAT_PARTS               | *Inte tom* | PurchaseCreditNote       |
| Undantag             | 9    | VAT_EXE                 | *Inte tom*  | PurchaseExempt           |
| Undantag             | 10   | VAT_EXE                 | *Inte tom* | PurchaseExemptCreditNote |
| Inte aktuellt         | 11   | *Inte tom*             | *Inte tom* | *Inte tom*              |

**PurchaseOperationTypeLookup**

| Sökningsresultat  | Rad | Momsgrupp  | Skattekod    | Namn                     |
|----------------|------|------------------|-------------|--------------------------|
| Lokal       | 1    | VAT_LOCAL        | *Inte tom* | Inköp                 |
| Lokal       | 2    | VAT_LOCAL        | *Inte tom* | PurchaseCreditNote       |
| Lokal       | 3    | VAT_LOCAL        | *Inte tom* | PurchaseExempt           |
| Lokal       | 4    | VAT_LOCAL        | *Inte tom* | PurchaseExemptCreditNote |
| Importerat       | 5    | VAT_IMPORT       | *Inte tom* | Inköp                 |
| Importerat       | 6    | VAT_IMPORT       | *Inte tom* | PurchaseCreditNote       |
| Importerat       | 7    | VAT_IMPORT       | *Inte tom* | PurchaseExempt           |
| Importerat       | 8    | VAT_IMPORT       | *Inte tom* | PurchaseExemptCreditNote |
| Modifieringar    | 9    | *Tom*          | VAT_ADJ     | PurchaseCreditNote       |
| Modifieringar    | 10   | *Tom*          | VAT_ADJ     | Inköp                 |
| Inte aktuellt | 11   | *Inte tom*      | *Inte tom* | *Inte tom*              |

**CustomerTypeLookup**

|    Sökningsresultat    | Rad | Momsgrupp |
|---------------------|------|-----------------|
| Organisation        |  1   | VAT_LOCAL       |
| Organisation        |  2   | VAT_EXPORT      |
| Organisation        |  3   | VAT_EXE         |
| Slutkund      |  4   | VAT_FINALC      |
| Offentlig organization |  5   | VAT_PUBLIO      |
| Inte tillämpligt      |  6   | *Inte tom*     |

**VATRateTypeLookup**

| Sökningsresultat  | Rad | Skattekod (kod) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Inte tom*     |
| SecondTable    | 4    | *Inte tom*     |
| Inte aktuellt | 5    | *Inte tom*     |


## <a name="set-up-general-ledger-parameters"></a>Ställ in redovisningsparametrar

Om du vill generera en formulärrapport för momsretur i Microsoft Excel-format definierar du ett ER-format på sidan **Allmänna redovisningsparametrar**.

1. Gå till **Skatt** > **Inställningar** > **Redovisningsparametrar**.
2. På fliken **Moms** i avsnitt **Alternativ för skatt** i fältet **Formatmappning för momsutdrag**, välj **Momsdeklaration Excel (EG)**. Om du lämnar fältet tomt genereras standard momsrapporten i SSRS-format.
3. Välj **kategorihierarki**. Med denna kategori kan varukoden i transaktioner för utländsk handel tillåta användarna att välja och klassificera varor och tjänster. Beskrivningen av den här klassificeringen finns detaljerad i försäljnings- och inköpstransaktionsrapporterna. Denna konfiguration är valfri.

![Deklarationsformulär.](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Generera en momsrapport
Processen för att förbereda och skicka in en momsreturrapport för en period baseras på momsbetalningstransaktioner som har bokförts under jobbet Kvitta och bokför moms. Mer information om hur du kvitta och rapportera moms finns i [Momsöversikt](../general-ledger/indirect-taxes-overview.md).

Gör på följande sätt när du vill generera skattedeklarationsrapporten.

1. Gå till **Skatt** > **Deklarationer** > **Moms** > **Rapportera moms för kvittningsperiod** eller **Kvitta och bokför moms**.
2. Välj **Kvittningsperiod**.
3. Välj från-datum och sedan momsbetalningsversion.
5. Välj **OK**. 
6. Ange kreditbeloppet från den föregående perioden, om det är tillämpligt, eller lämna beloppet som noll.
7. I fältet **Rapportdetaljer**, välj något av följande tillgängliga alternativ. 
   - **Momsbok för inköp**: Skapa en rapport över momstransaktioner för inköp.
   - **Momsbok för försäljning**: Skapa en rapport över momstransaktioner för försäljning.
   - **Momsdeklaration**: Generera endast formuläret för momsdeklaration.
8. Ange namnet på den person som är registrerad för att tilldela formuläret.
9. Välj språk. Alla rapporter översätts i **en-us** och **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


