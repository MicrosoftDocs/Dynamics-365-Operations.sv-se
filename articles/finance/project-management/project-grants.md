---
title: Projektanslag
description: Det här ämnet förklarar hur du skapar eller ändrar ett anslag.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282850"
---
# <a name="project-grants"></a><span data-ttu-id="ccd76-103">Projektanslag</span><span class="sxs-lookup"><span data-stu-id="ccd76-103">Project grants</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccd76-104">Ett anslag är en gåva av pengar för ett visst syfte eller projekt.</span><span class="sxs-lookup"><span data-stu-id="ccd76-104">A grant is a gift of money for a specific purpose or project.</span></span> <span data-ttu-id="ccd76-105">Vanligtvis finns det begränsningar på hur ett anslag kan använts.</span><span class="sxs-lookup"><span data-stu-id="ccd76-105">Usually, there are restrictions on how a grant can be spent.</span></span> <span data-ttu-id="ccd76-106">I Projekthantering och redovisning kan du ange och spåra anslag och definiera deras relationer till projekt och projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="ccd76-106">In Project management and accounting, you can enter and track grants, and define their relationships to projects and project contracts.</span></span> <span data-ttu-id="ccd76-107">Du kan till exempel utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="ccd76-107">For example, you can perform the following tasks:</span></span>

- <span data-ttu-id="ccd76-108">Associera bidrag med projekt och finansieringskällor via länkar till sidorna **projekt** och **projektkontraktsinformation**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-108">Associate grants with projects and funding sources through links to the **Project** and **Project contract details** pages.</span></span>
- <span data-ttu-id="ccd76-109">Ange och spåra ändringar i ett anslag som flyttar från en status till en annan.</span><span class="sxs-lookup"><span data-stu-id="ccd76-109">Enter and track changes to a grant as it moves from one status to another.</span></span>
- <span data-ttu-id="ccd76-110">Ange och spåra kostnader, begärda tilldelade belopp och belopp.</span><span class="sxs-lookup"><span data-stu-id="ccd76-110">Enter and track costs, requested amounts, and awarded amounts.</span></span>
- <span data-ttu-id="ccd76-111">Skapa huvudanslag och koppla delanslag med dem.</span><span class="sxs-lookup"><span data-stu-id="ccd76-111">Create master grants, and associate subgrants with them.</span></span>

<span data-ttu-id="ccd76-112">Du kan skapa ett anslag genom att ange alla detaljer till den nya posten, eller så kan du kopiera informationen från ett befintligt anslag och sedan uppdatera den.</span><span class="sxs-lookup"><span data-stu-id="ccd76-112">You can create a grant by entering all the details in a new record, or you can copy the details from an existing grant and then update them.</span></span>

## <a name="create-a-new-grant"></a><span data-ttu-id="ccd76-113">Skapa ett nytt anslag</span><span class="sxs-lookup"><span data-stu-id="ccd76-113">Create a new grant</span></span>

