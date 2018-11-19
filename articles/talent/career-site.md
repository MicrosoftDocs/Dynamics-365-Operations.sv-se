---
title: "Funktionen för karriärwebbplats i Attract"
description: "Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 for Talent - Attract. Den förklarar även hur du ställer in denna funktion."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="ee1b3-104">Funktionen för karriärwebbplats i Attract</span><span class="sxs-lookup"><span data-stu-id="ee1b3-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ee1b3-105">Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 for Talent - Attract.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="ee1b3-106">Den förklarar även hur du ställer in denna funktion.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="ee1b3-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="ee1b3-107">Overview</span></span>

<span data-ttu-id="ee1b3-108">Attract ger en karriärwebbplats för olika miljöer i en klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="ee1b3-109">Om till exempel ett företag har en utvecklingsmiljö och en testmiljö kan en karriärwebbplats för utvecklingsmiljön tilldelas utvecklingsmiljön och en annan karriärwebbplats tilldelas testmiljön.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="ee1b3-110">Varje karriärwebbplats är **helt isolerad** och har en egen autentiseringsmekanism.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="ee1b3-111">Jobb och kandidatprofiler delas inte mellan karriärwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="ee1b3-112">Som standard är karriärwebbplatsen offentlig.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-112">By default, the career site is public.</span></span> <span data-ttu-id="ee1b3-113">Kandidater kan därför visa alla jobb som markeras som externa utan att behöva logga in.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="ee1b3-114">Alla andra åtgärder kräver emellertid att kandidater loggar in.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="ee1b3-115">Hantera karriärwebbplats</span><span class="sxs-lookup"><span data-stu-id="ee1b3-115">Career site management</span></span>

<span data-ttu-id="ee1b3-116">Följande artiklar på karriärwebbplatsen styrs av inställningarna:</span><span class="sxs-lookup"><span data-stu-id="ee1b3-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="ee1b3-117">**Organisationsnamn:** organisationsnamnet visas i navigeringsfältet längst upp i karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="ee1b3-118">Genom att välja organisationsnamn kan kandidater gå till en sida som visar alla lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="ee1b3-119">**Organisationslogga:** en bild av företagets logotyp visas längst upp till vänster på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="ee1b3-120">Genom att välja logotypbild kan kandidater gå till en sida som visar alla lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="ee1b3-121">Om du vill ange värden för organisationsnamn och logotyp loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Företagsupplysningar**.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="ee1b3-122">Logotypbilden som visas på karriärwebbplatsen har en fast höjd på 20 pixlar (px).</span><span class="sxs-lookup"><span data-stu-id="ee1b3-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="ee1b3-123">Bilden som du lägger till i administratörscentret skalas så att den passar.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="ee1b3-124">Därför kan bredden ändras, beroende på bilden.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="ee1b3-125">Webbadress till karriärwebbplats</span><span class="sxs-lookup"><span data-stu-id="ee1b3-125">Career site URL</span></span>

