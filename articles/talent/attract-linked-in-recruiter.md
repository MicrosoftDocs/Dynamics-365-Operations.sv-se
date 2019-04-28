---
title: Rekrytering med LinkedIn Recruiter
description: Det här avsnittet innehåller information om hur du använder maskininlärning för att få rekommendationer om jobb och jobbkandidater.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
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
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4ac7a302e5bf589beb2b560b0ff5818e90c67139
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "859584"
---
# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="21d26-103">Rekrytering med LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="21d26-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="21d26-104">LinkedIn är världens största talangdatabasen och ofta det primära systemet som rekryterare använder för att hitta, kommunicera med och anskaffa kandidater till de jobb som rekryterarna vill fylla.</span><span class="sxs-lookup"><span data-stu-id="21d26-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="21d26-105">LinkedIn Recruiter integration med Dynamics 365 for Talent: Attract gör det enklare för användarna att anställa och synkronisera data mellan de två systemen.</span><span class="sxs-lookup"><span data-stu-id="21d26-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="21d26-106">Du behöver tillägg för omfattande anställning och LinkedIn Recruiter-platser för att kunna använda LinkedIn Recruiter-integration med Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="21d26-107">Ställa in LinkedIn Recruiter med Attract</span><span class="sxs-lookup"><span data-stu-id="21d26-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="21d26-108">Innan du kan använda funktionerna i LinkedIn Recruiter måste du konfigurera åtkomst på kontrakt- eller företagsnivå med din Attract-instans.</span><span class="sxs-lookup"><span data-stu-id="21d26-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="21d26-109">För att slutföra konfigurationsprocessen måste du samarbeta med användare är en administratör i ditt LinkedIn Recruiter-kontrakt.</span><span class="sxs-lookup"><span data-stu-id="21d26-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="21d26-110">Gör följande steg om du vill konfigurera LinkedIn Recruiter med Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="21d26-111">Logga in på Attract som en administratör och gå till **administrationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="21d26-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="21d26-112">I vänster fönster klickar du på fliken **LinkedIn-integration**.</span><span class="sxs-lookup"><span data-stu-id="21d26-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="21d26-113">[![Attract Admin-vy för att starta LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="21d26-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="21d26-114">Klicka på **Anslut** för att starta installation och få vägledning genom LinkedIn-inloggningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="21d26-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="21d26-115">Om du har platser på flera LinkedIn-kontrakt markerar du kontraktet som du vill ansluta till Attract-systemet.</span><span class="sxs-lookup"><span data-stu-id="21d26-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="21d26-116">Om du har en plats i ett enda LinkedIn-kontrakt behövs inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="21d26-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="21d26-117">LinkedIn-widgeten laddas nu i Admin-inställningarna med en lista över integrationer.</span><span class="sxs-lookup"><span data-stu-id="21d26-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="21d26-118">Under **Recruiter System Connect**, klickar du på **begära**.</span><span class="sxs-lookup"><span data-stu-id="21d26-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="21d26-119">[![Attract Admin-vy för att begära LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="21d26-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="21d26-120">När integrationen begärs från Attract visas den som **Partner-klar** och kan aktiveras från **Rekryterarens administratörsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="21d26-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="21d26-121">Om du vill se **meddela partner** vänta några sekunder på den här sidan, klicka på **meddela partner** och uppdatera sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="21d26-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="21d26-122">Den ska nu visa **Partner-klar**.</span><span class="sxs-lookup"><span data-stu-id="21d26-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="21d26-123">[![Attract Admin-vy om du vill visa att Attract-sidan av begäranden har slutförts](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="21d26-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="21d26-124">Du måste ha behörigheten Admin i LinkedIn Recruiter-kontrakt för att slutföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="21d26-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="21d26-125">Logga in på LinkedIn med administratörskontot och gå till LinkedIn Recruiter längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="21d26-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="21d26-126">I menyn **mer** längst upp på skärmen, klickar du på **administrationsinställningar**, och klickar sedan på fliken **ATS**.</span><span class="sxs-lookup"><span data-stu-id="21d26-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="21d26-127">Attract-systemet visas med två olika alternativ som kan aktiveras.</span><span class="sxs-lookup"><span data-stu-id="21d26-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="21d26-128">Om du vill aktivera endast 1 - klicka på exportera för **I ATS-indikatorn** och **I ATS-profilwidget**, markera **åtkomst på företagsnivå**.</span><span class="sxs-lookup"><span data-stu-id="21d26-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="21d26-129">Välj om du vill aktivera alla funktioner för åtkomst på företagsnivå plus åtkomst för InMail-historik, anteckningshistorik och InMail stub-profil, välj **Åtkomst på kontraktnivå**.</span><span class="sxs-lookup"><span data-stu-id="21d26-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="21d26-130">Aktivera önskad åtkomstnivå från dina LinkedIn Recruiter **Admin ATS**-inställningar.</span><span class="sxs-lookup"><span data-stu-id="21d26-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="21d26-131">[![Aktivera Attract-integration från LinkedIn Recruiter Admin-vy](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="21d26-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="21d26-132">Gå tillbaka till Attract administrationsinställningar som en AttractAdmin och välj fliken **LinkedIn-integration**. Du bör se LinkedIn-widgeten som visar **aktiverad** med den valda åtkomstnivån aktiverad.</span><span class="sxs-lookup"><span data-stu-id="21d26-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="21d26-133">[![LinkedIn Recruiter integration slutförd](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="21d26-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="21d26-134">Använda LinkedIn Recruiter-funktioner</span><span class="sxs-lookup"><span data-stu-id="21d26-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="21d26-135">När LinkedIn Recruiter-funktionerna har aktiverats av Attract Admin är den tillgänglig för anställande chefer och rekryterare.</span><span class="sxs-lookup"><span data-stu-id="21d26-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="21d26-136">Om du vill använda de här funktionerna anslut ditt LinkedIn-konto under **användarinställningar**.</span><span class="sxs-lookup"><span data-stu-id="21d26-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="21d26-137">Flera funktioner blir tillgängliga när både administratör och användare har anslutits.</span><span class="sxs-lookup"><span data-stu-id="21d26-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="21d26-138">Profilwidget för I-ATS</span><span class="sxs-lookup"><span data-stu-id="21d26-138">In-ATS profile widget</span></span>

