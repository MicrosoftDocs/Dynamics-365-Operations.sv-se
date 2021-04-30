---
title: Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument
description: Detta ämne förklarar hur du använder det nya användargränssnittet för funktionen för hantering av affärsdokument i ramverket för elektroniska rapporter (ER).
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881046"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="d65d3-103">Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument</span><span class="sxs-lookup"><span data-stu-id="d65d3-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d65d3-104">Hanteringen av affärsdokument gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda en Microsoft 365-tjänst eller lämpligt Microsoft Office-skrivbordsprogram.</span><span class="sxs-lookup"><span data-stu-id="d65d3-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="d65d3-105">Redigeringar kan omfatta designändringar eller nya distributioner, eller så kan användare lägga till platshållare för att inkludera ytterligare data utan att behöva ändra källkoden.</span><span class="sxs-lookup"><span data-stu-id="d65d3-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="d65d3-106">Mer information om hur du arbetar med hantering av affärsdokument finns i [översikt över hantering av affärsdokument](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="d65d3-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="d65d3-107">Det nya användargränssnittet (UI) är tydligare och bekvämare att använda.</span><span class="sxs-lookup"><span data-stu-id="d65d3-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="d65d3-108">I området **affärsdokument** visas bara de mallar som är tillgängliga för den aktuella leverantören.</span><span class="sxs-lookup"><span data-stu-id="d65d3-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="d65d3-109">I det föregående användargränssnittet angav fliken **Mall** alla mallar som var tillgängliga för alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="d65d3-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="d65d3-110">Den visar också alla mallar som har skapats och redigerats av en användare med samma roll.</span><span class="sxs-lookup"><span data-stu-id="d65d3-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="d65d3-111">Du kan använda knappen **Nytt dokument** för att skapa och redigera en mall i en formatkonfiguration för elektronisk rapportering (ER) som tillhandahålls av en annan leverantör.</span><span class="sxs-lookup"><span data-stu-id="d65d3-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="d65d3-112">I exemplet i det här avsnittet är leverantören Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d65d3-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="d65d3-113">Du kan också skapa en mall genom att överföra din egen mall i Excel-format.</span><span class="sxs-lookup"><span data-stu-id="d65d3-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="d65d3-114">Videon [Skapa ett nytt affärsdokument med hjälp av hantering av affärsdokument](https://youtu.be/gAIYl-mM_pw) (visas ovan) ingår i spellistan [Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.</span><span class="sxs-lookup"><span data-stu-id="d65d3-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="d65d3-115">Gör det nya dokumentgränssnittet tillgängligt i Hantering av affärsdokument</span><span class="sxs-lookup"><span data-stu-id="d65d3-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="d65d3-116">Om du vill kunna använda det nya dokumentgränssnittet i Hantering av affärsdokument måste du aktivera funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i arbetsytan **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="d65d3-117">Följ de här stegen för att aktivera funktionen för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="d65d3-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="d65d3-118">I arbetsytan **Funktionshantering** väljer du på fliken **All** funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i listan.</span><span class="sxs-lookup"><span data-stu-id="d65d3-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="d65d3-119">Välj **Aktivera nu** om du vill aktivera den valda funktionen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="d65d3-120">Uppdatera sidan för att komma åt den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="d65d3-121">Redigera mallar som ägs av andra leverantörer</span><span class="sxs-lookup"><span data-stu-id="d65d3-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="d65d3-122">Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="d65d3-124">På fliken **Välj** väljer du det dokument du vill använda som mall och sedan **Skapa dokument**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Dialogrutan affärsdokument](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="d65d3-126">I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål.</span><span class="sxs-lookup"><span data-stu-id="d65d3-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="d65d3-127">Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="d65d3-128">Utkastet till den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="d65d3-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="d65d3-129">Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="d65d3-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="d65d3-130">I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="d65d3-131">I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.</span><span class="sxs-lookup"><span data-stu-id="d65d3-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="d65d3-132">Välj **OK** för att bekräfta starten av redigeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Dialogrutan skapa dokument](./media/BDM_overview_new_template3.png)

<span data-ttu-id="d65d3-134">Knappen **Nytt dokument** används för att skapa och redigera en mall i formatkonfiguration för ER-format som tillhandahålls av en annan leverantör.</span><span class="sxs-lookup"><span data-stu-id="d65d3-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="d65d3-135">I exemplet i det här avsnittet är leverantören Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d65d3-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="d65d3-136">När du klickar på **Nytt dokument** visas alla mallar som ägs av aktuella och andra leverantörer.</span><span class="sxs-lookup"><span data-stu-id="d65d3-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="d65d3-137">När du har valt mallen kommer den att öppnas för redigering.</span><span class="sxs-lookup"><span data-stu-id="d65d3-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="d65d3-138">Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="d65d3-139">Överföra en mall som använder ett befintligt Excel-format</span><span class="sxs-lookup"><span data-stu-id="d65d3-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="d65d3-140">Följ de här stegen om du vill ange obligatorisk information innan du överför en mall.</span><span class="sxs-lookup"><span data-stu-id="d65d3-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="d65d3-141">Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="d65d3-143">På sidan **Skapa en ny mall** > fliken **Ladda upp** > fliken **Mall** väljer du **Bläddra** om du vill leta efter den Excel-fil som du vill använda som mall.</span><span class="sxs-lookup"><span data-stu-id="d65d3-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="d65d3-144">I avsnittet **Mall** fylls fälten **Rubrik** och **Beskrivning** i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="d65d3-145">De anger namn och beskrivning för den nya ER-formatkonfigurationen som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="d65d3-146">Du kan redigera dessa fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="d65d3-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="d65d3-147">I avsnittet **Dokumenttyp**, i fältet **Namn**, anger du affärsdokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="d65d3-148">Detta värde används för att söka efter rätt datakälla (det vill säga ER-modellkonfigurationen).</span><span class="sxs-lookup"><span data-stu-id="d65d3-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Mallflik](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="d65d3-150">I fliken **Datakälla**, på snabbfliken **Filter**, väljer du **Applicera filter**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="d65d3-151">I avsnittet **Datakälla** fylls fältet **Namn** i automatiskt, eller också kan du välja ett värde manuellt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="d65d3-152">Du kan använda filtret för att söka efter rätt datakällsnamn efter namn, beskrivning, lands-/regionkod och affärsdokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="d65d3-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Fliken datakälla](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="d65d3-154">Snabbfliken **Filter** används för att söka efter rätt datakälla (dvs. konfigurationen för ER-modell).</span><span class="sxs-lookup"><span data-stu-id="d65d3-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="d65d3-155">Du kan redigera alla filterfält för att hitta den lämpligaste datakällan för det dokument du överför.</span><span class="sxs-lookup"><span data-stu-id="d65d3-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="d65d3-156">Villkoren på snabbfliken **Filter** används som **ELLER**-villkor.</span><span class="sxs-lookup"><span data-stu-id="d65d3-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="d65d3-157">På fliken **Mappning** väljer du **Automatisk identifiering**.</span><span class="sxs-lookup"><span data-stu-id="d65d3-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="d65d3-158">Fältet **Rotdefinition** fylls i automatiskt, eller också kan du välja ett värde manuellt.</span><span class="sxs-lookup"><span data-stu-id="d65d3-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="d65d3-159">På denna flik visas slutmappningen för elementen från mallen och modellen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Fliken Mappning](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="d65d3-161">Mappningen i avsnittet **Mallstruktur** använder den fullständiga matchningen av etiketterna eller beskrivningarna i datakällan på användarens språk, samt i cellnamnet i mallen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="d65d3-162">Välj **Skapa dokument** för att bekräfta att du vill skapa en mall och starta redigeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="d65d3-163">Mer information finns i [översikt över hantering av affärsdokument](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="d65d3-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="d65d3-164">Om det inte finns någon leverantör i Elektronisk rapportering kan du skapa en.</span><span class="sxs-lookup"><span data-stu-id="d65d3-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="d65d3-165">Om det inte finns någon aktiv leverantör kan du välja att aktivera en.</span><span class="sxs-lookup"><span data-stu-id="d65d3-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="d65d3-166">Om du vill skapa en leverantör ändrar du namnet på leverantören i fältet **Namn**, uppdaterar internetadressen för den nya leverantören i fältet **Internetadress** och väljer sedan **OK** för att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="d65d3-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Skapa ny leverantör i BDM](./media/bdm_create_provider.png)
    
- <span data-ttu-id="d65d3-168">Om du vill aktivera befintlig leverantör väljer du namnet på leverantören i fältet **Konfigurationsleverantör** och väljer sedan **OK** för att ange leverantören som aktiv.</span><span class="sxs-lookup"><span data-stu-id="d65d3-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Aktivera leverantör i BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="d65d3-170">Varje BDM-mall refererar till leverantören som författare av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="d65d3-171">Därför krävs en aktiv leverantör för mallen.</span><span class="sxs-lookup"><span data-stu-id="d65d3-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
