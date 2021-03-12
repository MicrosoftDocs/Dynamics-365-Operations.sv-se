---
title: Uppdatera strukturen för en affärsdokumentmall
description: I det här ämnet beskrivs hur du uppdaterar strukturen för en affärsdokumentmall med hjälp av funktionen för hantering av affärsdokument.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cb0188e372b5f6275472cf040d10bb796eed1858
ms.sourcegitcommit: 95d2fc0fa7d17d3a96f7969f12c985b018b4ff94
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "4728099"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="df92e-103">Uppdatera strukturen för en affärsdokumentmall</span><span class="sxs-lookup"><span data-stu-id="df92e-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="df92e-104">I fönstret **Mallstruktur** i mallredigeraren för [Hantering av affärsdokument](er-business-document-management.md) kan du ändra en affärsdokumentmall genom att [lägga till nya fält](er-bdm-add-field-to-excel-template.md) i en mall i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="df92e-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="df92e-105">Mallens struktur uppdateras sedan automatiskt i Dynamics 365 Finance för att återspegla ändringarna som du gjorde i fönstret **Mallstruktur**.</span><span class="sxs-lookup"><span data-stu-id="df92e-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="df92e-106">Du kan också ändra en mall genom att använda online funktionerna i Office 365.</span><span class="sxs-lookup"><span data-stu-id="df92e-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="df92e-107">Du kan till exempel lägga till ett nytt namngivet objekt, som en bild eller form, i det redigerbara kalkylbladet.</span><span class="sxs-lookup"><span data-stu-id="df92e-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="df92e-108">I det här fallet uppdateras inte mallens struktur automatiskt i Finance och den post du har lagt till visas inte i fönstret **Mallstruktur**.</span><span class="sxs-lookup"><span data-stu-id="df92e-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="df92e-109">Uppdatera mallstrukturen manuellt i Finance genom att markera **Uppdatera struktur** på sidan för att redigera mallar.</span><span class="sxs-lookup"><span data-stu-id="df92e-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="df92e-110">För mer information om den här funktionen slutför du följande exempel.</span><span class="sxs-lookup"><span data-stu-id="df92e-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="df92e-111">Exempel: Uppdatera strukturen för en affärsdokumentmall</span><span class="sxs-lookup"><span data-stu-id="df92e-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="df92e-112">Det här exemplet visar hur en systemadministratör kan uppdatera strukturen för en affärsdokumentmall i Finans när mallen har ändrats i Office Online.</span><span class="sxs-lookup"><span data-stu-id="df92e-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="df92e-113">I följande avsnitt beskrivs de steg som ingår.</span><span class="sxs-lookup"><span data-stu-id="df92e-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="df92e-114">Förbereda en affärsdokumentmall för redigering</span><span class="sxs-lookup"><span data-stu-id="df92e-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="df92e-115">Slutför följande procedurer i [Översikt över hantering av affärsdokument](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="df92e-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="df92e-116">Konfigurera ER-parametrar</span><span class="sxs-lookup"><span data-stu-id="df92e-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="df92e-117">Importera ER-lösningar</span><span class="sxs-lookup"><span data-stu-id="df92e-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="df92e-118">Aktivera hantering av affärsdokument</span><span class="sxs-lookup"><span data-stu-id="df92e-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="df92e-119">Konfigurera parametrar</span><span class="sxs-lookup"><span data-stu-id="df92e-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="df92e-120">Redigera en affärsdokumentmall</span><span class="sxs-lookup"><span data-stu-id="df92e-120">Edit a business document template</span></span>

1. <span data-ttu-id="df92e-121">Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="df92e-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="df92e-122">På sidan **Skapa en ny mall** väljer du mallen **Fritextfaktura (ER-exempel)(Excel)**.</span><span class="sxs-lookup"><span data-stu-id="df92e-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="df92e-123">Välj **Skapa dokument**.</span><span class="sxs-lookup"><span data-stu-id="df92e-123">Select **Create document**.</span></span>
4. <span data-ttu-id="df92e-124">I fältet **Titel** anger du **FTI-exempel Litware**.</span><span class="sxs-lookup"><span data-stu-id="df92e-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="df92e-125">Skapa en ny mall genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="df92e-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df92e-126">Om du inte redan har loggat in på Office Online [dirigeras du om till Office 365-inloggningssidan](er-business-document-management.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="df92e-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="df92e-127">Om du vill återgå till Finance-miljön väljer du knappen **Tillbaka** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="df92e-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="df92e-128">Den nya mallen öppnas för redigering i den inbäddade kontrollen i Excel Online på sidan för att redigera mall.</span><span class="sxs-lookup"><span data-stu-id="df92e-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="df92e-129">[![Börja redigera en affärsdokumentmall med arbetsytan för hantering av affärsdokument](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="df92e-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="df92e-130">Granska den redigerbara mallens aktuella struktur</span><span class="sxs-lookup"><span data-stu-id="df92e-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="df92e-131">I Excel Online, i menyfliken, på fliken **Visa** i gruppen **Visa** väljer du **Rutnät**.</span><span class="sxs-lookup"><span data-stu-id="df92e-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="df92e-132">Markera rektangeln ovanför mallrubriken i den redigerbara mallen.</span><span class="sxs-lookup"><span data-stu-id="df92e-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="df92e-133">Den här rektangeln är en bild som heter **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="df92e-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="df92e-134">Om fönstret **Mallstruktur** är dolt väljer du **Visa struktur**.</span><span class="sxs-lookup"><span data-stu-id="df92e-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="df92e-135">I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="df92e-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="df92e-136">Observera att posten **rptHeaderCompLogo** i mallstrukturen i Finance, presenteras underordnad post till **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="df92e-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="df92e-137">[![Granska den aktuella strukturen för en redigerbar mall med arbetsytan för hantering av affärsdokument](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="df92e-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="df92e-138">Uppdatera strukturen för en affärsdokumentmall genom att radera en bild</span><span class="sxs-lookup"><span data-stu-id="df92e-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="df92e-139">Markera bilden **rptHeaderCompLogo** i den redigerbara mallen i Excel Online .</span><span class="sxs-lookup"><span data-stu-id="df92e-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="df92e-140">Gör något av följande för att radera den markerade bilden från den redigerbara mallen:</span><span class="sxs-lookup"><span data-stu-id="df92e-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="df92e-141">Välj tangenten **Delete** på tangentbordet.</span><span class="sxs-lookup"><span data-stu-id="df92e-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="df92e-142">Markera och håll (eller högerklicka på) bilden och välj sedan **Klipp ut**.</span><span class="sxs-lookup"><span data-stu-id="df92e-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df92e-143">**RptHeaderCompLogo**-posten finns fortfarande i mallstrukturen i Finance, även om bilden inte längre ingår i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="df92e-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="df92e-144">Välj **Uppdatera struktur** för att synkronisera strukturen för den redigerbara mallen i Excel och Finance.</span><span class="sxs-lookup"><span data-stu-id="df92e-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="df92e-145">I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="df92e-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="df92e-146">Observera att posten **rptHeaderCompLogo** inte längre ingår i mallstrukturen i Finance.</span><span class="sxs-lookup"><span data-stu-id="df92e-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="df92e-147">[![Radera en bild från en affärsdokumentmall med arbetsytan för hantering av affärsdokument](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="df92e-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="df92e-148">Uppdatera strukturen för en affärsdokumentmall genom att lägga till en bild</span><span class="sxs-lookup"><span data-stu-id="df92e-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="df92e-149">I Excel Online, i menyfliken, på fliken **Infoga** i gruppen **Illustrationer** väljer du **Bild**.</span><span class="sxs-lookup"><span data-stu-id="df92e-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="df92e-150">Välj **Välj fil**, bläddra till den bild som du vill lägga till, markera den och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="df92e-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="df92e-151">Välj **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="df92e-151">Select **Insert**.</span></span>
4. <span data-ttu-id="df92e-152">Flytta den nya bilden till rätt plats.</span><span class="sxs-lookup"><span data-stu-id="df92e-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="df92e-153">Som standard namnger Excel bilden.</span><span class="sxs-lookup"><span data-stu-id="df92e-153">By default, Excel names the picture.</span></span> <span data-ttu-id="df92e-154">Exempelvis kan bilden få namnet **Bild 2**.</span><span class="sxs-lookup"><span data-stu-id="df92e-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="df92e-155">Välj **Uppdatera struktur** för att synkronisera strukturen för den redigerbara mallen i Excel och Finance.</span><span class="sxs-lookup"><span data-stu-id="df92e-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="df92e-156">I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="df92e-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="df92e-157">Observera att den nya bilden nu ingår som en post i mallstrukturen i Finance.</span><span class="sxs-lookup"><span data-stu-id="df92e-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="df92e-158">[![Lägg till en bild i en affärsdokumentmall med arbetsytan för hantering av affärsdokument](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="df92e-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="df92e-159">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="df92e-159">Related links</span></span>

[<span data-ttu-id="df92e-160">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="df92e-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="df92e-161">Hantering av affärsdokument – översikt</span><span class="sxs-lookup"><span data-stu-id="df92e-161">Business document management overview</span></span>](er-business-document-management.md)