<span data-ttu-id="21d26-139">Du kan visa kandidatens LinkedIn-profil i Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="21d26-140">LinkedIn-widgeten visar kandidatens profil när ATS-informationen matchar LinkedIn-information för användarna.</span><span class="sxs-lookup"><span data-stu-id="21d26-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="21d26-141">Om du vill visa en profil, gå till kandidatens profil från ett jobb eller talangpool.</span><span class="sxs-lookup"><span data-stu-id="21d26-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="21d26-142">I kandidatprofilen väljer du fliken **LinkedIn** och profilwidgeten läses in.</span><span class="sxs-lookup"><span data-stu-id="21d26-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="21d26-143">Du kan också spara kandidaten till dina LinkedIn Recruiter-projekt på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="21d26-143">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>
1. <span data-ttu-id="21d26-144">Den sökandes profil visas om LinkedIn hittar en match baserat på e-post och LinkedIn medlems-ID (exakt träff).</span><span class="sxs-lookup"><span data-stu-id="21d26-144">If LinkedIn found the match based on email and LinkedIn member ID (exact match), the candidate's profile will be shown.</span></span> <span data-ttu-id="21d26-145">Användaren har fortfarande ett alternativ för att länka/ta bort länk till profilen.</span><span class="sxs-lookup"><span data-stu-id="21d26-145">The user still has an option to link/unlink the profile.</span></span>

2. <span data-ttu-id="21d26-146">Om LinkedIn inte hittar kandidaten baserat på deras e-post eller medlems-ID, visas en lista över möjliga kandidatmatchningar baserat på sökande och användaren kan välja en av dem och länka profilen.</span><span class="sxs-lookup"><span data-stu-id="21d26-146">If LinkedIn cannot find the candidate based on their email or member ID, it will show a list of possible candidate matches based on candidate name and the user can choose one of them and link the profile.</span></span>  

