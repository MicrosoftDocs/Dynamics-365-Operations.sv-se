---
title: Funktionen för karriärwebbplats i Attract
description: Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Attract.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/13/2019
ms.locfileid: "389986"
---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="3ac73-103">Funktionen för karriärwebbplats i Attract</span><span class="sxs-lookup"><span data-stu-id="3ac73-103">Career site functionality in Attract</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3ac73-104">Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="3ac73-104">This topic provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="3ac73-105">Den förklarar även hur du ställer in denna funktion.</span><span class="sxs-lookup"><span data-stu-id="3ac73-105">It also explains how to set up this functionality.</span></span>

<span data-ttu-id="3ac73-106">Attract ger en karriärwebbplats för olika miljöer i en klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="3ac73-106">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="3ac73-107">Om till exempel ett företag har en utvecklingsmiljö och en testmiljö kan en karriärwebbplats för utvecklingsmiljön tilldelas utvecklingsmiljön och en annan karriärwebbplats tilldelas testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3ac73-107">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="3ac73-108">Varje karriärwebbplats är helt isolerad och har en egen autentiseringsmekanism.</span><span class="sxs-lookup"><span data-stu-id="3ac73-108">Each career site is completely isolated and has its own authentication mechanism.</span></span> <span data-ttu-id="3ac73-109">Jobb och kandidatprofiler delas inte mellan karriärwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="3ac73-109">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="3ac73-110">Som standard är karriärwebbplatsen offentlig.</span><span class="sxs-lookup"><span data-stu-id="3ac73-110">By default, the career site is public.</span></span> <span data-ttu-id="3ac73-111">Kandidater kan därför visa alla jobb som markeras som externa utan att behöva logga in.</span><span class="sxs-lookup"><span data-stu-id="3ac73-111">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="3ac73-112">Alla andra åtgärder kräver emellertid att kandidater loggar in.</span><span class="sxs-lookup"><span data-stu-id="3ac73-112">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="3ac73-113">Hantera karriärwebbplats</span><span class="sxs-lookup"><span data-stu-id="3ac73-113">Career site management</span></span>

<span data-ttu-id="3ac73-114">Om du vill ange värden för följande artiklar loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Företagsupplysningar**.</span><span class="sxs-lookup"><span data-stu-id="3ac73-114">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

-   <span data-ttu-id="3ac73-115">**Organisationsnamn** - organisationsnamnet visas i navigeringsfältet längst upp i karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-115">**Organization name** - The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="3ac73-116">Genom att välja organisationsnamn kan kandidater gå till en sida som visar alla lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="3ac73-116">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>

-   <span data-ttu-id="3ac73-117">**Organisationslogga** - en bild av företagets logotyp visas längst upp till vänster på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-117">**Organization logo** - An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="3ac73-118">Genom att välja logotypbild kan kandidater gå till en sida som visar alla lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="3ac73-118">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="3ac73-119">Logotypbilden som visas på karriärwebbplatsen har en fast höjd på 20 pixlar (px).</span><span class="sxs-lookup"><span data-stu-id="3ac73-119">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="3ac73-120">Bilden som du lägger till i administratörscentret skalas så att den passar.</span><span class="sxs-lookup"><span data-stu-id="3ac73-120">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="3ac73-121">Därför kan bredden ändras, beroende på bilden.</span><span class="sxs-lookup"><span data-stu-id="3ac73-121">Therefore, depending on the image, the width might change.</span></span>
 
<span data-ttu-id="3ac73-122">Om du vill ange värden för följande artiklar loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Hantera karriärwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="3ac73-122">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="3ac73-123">**Sökmotoroptimering** - om aktiverad kommer alla offentliga jobb som publiceras på Attract karriärwebbplats att vara sökbara med hjälp av sökmotorer som Bing och Google.</span><span class="sxs-lookup"><span data-stu-id="3ac73-123">**Search Engine Optimization** - When enabled, all public jobs posted to Attract career site will be searchable using search engines like Bing and Google.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="3ac73-124">Det kan finnas en fördröjning mellan aktivering av inställningen och sökresultaten som visas, beroende på sökfunktionen du använder.</span><span class="sxs-lookup"><span data-stu-id="3ac73-124">There might be a delay between turning this setting on and search results appearing, depending on the search engine that you are using.</span></span>
         
## <a name="career-site-urls"></a><span data-ttu-id="3ac73-125">URL för karriärwebbplats</span><span class="sxs-lookup"><span data-stu-id="3ac73-125">Career site URLs</span></span>

<span data-ttu-id="3ac73-126">Följande lista innehåller vanliga URL för karriärwebbplatser och hur du kommer åt dem.</span><span class="sxs-lookup"><span data-stu-id="3ac73-126">The following list contains the commonly used career site URLs and how to access them.</span></span>

