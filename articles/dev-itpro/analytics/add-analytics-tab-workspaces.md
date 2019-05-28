---
title: Lägg till analyser i arbetsytor genom att använda Power BI Embedded
description: Det här avsnittet beskriver hur du bäddar in en Power BI-rapport på fliken analys i en arbetsyta.
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a190e15dc304f60739c80d75222830ee737c5a32
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548195"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Lägg till analyser i arbetsytor genom att använda Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Den här funktionen stöds i Dynamics 365 for Finance and Operations (version 7.2 och senare).

## <a name="introduction"></a>Introduktion
Det här avsnittet beskriver hur du bäddar in en Microsoft Power BI-rapport på fliken **analys** i en arbetsyta. För det exempel som anges här utökar vi arbetsytan **Reservationshantering** i programmet Hantering av vagnpark att bädda in en analytisk arbetsyta på fliken **analys**.

## <a name="prerequisites"></a>Förutsättningar
+ Åtkomst till en utvecklarmiljö som kör plattformsuppdatering 8 eller senare.
+ En analysrapport (.pbix-filen) som skapades med Microsoft Power BI Desktop och som har en datamodell som har ursprung i databasen för Enhetslagring.

## <a name="overview"></a>Översikt
Oavsett om du utökar en befintlig programarbetsyta eller introducerar en egen arbetsyta kan du använda inbäddade analytiska vyer för att ge insiktsfulla och interaktiva visningar av dina företagsuppgifter. Processen för att lägga till en flik för analytiska arbetsytan finns fyra steg.

1. Lägga till en .pbix-fil som en resurs i Dynamics 365.
2. Definiera flik för analytisk arbetsyta.
3. Bädda in resursen .pbix på fliken arbetsyta.
4. Valfritt: Lägg till tillägg för att anpassa vyn.

> [!NOTE]
> Mer information om hur du skapar analytiska rapporter finns i [komma igång med Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/). Den här sidan är en bra källa för information som kan hjälpa dig skapa verkningsfulla analytiska rapporteringslösningar.

## <a name="add-a-pbix-file-as-a-resource"></a>Lägga till en .pbix-fil som en resurs
Innan du börjar måste du skapa eller skaffa Power BI-rapporten som du bäddar in på arbetsytan. Mer information om hur du skapar analytiska rapporter finns i [komma igång med Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).

Följ dessa steg om du vill lägga till en .pbix-fil som en projektartefakt för Visual Studio.

1. Skapa ett nytt projekt i lämplig modell.
2. Välj projektet i Solution Explorer, högerklicka och välj sedan **Lägg till** \> **Ny artikel**.
3. I dialogrutan **Lägg till nytt objekt** under **Operations artefakter** markerar du mallen **resurs**.
4. Ange ett namn som används för att referera till rapporten i X++-metadata och klicka sedan på **Lägg till**.

    ![Lägg till dialogruta nytt objekt](media/analytical-workspace-add.png)

5. Leta upp filen .pbix som innehåller definitionen av analytisk rapport och klicka sedan på **öppna**.

    ![Välj dialogrutan Resursfil](media/analytical-workspace-select-resource.png)

Nu när du har lagt till .pbix-filen som en resurs i Dynamics 365, kan du bädda in rapporter i arbetsytor och lägga till direkta länkar med hjälp av menyalternativ.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Lägga till en flikkontroll till en programarbetsyta
I det här exemplet ska vi utöka arbetsytan **Hantering av reservationer** i modellen uthyrning av vagnpark genom att lägga till fliken **analys** till definitionen av formuläret **FMClerkWorkspace**.

Följande bild visar hur formuläret **FMClerkWorkspace** ser ut i designern i Microsoft Visual Studio.

![FMClerkWorkspace-formuläret innan ändringar](media/analytical-workspace-definition-before.png)

Följ dessa steg för att utöka formulärets definition för arbetsytan **Reservationshantering**.

