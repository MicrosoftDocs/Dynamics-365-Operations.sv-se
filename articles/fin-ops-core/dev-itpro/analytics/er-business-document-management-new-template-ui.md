---
title: Nytt användargränssnitt för dokument i hantering av affärsdokument
description: I det här avsnittet finns information om hur du använder det nya användargränssnittet för funktionen för hantering av affärsdokument i ramverket elektroniska rapporter.
author: v-anamir
ms.date: 05/12/2019
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
ms.openlocfilehash: 4c430e21e3bf7f1c01c7b60c0bef58fb49c0c601
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748351"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="dc107-103">Nytta användargränssnitt för dokument vid affärsdokumenthantering</span><span class="sxs-lookup"><span data-stu-id="dc107-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc107-104">Hanteringen av affärsdokument gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda en Microsoft 365-tjänst eller lämpligt Microsoft Office-skrivbordsprogram.</span><span class="sxs-lookup"><span data-stu-id="dc107-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="dc107-105">Redigeringar kan omfatta designändringar eller nya distributioner, eller så kan användare lägga till platshållare för att inkludera ytterligare data utan att behöva ändra källkoden.</span><span class="sxs-lookup"><span data-stu-id="dc107-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="dc107-106">Mer information om hur du arbetar med hantering av affärsdokument finns i [översikt över hantering av affärsdokument](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="dc107-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="dc107-107">Användargränssnittet för det nya dokumentet är tydligare och bekvämare att använda.</span><span class="sxs-lookup"><span data-stu-id="dc107-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="dc107-108">I området **affärsdokument** visas bara de mallar som är tillgängliga för den aktuella leverantören.</span><span class="sxs-lookup"><span data-stu-id="dc107-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="dc107-109">Med knappen **Nytt dokument** kan användare skapa och redigera en mall i formatkonfiguration för elektronisk rapportering (ER) som tillhandahålls av en annan leverantör.</span><span class="sxs-lookup"><span data-stu-id="dc107-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="dc107-110">I exemplet i det här avsnittet är leverantören Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dc107-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="dc107-111">Gör det nya dokumentgränssnittet tillgängligt i Hantering av affärsdokument</span><span class="sxs-lookup"><span data-stu-id="dc107-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="dc107-112">Om du vill kunna använda det nya dokumentgränssnittet i Hantering av affärsdokument måste du aktivera funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i arbetsytan **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="dc107-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="dc107-113">Följ de här stegen för att aktivera funktionen för alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="dc107-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="dc107-114">I arbetsytan **funktionshantering** på fliken **Ny** väljer du **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i listan.</span><span class="sxs-lookup"><span data-stu-id="dc107-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="dc107-115">Välj **Aktivera nu** om du vill aktivera den valda funktionen.</span><span class="sxs-lookup"><span data-stu-id="dc107-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="dc107-116">Uppdatera sidan för att komma åt den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="dc107-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="dc107-117">Redigera mallar som ägs av andra leverantörer</span><span class="sxs-lookup"><span data-stu-id="dc107-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="dc107-118">Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="dc107-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="dc107-120">I dialogrutan väljer du det dokument som ska användas som mall och väljer sedan **Skapa dokument**.</span><span class="sxs-lookup"><span data-stu-id="dc107-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Dialogrutan affärsdokument](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="dc107-122">I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål.</span><span class="sxs-lookup"><span data-stu-id="dc107-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="dc107-123">Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dc107-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="dc107-124">Utkastet till den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="dc107-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="dc107-125">Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.</span><span class="sxs-lookup"><span data-stu-id="dc107-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="dc107-126">I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dc107-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="dc107-127">I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.</span><span class="sxs-lookup"><span data-stu-id="dc107-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="dc107-128">Välj **OK** för att bekräfta starten av redigeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dc107-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Dialogrutan skapa dokument](./media/BDM_overview_new_template3.png)

<span data-ttu-id="dc107-130">Knappen **Nytt dokument** används för att skapa och redigera en mall i formatkonfiguration för ER-format som tillhandahålls av en annan leverantör.</span><span class="sxs-lookup"><span data-stu-id="dc107-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="dc107-131">I exemplet i det här avsnittet är leverantören Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dc107-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="dc107-132">När du klickar på **Nytt dokument** visas alla mallar som ägs av aktuella och andra leverantörer.</span><span class="sxs-lookup"><span data-stu-id="dc107-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="dc107-133">När du har valt mallen kommer den att öppnas för redigering.</span><span class="sxs-lookup"><span data-stu-id="dc107-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="dc107-134">Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dc107-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="dc107-135">Mer information finns i [översikt över hantering av affärsdokument](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="dc107-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]