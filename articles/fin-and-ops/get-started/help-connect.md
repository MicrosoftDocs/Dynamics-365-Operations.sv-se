---
title: "Ansluta hjälpsystemet"
description: "Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Finance and Operations, en översikt över hur du ansluter dem samt en sammanfattning över hur du skapar anpassad hjälp."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a><span data-ttu-id="d7474-103">Ansluta hjälpsystemet</span><span class="sxs-lookup"><span data-stu-id="d7474-103">Connect the Help system</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d7474-104">Det här avsnittet innehåller komponenten för hjälpsystemet för Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7474-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="d7474-105">Det ger en översikt över hur du skapar ansluter dessa komponenter en sammanfattning av hur du skapar anpassad hjälp.</span><span class="sxs-lookup"><span data-stu-id="d7474-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="d7474-106">Hjälparkitektur</span><span class="sxs-lookup"><span data-stu-id="d7474-106">Help architecture</span></span>
<span data-ttu-id="d7474-107">Följande bild visar delarna i hjälpsystemet för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7474-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="d7474-108">Produktens interna hjälpsystem hämtar artiklar från Finance and Operations-webbplatsen på https://docs.microsoft.com, samt på uppgiftsguider som lagras i Affärsprocessmodelleraren i Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d7474-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="d7474-109">Funktionerna som anges med en asterisk (\*) i diagrammet planeras, men är ännu inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d7474-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="d7474-110">[![Hjälparkitektur](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="d7474-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="d7474-111">Ansluta hjälpsystemet</span><span class="sxs-lookup"><span data-stu-id="d7474-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="d7474-112">Fliken **Uppgiftsguider** finns för närvarande inte i Microsoft Dynamics 365 for Talent eller Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="d7474-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="d7474-113">Vi arbetar för närvarande med att aktivera den här funktionen i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="d7474-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="d7474-114">Uppgiftsguiderna i Komma igång i Talent täcker fortsatt basfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="d7474-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="d7474-115">Procedurhjälp finns även att få via webbplatsen docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) för såväl Retail som Talent.</span><span class="sxs-lookup"><span data-stu-id="d7474-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>
 

<span data-ttu-id="d7474-116">Med hjälp av sidan **Systemparametrar** ansluter systemadministratörer delar av hjälpsystemet för en implementering</span><span class="sxs-lookup"><span data-stu-id="d7474-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="d7474-117">[![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Gå till sidan **Systemparametrar** och följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d7474-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7474-118">Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="d7474-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="d7474-119">Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och klicka sedan på **OK** för att nå sidan **Systemparametrar**.[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="d7474-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="d7474-120">Välj Lifecycle Services-projektet att ansluta till.</span><span class="sxs-lookup"><span data-stu-id="d7474-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="d7474-121">Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.</span><span class="sxs-lookup"><span data-stu-id="d7474-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="d7474-122">Välj det nyaste förenade APQC-biblioteket för Finance and Operations om du vill ha Microsoft-innehåll.</span><span class="sxs-lookup"><span data-stu-id="d7474-122">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span> 
    - <span data-ttu-id="d7474-123">För Retail släpps snart ett eget bibliotek.</span><span class="sxs-lookup"><span data-stu-id="d7474-123">For Retail, we will be releasing a library in the near future.</span></span> 
    - <span data-ttu-id="d7474-124">Du behöver inte välja ett bibliotek för Talent — anslutningen till rätt bibliotek sker automatiskt.</span><span class="sxs-lookup"><span data-stu-id="d7474-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="d7474-125">Välj BPM-bibliotekens visningsordning.</span><span class="sxs-lookup"><span data-stu-id="d7474-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="d7474-126">Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.</span><span class="sxs-lookup"><span data-stu-id="d7474-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="d7474-127">När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7474-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="d7474-128">Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.</span><span class="sxs-lookup"><span data-stu-id="d7474-128">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="d7474-129">Visa översatta uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="d7474-129">Showing translated task guides</span></span>

<span data-ttu-id="d7474-130">Översätta uppgiftsguider medföljde i för första gången i APQC Unified Library i maj 2016, samt i Komma igång-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="d7474-130">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="d7474-131">Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Finance and Operations, se då till att du är ansluten till maj-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="d7474-131">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="d7474-132">Språket i uppgiftsguiden styrs av varje användare via språkinställningarna under **Alternativ** &gt; **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="d7474-132">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7474-133">Även om många uppgiftsguider har översatts, visas för närvarande inte namnen på de översatta uppgiftsguiderna i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7474-133">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="d7474-134">Dessutom är enbart de uppgiftsguider som släpptes i februari 2016 tillgängliga i översättningen i maj-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="d7474-134">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="d7474-135">Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.</span><span class="sxs-lookup"><span data-stu-id="d7474-135">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="d7474-136">Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="d7474-136">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="d7474-137">Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="d7474-137">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="d7474-138">Skapa anpassad hjälp</span><span class="sxs-lookup"><span data-stu-id="d7474-138">Creating custom help</span></span>
<span data-ttu-id="d7474-139">Du kan skapa anpassad hjälp för Finance and Operations samt för Retail genom att skapa uppgiftsinspelningar som speglar din implementering och spara dessa i ett bibliotek för LCS-arbetsprocesser.</span><span class="sxs-lookup"><span data-stu-id="d7474-139">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="d7474-140">Du kan inte skapa anpassade uppgiftsguider för Talent.</span><span class="sxs-lookup"><span data-stu-id="d7474-140">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="d7474-141">För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder.</span><span class="sxs-lookup"><span data-stu-id="d7474-141">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="d7474-142">Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="d7474-142">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="d7474-143">Mer information finns i avsnittet [Skapa en uppgiftsregistrering att använda som dokumentation eller utbildning](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="d7474-143">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="d7474-144">Se även</span><span class="sxs-lookup"><span data-stu-id="d7474-144">See also</span></span>
--------

[<span data-ttu-id="d7474-145">Hjälpöversikt</span><span class="sxs-lookup"><span data-stu-id="d7474-145">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="d7474-146">Uppgiftsregistreringsöversikt</span><span class="sxs-lookup"><span data-stu-id="d7474-146">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="d7474-147">Skapa en uppgiftsinspelning som ska användas som dokumentation eller utbildning</span><span class="sxs-lookup"><span data-stu-id="d7474-147">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)





