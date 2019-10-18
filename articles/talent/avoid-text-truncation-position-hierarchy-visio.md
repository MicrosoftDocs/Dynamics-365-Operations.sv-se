---
title: Undvika att texten trunkeras i befattningshierarkin och exportera till Visio
description: Det här avsnittet beskriver hur du löser ett problem där namnen på personer och befattningar trunkeras när kunder visar befattningshierarkin i Microsoft Dynamics 365 Talent. Texttrunkering kan göra det svårt att ta en skärmbild eller skriva ut hierarkin.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e151818f29ac37ff449daaf1dc02e44b8fb317c3
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008510"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="7dc17-104">Undvika att texten trunkeras i befattningshierarkin och exportera till Visio</span><span class="sxs-lookup"><span data-stu-id="7dc17-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7dc17-105">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="7dc17-105">**Issue**</span></span>

<span data-ttu-id="7dc17-106">När en kund visar befattningshierarkin i Dynamics 365 Talent trunkeras namnen på individer och befattningar.</span><span class="sxs-lookup"><span data-stu-id="7dc17-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="7dc17-107">Därför kan det vara svårt att ta en skärmbild eller att skriva ut och distribuera hierarkin.</span><span class="sxs-lookup"><span data-stu-id="7dc17-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Befattningshierarki](media/position-h.png)

<span data-ttu-id="7dc17-109">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="7dc17-109">**Cause**</span></span>

<span data-ttu-id="7dc17-110">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="7dc17-110">This behavior is by design.</span></span>

<span data-ttu-id="7dc17-111">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="7dc17-111">**Resolution**</span></span>

<span data-ttu-id="7dc17-112">Tyvärr kan användare inte enkelt ändra textens storlek.</span><span class="sxs-lookup"><span data-stu-id="7dc17-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="7dc17-113">Du kan exportera befattningshierarkin från Talent och sedan importera den till Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="7dc17-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="7dc17-114">Även om följande artikel skrevs för Microsoft Dynamics AX 2012, gäller processen fortfarande för Talent: [Exportera en befattningshierarki till Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="7dc17-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="7dc17-115">Gör så här för att exportera till Visio.</span><span class="sxs-lookup"><span data-stu-id="7dc17-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="7dc17-116">I Talent, öppna listsidan **positioner**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="7dc17-117">För att inkludera mer information i organisationsstrukturdiagrammet, lägg till fält i listan **Positioner** så att de blir tillgängliga när du använder guiden senare i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="7dc17-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="7dc17-118">I åtgärdsfönstret, välj knappen **Öppen i Microsoft Office** och klicka sedan på **Exportera till Excel**, välj **Befattningar**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="7dc17-119">Du kan också trycka på Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="7dc17-119">Alternatively, press Ctrl+T.</span></span>

    ![Exportera positionslistsidan till Excel](media/org-admin.png)

3. <span data-ttu-id="7dc17-121">Spara Excel-filen som exporteras.</span><span class="sxs-lookup"><span data-stu-id="7dc17-121">Save the Excel file that is exported.</span></span>

    ![Exportera till Excel-dialogruta](media/export-excel.png)

4. <span data-ttu-id="7dc17-123">I Visio, välj **Visio - skapa ny** och välj mallkategorin **Företag**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nytt diagram](media/new.png)

5. <span data-ttu-id="7dc17-125">Välj **Guide för organisationsschema** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Dialogrutan Guide för organisationsschema](media/orgchart-wizard.png)

6. <span data-ttu-id="7dc17-127">Välj **Information som redan sparats i en fil eller databas** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Organisationsschema 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="7dc17-129">Välj **En text, Org Plus (\*.txt), eller Excel-fil** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Organisationsschema 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="7dc17-131">Bläddra till den exporterade Excel-filen som innehåller befattningshierarkin och markera sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Organisationsschema 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="7dc17-133">Ange fältet **Namn** till **Befattning**, ange **Rapporterar till** till **Rapportera till befattning** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Organisationsschema 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="7dc17-135">Markera de fält som ska visas på varje nod och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Organisationsschema 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="7dc17-137">Lägg till kolumnen **Befattning** till listan **Formdatafält** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Organisationsschema 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="7dc17-139">Bilder är inte tillgängliga för tillfället.</span><span class="sxs-lookup"><span data-stu-id="7dc17-139">Pictures aren't currently available.</span></span> <span data-ttu-id="7dc17-140">Därför på nästa sida välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="7dc17-141">Välj **Jag vill att guiden ska dela upp organisationsschemat över flera sidor**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Organisationsschema 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="7dc17-143">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="7dc17-143">Select **Finish**.</span></span>

    <span data-ttu-id="7dc17-144">Om det finns befattningar som inte finns med i strukturen, uppmanas du att ta med dem i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="7dc17-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="7dc17-145">Det diagram som skapas i Visio visar varje chef i ett separat kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="7dc17-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="7dc17-146">Baserat på de fält som du valt att inkludera i diagrammet visar varje nod den lämpliga informationen när Visio-filen genereras.</span><span class="sxs-lookup"><span data-stu-id="7dc17-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Hierarkidiagram](media/hierarchy.png)

<span data-ttu-id="7dc17-148">**Ytterligare alternativ**</span><span class="sxs-lookup"><span data-stu-id="7dc17-148">**Additional option**</span></span>

<span data-ttu-id="7dc17-149">I Talent kanske du också använder arbetsytan **Personer** för att visa hierarkirelaterad information.</span><span class="sxs-lookup"><span data-stu-id="7dc17-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
