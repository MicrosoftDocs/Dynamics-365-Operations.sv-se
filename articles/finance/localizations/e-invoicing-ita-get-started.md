---
title: Kom i gång med e-fakturering för Italien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Italien.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 53a3c315b38607a63cef36963843428385547e9e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985610"
---
# <a name="get-started-with-electronic-invoicing-for-italy"></a>Kom i gång med e-fakturering för Italien

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> E-fakturering för Italien kanske för närvarande inte stöder alla funktioner som är tillgängliga för elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management. 

Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering för Italien. Den guidar dig genom de konfigurationssteg som är beroende av RCS (Regulatory Configuration Services) och Finance. Det guidar dig också genom processen att skicka elektroniska fakturor som genereras i det italienska formatet **FatturaPA** via tjänsten och den förklarar hur du granskar resultaten av bearbetningen.

## <a name="prerequisites"></a>Förutsättningar

Innan du slutför stegen i det här avsnittet måste du slutföra stegen i [komma igång med e-fakturering](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Inställning av RCS

Under RCS-inställningar ska du utföra följande uppgifter:

1. Importera e-faktureringsfunktionen för export av kunders elektroniska fakturor i format **FatturaPA**.
2. Granska de formatkonfigurationer som krävs för att generera, skicka och ta emot svar om elektroniska fakturor.
3. Konfigurera de händelser som stöder överföringsscenarier för elektronisk faktura.
4. Publicera e-faktureringsfunktionen.

> [!NOTE]
> "e-faktureringsfunktionen" är det allmänna namnet för resursen som är konfigurerad och publicerad för att använda servern för e-fakturering. I detta fall, export av kunders elektroniska fakturor är den e-faktureringsfunktion som du ställer in.

## <a name="import-the-e-invoicing-feature"></a>Importera e-faktureringsfunktion

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-fakturering**.
3. På sidan **e-faktureringsfunktioner** väljer du **Importera** för att importera e-faktureringsfunktion från den globala databasen.

    > [!NOTE]
    > Om listan över tillgängliga funktioner inte visas väljer du **synkronisera**. 

4. Välj funktionen **export av e-fakturor (IT)** och välj sedan **Importera**.

![Importera funktionen för export av e-fakturor (IT).](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

När du importerar funktionen **exportera e-fakturor (IT)** från den globala databasen, importeras även alla inställningar som beskrivs i de följande avsnitten.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Skapa en ny version av funktionen export av e-fakturor (IT)

1. På sidan **e-faktureringsfunktioner** på fliken **Versioner** välj Ändra status **Ny**. 

    ![Lägga till en ny version av e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Därefter ska du konfigurera formaten för elektronisk rapportering (ER) som är kopplade till e-faktureringsfunktionen.

2. På fliken **Konfigurationer** välj **Lägg till** för att hantera konfigurationsversionerna.

    ![Hantera konfigurationsversioner av e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    I det här steget ska du lägga till och konfigurera ER-formaten för olika filer som används för att exportera italienska e-fakturor. För italienska FatturaPA e-fakturor använder du antingen följande standardkonfigurationer eller de anpassade konfigurationerna som du använder för e-fakturering:

    - Försäljningsfaktura (IT)
    - Projektfaktura (IT)

    När du skapar en e-faktureringsfunktion som härleds från en annan e-faktureringsfunktion ärvs alla ER-format från den ursprungliga funktionen.

3. Välj en specifik konfiguration för ER-formatfil.
4. Välj **Redigera** eller **Visa** för att öppna sidan **Formatdesigner**.

    ![Öppna sidan Formatdesigner.](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Använd sidan **Formatdesigner** för att redigera och visa filkonfigurationerna i ER-format.

    ![Formatdesignersida.](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Hantera inställningen för e-faktureringsfunktionen

- på sidan **e-faktureringsfunktioner** på fliken **Inställningar** välj **Lägg till**, **Ta bort** eller **Redigera** för att hantera inställningsfunktionen för e-fakturering.

![Hantera konfigurationer för e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

I det här steget konfigurerar du de händelser som gäller för elektroniska fakturor, inklusive generering av XML-utdatafilerna i **FatturaPA**-format och digital signering (om det behövs).

### <a name="configure-the-sales-invoice-feature-setup"></a>Konfigurera inställningen av funktionen Sales-faktura

1. På sidan **e-faktureringsfunktioner** på fliken **Inställningar** i kolumnen **Funktionsinställningar** välj **Försäljningsfaktura**.
2. Välj **Redigera**.
3. På sidan **Inställning av funktionsversion** välj fliken **Åtgärder** för att hantera listan med åtgärder. Åtgärder definierar en lista med operationer som måste köras i en sekventiell ordning för att händelsen ska kunna utföras.

    ![Fliken Åtgärder.](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | Åtgärds-ID | Namn på åtgärd        | Åtgärdsbeskrivning                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Omvandla dokument | Skapa e-fakturans XML-fil i formatet **FatturaPA**. |
    | 2         | Signera dokument      | Använd en digital signatur i XML-filen.             |

4. Välj fliken **tillämplighetsregler** om du vill visa och underhålla tillämplighetsreglerna. Tillämplighetsregler definierar i vilket sammanhang åtgärden ska köras.

    ![Fliken Tillämplighetsregler.](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Välj fliken **Variabler** om du vill visa och underhålla variablerna.

    ![Fliken Variabler.](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Definiera de offentliga variabler som krävs för att köra åtgärderna.

### <a name="configure-the-project-invoice-feature-setup"></a>Konfigurera inställningen av funktionen projektfaktura 

Stegen och inställningarna som krävs för att konfigurera funktionsinställning **Projektfaktura** är mycket liknande steget och inställningar för funktionsinställningen **Försäljningsfaktura**. När du arbetar med projektfakturor följer du procedurerna för försäljningsfakturor.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Tilldela e-faktureringsfunktionen till miljön

1. På sidan **e-faktureringsfunktioner** på fliken **Miljöer** välj Ändra status **Aktivera**.
2. I fältet **miljö** välj miljön.
3. I fältet **gäller från** väljer du det datum då miljön ska börja gälla.
4. Välj **Aktivera**. 

![Aktivera en e-faktureringsmiljön.](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Publicera e-faktureringsfunktion

Du kan publicera e-faktureringsfunktionen genom att ändra versionsstatus till **slutförd** eller **publicerad**.

### <a name="change-the-version-status-to-completed"></a>Ändra versionsstatus till slutförd

1. På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Utkast**.
2. Välj **Ändra status \> Slutför**. 

### <a name="change-the-version-status-to-published"></a>Ändra versionsstatus till publicerad 

1. På sidan **e-faktureringsfunktion** på fliken **Versioner**, välj den version av e-faktureringsfunktionen som har status **Slutförd**.
2. Välj **Ändra status \> Publicera**.

![Ändra status för e-faktureringsfunktionen.](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-integration-in-finance"></a>Ställ in integrering av e-fakturering i Finance

Under inställningar av Finance ska du utföra följande uppgifter:

1. Importera ER-datamodell, ER-datamodellmappning och kontextkonfigurationer för FatturaPA e-fakturor.
2. Konfigurera det certifikat som krävs för digital signering av italienska e-fakturor.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importera ER-datamodellen, datamodellmappningen och formaten

1. I arbetsytan **elektronisk rapportering** kontrollera att konfigurationsleverantören **Tjänst för affärsdokument** anges till **Aktiv**.
2. Välj **Databaser**.
3. Välj **Global resurs \> Öppna**.
4. Importera **Fakturamodell**, **Mappning av fakturamodell** och **Kontextmodell för kundfaktura**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Aktivera funktionen för att exportera kunders elektroniska fakturor för Italien

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Funktioner** markerar du kryssrutan **Aktivera** i raden för funktionsreferens **IT00036**.

![Aktivera funktionen FatturaPA.](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Konfigurera elektroniska dokument

1. Gå till **organisationsadministration \> inställning \> parametrar för elektroniska dokument**.
2. På fliken **Elektroniskt dokument** välj **Lägg till** och ange de register som krävs för att generera italienska e-fakturor:

    - **Registernamn:** Kundfakturajournal
    - **Registernamn:** projektfaktura

3. Definiera ett relaterat dokumentsammanhang för varje register.

    - För **Kundfakturajournaler** anger du **Kundfakturakontext**.
    - För **Projektfaktura**, ange **Projektfaktura kontext**.

![Konfigurera svarstyper.](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Elektronisk fakturabearbetning

Under bearbetningen i Finance ska du utföra följande uppgifter:

1. Skapa italienska e-fakturor via E-fakturering
2. Visa körningsloggarna och granska resultaten av bearbetningen

### <a name="generate-electronic-invoices"></a>Generera elektroniska fakturor

När du har aktiverat funktionen **konfigurerbara integrering för e-fakturering** och aktiverat funktionen **IT00036** kommer den gamla Finance-processen för att generera italienska e-fakturor inte längre kunna användas. Den ersätts med en ny process som kallas **skicka elektroniska dokument**.

Du kan skicka dokumenten manuellt, baserat på efterfrågan på e-fakturadokument.

> [!NOTE]
> Innan du fortsätter kontrollerar du att inställningarna som krävs för italienska e-fakturorna är slutförda. Mer information finns i [Elektroniska kundfakturor](./emea-ita-e-invoices.md). Tänk på att vissa av de inställningssteg som beskrivs i det ämnet kanske inte är tillgängliga på grund av aktivering av E-fakturering.

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> skicka elektroniska dokument**.
2. Ställ alltid in alternativet **Skicka dokument igen** till **Nej** för första inlämningen av ett dokument. Om du måste skicka ett dokument på nytt via tjänsten ställer du in det här alternativet på **Ja**.
3. På snabbfliken **Poster att inkludera** välj **Filter** för att öppna dialogrutan **fråga** där du kan skapa en frågeställning för att välja dokument för överföring.

![Skicka in dialogrutan för elektroniska dokument.](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Filterfråga

1. Dialogrutan **Förfrågning**, konfigurera filtreringsvillkoren för både försäljningsfakturor och projektfakturor, eller låt villkoren vara tomma för att inkludera alla icke inlämnade fakturor.

    ![Konfigurera kriterier för överföringsfilter.](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Välj **OK** för att stänga dialogrutan **Förfrågning**.
3. Välj **OK** för att skicka de valda dokumenten.

> ![OBS] Under ditt första försök att skicka ett dokument via tjänsten uppmanas du att bekräfta anslutningen med E-fakturering. Välj **Klicka här för att ansluta till tjänsten inlämning av elektroniska dokument**.

#### <a name="view-submission-logs"></a>Visa överföringsloggar

Du kan visa överföringsloggar för alla skickade dokument.

1. Gå till **organisationsadministration \> periodisk \> elektroniska dokument \> logg för inlämning av elektroniska dokument**.
2. I fältet **Dokumenttyp** väljer du **Kundfakturajournal** eller **Projektfaktura** för att filtrera fram nödvändiga elektroniska dokument.

    ![Välja en dokumenttyp för att visa överföringsloggarna.](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    Värdet som visas i kolumnen **överföringsstatus** representerar den status för överföringsprocessen. Det anger om processen kördes som konfigurerad och om ytterligare åtgärder krävs.

3. I åtgärdsfönstret, välj **Förfrågningar \> Överföringsinformation** om du vill visa information om körningsloggar för överföring.

    ![Visa information om överföringsloggen.](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. På snabbfliken **Bearbeta åtgärder** kan du visa körningsloggen för de åtgärder som är konfigurerade i funktionsversionen som ställdes in i RCS. Kolumnen **Status** visar om åtgärden har utförts utan fel.
5. På snabbfliken **Åtgärdsfiler** kan du visa de mellanliggande filer som genererades under körningen av åtgärderna. Du kan välja **vy** för att hämta utdata-XML-filen i format **FatturaPA** och visa dess innehåll.

## <a name="related-topics"></a>Relaterade ämnen

- [E-fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med e-fakturering](e-invoicing-get-started.md)
- [Ställ in e-fakturering](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]