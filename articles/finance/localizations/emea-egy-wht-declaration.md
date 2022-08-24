---
title: Källskattedeklaration för Egypten
description: I den här artikeln beskrivs hur du konfigurerar och genererar formuläret för källskattedeklaration för Egypten.
author: AdamTrukawka
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.search.scope: ''
ms.openlocfilehash: 83def72f1ff0423d1c2d217847082fa9bf1c3bca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269387"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Källskattedeklaration för Egypten (EG-00005)

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Översikt
Det här ämnet beskriver hur du ställer in och genererar källskattedeklarationen och källskattedeklaration formulär 41 och 11 för juridiska personer i Egypten 

Alla egyptiska företag måste förbereda formuläret 41, där det sammanfattas alla skatter som tas ut från lokala leverantörer och serviceleverantörer. Utöver formulär 41 måste formulär 11 genereras om du vill detaljerad information om alla behållna skatter från utländska leverantörer. 

Rapporten **Källskattedeklaration** i Dynamics 365 Finance inkluderar följande rapporter:

- Deklarationsformulär nr. 41
- Deklarationsformulär nr. 11
    
    
## <a name="prerequisites"></a>Förutsättningar
Den primära adressen för den juridiska personen måste dock finnas i Egypten.
I arbetsytan **utgiftshantering** aktiverar du följande funktion:

   - **Global källskatt**

Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. Gå till **Skatt** > **Inställningar** > **Parametrar** > **Redovisningsparametrar** och sedan, på fliken **Källskatt** anger du **Aktivera global källskatt** till **Ja**.
2. I arbetsytan **Elektroniskt rapportering**, importera följande elektroniskt rapporteringsformat från databasen:

    - Momsdeklaration Excel (EG)

    > [!NOTE]
    > Formatet ovan är baserat på **Skattedeklarationsmodell** och använder **Mappning för skattedeklarationsmodell**. Denna ytterligare konfiguration importeras automatiskt.

Mer information om hur du importerar konfigurationer för elektronisk rapportering finns i [Hämta konfigurationer för elektronisk rapportering från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Hämta konfigurationer för elektronisk rapportering

Implementeringen av WHT deklarationsformulär för Egypten är baserad på konfigurationer av Elektronisk rapportering (ER). Mer information om möjligheterna med och koncepten med konfigurerbara rapporter finns i [Elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Information om hur du testar produktion och användares godkännande (UAT), följ instruktionerna i ämnet [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Om du vill generera källskattedeklarationerna i en egyptisk juridisk person som är här måste du föra över följande konfigurationer:

- Skattedeklarationsmodell.version.82.xml eller senare version
- Skattedeklarationsmodell mappning.version.82.133.xml eller senare version
- Skattedeklaration Excel (EG).version.82.21 eller en senare version

När nedladdningen är klar av ER-konfigurationerna från Lifecycle Services (LCS) eller den globala databasen gör du så här.

1. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
1. På sidan **Konfigurationer** på åtgärdspanelen väljer du **Exchange > Läs in från XML-fil**.
1. Ladda upp alla filer i den ordning som de finns listade i föregående punkter. När alla konfigurationer har överförts ska konfigurationsträdet finnas med i Finance.

## <a name="set-up-application-specific-parameters"></a>Ställa in appspecifika parametrar

Alternativet appspecifika parametrar låter användare fastställa kriterierna för hur skattetransaktioner kommer att klassificeras och beräknas på varje rad i en genererad rapport beroende på konfigurationen av **Källskattegrupp för artiklar** eller andra kriterier som upprättats i sökdefinitionen.

Källdeklarationsformulär 41 innehåller en specifik kolumn där källskattetransaktionen måste klassificeras i enlighet med skattemyndighetens klassificering med namnet **Rabattkodtyp**. I stället för att inkludera dessa nya klassificeringar som ny postdata när transaktionerna publiceras kommer klassificeringarna att bestämmas baserat på olika uppslag som introducerades i **Konfigurationer** > **ställa in programspecifika parametrar** > **inställning** för att uppfylla kraven för källskattrapporter för Egypten. 

Följande konfiguration används för att klassificera transaktionerna i källdeklarationsformulär 41-rapporten:

- **DiscountTaxTypeLookup** -> Kolumnnr 18 

Gör på följande sätt om du vill ställa in de olika sökningar som används för att generera momsdeklarationer och relaterade redovisningsrapporter. 

1. I arbetsytan **Elektronisk rapportering**, välj **Konfigurations** > **Inställningar** för att ställa in reglerna för att identifiera hur transaktioner klassificeras i WHT-deklarationsrapporten. 
2. Markera den aktuella versionen och på snabbfliken **Uppslag** markera söknamnet. Till exempel **DiscountTaxTypeLookup**. I den här sökningen identifieras listan över rabatttyper som skattemyndigheten kräver.
3. På snabbfliken **Villkor** markerar du **Lägg till** och på den nya raden i kolumnen **Sökresultat** markerar du den relaterade rad som representerar klassificeringen i **Kolumn 18**.
4. I kolumnen **Källskattegrupp för artiklar** väljer du den relaterade kod som används för att identifiera klassificeringen. Till exempel **Tillåten rabatt**.  
5. Upprepa steg 3 och 4 för alla tillgängliga sökningar.
6. Välj **Lägg till** för att inkludera den sista postraden och i kolumnen **Sökresultat** välj **Inte aktuellt**. 
7. Välj i de återstående kolumnerna **Ej tom**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Ställ in redovisningsparametrar

Om du vill generera en rapport för deklarationsformulär i Microsoft Excel-format definierar du ett ER-format på sidan **Allmänna redovisningsparametrar**.

1. Gå till **Skatt** > **Inställningar** > **Redovisningsparametrar**.
2. På fliken **källskatt** i fältet **WHT mappning av deklarationsformat**, välj **WHT-deklaration Excel (EG)**. Om du lämnar fältet tomt genereras standard momsrapporten i SSRS-format.


![Deklarationsformulär.](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Generera källdeklarationsformulären
Processen för att förbereda och skicka ett källskattedeklarationsformulär för en viss period baseras på källskattetransaktionerna som bokförs under kvittnings- och redovisningsjobbet. Mer information om global källskatt finns i [Global källskatt](../general-ledger/global-withholding-tax-overview.md).

Gör på följande sätt när du vill generera skattedeklarationsrapporten.

1. Gå till **Skatt** > **Deklarationer** > **Källskatt** > **Betalning av källskatt*.
2. Välj kvittningsperiod och sedan från-datum för rapporten. 
3. Ange transaktionsdatum och klicka sedan på **OK**.
4. I dialogrutan som öppnas väljer du en eller flera av formulärtyperna **Formulär nr 41**, **Formulär nr 11** eller **Ingen**. Om du väljer **Ingen** genereras standardrapporten. 
5. Välj språk. Alla rapporter översätts i **en-us** och **ar-eg**.
6. Ange filial och namn för den bank där skattebetalningen ska betalas.
7. Välj affärstyp och ange sedan check- och dokumentnummer. 
8. Ange enhetstyp. 
9. Ange namnet på den person som har registrerats för att tilldela formuläret och välj **OK** för att bekräfta rapportgenereringen. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
