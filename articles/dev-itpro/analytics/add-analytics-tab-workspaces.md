---
title: "Lägg till analys i arbetsytor med Power BI Embedded"
description: "Det här avsnittet beskriver hur du bäddar in en Power BI-rapport på fliken analys i en arbetsyta."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations, Platform
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.intro: Platform update 8
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 677e008279b9f233026f87e469cbabb8c8bcf801
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="c21b5-103">Lägg till analys i arbetsytor med Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="c21b5-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="c21b5-104">Den här funktionen stöds i Dynamics 365 for Finance and Operations (version 7.2 och senare).</span><span class="sxs-lookup"><span data-stu-id="c21b5-104">This feature is supported in Dynamics 365 for Finance and Operations (version 7.2 and later).</span></span>

# <a name="introduction"></a><span data-ttu-id="c21b5-105">Introduktion</span><span class="sxs-lookup"><span data-stu-id="c21b5-105">Introduction</span></span>
<span data-ttu-id="c21b5-106">Det här avsnittet beskriver hur du bäddar in en Microsoft Power BI-rapport på fliken **Analys** i en arbetsyta.</span><span class="sxs-lookup"><span data-stu-id="c21b5-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="c21b5-107">För det exempel som anges här utökar vi arbetsytan **Reservationshantering** i programmet Hantering av vagnpark att bädda in en analytisk arbetsyta på fliken **analys**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

# <a name="prerequisites"></a><span data-ttu-id="c21b5-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c21b5-108">Prerequisites</span></span>
+ <span data-ttu-id="c21b5-109">Åtkomst till en utvecklarmiljö som kör plattformsuppdatering 8 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c21b5-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="c21b5-110">En analysrapport (.pbix-filen) som skapades med Microsoft Power BI Desktop och som har en datamodell som har ursprung i databasen för Enhetslagring.</span><span class="sxs-lookup"><span data-stu-id="c21b5-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

# <a name="overview"></a><span data-ttu-id="c21b5-111">Översikt</span><span class="sxs-lookup"><span data-stu-id="c21b5-111">Overview</span></span>
<span data-ttu-id="c21b5-112">Oavsett om du utökar en befintlig programarbetsyta eller introducerar en egen arbetsyta kan du använda inbäddade analytiska vyer för att ge insiktsfulla och interaktiva visningar av dina företagsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c21b5-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="c21b5-113">Processen för att lägga till en flik för analytiska arbetsytan finns fyra steg.</span><span class="sxs-lookup"><span data-stu-id="c21b5-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="c21b5-114">Lägga till en .pbix-fil som en resurs i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c21b5-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="c21b5-115">Definiera flik för analytisk arbetsyta.</span><span class="sxs-lookup"><span data-stu-id="c21b5-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="c21b5-116">Bädda in resursen .pbix på fliken arbetsyta.</span><span class="sxs-lookup"><span data-stu-id="c21b5-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="c21b5-117">Valfritt: Lägg till tillägg för att anpassa vyn.</span><span class="sxs-lookup"><span data-stu-id="c21b5-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="c21b5-118">Mer information om hur du skapar analytiska rapporter finns i [komma igång med Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="c21b5-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="c21b5-119">Den här sidan är en bra källa för information som kan hjälpa dig skapa verkningsfulla analytiska rapporteringslösningar.</span><span class="sxs-lookup"><span data-stu-id="c21b5-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

# <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="c21b5-120">Lägga till en .pbix-fil som en resurs</span><span class="sxs-lookup"><span data-stu-id="c21b5-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="c21b5-121">Innan du börjar måste du skapa eller skaffa Power BI-rapporten som du bäddar in på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="c21b5-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="c21b5-122">Mer information om hur du skapar analytiska rapporter finns i [komma igång med Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="c21b5-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span>
 
<span data-ttu-id="c21b5-123">Följ dessa steg om du vill lägga till en .pbix-fil som en projektartefakt för Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c21b5-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="c21b5-124">Skapa ett nytt projekt i lämplig modell.</span><span class="sxs-lookup"><span data-stu-id="c21b5-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="c21b5-125">Välj projektet i Solution Explorer, högerklicka och välj sedan **Lägg till** > **Ny artikel**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-125">In Solution Explorer, select the project, right-click, and then select **Add** > **New Item**.</span></span>
3. <span data-ttu-id="c21b5-126">I dialogrutan **Lägg till nytt objekt** under **Operations artefakter** markerar du mallen **resurs**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="c21b5-127">Ange ett namn som används för att referera till rapporten i X++-metadata och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Lägg till dialogruta nytt objekt](media/analytical-workspace-add.png)

