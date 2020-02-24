---
title: Ansluta hjälpsystemet
description: Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Finance and Operations-appar och ger en översikt över hur du kopplar dem och en sammanfattning av hur du skapar anpassad hjälp.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006182"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="fed6e-103">Ansluta hjälpsystemet</span><span class="sxs-lookup"><span data-stu-id="fed6e-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fed6e-104">I det här avsnittet beskrivs komponenterna i hjälpsystemet för Finance and Operations-appar, till exempel Dynamics 365 Finance, Supply Chain Management, Handel och Personal.</span><span class="sxs-lookup"><span data-stu-id="fed6e-104">This topic describes the components of the Help system for Finance and Operations apps, such as Dynamics 365 Finance, Supply Chain Management, Commerce, and Human Resources.</span></span> <span data-ttu-id="fed6e-105">Det ger en översikt över hur du skapar ansluter dessa komponenter en sammanfattning av hur du skapar anpassad hjälp.</span><span class="sxs-lookup"><span data-stu-id="fed6e-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="fed6e-106">Hjälparkitektur</span><span class="sxs-lookup"><span data-stu-id="fed6e-106">Help architecture</span></span>

<span data-ttu-id="fed6e-107">Följande bild visar delarna i hjälpsystemet.</span><span class="sxs-lookup"><span data-stu-id="fed6e-107">The following illustration shows the parts of the Help system.</span></span> <span data-ttu-id="fed6e-108">Produktens interna hjälpsystem hämtar artiklar från webbplatsen på https://docs.microsoft.com, samt på uppgiftsguider som lagras i Affärsprocessmodelleraren i Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fed6e-108">The in-product Help system pulls articles from https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="fed6e-109">Funktionerna som anges med en asterisk (\*) i diagrammet planeras, men är ännu inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="fed6e-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="fed6e-110">[![Hjälparkitektur](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="fed6e-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="fed6e-111">Ansluta hjälpsystemet</span><span class="sxs-lookup"><span data-stu-id="fed6e-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="fed6e-112">Fliken **uppgiftsguide** finns för närvarande inte i Dynamics 365 Human Resources eller Handel.</span><span class="sxs-lookup"><span data-stu-id="fed6e-112">The **Task guides** tab is currently not available in Dynamics 365 Human Resources or Commerce.</span></span> <span data-ttu-id="fed6e-113">Vi arbetar för närvarande med att aktivera den här funktionen i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="fed6e-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="fed6e-114">Uppgiftsguiderna i Komma igång i Personal täcker fortsatt basfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="fed6e-114">The Task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="fed6e-115">Procedurhjälp finns också på webbplatsen docs.microsoft.com för både Personal och Handel.</span><span class="sxs-lookup"><span data-stu-id="fed6e-115">Procedural help is also available on the docs.microsoft.com site for both Human Resources and Commerce.</span></span>

