---
title: Exportera data från Attract och Onboard
description: Exportera data från Dynamics 365 Talent - Attract och Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: acdd93637385246f9c5c652cccdf2cbfb263cc33
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975944"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="cbc3a-103">Exportera data från Attract och Onboard</span><span class="sxs-lookup"><span data-stu-id="cbc3a-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cbc3a-104">Som meddelas [Ta Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard-appar ur bruk](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), tar vi Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard ur bruk den 1 februari 2022.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="cbc3a-105">För att hjälpa till vid migreringen till en annan produkt tillhandahåller de båda apparna dataexportfunktioner.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="cbc3a-106">Exportera data från Attract</span><span class="sxs-lookup"><span data-stu-id="cbc3a-106">Export data from Attract</span></span>

<span data-ttu-id="cbc3a-107">Du kan exportera data utan att begränsa åtkomsten till din miljö.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="cbc3a-108">Du kanske vill göra detta i testningssyfte eller för att förstå vår datastruktur.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="cbc3a-109">När du är redo att migrera ska du begränsa åtkomsten till din locka miljö med hjälp av instruktionerna efter den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="cbc3a-110">Var noga med att exportera data.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="cbc3a-111">Gå till [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="cbc3a-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="cbc3a-112">Under **Dataexport**, välj **Begär en dataexport**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="cbc3a-113">Begär en dataexport från Attract</span><span class="sxs-lookup"><span data-stu-id="cbc3a-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="cbc3a-114">När meddelanderutan **Din begäran behandlas** visas, välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="cbc3a-115">Dataexporten kan ta upp till 20 minuter, beroende på hur stor exporten är.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="cbc3a-116">När exporten är klar väljer du knappen **Hämta** bredvid.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="cbc3a-117">All dataexport är tillgänglig i sju dagar, varvid länken **hämta** går ut.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="cbc3a-118">Hämtningen innehåller en zip-fil med dina Attract-data, inklusive följande mappar:</span><span class="sxs-lookup"><span data-stu-id="cbc3a-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="cbc3a-119">Mappnamn</span><span class="sxs-lookup"><span data-stu-id="cbc3a-119">Folder name</span></span> | <span data-ttu-id="cbc3a-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cbc3a-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="cbc3a-121">Administratörsinställningar</span><span class="sxs-lookup"><span data-stu-id="cbc3a-121">Admin settings</span></span> | <span data-ttu-id="cbc3a-122">Konfigurationer av Attract administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="cbc3a-123">Kandidater</span><span class="sxs-lookup"><span data-stu-id="cbc3a-123">Candidates</span></span> | <span data-ttu-id="cbc3a-124">Alla kandidater som har lagts till i jobb eller talangpooler.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="cbc3a-125">E-postmallar</span><span class="sxs-lookup"><span data-stu-id="cbc3a-125">Email templates</span></span> | <span data-ttu-id="cbc3a-126">Alla e-postmallar som har konfigurerats för miljön.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="cbc3a-127">Mallar för jobberbjudandepaket</span><span class="sxs-lookup"><span data-stu-id="cbc3a-127">Job offer package templates</span></span> | <span data-ttu-id="cbc3a-128">Alla jobberbjudandepaket som har skapats samt tillhörande konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="cbc3a-129">Regeluppsättningar för jobberbjudande</span><span class="sxs-lookup"><span data-stu-id="cbc3a-129">Job offer rule sets</span></span> |  <span data-ttu-id="cbc3a-130">Alla regeluppsättningsfiler som har överförts för erbjudandehantering.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="cbc3a-131">Mallar för jobberbjudande</span><span class="sxs-lookup"><span data-stu-id="cbc3a-131">Job offer templates</span></span> | <span data-ttu-id="cbc3a-132">Alla dokumentmallar för jobberbjudanden som skapats för miljön.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="cbc3a-133">Lediga jobb</span><span class="sxs-lookup"><span data-stu-id="cbc3a-133">Job openings</span></span> | <span data-ttu-id="cbc3a-134">Alla skapade jobb.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-134">All created jobs.</span></span> <span data-ttu-id="cbc3a-135">Borttagna jobb exporteras inte.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="cbc3a-136">Undermapparna innehåller kandidatansökningar, med undermappar för kandidatansökningars bilagor och erbjudandepaket, där det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="cbc3a-137">Mallar för lediga jobb</span><span class="sxs-lookup"><span data-stu-id="cbc3a-137">Job opening templates</span></span> | <span data-ttu-id="cbc3a-138">Mallar för jobbearbetning som har konfigurerats för miljön.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="cbc3a-139">Talangpooler</span><span class="sxs-lookup"><span data-stu-id="cbc3a-139">Talent pools</span></span> | <span data-ttu-id="cbc3a-140">Alla skapade talangpooler, deras deltagarlistor och listor över kandidater för talangpooler.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="cbc3a-141">Arbetare</span><span class="sxs-lookup"><span data-stu-id="cbc3a-141">Workers</span></span> | <span data-ttu-id="cbc3a-142">Lista över alla arbetare som finns i miljön, plus deras roller.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="cbc3a-143">(rotmapp)</span><span class="sxs-lookup"><span data-stu-id="cbc3a-143">(root folder)</span></span> | <span data-ttu-id="cbc3a-144">En JSON-schemafil som beskriver fälten i datastrukturen.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="cbc3a-145">Begränsa åtkomsten till Attract</span><span class="sxs-lookup"><span data-stu-id="cbc3a-145">Restrict access to Attract</span></span>

<span data-ttu-id="cbc3a-146">När du är redo att migrera kan du hindra icke-administratörer från att komma åt din Attract-miljö och exportera dina data.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="cbc3a-147">Att begränsa åtkomsten till din Attract-miljö är permanent och kan inte ångras.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="cbc3a-148">Om du vill att andra användare än administratörer ska kunna fortsätta att komma åt din miljö hoppar du över det här steget.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="cbc3a-149">Gå till [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="cbc3a-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="cbc3a-150">Om du vill hindra icke-administratörer från att komma åt din Attract-miljö, under **begränsa åtkomst till den här appen** väljer du **begränsa åtkomst nu**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="cbc3a-151">Om du begränsar åtkomsten avpublicerar du även aktiva jobb som har bokförts.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="cbc3a-152">Begränsa åtkomsten för de som inte är administratörer till Attract</span><span class="sxs-lookup"><span data-stu-id="cbc3a-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="cbc3a-153">Om varningen **Detta är en permanent ändring**, välj **begränsa åtkomsten** för att permanent begränsa användare som inte är administratörer från denna miljö.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="cbc3a-154">Om du inte är klar med det här steget väljer du **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="cbc3a-155">Varning att begränsa åtkomsten är permanent ändring</span><span class="sxs-lookup"><span data-stu-id="cbc3a-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="cbc3a-156">Administratörer kan fortsätta att komma åt sidorna för dataexport och personrapport när du har begränsat åtkomsten till din Attract-miljö.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="cbc3a-157">Exportera data från Onboard</span><span class="sxs-lookup"><span data-stu-id="cbc3a-157">Export data from Onboard</span></span>

<span data-ttu-id="cbc3a-158">När du är klar kan du hämta mallar, handböcker och kandidatdata från Onboard.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="cbc3a-159">Gå till [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="cbc3a-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="cbc3a-160">Under **Dataexport**, välj **Begär en dataexport**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="cbc3a-161">Begär en dataexport från Onboard</span><span class="sxs-lookup"><span data-stu-id="cbc3a-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="cbc3a-162">När meddelanderutan **Din begäran behandlas** visas, välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="cbc3a-163">Dataexporten kan ta upp till 20 minuter, beroende på hur stor exporten är.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="cbc3a-164">När exporten är klar väljer du knappen **Hämta** bredvid.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="cbc3a-165">Hämta dataexport från Onboard</span><span class="sxs-lookup"><span data-stu-id="cbc3a-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="cbc3a-166">Dataexporten är tillgänglig i sju dagar.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-166">Your data export is available for seven days.</span></span> <span data-ttu-id="cbc3a-167">Efter sju dagar går länken **hämta** ut och du måste begära en ny export om du behöver hämta dina data igen.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="cbc3a-168">När du startar en ny dataexport upphör alla befintliga hämtningar att gälla när den nya exporten har lyckats.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="cbc3a-169">Filen hämta är en zip-fil som innehåller:</span><span class="sxs-lookup"><span data-stu-id="cbc3a-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="cbc3a-170">En **mall**-mapp som innehåller dina Onboard-mallar i Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="cbc3a-171">En **Guider**-mapp som innehåller dina Onboard-guider i Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="cbc3a-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbc3a-172">Se även</span><span class="sxs-lookup"><span data-stu-id="cbc3a-172">See also</span></span>

[<span data-ttu-id="cbc3a-173">Ta Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard-appar ur bruk</span><span class="sxs-lookup"><span data-stu-id="cbc3a-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)