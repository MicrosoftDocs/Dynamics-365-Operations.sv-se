---
title: Integrering av Microsoft Project-klient
description: "Att planera och underhålla en projekttidsplan kan vara komplext, därför behöver projektledare verktyg som hjälper dem att hantera uppgiften. Integration med Microsoft Project-klienten ger stöd för att öppna och hantera en uppdelad arbetsstruktur för projekt."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d412c60f22347a38e38ca5f2c5515bd132814f25
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="microsoft-project-client-integration"></a><span data-ttu-id="b619d-104">Integrering av Microsoft Project-klient</span><span class="sxs-lookup"><span data-stu-id="b619d-104">Microsoft Project client integration</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="b619d-105">Att planera och underhålla en projekttidsplan kan vara komplext, därför behöver projektledare verktyg som hjälper dem att hantera uppgiften.</span><span class="sxs-lookup"><span data-stu-id="b619d-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="b619d-106">Integration med Microsoft Project-klienten ger stöd för att öppna och hantera en uppdelad arbetsstruktur för projekt.</span><span class="sxs-lookup"><span data-stu-id="b619d-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="b619d-107">Projektledaren kan publicera alla ändringar tillbaka till den uppdelade arbetsstrukturen för projekt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b619d-107">The project manager can publish any changes back to the Finance and Operations project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="b619d-108">Om du använder Microsoft Dynamics 365 for Finance and Operations, Juli uppdatering, måste du installera KB 4054797 and 4055884.</span><span class="sxs-lookup"><span data-stu-id="b619d-108">If you are using Microsoft Dynamics 365 for Finance and Operations, July update, you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="b619d-109">Konfigurera tillägget för Microsoft Project-klienten</span><span class="sxs-lookup"><span data-stu-id="b619d-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="b619d-110">Om du vill aktivera integrationen med Microsoft Project-klienten behöver Microsoft Dynamics 365-tillägget installeras på användarens klient i Microsoft Project-programmet.</span><span class="sxs-lookup"><span data-stu-id="b619d-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="b619d-111">Detta görs genom att öppna arbetsytan för **projekthantering**.</span><span class="sxs-lookup"><span data-stu-id="b619d-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="b619d-112">• Klicka på **konfigurera tillägg för projekt-klient** från arbetsytans **länkar** > **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b619d-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="b619d-113">• Klicka på **öppna** och välj **kör** när du blir tillfrågad.</span><span class="sxs-lookup"><span data-stu-id="b619d-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="b619d-114">Öppna och redigera ett befintligt utkast till uppdelad arbetsstruktur i Microsoft Project-klienten</span><span class="sxs-lookup"><span data-stu-id="b619d-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="b619d-115">Om ett projekt i Finance and Operations redan har en uppdelad arbetsstruktur kan den uppdelade arbetsstrukturen öppnas i Microsoft Project klientprogrammet, om strukturen har statusen utkast.</span><span class="sxs-lookup"><span data-stu-id="b619d-115">If a project in Finance and Operations already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="b619d-116">För att öppna från sidan för **projekt** klicka på länken som **öppnar Microsoft Project** från fliken för **planera**. Den här sidan kan även öppnas från Microsoft Project-klientprogrammet genom att klicka på **öppna** i fliken **Microsoft Dynamics 365**. Välj **juridisk person** och **projekt** i listan.</span><span class="sxs-lookup"><span data-stu-id="b619d-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="b619d-117">Om du använder Internet Explorer som webbläsare kan du behöva klicka på **spara** för att manuellt öppna från den plats filen är nedladdad till.</span><span class="sxs-lookup"><span data-stu-id="b619d-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="b619d-118">Eller klicka på **spara och öppna** för att öppna filen i Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="b619d-119">Byt inte namn på filen när du sparar.</span><span class="sxs-lookup"><span data-stu-id="b619d-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="b619d-120">Innan du gör redigeringar i filen med hjälp av Microsoft Project-klienten måste du checka ut den. Klicka på **utcheckning** i fliken **Microsoft Dynamics 365**. Detta förhindrar att andra användare redigerar den uppdelade arbetsstrukturen i Finance and Operations samtidigt.</span><span class="sxs-lookup"><span data-stu-id="b619d-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance and Operations at the same time.</span></span> <span data-ttu-id="b619d-121">Om du vill publicera den uppdelade arbetsstrukturen efter att du slutfört redigeringarna klickar du på **checka in** i fliken **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="b619d-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="b619d-122">Om en projektgrupp redan har lagts till projektet i Finance and Operations fylls resurslistan med gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="b619d-122">If a project team has already been added to the project in Finance and Operations, the resource list will be populated with the team members.</span></span> <span data-ttu-id="b619d-123">Om en projektgrupp inte har lagts till i projektet kan du välja resurser och skapa ett team i Microsoft Project-klienten genom att klicka på knappen **resurser** i fliken **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="b619d-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="b619d-124">Följande data synkroniseras tillbaka till Finance and Operations som en del av incheckningsprocessen:</span><span class="sxs-lookup"><span data-stu-id="b619d-124">The following data will be synced back to Finance and Operations as part of the check in process:</span></span>

<span data-ttu-id="b619d-125">•   Uppgiftsnamn</span><span class="sxs-lookup"><span data-stu-id="b619d-125">•   Task name</span></span>

