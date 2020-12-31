---
title: Konfigurera hjälpfunktionen för Finance and Operations-appar
description: I det här avsnittet finns information om komponenterna i hjälpsystemet för vissa Microsoft Dynamics 365-appar. Det innehåller även information om hur du ansluter dessa appar och en sammanfattning av processen för att skapa egen hjälp.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0495bbc008ed1760b98c2c1ace63fc4a8b1ab5cc
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694431"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="78c77-104">Konfigurera hjälpfunktionen för Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="78c77-104">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c77-105">I det här avsnittet finns en översikt över komponenterna i hjälpsystemet för Finance and Operations-appar, t.ex. Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="78c77-105">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="78c77-106">Ämnet förklarar även hur du ansluter dessa komponenter samt tillhandahåller en sammanfattning av processen för att skapa egen hjälp.</span><span class="sxs-lookup"><span data-stu-id="78c77-106">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="78c77-107">Hjälparkitektur</span><span class="sxs-lookup"><span data-stu-id="78c77-107">Help architecture</span></span>

<span data-ttu-id="78c77-108">Finance and Operations-appar innehåller begreppsmässiga översikter och andra ämnen som publiceras på [https://docs.microsoft.com/dynamics365](/dynamics365/)-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="78c77-108">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="78c77-109">Du når detta innehåll från **Hjälp**-fönstret i produkten.</span><span class="sxs-lookup"><span data-stu-id="78c77-109">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="78c77-110">Följande bild visar delarna i hjälpsystemet.</span><span class="sxs-lookup"><span data-stu-id="78c77-110">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="78c77-111">[![Hjälparkitektur](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="78c77-111">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="78c77-112">Hjälpsystemet i produkten hämtar artiklar från docs.microsoft.com och andra anslutna webbplatser.</span><span class="sxs-lookup"><span data-stu-id="78c77-112">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="78c77-113">Det tar också med uppgiftsguider som lagras i BPM (affärsprocessmodelleraren) i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="78c77-113">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="78c77-114">Lägga till uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="78c77-114">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="78c77-115">Fliken **Uppgiftsguider** finns för närvarande inte i Human Resources eller Commerce.</span><span class="sxs-lookup"><span data-stu-id="78c77-115">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="78c77-116">Uppgiftsguiderna i Komma igång i Human Resources täcker emellertid fortsatt basfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="78c77-116">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="78c77-117">Procedurhjälp för såväl Human Resources som Commerce finns att tillgå på [https://docs.microsoft.com/dynamics365](/dynamics365/)-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="78c77-117">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="78c77-118">På sidan **Systemparametrar** kan systemadministratörer konfigurera åtkomst till relevanta bibliotek för uppgiftsguider för en implementering.</span><span class="sxs-lookup"><span data-stu-id="78c77-118">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="78c77-119">Om du vill konfigurera Hjälp måste du vara inloggad på ett konto i samma klientorganisation där appen distribueras.</span><span class="sxs-lookup"><span data-stu-id="78c77-119">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="78c77-120">Det går inte att ansluta till ett LCS-bibliotek från en instans av appen som körs på en virtuell hårddisk (VHD).</span><span class="sxs-lookup"><span data-stu-id="78c77-120">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="78c77-121">[![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="78c77-121">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="78c77-122">Om du vill konfigurera uppgiftsguider för en lösning följer du instruktionerna på sidan **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="78c77-122">To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78c77-123">Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="78c77-123">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="78c77-124">Se till att välja länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och välj sedan **OK** för att komma till sidan **Systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="78c77-124">Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="78c77-125">[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="78c77-125">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="78c77-126">Välj Lifecycle Services-projektet att ansluta till.</span><span class="sxs-lookup"><span data-stu-id="78c77-126">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="78c77-127">Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.</span><span class="sxs-lookup"><span data-stu-id="78c77-127">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="78c77-128">Välj BPM-bibliotekens visningsordning.</span><span class="sxs-lookup"><span data-stu-id="78c77-128">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="78c77-129">Visningsordningen bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.</span><span class="sxs-lookup"><span data-stu-id="78c77-129">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="78c77-130">När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och välja fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="78c77-130">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="78c77-131">Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.</span><span class="sxs-lookup"><span data-stu-id="78c77-131">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="78c77-132">Visa översatta uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="78c77-132">Showing translated task guides</span></span>

<span data-ttu-id="78c77-133">Översatta uppgiftsguider medföljde för första gången i APQC Unified Library-versionen i maj 2016, samt i Komma igång-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="78c77-133">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="78c77-134">Om du vill se hjälpen för den lokaliserade uppgiftsguiden ska du se till att din Dynamics 365 for Operations-lösning är ansluten till maj 2016-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="78c77-134">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="78c77-135">Användare kan byta det språk som en uppgiftsguide visas i genom att byta språkinställning under **Alternativ** &gt; **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="78c77-135">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="78c77-136">Fastän många uppgiftsguider har översatts visas inte namnen på de översatta uppgiftsguiderna för närvarande i klienten.</span><span class="sxs-lookup"><span data-stu-id="78c77-136">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="78c77-137">I biblioteket från maj 2016 finns dessutom översättningar endast för de uppgiftsguider som släpptes i februari 2016.</span><span class="sxs-lookup"><span data-stu-id="78c77-137">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="78c77-138">Microsoft kommer att släppa ett uppdaterat bibliotek som omfattar fler översättningar.</span><span class="sxs-lookup"><span data-stu-id="78c77-138">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="78c77-139">Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="78c77-139">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="78c77-140">Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.</span><span class="sxs-lookup"><span data-stu-id="78c77-140">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="78c77-141">Lägga till anpassad hjälp</span><span class="sxs-lookup"><span data-stu-id="78c77-141">Adding custom Help</span></span>

<span data-ttu-id="78c77-142">Du kan använda uppgiftsguiderna för att skapa anpassad hjälp eller ansluta en anpassad hjälpwebbplats till fönstret **Hjälp**.</span><span class="sxs-lookup"><span data-stu-id="78c77-142">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="78c77-143">Skapa anpassad hjälp genom att använda uppgiftsguider</span><span class="sxs-lookup"><span data-stu-id="78c77-143">Create custom Help by using task guides</span></span>

<span data-ttu-id="78c77-144">Du kan skapa anpassad hjälp för dina stödda appar genom att skapa uppgiftsinspelningar som speglar din implementering och sedan spara dem i ett bibliotek för arbetsprocesser i LCS.</span><span class="sxs-lookup"><span data-stu-id="78c77-144">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="78c77-145">Du kan inte skapa anpassade uppgiftsguider för Human Resources.</span><span class="sxs-lookup"><span data-stu-id="78c77-145">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="78c77-146">Om du är partner och befordrar ett bibliotek till ett företagsbibliotek och inkluderar det i en lösning, blir det tillgängligt även för dina kunder.</span><span class="sxs-lookup"><span data-stu-id="78c77-146">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="78c77-147">Du kan också göra en kopia av APQC Unified Library och sedan öppna uppgiftsinspelningarna i din kopia, redigera dem och sedan spara dina ändringar.</span><span class="sxs-lookup"><span data-stu-id="78c77-147">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="78c77-148">Mer information finns i [Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="78c77-148">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="78c77-149">Ansluta en anpassad hjälpwebbplats</span><span class="sxs-lookup"><span data-stu-id="78c77-149">Connect a custom Help site</span></span>

<span data-ttu-id="78c77-150">Finance and Operations-appar används sällan i sina färdiga formulär.</span><span class="sxs-lookup"><span data-stu-id="78c77-150">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="78c77-151">Lösningen är i stället anpassad och utökad så att den passar organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="78c77-151">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="78c77-152">Du kan också anpassa och utöka hjälpfunktionen.</span><span class="sxs-lookup"><span data-stu-id="78c77-152">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="78c77-153">Du kan till exempel lägga till egen hjälp i produktens egna **Hjälp**-fönster.</span><span class="sxs-lookup"><span data-stu-id="78c77-153">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="78c77-154">Microsoft tillhandahåller en verktygslåda som hjälper dig att distribuera och ansluta anpassad hjälp till **Hjälp**-fönstret.</span><span class="sxs-lookup"><span data-stu-id="78c77-154">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="78c77-155">Information om hur du ställer in en anpassad hjälp-lösning som är ansluten till **Hjälp**-fönstret finns i [Översikt över anpassad hjälp](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78c77-155">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="78c77-156">Om du vill samarbeta med Microsoft angående verktyg och processer för att anpassa Hjälpen fyller du i formuläret på [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="78c77-156">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="78c77-157">Se även</span><span class="sxs-lookup"><span data-stu-id="78c77-157">See also</span></span>

[<span data-ttu-id="78c77-158">Hjälpsystem</span><span class="sxs-lookup"><span data-stu-id="78c77-158">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="78c77-159">Anpassad Hjälp – en översikt</span><span class="sxs-lookup"><span data-stu-id="78c77-159">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="78c77-160">Uppgiftsinspelarresurser</span><span class="sxs-lookup"><span data-stu-id="78c77-160">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="78c77-161">Skapa dokumentation eller utbildning med Uppgiftsinspelare</span><span class="sxs-lookup"><span data-stu-id="78c77-161">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="78c77-162">Anpassad GitHub-databas för Hjälp</span><span class="sxs-lookup"><span data-stu-id="78c77-162">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  