-   <span data-ttu-id="3ac73-127">**Karriärwebbplatsens startside-URL** - för att visa startsidan för karriärwebbplatsen, logga in i Attract som administratör och välj **administratörscenter** på menyn **inställningar** -och välj sedan fliken **Hantera karriärwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="3ac73-127">**Career site home page URL** - To view the career site home page URL, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="3ac73-128">**Svars-URL för individuell jobbpublicering** - När du [publicerar ett externt jobb](Creating-jobs-Attract.md#postings) för första gången, kan du kopiera länken **Använd** från Attract-programmet.</span><span class="sxs-lookup"><span data-stu-id="3ac73-128">**Individual job post apply URL** - When you [post an external job](Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="3ac73-129">URL-adressen för den här länken är i följande format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span><span class="sxs-lookup"><span data-stu-id="3ac73-129">The URL for this link will be in the following format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span></span>

-   <span data-ttu-id="3ac73-130">**Individuell jobbpublicerings-URL** - URL för jobbpubliceringen är en delsträng av svars-URL.</span><span class="sxs-lookup"><span data-stu-id="3ac73-130">**Individual job post URL** - The URL of the job post is a substring of the Apply URL.</span></span> <span data-ttu-id="3ac73-131">Den består av allt upp genom jobbnumret.</span><span class="sxs-lookup"><span data-stu-id="3ac73-131">It consists of everything up through the job number.</span></span> <span data-ttu-id="3ac73-132">Därför är jobbpublicerings-URL:en för de föregående svars-URL [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span><span class="sxs-lookup"><span data-stu-id="3ac73-132">Therefore, for the preceding Apply URL, the job post URL is [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span></span>

## <a name="authentication-options"></a><span data-ttu-id="3ac73-133">Autentiseringsalternativ</span><span class="sxs-lookup"><span data-stu-id="3ac73-133">Authentication options</span></span>

<span data-ttu-id="3ac73-134">Kandidater har följande inloggningsalternativ för en Attract karriärwebbplats:</span><span class="sxs-lookup"><span data-stu-id="3ac73-134">Candidates have the following sign-in options for an Attract career site:</span></span>

-   <span data-ttu-id="3ac73-135">Personligt konto:</span><span class="sxs-lookup"><span data-stu-id="3ac73-135">Personal account:</span></span>

    -   <span data-ttu-id="3ac73-136">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3ac73-136">LinkedIn</span></span>

    -   <span data-ttu-id="3ac73-137">Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ac73-137">Microsoft</span></span>

    -   <span data-ttu-id="3ac73-138">Google</span><span class="sxs-lookup"><span data-stu-id="3ac73-138">Google</span></span>

    -   <span data-ttu-id="3ac73-139">Facebook</span><span class="sxs-lookup"><span data-stu-id="3ac73-139">Facebook</span></span>

-   <span data-ttu-id="3ac73-140">Jobb- eller skolkonto:</span><span class="sxs-lookup"><span data-stu-id="3ac73-140">Work or school account:</span></span>

    -   <span data-ttu-id="3ac73-141">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3ac73-141">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="3ac73-142">Azure AD-inloggning är endast avsedd för interna kandidater.</span><span class="sxs-lookup"><span data-stu-id="3ac73-142">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="3ac73-143">Därför fungerar den endast för interna kandidater som utnyttjar deras Azure AD-autentiseringsuppgifter för företag.</span><span class="sxs-lookup"><span data-stu-id="3ac73-143">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="3ac73-144">Till exempel vill en kandidat som för närvarande är anställd på Contoso, Ltd. ansöka om ett jobb i ett inte relaterat företag Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="3ac73-144">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="3ac73-145">I det här fallet kommer inloggningen att misslyckas om medarbetaren försöker använda hans eller hennes Azure AD-autentiseringsuppgifter från Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="3ac73-145">In this case, the sign-in will be unsuccessful if the employee tries to use Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="3ac73-146">Skapa och underhålla en profil</span><span class="sxs-lookup"><span data-stu-id="3ac73-146">Create and maintain a profile</span></span>

<span data-ttu-id="3ac73-147">När kandidater loggar in på karriärwebbplatsen kan de välja **min profil** i navigeringsfältet längst upp på sidan om de vill skapa och underhålla sin profil.</span><span class="sxs-lookup"><span data-stu-id="3ac73-147">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span>
<span data-ttu-id="3ac73-148">Profilen innehåller personuppgifter, information om arbetserfarenhet, utbildningsuppgifter, dokument, länkar och information om kompetensuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="3ac73-148">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="3ac73-149">När en profil har skapats kan den användas till att ansöka om ett jobb som kandidaten är intresserad av.</span><span class="sxs-lookup"><span data-stu-id="3ac73-149">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="3ac73-150">Profiler kan också hjälpa Attract att rekommendera rätt jobb till kandidater.</span><span class="sxs-lookup"><span data-stu-id="3ac73-150">Profiles also help Attract recommend the right jobs to candidates.</span></span>

>   [!NOTE]
>   <span data-ttu-id="3ac73-151">Om en kandidat använder ett e-post-ID för att logga in på någon av de autentiseringsproviders som anges ovan, kommer detta e-post-ID överföras som standard till kontaktens e-post-ID som är kopplat till profilen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-151">If a candidate uses an email ID to sign in using one of the authentication providers listed above, that email ID will default to the contact email ID associated with the profile.</span></span> <span data-ttu-id="3ac73-152">Men detta kan ändras när som helst och är helt oberoende av den förra.</span><span class="sxs-lookup"><span data-stu-id="3ac73-152">However, the latter can be changed at any time and is completely independent of the former.</span></span> <span data-ttu-id="3ac73-153">Attract kommer alltid använder kontakters e-post-ID för att koppla till profilen för alla e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="3ac73-153">Attract will always use the contact email ID to associate with your profile for all email communications.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="3ac73-154">Hitta rätt jobb</span><span class="sxs-lookup"><span data-stu-id="3ac73-154">Find the right job</span></span>

<span data-ttu-id="3ac73-155">På listsidan för jobb kan kandidater söka efter ett visst jobb genom att ange sökvillkor.</span><span class="sxs-lookup"><span data-stu-id="3ac73-155">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="3ac73-156">Sökfunktionen söker efter sökord i jobbtitlar och arbetsbeskrivningar och visar relevanta jobb som resultat.</span><span class="sxs-lookup"><span data-stu-id="3ac73-156">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="3ac73-157">Kandidater kan filtrera resultaten när som helst baserat på plats för jobbet eller arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3ac73-157">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="3ac73-158">Kandidater kan också visa en uppsättning av rekommenderade jobb på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-158">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="3ac73-159">Jobben som rekommenderas till en kandidat baseras på kandidatens tidigare ansökningar, profil och meritförteckningar.</span><span class="sxs-lookup"><span data-stu-id="3ac73-159">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

>   [!NOTE] 
>   <span data-ttu-id="3ac73-160">Jobbrekommendationer visas endast om minst 10 jobb publiceras på karriärwebbplatsen och om kandidaten har slutfört en profil.</span><span class="sxs-lookup"><span data-stu-id="3ac73-160">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed a profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="3ac73-161">Söka jobb</span><span class="sxs-lookup"><span data-stu-id="3ac73-161">Apply for jobs</span></span>

<span data-ttu-id="3ac73-162">När kandidater hittar rätt jobb kan de ansöka om det med hjälp av knappen **Ansök** på sidan **Jobbdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="3ac73-162">After candidates find the right job, they can apply by using the **Apply** button on the **Job details** page.</span></span> <span data-ttu-id="3ac73-163">Nu kan kandidater antingen skapa en ny profil eller gå igenom informationen i den befintliga profilen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-163">At this point, candidates can either create a new profile or review the information in their existing profile.</span></span>
<span data-ttu-id="3ac73-164">Kandidater kan också vid behov överföra en meritförteckning och sedan skicka in jobbansökningen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-164">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="3ac73-165">Kontrollera ansökningsstatus</span><span class="sxs-lookup"><span data-stu-id="3ac73-165">Check application status</span></span>

<span data-ttu-id="3ac73-166">När kandidater ansöker om ett eller flera jobb, kan de välja **Ansökningar** i navigeringsfältet längst upp på sidan för att visa öppna och stängda ansökningar.</span><span class="sxs-lookup"><span data-stu-id="3ac73-166">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="3ac73-167">När kandidater öppnar en av sina ansökningar, visas den aktuella fasen samt eventuella väntande uppgifter som de måste slutföra.</span><span class="sxs-lookup"><span data-stu-id="3ac73-167">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="3ac73-168">Om en kandidat t.ex. måste ange möjliga datum för en personlig intervju visar sidan tillgängliga alternativ.</span><span class="sxs-lookup"><span data-stu-id="3ac73-168">For example, if a candidate must provide potential dates for an in-person interview, the page shows the available options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="3ac73-169">Interna jobb</span><span class="sxs-lookup"><span data-stu-id="3ac73-169">Internal jobs</span></span>

<span data-ttu-id="3ac73-170">För närvarande visas jobb som markerats som interna och publicerade på Attract karriärwebbplatsen inte på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3ac73-170">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="3ac73-171">De är endast tillgängliga via den direkta **Ansöknings**-URL:en som kan kopieras från Attract-programmet.</span><span class="sxs-lookup"><span data-stu-id="3ac73-171">They are only accessible using the direct **Apply** URL that can be copied from the Attract application.</span></span>