1. <span data-ttu-id="ccd76-114">Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-114">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="ccd76-115">Välj **Ny** \> **Anslag**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-115">Select **New** \> **Grant**.</span></span>
3. <span data-ttu-id="ccd76-116">På sidan anslagsinformation, på snabbfliken **Allmänt** i fältet **anslags-ID** anger du en alfanumerisk identifierare för anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-116">On the grant details page, on the **General** FastTab, in the **Grant ID** field, enter an alphanumeric identifier for the grant.</span></span>
4. <span data-ttu-id="ccd76-117">I fältet **anslagsnamn** anger du ett namn för anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-117">In the **Grant name** field, enter a name for the grant.</span></span>
5. <span data-ttu-id="ccd76-118">I fältet **Beskrivning** lägger du till information om det nya anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-118">In the **Description** field, add details about the new grant.</span></span>

    <span data-ttu-id="ccd76-119">De flesta av de andra fälten på sidan är valfria, och du kan ange lite eller så mycket information, som du vill ha.</span><span class="sxs-lookup"><span data-stu-id="ccd76-119">Most of the other fields on the page are optional, and you can enter as little or as much information as you want.</span></span>

    <span data-ttu-id="ccd76-120">I följande lista beskrivs den information som anges på varje snabbflik på sidan beviljande av information:</span><span class="sxs-lookup"><span data-stu-id="ccd76-120">The following list describes the information that is specified on each FastTab of the grant details page:</span></span>

    - <span data-ttu-id="ccd76-121">**Allmänt** – Ange anslagets namn, status, beskrivning, syfte och belopp.</span><span class="sxs-lookup"><span data-stu-id="ccd76-121">**General** – Enter the grant name, status, description, purpose, and amount.</span></span>
    - <span data-ttu-id="ccd76-122">**Kontaktinformation** – Ange information om anställda, den avdelning som hanterar anslaget och anslagskunden eller organisationskällan för anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-122">**Contact information** – Enter details about staff members, the department that manages the grant, and the grant customer or organization source of the grant.</span></span> <span data-ttu-id="ccd76-123">Du kan också ange om din organisation är en mellanhand som tar emot anslaget och sedan passar det vidare till en annan mottagare.</span><span class="sxs-lookup"><span data-stu-id="ccd76-123">You can also indicate whether your organization is a pass-through entity that receives the grant and then passes it on to another recipient.</span></span> <span data-ttu-id="ccd76-124">Välj **Lägg till** om du vill lägga till kontaktinformation till exempel telefonnummer och e-postadresser för företaget som tillhandahåller anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-124">Select **Add** to add contact information such as telephone numbers and email addresses for the organization that provides the grant.</span></span>
    - <span data-ttu-id="ccd76-125">**Datum och deadlines** – Ange datum som är relaterade till anslaget och bevilja den till programmet.</span><span class="sxs-lookup"><span data-stu-id="ccd76-125">**Dates and deadlines** – Enter dates that are related to the grant and the grant application.</span></span> <span data-ttu-id="ccd76-126">Exempel på detta är förfallodatum för ansökan, överföringsdatum och det datum då anslaget godkänns eller avvisas.</span><span class="sxs-lookup"><span data-stu-id="ccd76-126">Examples include the application due date, the submission date, and the date when the grant is approved or rejected.</span></span>
    - <span data-ttu-id="ccd76-127">**Associerade projekt och projektkontrakt** – du kan bara ange information på den här snabbfliken om fältet **anslagets status** på snabbfliken **allmänt** är inställt på **aktiv** eller **beviljad**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-127">**Associated projects and project contracts** – You can enter information on this FastTab only if the **Grant status** field on the **General** FastTab is set to **Active** or **Awarded**.</span></span> <span data-ttu-id="ccd76-128">Välj bland följande alternativ för att slutföra den relaterade uppgiften:</span><span class="sxs-lookup"><span data-stu-id="ccd76-128">Select among the following options to complete the related task:</span></span>

        - <span data-ttu-id="ccd76-129">**Lägg till finansieringskällor** – Lägg till en ny finansieringskälla för anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-129">**Add funding source** – Add a new funding source for the grant.</span></span> <span data-ttu-id="ccd76-130">Du kan ange all information nu, eller du kan använda standardinformation och uppdatera dem senare.</span><span class="sxs-lookup"><span data-stu-id="ccd76-130">You can enter all the details now, or you can use default information and then update it later.</span></span>
        - <span data-ttu-id="ccd76-131">**Lägg till projektkontrakt** – Lägg till eller uppdatera information om projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="ccd76-131">**Add project contract** – Add or update project contract information.</span></span>
        - <span data-ttu-id="ccd76-132">**Lägg till projekt** – Lägg till eller uppdatera projektinformation.</span><span class="sxs-lookup"><span data-stu-id="ccd76-132">**Add project** – Add or update project details.</span></span>

    - <span data-ttu-id="ccd76-133">**Inställningar** – ange information om matchande medel, om den här informationen behövs.</span><span class="sxs-lookup"><span data-stu-id="ccd76-133">**Setup** – Enter details about matching funds, if this information is required.</span></span> <span data-ttu-id="ccd76-134">Många organisationer som tilldelar anslag kräver att den mottagaren spendera en viss summa av sina egna pengar eller resurser som matchar det belopp som används i anslaget.</span><span class="sxs-lookup"><span data-stu-id="ccd76-134">Many organizations that award grants require that recipients spend a specific amount of their own money or resources, to match the amount that is awarded in the grant.</span></span> <span data-ttu-id="ccd76-135">I fältet **lokalt projekt eller spårnings-ID** kan du ange en identifierare som skiljer sig från projektidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="ccd76-135">In the **Local project or tracking ID** field, you can enter an identifier that differs from the project identifier.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ccd76-136">Om en del av anslaget kommer att tilldelas en annan organisation, ange alternativet **Delöverlåtare** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-136">If part of the grant will be awarded to a different organization, set the **Subgrantor** option to **Yes**.</span></span> <span data-ttu-id="ccd76-137">För anslag som tilldelas i USA kan du ange om ett anslag tilldelas under en delstat eller federal fullmakt.</span><span class="sxs-lookup"><span data-stu-id="ccd76-137">For grants that are awarded in the United States, you can specify whether a grant will be awarded under a state mandate or a federal mandate.</span></span>

    - <span data-ttu-id="ccd76-138">**Neddragna detaljer** – Lägg till eller uppdatera information om hur ofta, anslag kan tas ut, faktureras eller spenderas.</span><span class="sxs-lookup"><span data-stu-id="ccd76-138">**Drawdown details** – Add or update information about how often grant funds can be withdrawn, billed for, or spent.</span></span>