3. <span data-ttu-id="21d26-147">Om LinkedIn inte hittar dem utifrån namnet kommer den returnera att ingen matchning hittades.</span><span class="sxs-lookup"><span data-stu-id="21d26-147">If LinkedIn cannot find any candidate based on the name, it will return that no match was found.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="21d26-148">1-klick exportera</span><span class="sxs-lookup"><span data-stu-id="21d26-148">1-click export</span></span> 

<span data-ttu-id="21d26-149">Vid anskaffning av kandidater i LinkedIn kan 1-klick exportera kandidaten till jobb som för närvarande är öppna.</span><span class="sxs-lookup"><span data-stu-id="21d26-149">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="21d26-150">Gör följande steg för en 1-klick export.</span><span class="sxs-lookup"><span data-stu-id="21d26-150">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="21d26-151">Innan du utför de här stegen ska du kontrollera att har tilldelats rollen anställande chef eller rekryterare för jobbet och att jobbet har fasen **potentiell kandidat**.</span><span class="sxs-lookup"><span data-stu-id="21d26-151">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="21d26-152">Skapa jobbet, tilldela lämpliga roller och aktivera jobbet.</span><span class="sxs-lookup"><span data-stu-id="21d26-152">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="21d26-153">Navigera till LinkedIn Recruiter när jobbet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="21d26-153">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="21d26-154">Hitta den kandidat som du söker efter och gå till deras profil.</span><span class="sxs-lookup"><span data-stu-id="21d26-154">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="21d26-155">Använd jobbsökrutan i kontaktkortet, hitta jobbet med titeln eller jobb-id som aktiverades i Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-155">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="21d26-156">Om du inte hittar jobbet klickar du på **ändra ATS** för att hitta rätt Attract-instans.</span><span class="sxs-lookup"><span data-stu-id="21d26-156">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="21d26-157">När jobbet är markerat klickar du på **exportera**.</span><span class="sxs-lookup"><span data-stu-id="21d26-157">After the job is selected, click **Export**.</span></span> <span data-ttu-id="21d26-158">Kandidaten hämtas nu av Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-158">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="21d26-159">Gå till Attract och öppna respektive jobb.</span><span class="sxs-lookup"><span data-stu-id="21d26-159">Go to Attract and open the respective job.</span></span> <span data-ttu-id="21d26-160">Du hittar kandidaten som du just har exporterat i fasen **potentiella kandidater** för jobbet.</span><span class="sxs-lookup"><span data-stu-id="21d26-160">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="21d26-161">Indikatorn I-ATS</span><span class="sxs-lookup"><span data-stu-id="21d26-161">In-ATS indicator</span></span> 

<span data-ttu-id="21d26-162">Genom att använda LinkedIn-rekryterare kan du följa upp om en kandidat har sökt andra jobb i organisationen, titta på när de är i olika faser i jobbansökningar och visa feedback och kommentarer från Attract i LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="21d26-162">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="21d26-163">Öppna LinkedIn Recruiter och leta reda på kandidatprofilen som du söker efter.</span><span class="sxs-lookup"><span data-stu-id="21d26-163">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="21d26-164">Bläddra nedåt i avsnittet **I-ATS** i kandidatens profil.</span><span class="sxs-lookup"><span data-stu-id="21d26-164">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="21d26-165">Du kan använda denna widgeten för att visa all information om kandidaten som finns i Attract från LinkedIn Recruiter-vyn.</span><span class="sxs-lookup"><span data-stu-id="21d26-165">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="21d26-166">Välj fliken **jobb och status** för att se jobb som de är en del av, senaste status och hur de har flyttat mot varje jobb.</span><span class="sxs-lookup"><span data-stu-id="21d26-166">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="21d26-167">Välj fliken **intervjufeedback** för att se feedback som intervjuare har lämnat i Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-167">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="21d26-168">Välj fliken **anteckningar** för att visa anteckningar som har hämtats för sökanden i Attract.</span><span class="sxs-lookup"><span data-stu-id="21d26-168">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