<span data-ttu-id="fed6e-116">Med hjälp av sidan **Systemparametrar** ansluter systemadministratörer delar av hjälpsystemet för en implementering</span><span class="sxs-lookup"><span data-stu-id="fed6e-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="fed6e-117">[![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="fed6e-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="fed6e-118">Gå till sidan **Systemparametrar** och följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="fed6e-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fed6e-119">Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="fed6e-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="fed6e-120">Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och klicka sedan på **OK** för att komma till sidan **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="fed6e-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="fed6e-121">[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="fed6e-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="fed6e-122">Välj Lifecycle Services-projektet att ansluta till.</span><span class="sxs-lookup"><span data-stu-id="fed6e-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="fed6e-123">Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.</span><span class="sxs-lookup"><span data-stu-id="fed6e-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="fed6e-124">Välj BPM-bibliotekens visningsordning.</span><span class="sxs-lookup"><span data-stu-id="fed6e-124">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="fed6e-125">Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.</span><span class="sxs-lookup"><span data-stu-id="fed6e-125">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="fed6e-126">När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="fed6e-126">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="fed6e-127">Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.</span><span class="sxs-lookup"><span data-stu-id="fed6e-127">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="fed6e-128">Visa översatta uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="fed6e-128">Showing translated task guides</span></span>

<span data-ttu-id="fed6e-129">Översätta uppgiftsguider medföljde i för första gången i APQC Unified Library i maj 2016, samt i Komma igång-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="fed6e-129">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="fed6e-130">I Finance and Operations-appar om du vill se hjälpen för den lokaliserade uppgiftsguiden ska du kontrollera att du är ansluten till May-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="fed6e-130">In Finance and Operations apps, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="fed6e-131">Språket i uppgiftsguiden styrs av varje användare via språkinställningarna under **Alternativ** &gt; **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="fed6e-131">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="fed6e-132">Även om många uppgiftsguider har översatts visas inte de översatta uppgiftsguiderna för närvarande i klienten.</span><span class="sxs-lookup"><span data-stu-id="fed6e-132">Even though many task guides have been translated, right now the client is not showing the translated task guide names.</span></span> <span data-ttu-id="fed6e-133">Dessutom är enbart de uppgiftsguider som släpptes i februari 2016 tillgängliga i översättningen i maj-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="fed6e-133">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="fed6e-134">Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.</span><span class="sxs-lookup"><span data-stu-id="fed6e-134">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="fed6e-135">Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="fed6e-135">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="fed6e-136">Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="fed6e-136">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="fed6e-137">Skapa anpassad hjälp</span><span class="sxs-lookup"><span data-stu-id="fed6e-137">Creating custom help</span></span>

<span data-ttu-id="fed6e-138">Du kan använda uppgiftsguiderna för att skapa anpassad hjälp eller ansluta en webbplats till hjälpfönstret.</span><span class="sxs-lookup"><span data-stu-id="fed6e-138">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="fed6e-139">Skapa anpassad hjälp med uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="fed6e-139">Create custom help with task guides</span></span>

<span data-ttu-id="fed6e-140">Du kan skapa anpassad hjälp för Finance and Operations, Supply Chain Management samt Handel genom att skapa uppgiftsinspelningar som speglar din implementering och spara dessa i ett bibliotek för LCS-arbetsprocesser.</span><span class="sxs-lookup"><span data-stu-id="fed6e-140">You can create custom help for Finance, Supply Chain Management, and Commerce by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="fed6e-141">Du kan inte anpassade uppgiftsguider för Personal.</span><span class="sxs-lookup"><span data-stu-id="fed6e-141">You cannot create custom task guides for Human Resources.</span></span>

<span data-ttu-id="fed6e-142">För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder.</span><span class="sxs-lookup"><span data-stu-id="fed6e-142">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="fed6e-143">Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="fed6e-143">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="fed6e-144">Mer information finns i [Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="fed6e-144">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="fed6e-145">Ansluta en anpassad webbplats</span><span class="sxs-lookup"><span data-stu-id="fed6e-145">Connect a custom site</span></span>

<span data-ttu-id="fed6e-146">Microsoft tillhandahåller en vitbok och exempelkod som beskriver hur du skapar och ansluter en anpassad hjälpwebbplats till hjälpfönstret.</span><span class="sxs-lookup"><span data-stu-id="fed6e-146">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="fed6e-147">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="fed6e-147">For more information, see:</span></span>

- [<span data-ttu-id="fed6e-148">Skapa anpassad hjälp för Finance and Operations-appar (vitbok)</span><span class="sxs-lookup"><span data-stu-id="fed6e-148">Create Custom Help for Finance and Operations apps (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="fed6e-149">Anpassad hjälp GitHub-databasen</span><span class="sxs-lookup"><span data-stu-id="fed6e-149">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="fed6e-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fed6e-150">Additional resources</span></span>

[<span data-ttu-id="fed6e-151">Hjälpsystem</span><span class="sxs-lookup"><span data-stu-id="fed6e-151">Help system</span></span>](help-overview.md)

[<span data-ttu-id="fed6e-152">Uppgiftsinspelarresurser</span><span class="sxs-lookup"><span data-stu-id="fed6e-152">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="fed6e-153">Skapa dokumentation eller utbildning med Uppgiftsinspelare</span><span class="sxs-lookup"><span data-stu-id="fed6e-153">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