<span data-ttu-id="ee1b3-126">När du [bokför ett externt jobb](./Creating-jobs-Attract.md#postings) för första gången, kan du kopiera länken **Använd** från Attract-programmet.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="ee1b3-127">URL-adressen för den här länken är i följande format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="ee1b3-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="ee1b3-128">URL-adressen till karriärwebbplatsen är en delsträng av URL:en **Använd**.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="ee1b3-129">Den består av allt upp genom företagsnamnet.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="ee1b3-130">Därför är karriärwebbplatsens URL för de föregående webbadressen för **Använd** `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="ee1b3-131">Autentiseringsalternativ</span><span class="sxs-lookup"><span data-stu-id="ee1b3-131">Authentication options</span></span>

<span data-ttu-id="ee1b3-132">Kandidater har följande inloggningsalternativ för en Attract karriärwebbplats:</span><span class="sxs-lookup"><span data-stu-id="ee1b3-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="ee1b3-133">Personligt konto:</span><span class="sxs-lookup"><span data-stu-id="ee1b3-133">Personal account:</span></span>

    - <span data-ttu-id="ee1b3-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ee1b3-134">LinkedIn</span></span>
    - <span data-ttu-id="ee1b3-135">Microsoft </span><span class="sxs-lookup"><span data-stu-id="ee1b3-135">Microsoft</span></span>
    - <span data-ttu-id="ee1b3-136">Google</span><span class="sxs-lookup"><span data-stu-id="ee1b3-136">Google</span></span>
    - <span data-ttu-id="ee1b3-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="ee1b3-137">Facebook</span></span>

- <span data-ttu-id="ee1b3-138">Jobb- eller skolkonto:</span><span class="sxs-lookup"><span data-stu-id="ee1b3-138">Work or school account:</span></span>

    - <span data-ttu-id="ee1b3-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ee1b3-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="ee1b3-140">Azure AD-inloggning är endast avsedd för interna kandidater.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="ee1b3-141">Därför fungerar den endast för interna kandidater som utnyttjar deras Azure AD-autentiseringsuppgifter för företag.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="ee1b3-142">Till exempel vill en kandidat som för närvarande är anställd på Contoso, Ltd. ansöka om ett jobb i ett inte relaterat företag Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="ee1b3-143">I det här fallet kommer inloggningen att misslyckas om medarbetaren försöker använda hans eller hennes Azure AD-autentiseringsuppgifter från Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="ee1b3-144">Skapa och underhålla en profil</span><span class="sxs-lookup"><span data-stu-id="ee1b3-144">Create and maintain a profile</span></span>

<span data-ttu-id="ee1b3-145">När kandidater loggar in på karriärwebbplatsen kan de välja **min profil** i navigeringsfältet längst upp på sidan om de vill skapa och underhålla sin profil.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="ee1b3-146">Profilen innehåller personuppgifter, information om arbetserfarenhet, utbildningsuppgifter, dokument, länkar och information om kompetensuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="ee1b3-147">När en profil har skapats kan den användas till att ansöka om ett jobb som kandidaten är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="ee1b3-148">Profiler kan också hjälpa Attract att rekommendera rätt jobb till kandidater.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="ee1b3-149">Hitta rätt jobb</span><span class="sxs-lookup"><span data-stu-id="ee1b3-149">Find the right job</span></span>

<span data-ttu-id="ee1b3-150">På listsidan för jobb kan kandidater söka efter ett visst jobb genom att ange sökvillkor.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="ee1b3-151">Sökfunktionen söker efter sökord i jobbtitlar och arbetsbeskrivningar och visar relevanta jobb som resultat.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="ee1b3-152">Kandidater kan filtrera resultaten när som helst baserat på plats för jobbet eller arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="ee1b3-153">Kandidater kan också visa en uppsättning av rekommenderade jobb på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="ee1b3-154">Jobben som rekommenderas till en kandidat baseras på kandidatens tidigare ansökningar, profil och meritförteckningar.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="ee1b3-155">Jobbrekommendationer visas endast om minst 10 jobb publiceras på karriärwebbplatsen och om kandidaten har slutfört sin profil.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="ee1b3-156">Söka jobb</span><span class="sxs-lookup"><span data-stu-id="ee1b3-156">Apply for jobs</span></span>

<span data-ttu-id="ee1b3-157">När kandidater hittar rätt jobb kan de ansöka om det med hjälp av knappen **Ansök** på jobbets detaljsida.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="ee1b3-158">Nu kan kandidater antingen skapa en helt ny profil eller gå igenom informationen i den befintliga profilen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="ee1b3-159">Kandidater kan också vid behov överföra en meritförteckning och sedan skicka in jobbansökningen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="ee1b3-160">Kontrollera ansökningsstatus</span><span class="sxs-lookup"><span data-stu-id="ee1b3-160">Check application status</span></span>

<span data-ttu-id="ee1b3-161">När kandidater ansöker om ett eller flera jobb, kan de välja **Ansökningar** i navigeringsfältet längst upp på sidan för att visa öppna och stängda ansökningar.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="ee1b3-162">När kandidater öppnar en av sina ansökningar, visas den aktuella fasen samt eventuella väntande uppgifter som de måste slutföra.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="ee1b3-163">Om en kandidat t.ex. måste ange möjliga datum för en personlig intervju visar sidan hans eller hennes alternativ.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="ee1b3-164">Interna jobb</span><span class="sxs-lookup"><span data-stu-id="ee1b3-164">Internal jobs</span></span>

<span data-ttu-id="ee1b3-165">För närvarande visas jobb som markerats som interna och publicerade på Attract karriärwebbplatsen inte på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="ee1b3-166">De är endast tillgängliga via den direkta **Ansöknings**-URL:en som kan kopieras från Attract-programmet.</span><span class="sxs-lookup"><span data-stu-id="ee1b3-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