> [!NOTE]
> <span data-ttu-id="21d26-169">Kandidater och programdata synkroniseras inte med LinkedIn Recruiter om kandidaten inte har flyttats från fasen potentiell kandidat.</span><span class="sxs-lookup"><span data-stu-id="21d26-169">Candidate and application data will not be synced to LinkedIn Recruiter if the candidate hasn't moved past the prospect stage.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="21d26-170">InMail historik</span><span class="sxs-lookup"><span data-stu-id="21d26-170">InMail history</span></span>

<span data-ttu-id="21d26-171">LinkedIn InMail-historik finns i åtkomst på kontraktnivå med LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="21d26-171">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="21d26-172">Om den är aktiverad måste visa hela InMail-historiken med kandidaten.</span><span class="sxs-lookup"><span data-stu-id="21d26-172">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="21d26-173">Du kan också se vilka andra från din organisation som har utbytt InMail med kandidaten, men du inte kan visa meddelanden mellan dem.</span><span class="sxs-lookup"><span data-stu-id="21d26-173">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="21d26-174">För att historik för InMail, gå till kandidatens profil, gå till fliken **LinkedIn** och bläddra till slutet på sidan för att visa historik.</span><span class="sxs-lookup"><span data-stu-id="21d26-174">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="21d26-175">Du kan visa InMail-historik om du har haft en diskussion med kandidaten.</span><span class="sxs-lookup"><span data-stu-id="21d26-175">You can view InMail history if you have had a discussion with the candidate.</span></span> <span data-ttu-id="21d26-176">Meddelanden från InMail synkroniseras med Attract varannan timme.</span><span class="sxs-lookup"><span data-stu-id="21d26-176">The messages from InMail will sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="21d26-177">Anteckningshistorik</span><span class="sxs-lookup"><span data-stu-id="21d26-177">Notes history</span></span> 

<span data-ttu-id="21d26-178">LinkedIn anteckningshistorik finns i åtkomst på kontraktnivå med LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="21d26-178">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="21d26-179">När den är aktiverad kan du visa anteckningar som har gjorts om kandidaten av olika rekryterare från organisationen.</span><span class="sxs-lookup"><span data-stu-id="21d26-179">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="21d26-180">För att historik för anteckningar, gå till kandidatens profil, gå till fliken **LinkedIn** och bläddra till slutet på sidan för att visa historik.</span><span class="sxs-lookup"><span data-stu-id="21d26-180">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="21d26-181">Du kan visa alla anteckningar om kandidaten från LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="21d26-181">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="21d26-182">InMail stub-profil</span><span class="sxs-lookup"><span data-stu-id="21d26-182">InMail stub profile</span></span>

<span data-ttu-id="21d26-183">InMail stub-historik finns i åtkomst på kontraktnivå med LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="21d26-183">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="21d26-184">Om kandidater enas om att deras LinkedIn-profiler delas med alla användare i organisationen, kan du spåra kandidater i Attract och en ny kandidatpost skapas för varje kandidat.</span><span class="sxs-lookup"><span data-stu-id="21d26-184">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span> <span data-ttu-id="21d26-185">Du kan visa kandidatens e-postadress om kandidaten redan finns i systemet med en e-postadress eller delat adressen med rekryteraren.</span><span class="sxs-lookup"><span data-stu-id="21d26-185">You can view candidate's email address if the candidate already exists in the system with an email address or has chosen to share their address with the recruiter.</span></span>

<span data-ttu-id="21d26-186">Om du vill visa listan med kandidater, gå till **talangpooler** för att se en systemskapad LinkedIn talangpool.</span><span class="sxs-lookup"><span data-stu-id="21d26-186">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="21d26-187">Den här talangpoolen innehåller listan av kandidater och deras stub-profiler som fås från LinkedIn och som visar kandidatens förnamn och efternamn.</span><span class="sxs-lookup"><span data-stu-id="21d26-187">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="21d26-188">Kandidatens e-post-ID visas om kandidaten har delat sin e-postadress.</span><span class="sxs-lookup"><span data-stu-id="21d26-188">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>