5. <span data-ttu-id="c21b5-129">Leta upp filen .pbix som innehåller definitionen av analytisk rapport och klicka sedan på **öppna**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Välj dialogrutan Resursfil](media/analytical-workspace-select-resource.png)
  
<span data-ttu-id="c21b5-131">Nu när du har lagt till .pbix-filen som en resurs i Dynamics 365, kan du bädda in rapporter i arbetsytor och lägga till direkta länkar med hjälp av menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="c21b5-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

# <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="c21b5-132">Lägga till en flikkontroll till en programarbetsyta</span><span class="sxs-lookup"><span data-stu-id="c21b5-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="c21b5-133">I det här exemplet ska vi utöka arbetsytan **Hantering av reservationer** i modellen uthyrning av vagnpark genom att lägga till fliken **analys** till definitionen av formuläret **FMClerkWorkspace**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>
 
<span data-ttu-id="c21b5-134">Följande bild visar hur formuläret **FMClerkWorkspace** ser ut i designern i Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c21b5-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![FMClerkWorkspace-formuläret innan ändringar](media/analytical-workspace-definition-before.png)

<span data-ttu-id="c21b5-136">Följ dessa steg för att utöka formulärets definition för arbetsytan **Reservationshantering**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="c21b5-137">Öppna formulärdesignern för att utöka designdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c21b5-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="c21b5-138">I designdefinitionen, markera det översta elementet med etiketten **Design | Mönster: Arbetsyta fungerar**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="c21b5-139">Högerklicka och välj sedan **Ny** > **Flik** för att lägga till en ny kontroll med namnet **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-139">Right-click, and then select **New** > **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="c21b5-140">I formdesignern väljer du **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="c21b5-141">Högerklicka och välj sedan **Ny fliksida** för att lägga till en ny fliksida.</span><span class="sxs-lookup"><span data-stu-id="c21b5-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="c21b5-142">Byt namn på fliksidan till något beskrivande som t.ex. **arbetsytan**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="c21b5-143">I formdesignern väljer du **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="c21b5-144">Högerklicka och markera sedan **Ny fliksida**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="c21b5-145">Byt namn på fliksidan till något beskrivande som t.ex. **analys**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="c21b5-146">I formulärdesignern väljer du **analys (fliksida)**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="c21b5-147">Ange egenskapen **Rubrik** till **Analys**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="c21b5-148">Högerklicka på kontrollen och välj sedan **ny** > **grupp** för att lägga till en ny formulärgruppkontroll.</span><span class="sxs-lookup"><span data-stu-id="c21b5-148">Right-click the control, and then select **New** > **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="c21b5-149">Byt namn på formulärgruppen till något beskrivande som t.ex. **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="c21b5-150">I formulärdesignern väljer du **PanoramaBody (fliken)**, och drar sedan kontrollen till fliken **arbetsyta**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="c21b5-151">I designdefinitionen, markera det översta elementet med etiketten **Design | Mönster: Arbetsyta fungerar**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="c21b5-152">Högerklicka och markera sedan **Ta bort mönster**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="c21b5-153">Högerklicka igen och välj **Lägg till mönster** > **Arbetsytan tabbad**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-153">Right-click again, and then select **Add pattern** > **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="c21b5-154">Utföra en version för att kontrollera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c21b5-154">Perform a build to verify your changes.</span></span>
 
<span data-ttu-id="c21b5-155">Följande illustration visar hur designen ser ut efter ändringarna har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="c21b5-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![FMClerkWorkspace efter ändringar](media/analytical-workspace-definition-after.png)

<span data-ttu-id="c21b5-157">Nu när du har lagt till formulärkontroller som används för att bädda in arbetsytrapporten måste du ange storleken på den överordnade kontrollen så att layouten sparas.</span><span class="sxs-lookup"><span data-stu-id="c21b5-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="c21b5-158">Som standard visas både sidan **filterruta** och **flik** i rapporten.</span><span class="sxs-lookup"><span data-stu-id="c21b5-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="c21b5-159">Du kan dock ändra synligheten för dessa kontroller efter målkonsumenten för rapporten.</span><span class="sxs-lookup"><span data-stu-id="c21b5-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>
 
> [!NOTE]
> <span data-ttu-id="c21b5-160">Vi rekommenderar att du använder tillägg för att dölja både sidan **filterruta** och **flik** för konsekvens.</span><span class="sxs-lookup"><span data-stu-id="c21b5-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>
 
<span data-ttu-id="c21b5-161">Du har nu slutfört uppgiften att utöka definitionen för ansökningsformulär.</span><span class="sxs-lookup"><span data-stu-id="c21b5-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="c21b5-162">Mer information om hur du använder tillägg om du vill göra anpassningar finns [anpassning: överlagring och tillägg](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c21b5-162">For more information about how to use extensions to do customizations, see  [Customization: Overlayering and extensions](../extensibility/customization-overlayering-extensions.md).</span></span>

