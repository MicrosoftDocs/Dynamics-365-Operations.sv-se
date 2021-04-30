---
title: Undvika att texten trunkeras i befattningshierarkin och exportera till Visio
description: Det här avsnittet beskriver hur du löser ett problem där namnen på personer och befattningar trunkeras när kunder visar befattningshierarkin i Microsoft Dynamics 365 Human Resources. Texttrunkering kan göra det svårt att ta en skärmbild eller skriva ut hierarkin.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dc723728801909c67cb823a043a2ae3e7eaf9f05
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892213"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="44909-104">Undvika att texten trunkeras i befattningshierarkin och exportera till Visio</span><span class="sxs-lookup"><span data-stu-id="44909-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="44909-105">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="44909-105">**Issue**</span></span>

<span data-ttu-id="44909-106">När en kund visar befattningshierarkin i Dynamics 365 Human Resources trunkeras namnen på individer och befattningar.</span><span class="sxs-lookup"><span data-stu-id="44909-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Human Resources, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="44909-107">Därför kan det vara svårt att ta en skärmbild eller att skriva ut och distribuera hierarkin.</span><span class="sxs-lookup"><span data-stu-id="44909-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Befattningshierarki](media/position-h.png)

<span data-ttu-id="44909-109">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="44909-109">**Cause**</span></span>

<span data-ttu-id="44909-110">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="44909-110">This behavior is by design.</span></span>

<span data-ttu-id="44909-111">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="44909-111">**Resolution**</span></span>

<span data-ttu-id="44909-112">Tyvärr kan användare inte enkelt ändra textens storlek.</span><span class="sxs-lookup"><span data-stu-id="44909-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="44909-113">Du kan exportera befattningshierarkin från Personal och sedan importera den till Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="44909-113">However, you can export the position hierarchy out of Human Resources and then import it into Microsoft Visio.</span></span> <span data-ttu-id="44909-114">Även om följande artikel skrevs för Microsoft Dynamics AX 2012, gäller processen fortfarande för Personal: [Exportera en befattningshierarki till Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="44909-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Human Resources: [Export a position hierarchy to Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="44909-115">Gör så här för att exportera till Visio.</span><span class="sxs-lookup"><span data-stu-id="44909-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="44909-116">I Personal, öppna listsidan **befattningar**.</span><span class="sxs-lookup"><span data-stu-id="44909-116">In Human Resources, open the **Positions** list page.</span></span>

    <span data-ttu-id="44909-117">För att inkludera mer information i organisationsstrukturdiagrammet, lägg till fält i listan **Positioner** så att de blir tillgängliga när du använder guiden senare i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="44909-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="44909-118">I åtgärdsfönstret, välj knappen **Öppen i Microsoft Office** och klicka sedan på **Exportera till Excel**, välj **Befattningar**.</span><span class="sxs-lookup"><span data-stu-id="44909-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="44909-119">Du kan också trycka på Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="44909-119">Alternatively, press Ctrl+T.</span></span>

    ![Exportera positionslistsidan till Excel](media/org-admin.png)

3. <span data-ttu-id="44909-121">Spara Excel-filen som exporteras.</span><span class="sxs-lookup"><span data-stu-id="44909-121">Save the Excel file that is exported.</span></span>

    ![Exportera till Excel-dialogruta](media/export-excel.png)

4. <span data-ttu-id="44909-123">I Visio, välj **Visio – skapa ny** och välj mallkategorin **Företag**.</span><span class="sxs-lookup"><span data-stu-id="44909-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nytt diagram](media/new.png)

5. <span data-ttu-id="44909-125">Välj **Guide för organisationsschema** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="44909-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Dialogrutan Guide för organisationsschema](media/orgchart-wizard.png)

6. <span data-ttu-id="44909-127">Välj **Information som redan sparats i en fil eller databas** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Organisationsschema 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="44909-129">Välj **En text, Org Plus (\*.txt), eller Excel-fil** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Organisationsschema 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="44909-131">Bläddra till den exporterade Excel-filen som innehåller befattningshierarkin och markera sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Organisationsschema 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="44909-133">Ange fältet **Namn** till **Befattning**, ange **Rapporterar till** till **Rapportera till befattning** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Organisationsschema 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="44909-135">Markera de fält som ska visas på varje nod och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Organisationsschema 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="44909-137">Lägg till kolumnen **Befattning** till listan **Formdatafält** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Organisationsschema 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="44909-139">Bilder är inte tillgängliga för tillfället.</span><span class="sxs-lookup"><span data-stu-id="44909-139">Pictures aren't currently available.</span></span> <span data-ttu-id="44909-140">Därför på nästa sida välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="44909-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="44909-141">Välj **Jag vill att guiden ska dela upp organisationsschemat över flera sidor**.</span><span class="sxs-lookup"><span data-stu-id="44909-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Organisationsschema 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="44909-143">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="44909-143">Select **Finish**.</span></span>

    <span data-ttu-id="44909-144">Om det finns befattningar som inte finns med i strukturen, uppmanas du att ta med dem i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="44909-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="44909-145">Det diagram som skapas i Visio visar varje chef i ett separat kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="44909-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="44909-146">Baserat på de fält som du valt att inkludera i diagrammet visar varje nod den lämpliga informationen när Visio-filen genereras.</span><span class="sxs-lookup"><span data-stu-id="44909-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Hierarkidiagram](media/hierarchy.png)

<span data-ttu-id="44909-148">**Ytterligare alternativ**</span><span class="sxs-lookup"><span data-stu-id="44909-148">**Additional option**</span></span>

<span data-ttu-id="44909-149">I Personal kanske du också använder arbetsytan **Personer** för att visa hierarkirelaterad information.</span><span class="sxs-lookup"><span data-stu-id="44909-149">In Human Resources, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]