<span data-ttu-id="b619d-126">•   Startdatum</span><span class="sxs-lookup"><span data-stu-id="b619d-126">•   Start date</span></span>

<span data-ttu-id="b619d-127">•   Slutdatum</span><span class="sxs-lookup"><span data-stu-id="b619d-127">•   Finish date</span></span>

<span data-ttu-id="b619d-128">•   Företrädare</span><span class="sxs-lookup"><span data-stu-id="b619d-128">•   Predecessors</span></span>

<span data-ttu-id="b619d-129">•   Resursnamn</span><span class="sxs-lookup"><span data-stu-id="b619d-129">•   Resource names</span></span>

<span data-ttu-id="b619d-130">•   Kategori</span><span class="sxs-lookup"><span data-stu-id="b619d-130">•   Category</span></span>

<span data-ttu-id="b619d-131">•   Resurskategori</span><span class="sxs-lookup"><span data-stu-id="b619d-131">•   Resource category</span></span>

<span data-ttu-id="b619d-132">•   Arbetstimmar</span><span class="sxs-lookup"><span data-stu-id="b619d-132">•   Work hours</span></span>

<span data-ttu-id="b619d-133">•   Noteringar</span><span class="sxs-lookup"><span data-stu-id="b619d-133">•   Notes</span></span>

<span data-ttu-id="b619d-134">•   Prioritet</span><span class="sxs-lookup"><span data-stu-id="b619d-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="b619d-135">Om du lägger till andra kolumner i filen i Microsoft Project-klienten sparas inte kolumnerna och visas inte när filen öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="b619d-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="b619d-136">Skapa den uppdelade arbetsstrukturen för ett befintligt projekt med hjälp av Microsoft Project-klienten</span><span class="sxs-lookup"><span data-stu-id="b619d-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="b619d-137">För att skapa en ny uppdelad arbetsstruktur för ett befintligt projekt med hjälp av Microsoft Project-klienten gör du så här:</span><span class="sxs-lookup"><span data-stu-id="b619d-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="b619d-138">Öppna Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="b619d-139">I fliken **Microsoft Dynamics 365** klickar du på **öppna**.</span><span class="sxs-lookup"><span data-stu-id="b619d-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="b619d-140">Välj **juridisk person** för projektet.</span><span class="sxs-lookup"><span data-stu-id="b619d-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="b619d-141">Välj lämpligt **projekt**.</span><span class="sxs-lookup"><span data-stu-id="b619d-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="b619d-142">I fliken **Microsoft Dynamics 365** klickar du på **checka ut**.</span><span class="sxs-lookup"><span data-stu-id="b619d-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="b619d-143">När du är klar att publicera till Finance and Operations klickar du på **checka in** på fliken **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="b619d-143">When ready to publish to Finance and Operations, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="b619d-144">Ersätt en befintlig uppdelad arbetsstruktur för ett befintligt projekt med hjälp av Microsoft Project-klienten</span><span class="sxs-lookup"><span data-stu-id="b619d-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="b619d-145">Om du vill skapa en ny uppdelad arbetsstruktur med hjälp av Microsoft Project-klienten och ersätta en befintlig struktur för ett befintligt projekt gör så här:</span><span class="sxs-lookup"><span data-stu-id="b619d-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="b619d-146">Öppna Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="b619d-147">Skapa tidsplanen i Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="b619d-148">I fliken **Microsoft Dynamics 365** klickar du på **spara ändringarna** > **ersätt befintligt projekt**.</span><span class="sxs-lookup"><span data-stu-id="b619d-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="b619d-149">Välj **juridisk person** för projektet.</span><span class="sxs-lookup"><span data-stu-id="b619d-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="b619d-150">Välj lämpligt **projekt**.</span><span class="sxs-lookup"><span data-stu-id="b619d-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="b619d-151">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b619d-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="b619d-152">Skapa ett nytt projekt från Microsoft Project-klienten</span><span class="sxs-lookup"><span data-stu-id="b619d-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="b619d-153">Öppna Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="b619d-154">Skapa tidsplanen i Microsoft Project-klienten.</span><span class="sxs-lookup"><span data-stu-id="b619d-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="b619d-155">I fliken **Microsoft Dynamics 365** klickar du på **spara ändringarna** > **spara som nytt projekt**.</span><span class="sxs-lookup"><span data-stu-id="b619d-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="b619d-156">Välj **juridisk person** för projektet.</span><span class="sxs-lookup"><span data-stu-id="b619d-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="b619d-157">Ange **projekt-ID** om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b619d-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="b619d-158">Ange det **projektnamnet**.</span><span class="sxs-lookup"><span data-stu-id="b619d-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="b619d-159">Välj **projekttyp**, **projektgrupp** och **projektkontrakt-ID**.</span><span class="sxs-lookup"><span data-stu-id="b619d-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="b619d-160">Du kan också skapa ett nytt projektkontrakt genom att klicka på **New**.</span><span class="sxs-lookup"><span data-stu-id="b619d-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="b619d-161">Välj vilken **kalender** som ska användas för resurshantering.</span><span class="sxs-lookup"><span data-stu-id="b619d-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="b619d-162">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b619d-162">Click **OK**.</span></span>