# <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="c21b5-163">Lägg till X ++-affärslogik om du vill inkludera visningskontrollen</span><span class="sxs-lookup"><span data-stu-id="c21b5-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="c21b5-164">Så här lägger du till affärslogik som initierar rapportvisningskontrollen som är inbäddad i arbetsytan **Reservationshantering**.</span><span class="sxs-lookup"><span data-stu-id="c21b5-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="c21b5-165">Öppna formulärdesignern **FMClerkWorkspace** för att utöka designdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c21b5-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="c21b5-166">Tryck på F7 för att komma åt koden bakom koddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c21b5-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="c21b5-167">Lägg till följande X++-kod:</span><span class="sxs-lookup"><span data-stu-id="c21b5-167">Add the following X++ code.</span></span>

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
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
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

4. <span data-ttu-id="c21b5-168">Utföra en version för att kontrollera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c21b5-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="c21b5-169">Du har nu slutfört uppgiften att lägga till inbäddad affärslogik för att initiera rapportvisningskontrollen.</span><span class="sxs-lookup"><span data-stu-id="c21b5-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="c21b5-170">Följande illustration visar hur arbetsytan ser ut efter ändringarna har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="c21b5-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![Rapport som är inbäddad i arbetsytan](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="c21b5-172">Du kommer åt den befintliga vyn med hjälp av flikarna för arbetsyta under en rubrik.</span><span class="sxs-lookup"><span data-stu-id="c21b5-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

# <a name="reference"></a><span data-ttu-id="c21b5-173">Referens</span><span class="sxs-lookup"><span data-stu-id="c21b5-173">Reference</span></span>

## <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="c21b5-174">PBIReportHelper.initializeReportControl-metoden</span><span class="sxs-lookup"><span data-stu-id="c21b5-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="c21b5-175">Det här avsnittet innehåller information om den hjälpklass som används för att bädda in en Power BI-rapport (.pbix resurs) i formulärgruppkontroll.</span><span class="sxs-lookup"><span data-stu-id="c21b5-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

### <a name="syntax"></a><span data-ttu-id="c21b5-176">Syntax</span><span class="sxs-lookup"><span data-stu-id="c21b5-176">Syntax</span></span>
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

### <a name="parameters"></a><span data-ttu-id="c21b5-177">Parametrar</span><span class="sxs-lookup"><span data-stu-id="c21b5-177">Parameters</span></span>

| <span data-ttu-id="c21b5-178">Namn</span><span class="sxs-lookup"><span data-stu-id="c21b5-178">Name</span></span> | <span data-ttu-id="c21b5-179">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c21b5-179">Description</span></span> |
|---|---|
| <span data-ttu-id="c21b5-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="c21b5-180">resourceName</span></span> | <span data-ttu-id="c21b5-181">Namnet på .pbix-resursen</span><span class="sxs-lookup"><span data-stu-id="c21b5-181">The name of the .pbix resource.</span></span> |
| <span data-ttu-id="c21b5-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="c21b5-182">formGroupControl</span></span> | <span data-ttu-id="c21b5-183">Formulärgruppkontrollen som Power BI-rapportkontrollen ska tillämpas till.</span><span class="sxs-lookup"><span data-stu-id="c21b5-183">The form group control to apply the Power BI report control to.</span></span> |
| <span data-ttu-id="c21b5-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="c21b5-184">defaultPageName</span></span> | <span data-ttu-id="c21b5-185">Standardsidnamnet.</span><span class="sxs-lookup"><span data-stu-id="c21b5-185">The default page name.</span></span> |
| <span data-ttu-id="c21b5-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="c21b5-186">showFilterPane</span></span> | <span data-ttu-id="c21b5-187">Ett booleskt värde som anger om filterrutan ska visas (**sant**) eller döljas (**falsk**).</span><span class="sxs-lookup"><span data-stu-id="c21b5-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="c21b5-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="c21b5-188">showNavPane</span></span> | <span data-ttu-id="c21b5-189">Ett booleskt värde som anger om navigeringsrutan ska visas (**sant**) eller döljas (**falsk**).</span><span class="sxs-lookup"><span data-stu-id="c21b5-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="c21b5-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="c21b5-190">defaultFilters</span></span> | <span data-ttu-id="c21b5-191">Standardfilter för Power BI-rapporten.</span><span class="sxs-lookup"><span data-stu-id="c21b5-191">The default filters for the Power BI report.</span></span> |