1. Öppna formulärdesignern för att utöka designdefinitionen.
2. I designdefinitionen, markera det översta elementet med etiketten **Design | Mönster: Arbetsyta fungerar**.
3. Högerklicka och välj sedan **Ny** \> **Flik** för att lägga till en ny kontroll med namnet **FormTabControl1**.
4. I formdesignern väljer du **FormTabControl1**.
5. Högerklicka och välj sedan **Ny fliksida** för att lägga till en ny fliksida.
6. Byt namn på fliksidan till något beskrivande som t.ex. **arbetsytan**.
7. I formdesignern väljer du **FormTabControl1**.
8. Högerklicka och markera sedan **Ny fliksida**.
9. Byt namn på fliksidan till något beskrivande som t.ex. **analys**.
10. I formulärdesignern väljer du **analys (fliksida)**.
11. Ange egenskapen **Rubrik** till **Analys**.
12. Högerklicka på kontrollen och välj sedan **Ny** \> **Grupp** för att lägga till en ny formulärgruppkontroll.
13. Byt namn på formulärgruppen till något beskrivande som t.ex. **powerBIReportGroup**.
14. I formulärdesignern väljer du **PanoramaBody (fliken)**, och drar sedan kontrollen till fliken **arbetsyta**.
15. I designdefinitionen, markera det översta elementet med etiketten **Design | Mönster: Arbetsyta fungerar**.
16. Högerklicka och markera sedan **Ta bort mönster**.
17. Högerklicka igen och välj **Lägg till mönster** \> **Arbetsytan tabbad**.
18. Utföra en version för att kontrollera ändringarna.

Följande illustration visar hur designen ser ut efter ändringarna har tillämpats.

![FMClerkWorkspace efter ändringar](media/analytical-workspace-definition-after.png)

Nu när du har lagt till formulärkontroller som används för att bädda in arbetsytrapporten måste du ange storleken på den överordnade kontrollen så att layouten sparas. Som standard visas både sidan **filterruta** och **flik** i rapporten. Du kan dock ändra synligheten för dessa kontroller efter målkonsumenten för rapporten.

> [!NOTE]
> Vi rekommenderar att du använder tillägg för att dölja både sidan **filterruta** och **flik** för konsekvens.

Du har nu slutfört uppgiften att utöka definitionen för ansökningsformulär. Mer information om hur du använder tillägg om du vill göra anpassningar finns i [anpassning: överlagring och tillägg](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Lägg till X ++-affärslogik om du vill inkludera visningskontrollen
Så här lägger du till affärslogik som initierar rapportvisningskontrollen som är inbäddad i arbetsytan **Reservationshantering**.

1. Öppna formulärdesignern **FMClerkWorkspace** för att utöka designdefinitionen.
2. Tryck på F7 för att komma åt koden bakom koddefinitionen.
3. Lägg till följande X++-kod:

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Utföra en version för att kontrollera ändringarna.

Du har nu slutfört uppgiften att lägga till inbäddad affärslogik för att initiera rapportvisningskontrollen. Följande illustration visar hur arbetsytan ser ut efter ändringarna har tillämpats.

![Rapport som är inbäddad i arbetsytan](media/analytical-workspace-final.png)

> [!NOTE]
> Du kommer åt den befintliga vyn med hjälp av flikarna för arbetsyta under en rubrik.

## <a name="reference"></a>Referens

### <a name="pbireporthelperinitializereportcontrol-method"></a>PBIReportHelper.initializeReportControl-metoden
Det här avsnittet innehåller information om den hjälpklass som används för att bädda in en Power BI-rapport (.pbix resurs) i formulärgruppkontroll.

#### <a name="syntax"></a>Syntax
```
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Parametrar

| Namn             | beskrivning                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | Namnet på .pbix-resursen                                                                              |
| formGroupControl | Formulärgruppkontrollen som Power BI-rapportkontrollen ska tillämpas till.                                              |
| defaultPageName  | Standardsidnamnet.                                                                                       |
| showFilterPane   | Ett booleskt värde som anger om filterrutan ska visas (**sant**) eller döljas (**falsk**).     |
| showNavPane      | Ett booleskt värde som anger om navigeringsrutan ska visas (**sant**) eller döljas (**falsk**). |
| defaultFilters   | Standardfilter för Power BI-rapporten.                                                                 |