## <a name="create-a-new-grant-from-a-copy"></a><span data-ttu-id="ccd76-139">Skapa ett nytt anslag från en kopia</span><span class="sxs-lookup"><span data-stu-id="ccd76-139">Create a new grant from a copy</span></span>

1. <span data-ttu-id="ccd76-140">Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-140">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="ccd76-141">Välj **Ny** \> **kopia från anslag**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-141">Select **New** \> **Copy from grant**.</span></span>
3. <span data-ttu-id="ccd76-142">Ange en alfanumerisk identifierare och ett namn för det nya anslaget och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-142">Enter an alphanumeric identifier and a name for the new grant, and then select **OK**.</span></span>
4. <span data-ttu-id="ccd76-143">Granska informationen för det kopierade anslaget på sidan med anslagsinformation och gör de ändringar som behövs.</span><span class="sxs-lookup"><span data-stu-id="ccd76-143">On the grant details page, review the details of the copied grant, and make any changes that are required.</span></span> <span data-ttu-id="ccd76-144">De flesta fälten på sidan är valfria.</span><span class="sxs-lookup"><span data-stu-id="ccd76-144">Most of the fields on the page are optional.</span></span>

## <a name="view-or-modify-grant-details"></a><span data-ttu-id="ccd76-145">Visa eller ändra anslagsdetaljer</span><span class="sxs-lookup"><span data-stu-id="ccd76-145">View or modify grant details</span></span>

1. <span data-ttu-id="ccd76-146">Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-146">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="ccd76-147">Välj det anslag du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="ccd76-147">Select the grant to modify.</span></span>
3. <span data-ttu-id="ccd76-148">I Åtgärdsfönstret, på fliken **anslag**, i gruppen **underhåll**, markerar du **redigera**.</span><span class="sxs-lookup"><span data-stu-id="ccd76-148">On the Action Pane, on the **Grant** tab, in the **Maintain** group, select **Edit**.</span></span>
4. <span data-ttu-id="ccd76-149">Granska anslagsdetaljerna och gör nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="ccd76-149">Review the grant details, and make any changes that are required.</span></span>
