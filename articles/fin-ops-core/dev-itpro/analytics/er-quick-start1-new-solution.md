---
title: Skapa en ny ER-lösning för att skriva ut en egen rapport
description: I det här avsnittet beskrivs hur du utformar en elektronisk rapporteringslösning (ER) för att skriva ut en egen rapport.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af610ae86e751ec4425f4c555cdf59c042fabcdb46e6a3a018b0d94a8926d92e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770078"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Skapa en ny ER-lösning för att skriva ut en egen rapport

[!include[banner](../includes/banner.md)]

Följande steg beskriver hur en roll för användare i en systemadministratör, elektronisk rapportutvecklare eller en funktionell konsult för elektronisk rapportering kan konfigurera parametrar för ER-ramverk, utforma nödvändiga ER-konfigurationer för en ny ER-lösning för att komma åt data i en viss affärsdomän och skapa en anpassad rapport i Microsoft Office-formatet. Dessa steg kan slutföras i **USMF**-företaget.

- [Konfigurera ER-ramverket](#ConfigureFramework)

    - [Konfigurera ER-parametrar](#ConfigureParameters)
    - [Aktivera en ER-konfigurationsleverantör](#ActivateProvider)

        - [Granska listan med ER-konfigurationsleverantörer](#ReviewProvidersList)
        - [Lägg till en ny ER-konfigurationsleverantör](#AddProvider)
        - [Aktivera en ER-konfigurationsleverantör](#ActivateAddedProvider)

- [Utforma domänspecifik datamodell](#DesignModel)

    - [Importera en ny konfiguration för datamodell](#ImportDataModel)
    - [Skapa en ny datamodellskonfiguration](#DesignDataModel)

        - [Namnge och datamodellen](#NameDataModel)
        - [Lägg till fält för datamodell](#FieldsEntry)
        - [Färdigställa datamodellens utformning](#CompleteDataModel)

- [Designa en modellmappning för den konfigurerade datamodellen](#DesignMapping)

    - [Importera en ny konfiguration för modellmappning](#ImportModelMapping)
    - [Skapa en ny konfiguration av modellmappning](#CreateModelMapping)

        - [Designa en ny modellmappningskomponent](#DesignMappingComponent)
        - [Lägga till datakällor för att öppna programtabeller](#AddMmDataSource1)
        - [Lägga till datakällor för att öppna programuppräkningar](#AddMmDataSource2)
        - [Lägga till ER-etiketter för att generera en rapport på ett angivet språk](#AddMmLabels)
        - [Lägga till en datakälla som transformerar resultaten från att jämföra uppräkningsvärden till ett textvärde](#AddMmDataSource3)
        - [Binda datakällor till fält för datamodell](#AddMmBindings1)
        - [Färdigställa modellmappningens utformning](#CompleteModelMapping)

- [Utforma en mall för en anpassad rapport](#DesignReportTemplate)
- [Designa ett format](#DesignFormat)

    - [Importera en utformad formatkonfiguration](#FormatImport)
    - [Skapa en ny formatkonfiguration](#FormatCreate)

        - [Importera rapportmall](#ImportReportTemplate)
        - [Konfigurera ett format](#ConfigureFormat)
        - [Definiera databindningen för en rapportrubrik](#DefineFormatBindings)
        - [Granska modellens datakälla](#ReviewModelDataSource)
        - [Binda formatelement till fält för datakällor](#BindFormatElements)

    - [Kör ett format som skapats från ER](#RunFormatFromER)

- [Justera ett utformat format](#TuneFormat)

    - [Ändra ett format för att ändra namnet på ett skapat dokument](#ModifyToChangeName)
    - [Ändra ett format för att ändra ordning på frågeställningarna](#ModifyToOrder)
    - [Kör ett ändrat format från ER](#RunFormatFromER2)
    - [Slutför formatdesignen](#CompleteFormat)

- [Utveckla programartefakter för att anropa den utformade rapporten](#DevelopCustomCode)

    - [Modifiera källkod](#ModifySourceCode)

        - [Lägga till en datakontraktklass](#DataContractClass)
        - [Lägg till en UI-skaparklass](#UIBuilderClass)
        - [Lägga till en dataleverantörsklass](#DataProviderClass)
        - [Lägga till en etikettfil](#LabelsFile)
        - [Lägg till en rapporttjänstklass](#ServiceClass)
        - [Lägg till en rapportkontrollantklass](#ControllerClass)
        - [Lägg till ett menyalternativ](#MenuItem)
        - [Lägg till ett menyalternativ till en meny](#Menu)
        - [Bygga ett Visual Studio-projekt](#BuildVSProject)

    - [Kör ett format från programmet](#RunFormatFromApp)

- [Finjustera en designad ER-lösning](#TuneSolution)

    - [Ändra modellmappning](#ModifyModelMapping)

        - [Lägga till datakällor för att öppna ett datakontraktobjekt](#AddDataSource1)
        - [Lägga till en datakälla för åtkomst av mappningsposter för ER-format](#AddDataSource2)
        - [Lägga till en datakälla för åtkomst av formatmappningsposter för ett ER-format som körs](#AddDataSource3)
        - [Ange namnet på det ER-format som körs i datamodellen](#AddBinding)
        - [Färdigställa modellmappningens utformning](#CompleteModelMapping2)

    - [Ändra ett format](#ModifyFormat)

        - [Lägg till ett nytt formatelement](#AddFormatElement)
        - [Bind det tillagda formatelementet](#BindAddedFormatElement)
        - [Slutför formatdesignen](#CompleteFormat2)

    - [Kör ett format från programmet](#RunFormatFromApp2)
    - [Kör ett format från ER](#RunFormatFromER3)
    - [Konfigurera ett formatmål för förhandsvisning på skärmen](#ConfigureDestination)
    - [Kör ett format från programmet för att förhandsgranska det som ett PDF-dokument](#RunFormatFromApp3)

- [Ytterligare resurser](#References)

I det här exemplet ska du skapa en ny ER-lösning för modulen [enkät](../../../human-resources/hr-learning-questionnaires.md). Med den nya ER-lösningen kan du utforma en rapport genom att använda ett Microsoft Excel kalkylblad som en mall. Du kan sedan generera **enkät**-rapport i Excel-eller PDF-format, förutom att generera den befintliga rapporten från SQL Server Reporting Services (SSRS). Du kan också senare ändra den nya rapporten vid begäran. Ingen kod behövs.

1. Om du vill köra den befintliga rapporten går du till **enkät** \> **design** \> **enkätrapport**.

    ![Välja menyalternativet Enkätrapport i modulen Enkät för att köra den befintliga SSRS-rapporten.](./media/er-quick-start1-application-menu-origin.png)

2. I dialogrutan **enkätrapport** ange urvalskriterier. Använd ett filter så att rapporten bara innehåller **SBCCrsExam** enkät.

    ![Ange urvalskriterier i dialogrutan för enkätrapport.](./media/er-quick-start1-ssrs-report-dialog.png)

Följande bild visar den genererade versionen av SSRS-rapporten för **SBCCrsExam**-enkät.

![Genererad SSRS-rapport.](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Konfigurera ER-ramverket

Som användare i rollen Utvecklare för elektronisk rapportering måste du konfigurera den minsta uppsättningen ER-parametrar innan du kan börja använda ER-ramverket för att designa din nya ER-lösning.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Konfigurera ER-parametrar

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På arbetsytan **Elektronisk rprogramortering** väljer du **Elektroniska rprogramorteringsparametrar**.
3. På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.
4. Ange följande parametrar på fliken **Bilagor**:

    - Ange fältet **Konfigurationer** till **Fil** för **USMF**-företaget.
    - Ange **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** till **Fil**.

Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Aktivera en ER-konfigurationsleverantör

Varje ER-konfiguration markeras som ägd av en ER-konfigurationsleverantör. Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.

> [!NOTE]
> Endast ägaren till en ER-konfiguration kan redigera den. Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Granska listan med ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. På sidan **Konfigurationsleverantörer** har varje konfigurationsleverantörspost ett unikt namn och en URL. Granska innehållet på den här sidan. Om det redan finns en post för **Litware, Inc.** (`https://www.litware.com`) hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Lägg till en ny ER-konfigurationsleverantör

1. Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.
2. I fältet **Namn** anger du **Litware, Inc.**.
3. I fältet **Internetadress** anger du `https://www.litware.com`.
4. Välj **Spara**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Aktivera en ER-konfigurationsleverantör

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. I arbetsytan **Elektronisk rapportering** väljer du **Litware, Inc.** för din konfigurationsleverantör.
3. Ställ in **Ange aktiva**.

Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Ange urvalskriterier i dialogrutan för frågeformulär

Du måste skapa en ny ER-konfiguration som innehåller komponenten [datamodell](general-electronic-reporting.md#data-model-and-model-mapping-components) för affärsdomänen **Enkät**. Den här datamodellen kommer senare att användas som datakälla när du designar ett ER-format för att generera **enkät**-rapporten.

Genom att slutföra stegen i avsnittet [Importera en ny konfiguration för datamodell](#ImportDataModel) kan du importera den datamodell som krävs från den angivna XML-filen. Du kan också slutföra stegen i avsnittet [Skapa en ny konfiguration för datamodell](#DesignDataModel) om du vill designa den här datamodellen från början.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importera en ny konfiguration för datamodell

1. Hämta filen [enkätmodell.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **enkätmodell.version.1.xml**.
6. Välj **OK** för att importera konfigurationen.

Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny konfiguration för datamodell](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Skapa en ny datamodellskonfiguration

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
3. Välj **Skapa konfiguration**.
4. I listrutan i fältet **Namn** anger du **enkätmodell**.
5. Välj **Skapa konfiguration** för att skapa konfigurationen.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Namnge och datamodellen

1. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.
2. Välj **Designer**.
3. På sidan **Datamodelldesigner** på snabbfliken **Allmänt** i fält **Namn** ange <a name="DataModeName"></a>**Enkät**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Lägg till nya fält för datamodell

1. Välj **Nytt** på sidan **Datamodelldesigner**.
2. Gör så här i listrutan för att lägga till en datamodellnod:

    1. Välj **modellrot** som typ för den nya noden.
    2. Skriv <a name="RootDefinitionName"></a>**Kassa** i fältet **Rot**.
    3. Välj **Lägg till** för att lägga till en ny nod.

    Den här rotbeskrivningen används för att tillhandahålla data för rapporten **enkät**. En enskild datamodell kan ha flera beskrivare. Varje beskrivning kan anges för ett enda ER-format, för att identifiera de data som krävs för att generera rapporten.

3. Välj **Ny** igen och sedan, i rullgardinsmenyn för att lägga till en datamodellnod, följ dessa steg:

    1. Välj **Underordnad av en aktiv nod** som typ för den nya noden.
    2. Skriv **Namn** i fältet **CompanyName**.
    3. Välj **Sträng** i fältet **Artikeltyp**.
    4. Välj **Lägg till** för att lägga till ett nytt fält.

    Det här fältet är obligatoriskt om du vill skicka namnet på det aktuella företaget till en ER-rapport som använder den här datamodellen som datakälla.

4. Välj **Ny** igen och sedan, i rullgardinsmenyn för att lägga till en datamodellnod, följ dessa steg:

    1. Välj **Underordnad av en aktiv nod** som typ för den nya noden.
    2. Skriv **Namn** i fältet **Enkät**.
    3. Välj **Postlista** i fältet **Artikeltyp**.
    4. Välj **Lägg till** för att lägga till ett nytt fält.

    Detta fält kommer att användas för att skicka listan över enkäter på det aktuella företaget till en ER-rapport som använder den här datamodellen som datakälla.

5. Välj nod **enkät** .
6. Fortsätt att lägga till de obligatoriska fälten i den redigerbara datamodellen på samma sätt tills du har slutfört följande datamodellstruktur.

    | Sökväg för fält                                                    | Datatyp   | Fältbeteckning/returnerat värde |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Rot                                                          |             | Referenspunkten för att begära enkätdata. |
    | Root\\CompanyName                                             | Sträng      | Namnet på det aktuella företaget. |
    | Root\\ExecutionContext                                        | Registrera      | Information om formatkörning. |
    | Root\\ExecutionContext\\FormatName                            | Sträng      | Namnet på ER-formatet som körs. |
    | Root\\Questionnaire                                           | Postlista | Listan över enkäter |
    | Root\\Questionnaire\\Active                                   | Sträng      | Status för aktuella enkäten. |
    | Root\\Questionnaire\\Code                                     | Sträng      | Kod för aktuell aktuella enkäten. |
    | Root\\Questionnaire\\Description                              | Sträng      | Beskrivning för aktuella enkäten. |
    | Root\\Questionnaire\\QuestionnaireType                        | Sträng      | Typ för aktuella enkäten. |
    | Root\\Questionnaire\\QuestionOrder                            | Sträng      | Den numeriska ordningen för aktuella enkäten. |
    | Root\\Questionnaire\\ResultsGroup                             | Registrera      | De resulterande parametrarna för aktuella enkäten. |
    | Root\\Questionnaire\\ResultsGroup\\Code                       | Sträng      | Identifieringskoden för den aktuella resultatgruppen. |
    | Root\\Questionnaire\\ResultsGroup\\Description                | Sträng      | Beskrivning för aktuella resultatgruppen. |
    | Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Realtal        | Det maximala antal poäng som kan intjänas. |
    | Root\\Questionnaire\\Question                                 | Postlista | Listan med frågeställningar för den aktuella enkäten. |
    | Root\\Questionnaire\\Question\\CollectionSequenceNumber       | Heltal     | Sekvensnumret för den aktuella svarssamlingen. |
    | Root\\Questionnaire\\Question\\Id                             | Sträng      | Identifieringskoden för den aktuella frågeställningen. |
    | Root\\Questionnaire\\Question\\MustBeCompleted                | Sträng      | En flagga som anger om den aktuella frågeställningen måste besvaras. |
    | Root\\Questionnaire\\Question\\PrimaryQuestion                | Sträng      | En flagga som anger om den aktuella frågeställningen är primär. |
    | Root\\Questionnaire\\Question\\SequenceNumber                 | Heltal     | Sekvensnumret för den aktuella frågeställningen. |
    | Root\\Questionnaire\\Question\\Text                           | Sträng      | Texten för den aktuella frågeställningen. |
    | Root\\Questionnaire\\Question\\Answer                         | Postlista | Listan med svar för den aktuella frågeställningen. |
    | Root\\Questionnaire\\Question\\Answer\\CorrectAnswer          | Sträng      | En flagga som anger om det aktuella svaret är korrekt. |
    | Root\\Questionnaire\\Question\\Answer\\Points                 | Realtal        | De poäng som intjänas när det aktuella svaret väljs. |
    | Root\\Questionnaire\\Question\\Answer\\SequenceNumber         | Heltal     | Sekvensnumret för det aktuella svaret. |
    | Root\\Questionnaire\\Question\\Answer\\Text                   | Sträng      | Texten för det aktuella svaret. |

    I bilden nedan visas den färdiga redigerbara datamodellen på sidan **Datamodelldesigner**.

    ![Konfigurerad datamodell i ER-datamodelldesignern.](./media/er-quick-start1-model2.png)

7. Spara ändringarna.
8. Stäng sidan **datamodelldesigner**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Färdigställa datamodellens utformning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.
3. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
4. Välj **Ändra status** \> **Slutför**.

Status för version 1 av denna konfiguration ändras från **utkast** till **slutförd**. Version 1 kan inte längre ändras. Den här versionen innehåller den konfigurerade datamodellen och kan användas som grund för andra ER-konfigurationer. Version 2 av denna konfiguration skapas och har statusen **utkast**. Du kan redigera den här versionen för att justera datamodellen **enkät**.

![Versioner av den redigerbara konfigurationen på sidan Konfigurationer.](./media/er-quick-start1-model-configuration.png)

Mer information om versionshantering för ER-konfigurationer finns i [Översikt över elektroniska rapporter (ER)](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> Den konfigurerade datamodellen är din abstrakta representation av affärsdomänen **enkät** och innehåller inga relationer till artefakter som är specifika för Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Designa en modellmappning för den konfigurerade datamodellen

Som användare i rollen som elektronisk rapporteringsutvecklare måste du skapa en ny ER-konfiguration som innehåller en komponent för [modellmappning](general-electronic-reporting.md#data-model-and-model-mapping-components) för datamodellen **enkät**. Eftersom den här komponenten implementerar den konfigurerade datamodellen för Finance, är den Finance-specifik. Du måste konfigurera komponenten för modellmappning för att ange vilka programobjekt som ska användas för att fylla i den konfigurerade datamodellen med programdata vid körning. För att slutföra den här uppgiften måste du vara medveten om implementeringsinformationen för datastrukturen i affärsdomänen **enkät** i Finance.

Genom att slutföra stegen i avsnittet [Importera en ny konfiguration för modellmappning](#ImportModelMapping) som följer kan du importera den konfiguration av modellmappning som krävs från den angivna XML-filen. Du kan också slutföra stegen i avsnittet [Skapa en ny konfiguration för modellmappning](#CreateModelMapping) om du vill designa den här modellmappningen från början.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importera en ny konfiguration för modellmappning

1. Hämta filen [enkätmappning.version.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **enkätmappning.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny konfiguration för modellmappning](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Skapa en ny konfiguration av modellmappning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.
3. Välj **Skapa konfiguration**.
4. Gör följande i listrutan:

    1. I fältet **Nytt** väljer du **Modellmappning baserat på datamodellenkäter**.
    2. Ange **enkätmappning** i fältet **Namn**.
    3. I fältet **Definition av datamodell** välj definitionen **Rot**.
    4. Välj **Skapa konfiguration** för att skapa konfigurationen.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Designa en ny modellmappningskomponent

1. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmappning**.
2. Välj **designer** om du vill öppna listan över mappningar.
3. Välj den **enkätmappning** som automatiskt lades till för definitionen **Rot**
4. Välj **Designer** om du vill starta konfigurationen av den valda mappningen.

En ny mappning läggs automatiskt till för definitionen **rot**. Den här mappningen har riktningen **Till modell**. Denna mappning kan därför användas för att fylla i en datamodell med de data som krävs.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Lägga till datakällor för att öppna programtabeller

Du måste konfigurera datakällor för att få åtkomst till programtabellerna som innehåller enkätuppgifter.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Tabellregister**.
2. Lägg till en ny datakälla som ska användas för att komma åt KMCollection-registret, där varje post representerar en enda enkät:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I dialogrutan i fältet **Namn**, ange **enkät**.
    3. I fältet **Tabell** ange **KMCollection**.
    4. Ange alternativet **Fråga efter fråga** till **Ja**. Du kan sedan ange alternativet [filtrering](../../fin-ops/get-started/advanced-filtering-query-options.md) för det här registret i dialogrutan för systemfråga under körning.
    5. Klicka på **OK** om du vill lägga till den nya datakällan.

3. I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\registerposter**.
4. Lägg till en ny datakälla som ska användas för att komma åt KMQuestion-registret, där varje post representerar en enda fråga i en enkät:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I dialogrutan i fältet **Namn**, ange **Fråga**.
    3. I fältet **Tabell** ange **KMQuestion**.
    4. Klicka på **OK** om du vill lägga till den nya datakällan.

5. I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\registerposter**.
6. Lägg till en ny datakälla som ska användas för att komma åt KMAnswer-registret, där varje post representerar ett enda svar på en frågeställning i en enkät:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I fältet **Namn** ange **Svar**.
    3. I fältet **Tabell** ange **KMAnswer**.
    4. Klicka på **OK** om du vill lägga till den nya datakällan.

7. I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.
8. Lägg till ett nytt beräknat fält som ska användas för att komma åt en post i KMQuestionResultGroup-registret från alla poster i det överordnade KMCollection-registret:

    1. I fönstret **Datakällor** välj **Enkät**.
    2. Markera **Lägg till**.
    3. I dialogrutan i fältet **Namn** ange **\$ResultGroup**.
    4. Välj **Redigera recept**.
    5. I [ER-formelredigeraren](general-electronic-reporting-formula-designer.md), i fältet **Formel** ange **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** för att använda [sökväg](er-formula-language.md#Paths) för 1:n-relation mellan register KMCollection och KMQuestionResultGroup.
    6. Markera **Spara** och stäng sedan formelredigeraren.
    7. Klicka på **OK** om du vill lägga till nya beräknade fält.

9. I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.
10. Lägg till ett nytt beräknat fält som ska användas för att komma åt poster i KMQuestion-registret från alla poster i det överordnade KMCollectionQuestion-registret:

    1. I fönstret **Datakällor** välj **Enkät**.
    2. Expandera noden **\<relationer** som innehåller 1:n-relationer i KMCollection-registret.
    3. Välj relaterat **KMCollectionQuestion**-register och välj sedan **Lägg till**.
    4. I dialogrutan i fältet **Namn** ange **\$Fråga**.
    5. Välj **Redigera recept**.
    6. I formelredigeraren i fältet **Formel** ange **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** för att returnera lämpliga frågerader från KMQuestion-registret.
    7. Markera **Spara** och stäng sedan formelredigeraren.
    8. Klicka på **OK** om du vill lägga till nya beräknade fält.

11. I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.
12. Lägg till ett nytt beräknat fält som ska användas för att komma åt svarsposter i KMAnswer-registret från alla poster i det överordnade KMQuestion-registret:

    1. I fönstret **Datakällor** välj **enkät.\<Relations.KMCollectionQuestion.\$fråga** och välj sedan **Lägg till**.
    2. I dialogrutan i fältet **Namn** ange **\$Svar**.
    3. Välj **Redigera recept**.
    4. I formelredigeraren i fältet **Formel** ange **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** för att returnera lämpliga svarsrader från KMAnswer-registret.
    5. Markera **Spara** och stäng sedan formelredigeraren.
    6. Klicka på **OK** om du vill lägga till nya beräknade fält.

13. I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\register**.
14. Lägg till en ny datakälla som ska användas för att komma åt metoder i CompanyInfo-registret. Observera att metoden **find()** i det här registret returnerar en post som representerar ett företag för den aktuella Finance-instansen som den här mappningen anropas i kontexten för.

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I dialogrutan i fältet **Namn**, ange **CompanyInfo**.
    3. I fältet **Tabell** ange **CompanyInfo**.
    4. Klicka på **OK** om du vill lägga till den nya datakällan.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Lägga till datakällor för att öppna programuppräkningar

Du måste konfigurera datakällor för att få åtkomst till programuppräkningar och jämföra deras värden med värden i fälten för typen **uppräkning** i programtabellerna. Du måste använda resultatet av jämförelsen för att fylla i lämpliga fält i datamodellen.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Uppräkning**.
2. Lägg till en ny datakälla som ska användas för att komma åt värden i uppräkningen **EnumAppNoYes**:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I dialogrutan i fältet **Namn**, ange **EnumAppNoYes**.
    3. I fältet **Uppräkning** ange **NoYes**.
    4. Klicka på **OK** om du vill lägga till den nya datakällan.

3. I fönstret **Datakälltyper** välj **Dynamics 365 for Operations\\Uppräkning**.
4. Lägg till en ny datakälla som ska användas för att komma åt värden i uppräkningen **KMCollectionQuestionMode**:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. Ange **KMCollectionQuestionMode** i dialogrutan i fältet **namn**.
    3. I fältet **Uppräkning** ange **KMCollectionQuestionMode**.
    4. Klicka på **OK** om du vill lägga till den nya datakällan.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Lägga till ER-etiketter för att generera en rapport på ett angivet språk

Du kan lägga till ER-etiketter för att konfigurera vissa av dina datakällor för att returnera värden som är beroende av språket som definieras i kontexten för modellmappningens anrop.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du **Svar** och sedan **Redigera**.
2. Aktivera fältet **etikett**.
3. Välj **översätt**.
4. I dialogrutan **Textöversättning** gör följande:

    1. I fältet **Etikett-ID** anger du **PositiveAnswer**.
    2. I fältet **text på standardspråk** anger du **Ja**.
    3. Välj **översätt**.
    4. I fältet **Etikett-ID** anger du **NegativeAnswer**.
    5. I fältet **text på standardspråk** anger du **Nej**.
    6. Välj **översätt**.

5. Stäng dialogrutan **textöversättning**.
6. Välj **Avbryt**.

![Lägga till ER-etiketter för redigerbar modellmappning.](./media/er-quick-start1-adding-labels.png)

Du har bara angett ER-etiketter för standardspråket. Information om hur ER-etiketter kan översättas till andra språk finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Lägga till en datakälla som transformerar resultaten från att jämföra uppräkningsvärden till ett textvärde

Eftersom du måste transformera resultaten av jämförelsen mellan uppräkningsvärden och textvärden flera gånger för differenskällor kan det vara en bra idé att konfigurera den här logiken som en enda datakälla. Om du vill kunna använda datakällan igen måste du dock konfigurera den som parametriserad datakälla. För mer information, se [Stöd parameteranrop till ER-datakällor för beräknad fälttyp](er-calculated-field-type.md).

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Allmänt\\Tom behållare**.
2. Lägg till en ny datakälla för behållare:

    1. I fönstret **Datakällor** välj **Lägg till rot**.
    2. I dialogrutan i fältet **Namn**, ange **Stödprocess**.
    3. Klicka på **OK** om du vill lägga till den nya datakällan för behållare.

3. I fönstret **Datakälltyper** välj **Funktioner\\Beräknade fält**.
4. Lägg till en ny datakälla:

    1. Välj **Stödprocess** i fönstret **Datakällor**.
    2. Markera **Lägg till**.
    3. Ange **NoYesEnumToString** i dialogrutan i fältet **namn**.
    4. Välj **Redigera recept**.
    5. Välj **parametrar** i formelredigeraren.
    6. Följ dessa steg för att ange parametrar för det konfigurerade uttrycket:

        1. Välj **Ny**.
        2. I dialogrutan i fältet **Namn**, ange **Argument**.
        3. I fältet **Typ** välj datatypen **Boolesk**.
        4. Välj **OK**.

    7. I fältet **Formel** ange **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** du vill returnera texten i motsvarande ER-etikett, beroende på språket för körningskontexten och värdet för den angivna parametern.
    8. Markera **Spara** och stäng sedan formelredigeraren.
    9. Klicka på **OK** om du vill lägga till den nya datakällan.

![Konfigurerad modellmappning i ER-modellmappningsdesignern.](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Binda datakällor till fält för datamodell

Du måste binda de konfigurerade datakällorna till fälten i datamodellen för att ange hur datamodellen ska fyllas i med programdata vid körning.

1. På sidan **Modellmappingsdesigner** i fönstret **Datamodell** väljer du **CompanyName**.
2. I fönstret **Datakällor** expanderar **CompanyInfo** och följer sedan de här stegen:

    1. Expandera noden **CompanyInfo.find()** som representerar **find()**-metoden i CompanyInfo-registret.
    2. Välj **CompanyInfo.find().Name**.
    3. Välj **Bind** om du vill fylla i namnet på det företag som den konfigurerade modellmappningen anropas i kontexten vid körning.

3. I fönstret **Datamodell** välj **Enkät**.
4. I fönstret **Datakällor** välj **Enkät** och välj sedan **Bind** för att fylla i enkätposter.
5. I fönstret **Datamodell** expanderar du **Enkät** och följer sedan de här stegen:

    1. I fönstret **Datamodell** välj **Aktiv**.
    2. I fönstret **Datamodell** välj **Redigera**.
    3. I fältet **Formel** ange **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** om du vill fylla det textberoende och språkberoende resultatet i jämförelsen mellan uppräkningsvärden.

6. Fortsätt att binda datakällor till datamodellfält på samma sätt tills du uppnår följande resultat.

    | Sökväg för fält                                              | Datatyp   | Åtgärd | Bindningsuttryck |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Sträng      | Bind   | CompanyInfo.'find()'.Name |
    | Enkät                                           | Postlista | Bind   | Enkät |
    | Etikett\\Aktiv                                   | Sträng      | Redigera   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Enkät\\Kod                                     | Sträng      | Bind   | \@.kmCollectionId |
    | Enkät\\Beskrivning                              | Sträng      | Bind   | \@.Description |
    | Questionnaire\\QuestionnaireType                        | Sträng      | Bind   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionnaire\\QuestionOrder                            | Sträng      | Redigera   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "Slumpmässig (procent i enkät)",<br>EnumAppQuestionOrder.RandomGroup, "Slumpmässig (procent i resultatgrupper)",<br>EnumAppQuestionOrder.Sequence, "Sekventiell",<br>"") |
    | Questionnaire\\ResultsGroup                             | Registrera      |        | |
    | Questionnaire\\ResultsGroup\\Code                       | Sträng      | Bind   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionnaire\\ResultsGroup\\Description                | Sträng      | Bind   | \@.'\$ResultGroup'.description |
    | Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Realtal        | Bind   | \@.'\$ResultGroup'.maxPoint |
    | Questionnaire\\Question                                 | Postlista | Bind   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionnaire\\Question\\CollectionSequenceNumber       | Heltal     | Bind   | \@.answerCollectionSequenceNumber |
    | Questionnaire\\Question\\Id                             | Sträng      | Bind   | \@.kmQuestionId |
    | Questionnaire\\Question\\MustBeCompleted                | Sträng      | Redigera   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\PrimaryQuestion                | Sträng      | Bind   | \@.parentQuestionId |
    | Questionnaire\\Question\\SequenceNumber                 | Heltal     | Bind   | \@.SequenceNumber |
    | Questionnaire\\Question\\Text                           | Sträng      | Bind   | \@.'\$Question'.text |
    | Questionnaire\\Question\\Answer                         | Postlista | Bind   | \@.'\$Question'.'\$Answer' |
    | Questionnaire\\Question\\Answer\\CorrectAnswer          | Sträng      | Redigera   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\Answer\\Points                 | Realtal        | Bind   | \@.point |
    | Questionnaire\\Question\\Answer\\SequenceNumber         | Heltal     | Bind   | \@.sequenceNumber |
    | Questionnaire\\Question\\Answer\\Text                   | Sträng      | Bind   | \@.text |

    Bilden nedan visar det slutliga tillståndet för den konfigurerade modellmappningen på sidan **modellmappningsdesigner**.

    ![Helt konfigurerad modellmappning i ER-modellmappningsdesignern.](./media/er-quick-start1-mapping2.png)

7. Spara ändringarna.
8. Stäng sidan **modellmappningsdesigner**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Färdigställa modellmappningens utformning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmappning**.
3. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
4. Välj **Ändra status** \> **Slutför**.

Status för version 1.1 av denna konfiguration ändras från **utkast** till **slutförd**. Version 1.1 kan inte längre ändras. Den här versionen innehåller den konfigurerade modellmappningen och kan användas som grund för andra ER-konfigurationer. Version 1.2 av denna konfiguration skapas och har statusen **utkast**. Du kan redigera den här versionen för att justera konfigurationen **enkätmappningen**.

![Versioner av den redigerbara ER-konfigurationen på sidan Konfigurationer.](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> Den konfigurerade modellmappningen är din Finance-specifika implementering av den abstrakta datamodellen som representerar affärsdomän **enkät**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Utforma en mall för en anpassad rapport

ER-ramverket använder fördefinierade mallar för att generera rapporter i Microsoft Office-format (Excel-arbetsböcker eller Word-dokument). Medan den rapport som krävs skapas fylls en mall i med de data som krävs enligt det konfigurerade dataflöden. Därför måste du först designa en mall för din anpassade rapport. Den här mallen måste vara utformad som en Excel-arbetsbok, vars struktur representerar layouten i en anpassad rapport. Du måste namnge varje Excel-artikel som du tänker fylla i med nödvändiga data.

1. Hämta filen [enkätrapportmall.xslx](https://download.microsoft.com/download/3/8/2/382c3cf0-87bb-473f-b7bb-3015b4facb74/Questionnaires_report_template.xlsx) och spara den på den lokala datorn.
2. Öppna filen i Excel och granska arbetsbokens struktur.

Som visas i bilden nedan har den hämtade mallen utformats för att skriva ut angivna enkäter som visar en enkätfrågeställningar tillsammans med lämpliga svar.

![Excel-mall för att skriva ut angivna enkäter.](./media/er-quick-start1-template-layout.png)

Excel-namn har lagts till i den här mallen för ifyllning av enkätinformation. Du kan använda namnhanteraren för att granska Excel-namnen.

![Använda namnhanteraren för att granska Excel-namn i den medföljande Excel-mallen.](./media/er-quick-start1-template-names.png)

Rapportetiketter har lagts till som fast text på engelska. Du kan ersätta rapportetiketterna med nya Excel-namn som fyller i etiketterna med språkberoende text genom att använda etiketterna för återställningsformat [etikett](#AddMmLabels), på samma sätt som för språkberoende uttryck i den konfigurerade modellmappningen. I det här fallet måste du lägga till ER-etiketter i det redigerbara återställningsformatet.

Som visas i bilden nedan har det anpassade rapporthuvudet angetts för att Excel ska kunna göra sidindelning.

![Anpassat rapportsidhuvud i den angivna Excel-mallen.](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Designa ett format

Som användare i rollen funktionell konsult för elektronisk rapportering måste du skapa en ny ER-konfiguration som innehåller komponenten [format](general-electronic-reporting.md#FormatComponentOutbound). Du måste konfigurera formatkomponenten för att ange hur en rapportmall ska fyllas i med nödvändiga data vid körning.

Genom att slutföra stegen i avsnittet [Importera en utformad formatkonfiguration](#FormatImport) kan du importera det format som krävs från den angivna XML-filen. Du kan också slutföra stegen i avsnittet [Skapa en ny formatkonfiguration](#FormatCreate) om du vill designa det här formatet från början.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Importera en utformad formatkonfiguration

1. Hämta filen [enkätformat.version.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **enkätformat.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

Om du vill fortsätta hoppar du över nästa procedur, [skapa en ny formatkonfiguration](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Skapa en ny formatkonfiguration
 
1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätmodell**.
3. Välj **Skapa konfiguration**.
4. Gör följande i listrutan:

    1. I fältet **Nytt** väljer du **Format baserat på datamodellenkäter**.
    2. Ange **enkätrapport** i fältet **Namn**.
    3. I fältet **Datamodellversion** välj **1**.

        > [!NOTE]
        > - Om du väljer en specifik version av basdatamodellen, kommer strukturen för motsvarande version av datamodellen att presenteras för dig som strukturen för datakällan **Modell** i det format som skapas.
        > - Fältet kan vara tomt. I så fall visas strukturen på **utkast**-versionen av datamodellen som en struktur för datakällan **modell** i det format som skapas. Du kan sedan justera modellen och omedelbart se justeringarna i formatet. Den här metoden kan förbättra effektiviteten hos ER-lösningen när du konfigurerar datamodellen, modellmappningen och formaterar samtidigt.
        > - Om du väljer en specifik version av basdatamodellen kan du senare växla till att använda **utkast**-versionen när du börjar redigera ett format.

    4. I fältet **Definition av datamodell** välj definitionen **Rot**.

5. Välj **Skapa konfiguration** för att skapa konfigurationen.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Importera rapportmall

1. På sidan **konfigurationer** i konfigurationsträdet väljer du **enkätrapport**.
2. Välj **Designer** om du vill starta konfigureringen av ett anpassat format.
3. På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Importera** \> **Importera från Excel**.
4. Gör följande i dialogrutan:

    1. Välj **Lägg till mall**.
    2. Sök och markera den lokalt sparade filen **enkätrapportmall.xslx** och välj sedan **Öppna**.
    3. Välj **OK** för att importera mallen.

    ![Importera en rapportmall.](./media/er-quick-start1-template-import.png)

Formatelementet **Excel\\File** läggs automatiskt till i det redigerbara formatet som ett rotelement. Dessutom läggs formatelementet **Excel\\Range** eller formatelementet **Excel\\Cell** automatiskt till för varje identifierat Excel-namn i den importerade mallen. Formatet **Excel\\Header** som har kapslade **Sträng**-element läggs automatiskt till för att avspegla rubrikinställningarna för den importerade mallen.

![Formatstruktur som innehåller automatiskt tillagda element i ER-funktionsdesignern.](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Konfigurera ett format

1. På sidan **Formatdesigner** i formatträdet, välj rotelementet **Excel**.
2. Gå till fliken **Format** på sidans högra sida, ange en rapport i fältet **Namn** anger <a name="AddFormatRootElement"></a>**rapport**.
3. I fältet **Språkinställningar** välj **Användarinställningar** om du vill köra rapporten på användarens önskade språk.
4. I fältet **Kulturinställningar** välj **Användarinställningar** om du vill köra rapporten i användarens önskade kultur.

    Information om hur du anger språk och kulturkontexter för en ER-process finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).

    ![Konfigurera språk- och kulturinställningar för den designade rapporten i ER-funktionsdesignern.](./media/er-quick-start1-template-format-structure1.png)

5. Expandera rotnoden i formatträdet och välj sedan **ResultsGroup**.
6. På fliken **Format** i fältet **Replikeringsriktning** välj **Ingen replikering**, eftersom du inte förväntar dig att ha flera resultatgrupper för en enda enkät.

    ![Definiera riktning för replikering för områdesformatelement i ER-funktionsdesignern.](./media/er-quick-start1-template-format-structure2.png)

7. Välj **Spara**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Definiera databindningen för en rapportrubrik

Du måste ange en databindning för ett formatelement som används för att fylla i rubriken för en genererad rapport.

1. På sidan **Formatdesigner** på fliken **Mappning** till höger väljer du elementet **Report\\ReportTitle**.
2. Välj **Redigera recept**.
3. Välj **översätt** i formelredigeraren.
4. I dialogrutan **Textöversättning** gör följande:

    1. I fältet **Etikett-ID** anger du **ReportTitle**.
    2. I fältet **text på standardspråk** anger du **enkätrapport**.
    3. Välj **Översätt** och välj sedan **Spara**.
    4. Välj **Översätt** om du vill stänga dialogrutan **textöversättning**.

5. Stäng formelredigeraren.

    ![Konfigurera bindningen så att den fyller i rubriken i en genererad rapport.](./media/er-quick-start1-add-report-title-label.png)

Du kan använda den här tekniken för att göra alla andra etiketter för den aktuella mallspråkberoende. Information om hur tillagda etiketter för en enskild ER-konfiguration kan översättas till alla språk som stöds finns i [utforma flerspråkiga rapporter](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Granska modellens datakälla

1. På sidan **Formatdesigner** på fliken **Mappning** välj datakällan <a name="ModelDSName"></a>**modell** som representerar basdatamodellen för det här ER-formatet.
2. Välj **Redigera**.
3. Granska informationen i dialogrutan **Egenskaper för datakälla**. Den här datakällan representerar version 1 av den datamodellkomponent för **enkäter** som finns i ER-konfigurationen för **enkätmodell**.

![Egenskaper för modelldatakällan i ER-funktionsdesignern.](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Binda formatelement till fält för datakällor

Om du vill ange hur en mall ska fyllas i vid körning måste du binda varje formatelement som är associerat med ett lämpligt Excel-namn till ett enda fält i det här formatets datakälla.

1. På sidan **Formatdesigner** i formatträdet, välj formatelementet **Report\\CompanyName**.
2. På fliken **mappning** välj datakällfältet **model.CompanyName** på typen **sträng**.
3. Välj **Bind** om du vill ange ett företagsnamn i en mall.
4. I formatträdet, välj elementet **Report\\Questionnaire**.
5. På fliken **mappning** välj datakällfältet **model.Questionnaire** på typen **postlista**.
6. Välj **bind**.
7. Välj **Visa detaljer** om du vill visa mer information för formatelement.

    Områdesformatelement **enkät** intervall konfigureras som vertikalt replikerat. När den är bunden till en datakälla för typen **postlista** upprepas det korrekta intervallet **enkät** för Excel-mallen för varje post i den bundna datakällan.
 
    ![Binda områdesformatelement för enkät till lämpliga datakällor för postlista i ER-funktionsdesignern.](./media/er-quick-start1-bindings1.png)

    Eftersom området **enkät** för Excel-mallen definieras mellan raderna 5 till 14, upprepas dessa rader för varje rapporterad enkät.

    ![De rader i Excel-mallen som ska upprepas i en genererad rapport för varje post i postlistans datakällor.](./media/er-quick-start1-template-questionnaire-range.png)

8. Konfigurera liknande bindningar för de återstående formatelementen enligt beskrivningen i följande tabell.

    > [!NOTE]
    > I den här tabellen förutsätter informationen i kolumnen "sökväg till datakälla" att den [relativa sökvägen](relative-path-data-bindings-er-models-format.md) ER-funktion är aktiverad.

    | Formatera element för sökväg                                      | Sökväg för datakälla |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionnaire                                     | **model.Questionnaire** |
    | Excel\\Questionnaire\\Active                             | **\@.Active**, where **\@** is **model.Questionnaire** |
    | Excel\\Questionnaire\\Code                               | **\@.Code** |
    | Excel\\Questionnaire\\Description                        | **\@.Description** |
    | Excel\\Questionnaire\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionnaire\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionnaire\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionnaire\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionnaire\\Question                           | **\@.Question** |
    | Excel\\Questionnaire\\Question\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question** |
    | Excel\\Questionnaire\\Question\\Id                       | **\@.Id** |
    | Excel\\Questionnaire\\Question\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionnaire\\Question\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionnaire\\Question\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionnaire\\Question\\Text                     | **\@.Text** |
    | Excel\\Questionnaire\\Question\\Answer                   | **\@.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionnaire\\Question\\Answer\\Text             | **\@.Text** |

9. Välj **Spara** när du är klar.

Bilden nedan visar det slutliga tillståndet för den konfigurerade databindningar på sidan **Formatdesigner**.

![Konfigurerade databindningar i ER-funktionsdesignern.](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> Hela mängden med angivna datakällor och bindningar representerar en formatmappningskomponent i det konfigurerade formatet. Den här formatmappningen anropas när du kör det konfigurerade formatet för rapportgenerering.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Kör ett format som skapats från ER

Du kan nu köra ett utformat format för testning från sidan **konfigurationer**.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfiguration** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.
3. Välj **Designer** för formatversionen som har statusen **utkast**.
4. Välj **Formatdesigner** på sidan **Kör**.
5. I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
6. Bekräfta filtreringsåtgärden genom att välja **OK**.
7. Klicka på **OK** om du vill köra rapporten.
8. Granska den genererade rapporten.

Som [standard](electronic-reporting-destinations.md#default-behavior) levereras en genererad rapport som en Excel-fil som du kan hämta. I följande illustrationer visas två sidor i den genererade rapporten i Excel-format.

![Exempel på en genererad rapport i Excel-format, sida 1.](./media/er-quick-start1-report1a.png)

![Exempel på en genererad rapport i Excel-format, sida 2.](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Justera ett utformat format

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Ändra ett format för att ändra namnet på ett skapat dokument

Som standard namnges ett genererat dokument med hjälp av den aktuella användarens alias. Genom att ändra formatet kan du ändra det här beteendet så att ett genererat dokument namnges baserat på din anpassade logik. Namnet på ett dokument kan till exempel baseras på dagens datum och aktuell tid och på rapportens titel.

1. På sidan **Formatdesigner** välj rotobjekt **Rapport**.
2. På fliken **Mappning** välj **Redigera filnamn**.
3. I fältet **Formel** ange **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.
4. Markera **Spara** och stäng sedan formelredigeraren.
5. Välj **Spara**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Ändra ett format för att ändra ordning på frågeställningarna

Frågeställningarna ordnas inte korrekt i en genererad rapport. Du kan ändra ordningen genom att ändra formatet.

1. På sidan **Formatdesigner** välj rotobjekt **Rapport**.
2. På fliken **Mappning** i formatträdet, expandera **Report\\Questionnaire\\Question**.

    ![Element i frågeformat för typen Område i ER-funktionsdesignern.](./media/er-quick-start1-bindings3.png)

3. På fliken **Mappning** välj **model.Questionnaire**.
4. Välj **Lägg till** \> **funktioner\\beräknat fält** och skriv sedan i fältet **Name** **OrderedQuestions**.
5. Välj **Redigera recept**.
6. I formelredigeraren i fältet **Formel** anger du **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** om du vill beställa en lista med frågeställningar i den aktuella enkäten utifrån sekvensordernumret.
7. Markera **Spara** och stäng sedan formelredigeraren.
8. Välj **OK** för att slutföra posten för ett nytt beräknat fält.
9. På fliken **Mappning** välj **model.Questionnaire.OrderedQuestions**.
10. I formatträdet, välj **Excel\\Questionnaire\\Question**.
11. Välj **Bind** och bekräfta att den aktuella sökvägen **model.Questionnaire.Questions** ersätts av den nya sökvägen **model.Questionnaire.OrderedQuestions** i alla bindningar för kapslade element.
12. Välj **Spara**.

![Binda frågeformatelementet till den konfigurerade OrderedQuestions-datakällan i ER-funktionsdesignern.](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Kör ett ändrat format från ER

Du kan nu köra ett ändrat format för testning från ER-ramverket.

1. Välj **Formatdesigner** på sidan **Kör**.
2. I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
3. Bekräfta filtreringsåtgärden genom att välja **OK**.
4. Klicka på **OK** om du vill köra rapporten.
5. Granska den genererade rapporten.

Följande bild visar en genererad rapport i Excel-format där frågeställningarna har beställts på rätt sätt.

![Genererad rapport i Excel-format med korrekt ordnade frågeställningar.](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Slutför formatdesignen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.
3. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
4. Välj **Ändra status** \> **Slutför**.

Status för version 1.1 av denna konfiguration ändras från **utkast** till **slutförd**. Version 1.1 kan inte längre ändras. Den här versionen innehåller det konfigurerade formatet och kan användas för att skriva ut din anpassade rapport. Version 1.2 av denna konfiguration skapas och har statusen **utkast**. Du kan redigera den här versionen för att justera formatet för rapporten **enkät**.

![Redigerbar ER-konfiguration på sidan Konfigurationer.](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> Det konfigurerade formatet är din design av **enkät**-rapporten och innehåller inga relationer till de Finance-specifika artefakter.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Utveckla programartefakter för att anropa den utformade rapporten

Som användare i rollen systemadministratör måste du utveckla en ny logik så att det konfigurerade ER-formatet kan anropas från programmets användargränssnitt för att skapa din anpassade rapport. För närvarande erbjuder ER inte någon möjlighet att konfigurera den här typen av logik. Därför krävs en del konstruktionsarbete. 

För att utveckla den nya logiken måste du distribuera en topologi som stöder kontinuerlig version. Mer information finns i [distribuera topologier som stöder kontinuerlig automatisering av bygga och testa](../perf-test/continuous-build-test-automation.md). Du måste också ha tillgång till utvecklingsmiljön för den här topologin. Mer information om tillgängliga ER API:er finns i [ER-ramverks-API](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Modifiera källkod

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Lägga till en datakontraktklass

Lägg till den nya klassen **QuestionnairesErReportContract** till ditt Microsoft Visual Studio-projekt och skriv kod som anger det datakontrakt som ska användas för att köra det konfigurerade ER-formatet.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Lägg till en UI-skaparklass

Lägg till den nya **QuestionnairesErReportUIBuilder**-klassen i Visual Studio-projektet och skriv kod för att skapa en dialogruta för körning som ska användas för att slå upp formatmappnings-ID:t för det återställningsformat som måste köras. Den angivna koden söker bara efter ER-format som innehåller en datakälla för den typ av **Datamodell** som refererar till **[enkät](#DataModeName)** datamodell med definitionen **[Rot](#RootDefinitionName)**.

> [!NOTE]
> Alternativt kan du använda ER-integreringspunkter för att filtrera ER-format. Mer information finns i [API för att visa sökning efter formatmappningar](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Lägga till en dataleverantörsklass

Lägg till den nya klassen **QuestionnairesErReportDP** till ditt Microsoft Visual Studio-projekt och skriv kod som introducerar den dataleverantör som ska användas för att köra det konfigurerade ER-formatet. Den angivna koden inkluderar bara datakontraktet för denna dataleverantör.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Lägga till en etikettfil

Lägg till den nya etikettfilen **QuestionnairesErReportLabels\_en-US** till ditt Visual Studio-projekt och ange följande etiketter för nya användargränssnittsresurser:

- Etiketten **\@QuestionnairesReport** för ett nytt menyalternativ som innehåller följande text på amerikansk engelska (en-US): **enkätrappoprt (drivs av ER)**
- Etiketten **\@QuestionnairesReportBatchJobDescription** för en batch-jobbtitel om ett valt ER-format schemaläggs för körning av ett batchjobb

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Lägg till en rapporttjänstklass

Lägg till den nya klassen **QuestionnairesErReportService** i Visual Studio-projektet och skriv kod som anropar ett ER-format, identifierar den med ett format mappnings-ID och tillhandahåller ett datakontrakt som parameter.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

När du måste använda ett ER-format som kör programdata måste du konfigurera en datakälla för typen **datamodellen** i formatmappningen. Den här datakällan refererar till en specifik del av den angivna datamodellen genom att använda en enda rotdefinition. När ER-formatet körs anropar det denna datakälla för att komma åt lämplig ER-modellmappning som konfigurerats för en viss modell och rotdefinition.

All information som du kan förbereda i källkoden och butiken som en del av datakontraktet kan överföras till ER-format med hjälp av en ER-modellmappning av den här typen. I ER-modellmappningen måste du konfigurera en datakälla för **objekt** typen som refererar till **[QuestionnairesErReportContract](#DataContractClass)**. Om du vill identifiera en modellmappning måste du ange en datakälla som anropar den här modellmappningen. I den angivna koden är denna datakälla angiven av **ERModelDataSourceName** konstanten som har värdet **[modell](#ModelDSName)**. Om du vill identifiera vilken datakälla som används för att visa datakontraktet i modellmappningen måste du ange namnet på en datakälla. I den angivna koden är detta namn angivet av konstanten **ParametersDataSourceName** som har värdet <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> I en ny miljö kan du behöva uppdatera ER-metadata så att den här typen av klass finns tillgänglig i ER-modellmappningsdesigner. Mer information finns i [Konfigurera ER-ramverket](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Lägg till en rapportkontrollantklass

Lägg till den nya klassen **QuestionnairesErReportController** till ditt Visual Studio projekt och skriv kod som kör ett ER-format i antingen synkront läge eller batchläge, vilket du föredrar, i den dialogruta som har skapats baserat på logiken i den angivna klassen **QuestionnairesErReportUIBuilder**.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Lägg till ett menyalternativ

Lägg till det nya menyalternativet **QuestionnairesErReport** till ditt Visual Studio-projektet. I egenskapen **Objekt** hänvisar det här menyalternativet till klassen **QuestionnairesErReportController** och används för att ange en användarbehörighet för att välja och köra ett ER-format. I egenskapen **etikett** refererar det här menyalternativet till etiketten **\@QuestionnairesReport** som du skapade tidigare, så att korrekt text visas i programgränssnittet.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Lägg till ett menyalternativ till en meny

Lägg till den befintliga **KM**-menyn i Visual Studio-projektet. Du måste lägga till ett nytt **QuestionnairesErReport**-objekt av typen **Utdata** i den här menyn. Det här objektet måste referera till menyartikeln **QuestionnairesErReport** som beskrivs i föregående avsnitt.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Bygga ett Visual Studio-projekt

Bygg ditt projekt för att göra ett nytt menyalternativ tillgängligt för användare.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Kör ett format från programmet

1. Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.

    ![Att välja menyalternativet enkätrapport (drivs av ER) i modulen Enkät för att köra det konfigurerade ER-formatet.](./media/er-quick-start1-application-menu-modified.png)

2. I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.
3. Välj **OK**.
4. I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
5. Bekräfta filtreringsåtgärden genom att välja **OK**.
6. Klicka på **OK** om du vill köra rapporten.

    ![Ange urvalskriterier i dialogrutan för Elektronisk rapport.](./media/er-quick-start1-report-run-dialog-page.png)

7. Granska den genererade rapporten.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Finjustera en designad ER-lösning

Du kan ändra den konfigurerade ER-lösningen så att den använder dataleverantörsklassen som du utvecklade för att få åtkomst till detaljer i det ER-format som körs och så att det anger namnet på detta ER-format i en genererad rapport.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Ändra modellmappning

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Lägga till datakällor för att öppna ett datakontraktobjekt

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätmappning**.
3. Välj **Designer** om du vill öppna sidan **Modell till mappning av datakälla**.
4. Välj **Designer** om du vill öppna den markerade mappningen i modellmappningsdesigner.
5. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Objekt**.
6. I fönstret **Datakällor** välj **Lägg till rot**.
7. I dialogrutan i fältet **Namn** ange **[RunTimeParameters](#DataContractDSName)**, som definieras i källkoden för klassen **QuestionnairesErReportService**.
8. I fältet **Klass** ange **[QuestionnairesErReportContract](#DataContractClass)**, som har kodats tidigare.
9. Välj **OK**.
10. Expandera **RunTimeParameters**.

Den tillagda datakällan innehåller information om post-ID för den ER-formatmappning som körs.

![Tillagd datakälla i ER-modellmappningsdesignern.](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Lägga till en datakälla för åtkomst av mappningsposter för ER-format

Fortsätt att redigera den valda modellmappningen genom att lägga till en datakälla för att komma åt mappningsposter för ER-format.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Tabellregister**.
2. I fönstret **Datakällor** välj **Lägg till rot**.
3. I dialogrutan i fältet **Namn**, ange **ER1**.
4. I fältet **Tabell** ange **ERFormatMappingTable**.
5. Välj **OK**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Lägga till en datakälla för åtkomst av formatmappningsposter för ett ER-format som körs

Fortsätt att redigera den valda modellmappningen genom att lägga till en datakälla för att komma åt formatmappningsposter för det ER-format som körs.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Funktioner\\Beräknade fält**.
2. I fönstret **Datakällor** välj **Lägg till rot**.
3. I dialogrutan i fältet **Namn**, ange **ER2**.
4. Välj **Redigera recept**.
5. I formelredigeraren i fältet **Formel** ange **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Markera **Spara** och stäng sedan formelredigeraren.
7. Välj **OK**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Ange namnet på det ER-format som körs i datamodellen

Fortsätt att redigera den valda modellmappningen så att namnet på det ER-format som körs anges i datamodellen.

1. På sidan **Modellmappingsdesigner** i fönstret **Datamodell** expandera **ExecutionContext** och välj sedan **ExecutionContext\\FormatName**.
2. I fönstret **Datamodell** välj **Redigera** för att konfigurera en databindning för den valda datamodellens fält.
3. I formelredigeraren i fältet **Formel** anger du **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.
4. Markera **Spara** och stäng sedan formelredigeraren.

Eftersom du använde fältet **FormatName** visar den konfigurerade modellmappningen namnet på ett ER-format som anropar modellmappningen under körningen.

![Binda datamodellfältet till metoden för den tillagda datakällan i ER-modellmappningsdesignern.](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Färdigställa modellmappningens utformning

1. På sidan **Modellmappningsdesigner** välj **Spara**.
2. Stäng sidan.
3. Stäng sidan modellmappningar.
4. På sidan **konfigurationer** i konfigurationsträdet, se till att konfigurationen **enkätmappning** fortfarande är vald. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
5. Välj **Ändra status** \> **Slutför**.

Status för version 1.2 av denna konfiguration ändras från **utkast** till **slutförd**. Version 1.2 kan inte längre ändras. Den här versionen innehåller den konfigurerade modellmappningen och kan användas som grund för andra ER-konfigurationer. Version 1.3 av denna konfiguration skapas och har statusen **utkast**. Du kan redigera den här versionen för att justera modellmappningen **enkät**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Ändra ett format

Du kan ändra det konfigurerade ER-formatet så att namnet visas i sidfoten i en rapport som genereras när ER-formatet körs.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Lägg till ett nytt formatelement.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.
3. Välj **Designer**.
4. På sidan **Formatdesigner** välj rotobjekt **Rapport**.
5. Välj **Lägg till** om du vill lägga till ett nytt kapslat formatelement för det markerade rotobjektet **rapport**.
6. Välj **Excel\\Footer**.
7. I fältet **Namn** ange **Sidfot**.
8. Markera **Report\Footer** och välj sedan **Lägg till**.
9. Välj **Text\\String**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Bind det tillagda formatelementet

1. På sidan **Formatdesigner** på fliken **Mappning** i formatträdet för det aktiva elementet **Footer\\String** välj **Redigera formel**.
2. I formelredigeraren i fältet **Formel** ange **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.
3. Markera **Spara** och stäng sedan formelredigeraren.
4. Välj **Spara**.

Det konfigurerade formatet har nu ändrats så att namnet infogas i sidfoten i en genererad rapport med hjälp av elementet **Footer\\String**.

![Lägga till elementet Sidfotsformat i det konfigurerade formatet i ER-åtgärdsdesignern.](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Slutför formatdesignen

1. Stäng sidan **Formatdesigner**.
2. På sidan **konfigurationer** i konfigurationsträdet, se till att konfigurationen **enkätrapport** fortfarande är vald. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
3. Välj **Ändra status** \> **Slutför**.

Status för version 1.2 av denna konfiguration ändras från **utkast** till **slutförd**. Version 1.2 kan inte längre ändras. Den här versionen innehåller det konfigurerade format och kan användas som grund för andra ER-konfigurationer. Version 1.3 av denna konfiguration skapas och har statusen **utkast**. Du kan redigera den här versionen för att justera rapporten **enkät**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Kör ett format från programmet

1. Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.
2. I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.
3. Välj **OK**.
4. I dialogrutan **ER-parametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
5. Bekräfta filtreringsåtgärden genom att välja **OK**.
6. Klicka på **OK** om du vill köra rapporten.
7. Granska den genererade rapporten i Excel-format.

Observera att den genererade rapportens sidfot innehåller namnet på det ER-format som användes för att generera den.

![Genererad rapport i Excel-format.](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Kör ett format från ER

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **enkätmodell** och väljer sedan **enkätrapport**.
3. Klicka på **Kör** i åtgärdsfönstret.
4. I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
5. Bekräfta filtreringsåtgärden genom att välja **OK**.
6. Klicka på **OK** om du vill köra rapporten.
7. Granska den genererade rapporten i Excel-format.

Observera att den genererade rapportens sidfot inte innehåller namnet på ER-formatet som användes för att generera den, eftersom datakontraktets objekt inte skickades till modellmappningen vid körning när det anropades av det ER-format som kördes från ER.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Konfigurera ett formatmål för förhandsvisning på skärmen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsmål**.
2. På sidan **Destination för elektronisk rapportering** lägger du till en målpost för det konfigurerade ER-formatet **enkätrapport**.
3. På snabbfliken **Filmål** ange **Skärm** [destination](er-destination-type-screen.md) för formatkomponenten **rapport** som har [lagts till](#AddFormatRootElement) som rotelement för det konfigurerade ER-formatet **enkätrapport**.
4. På snabbfliken **inställningar av PDF-konvertering** konfigurera destinationen för att konvertera en rapport till [PDF-format](electronic-reporting-destinations.md#OutputConversionToPDF) som använder sidorienteringen **liggande**.

![Konfigurera det anpassade skärmmålet för ER-format på målsidan för elektronisk rapportering.](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Kör ett format från programmet för att förhandsgranska det som ett PDF-dokument

1. Gå till **Enkät** \> **Design** \> **Enkätrapport (drivs av ER)**.
2. I dialogrutan i fältet **Formatmappning** välj **Enkätrapport**.
3. Välj **OK**.
4. I dialogrutan **Elektroniska rapportparametrar** på snabbfliken **Poster som ska ingå** konfigurerar du filtreringsalternativet så att bara enkäten **SBCCrsExam** ingår.
5. Bekräfta filtreringsåtgärden genom att välja **OK**.

    På snabbfliken **destinationer** ser du att fältet **resultat** är angivet till **skärm**. Om du vill ändra det konfigurerade målet väljer du **ändra**.

    ![Dialogrutan för ER-rapportkörning där du kan ändra det konfigurerade målet.](./media/er-quick-start1-run-settings.png)

6. Klicka på **OK** om du vill köra rapporten.
7. Granska den genererade rapporten i PDF-format.

    ![Granska den genererade rapporten i PDF-format på skärmen.](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Formelspråk i elektronisk rapportering](er-formula-language.md)
- [Utforma flerspråkiga rapporter](er-design-multilingual-reports.md)
- [API för ER-ramverk](er-apis-app73.md)
- [CASE-funktion](er-functions-logical-case.md)
- [CONCATENATE-funktion](er-functions-text-concatenate.md)
- [DATETIMEFORMAT-funktion](er-functions-datetime-datetimeformat.md)
- [FILTER-funktion](er-functions-list-filter.md)
- [FIRSTORNULL-funktion](er-functions-list-firstornull.md)
- [FORMAT-funktion](er-functions-text-format.md)
- [IF-funktion](er-functions-logical-if.md)
- [ORDERBY-funktion](er-functions-list-orderby.md)
- [SESSIONNOW-funktion](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
