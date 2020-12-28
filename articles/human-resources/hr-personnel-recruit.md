---
title: Rekrytera jobbkandidater
description: I det här avsnittet visas hur du rekryterar kandidater i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9a35abcb8a2f6aa8031c8d84a44c2a8ad93883ac
ms.sourcegitcommit: 0354ca7e566fbd2eb0aabdd40000d4ac5c44ea78
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "4669191"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="da150-103">Rekrytera jobbkandidater</span><span class="sxs-lookup"><span data-stu-id="da150-103">Recruit job candidates</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="da150-104">Dynamics 365 Human Resources hjälper dig att hantera rekryteringsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="da150-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="da150-105">Den hjälper dig också att på ett smidigt sätt överföra jobbkandidater till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="da150-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="da150-106">Om din organisation använder ett separat rekryteringsprogram kan din rekryteringsprocess innehålla följande steg:</span><span class="sxs-lookup"><span data-stu-id="da150-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="da150-107">Ange din rekryteringsförfrågan i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da150-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="da150-108">Ta emot kandidathänvisningar i Human Resources från programmet för rekrytering.</span><span class="sxs-lookup"><span data-stu-id="da150-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="da150-109">Slutför godkännandeprocessen för kandidater i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da150-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="da150-110">Om du inte använder ett separat rekryteringsprogram kan du även hantera kandidater manuellt i Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da150-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="da150-111">Om du är administratör eller utvecklare och vill integrera Human Resources med ett rekryteringsprogram från tredje part, se [Konfigurera Common Data Service-integration](hr-admin-integration-common-data-service.md) och [Konfigurera Common Data Service virtuella entiteter](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="da150-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Common Data Service integration](hr-admin-integration-common-data-service.md) and [Configure Common Data Service virtual entities](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="da150-112">Du kan också hitta integrationsappar för rekrytering på [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="da150-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="da150-113">Om du vill testa vår förhandsversionsfunktion för integrering med LinkedIn Talent Hub läser du [Integrera med LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="da150-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="da150-114">Aktivera rekryteringsbegäranden</span><span class="sxs-lookup"><span data-stu-id="da150-114">Enable recruiting requests</span></span>

<span data-ttu-id="da150-115">Om du vill skicka in rekryteringsförfrågningar i Human Resources måste du först aktivera funktionerna i **personalparametrarna**.</span><span class="sxs-lookup"><span data-stu-id="da150-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources parameters**.</span></span>

1. <span data-ttu-id="da150-116">I arbetsytan **Personalhantering** väjer du **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="da150-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="da150-117">Under **Inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="da150-117">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="da150-118">Under fliken **Allmänt**, under **REKRYTERING**, ställer du in **Aktivera rekryteringsförfrågningar** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="da150-118">On the **General** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

   ![Aktivera rekryteringsbegäranden](./media/hr-recruit-0-enable-requests.png)

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="da150-120">Lägg till en plats för rekryteringsförfrågan</span><span class="sxs-lookup"><span data-stu-id="da150-120">Add a recruiting request location</span></span>

<span data-ttu-id="da150-121">Om din organisation har flera platser kan du lägga till dem så att de kan välja en plats där den nya rekryteringen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="da150-121">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="da150-122">Platsen tas med i jobbpubliceringen.</span><span class="sxs-lookup"><span data-stu-id="da150-122">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="da150-123">I sökfältet anger du **platsen för rekryteringsförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="da150-123">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="da150-124">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="da150-124">Select **New**.</span></span>

3. <span data-ttu-id="da150-125">I fältet **Plats för rekryteringsförfrågan** anger du platsens namn.</span><span class="sxs-lookup"><span data-stu-id="da150-125">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Lägg till en plats för rekryteringsförfrågan](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="da150-127">I **Beskrivning** anger du en beskrivning av platsen.</span><span class="sxs-lookup"><span data-stu-id="da150-127">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="da150-128">Under **Plats**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="da150-128">Under **Location**, select **Add**.</span></span> <span data-ttu-id="da150-129">Om popup-fönstret **Ny adress** visas anger du platsens adress.</span><span class="sxs-lookup"><span data-stu-id="da150-129">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Ange adress](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="da150-131">Under **Kontaktuppgifter** anger du uppgifterna för platsens kontaktperson.</span><span class="sxs-lookup"><span data-stu-id="da150-131">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="da150-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="da150-132">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="da150-133">Lägg till en rekryteringsförfrågan</span><span class="sxs-lookup"><span data-stu-id="da150-133">Add a recruiting request</span></span>

<span data-ttu-id="da150-134">Chefer kan skicka in rekryteringsförfrågningar till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da150-134">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="da150-135">Om du använder ett separat rekryteringsprogram skickar du en rekryteringsförfrågan och startar rekryteringsprocessen i det programmet.</span><span class="sxs-lookup"><span data-stu-id="da150-135">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="da150-136">I annat fall måste du utföra den här proceduren för att starta arbetsflödet för din interna rekryteringsprocess.</span><span class="sxs-lookup"><span data-stu-id="da150-136">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="da150-137">Välj **Självbetjäning för medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="da150-137">Select **Employee self service**.</span></span>

2. <span data-ttu-id="da150-138">Välj fliken **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="da150-138">Select the **My team** tab.</span></span>

3. <span data-ttu-id="da150-139">Välj **Begär att rekrytera**.</span><span class="sxs-lookup"><span data-stu-id="da150-139">Select  **Request to recruit**.</span></span>

   ![Starta en rekryteringsförfrågan](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="da150-141">Fyll i fälten **Beskrivning**, **Jobb** och **Uppskattat startdatum**.</span><span class="sxs-lookup"><span data-stu-id="da150-141">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Slutför rekryteringsförfrågan](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="da150-143">Välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="da150-143">Select **Continue**.</span></span> <span data-ttu-id="da150-144">Rekryteringsförfrågan för din befattning visas.</span><span class="sxs-lookup"><span data-stu-id="da150-144">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="da150-145">Under **Allmänt** väljer du en rekryterare från listrutan **Rekryterare** och väljer sedan en plats från listrutan **Plats för rekryteringsförfrågan**.</span><span class="sxs-lookup"><span data-stu-id="da150-145">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="da150-146">Under **Jobb** ändrar du informationen efter behov och väljer sedan **Skapa information från jobb**.</span><span class="sxs-lookup"><span data-stu-id="da150-146">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Skapa information från jobb](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="da150-148">Resten av din rekryteringsförfrågan fylls i med standardinformation för det jobb som du har angett.</span><span class="sxs-lookup"><span data-stu-id="da150-148">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="da150-149">Under **Extern beskrivning** anger du en jobbeskrivning som är riktad utåt.</span><span class="sxs-lookup"><span data-stu-id="da150-149">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="da150-150">Under **Befattningar** väljer du **Lägg till** och sedan en befattning för den här rekryteringsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="da150-150">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Lägg till en befattning](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="da150-152">Under **Färdigheter** väljer du **Lägg till** och sedan en färdighet.</span><span class="sxs-lookup"><span data-stu-id="da150-152">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="da150-153">Under **Utbildningsmässiga krav** väljer du **Lägg till** och sedan värden från listrutorna **Utbildning** och **Utbildningsnivå**.</span><span class="sxs-lookup"><span data-stu-id="da150-153">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Lägg till utbildningsmässiga krav](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="da150-155">Under **Kommentar** lägger du till kommentarer efter behov.</span><span class="sxs-lookup"><span data-stu-id="da150-155">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="da150-156">Under **Kompensation** väljer du en nivå från listrutan **Nivå** och justerar sedan **Låg tröskel**, **Kontrollpunkt** och **Hög tröskel** efter behov.</span><span class="sxs-lookup"><span data-stu-id="da150-156">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="da150-157">När din rekryteringsförfrågan är slutförd och du är redo att starta rekryteringsprocessen väljer du **Aktivera** på menyraden.</span><span class="sxs-lookup"><span data-stu-id="da150-157">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Aktivera rekryteringsförfrågan](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="da150-159">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="da150-159">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="da150-160">Visa och redigera dina rekryteringsförfrågningar</span><span class="sxs-lookup"><span data-stu-id="da150-160">View and edit your recruiting requests</span></span>

<span data-ttu-id="da150-161">Om du är chef och vill visa dina egna begäranden:</span><span class="sxs-lookup"><span data-stu-id="da150-161">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="da150-162">Välj **Självbetjäning för medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="da150-162">Select **Employee self service**.</span></span>

2. <span data-ttu-id="da150-163">Välj fliken **Mitt team**.</span><span class="sxs-lookup"><span data-stu-id="da150-163">Select the **My team** tab.</span></span>

3. <span data-ttu-id="da150-164">Under fliken **Information om mitt team**, välj fliken **Rekryteringsförfrågningar**.</span><span class="sxs-lookup"><span data-stu-id="da150-164">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Välj fliken Rekryteringsförfrågningar](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="da150-166">Om du vill visa eller redigera en rekryteringsförfrågan väljer du den i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="da150-166">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="da150-167">Om du är HR Pro och vill visa alla rekryteringsförfrågningar:</span><span class="sxs-lookup"><span data-stu-id="da150-167">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="da150-168">Välj **Personalhantering**.</span><span class="sxs-lookup"><span data-stu-id="da150-168">Select **Personnel management**.</span></span>

2. <span data-ttu-id="da150-169">Välj **Rekryteringsförfrågningar**.</span><span class="sxs-lookup"><span data-stu-id="da150-169">Select **Recruiting requests**.</span></span>

   ![Visa rekryteringsförfrågningar i Personalhantering](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="da150-171">Om du vill visa eller redigera en rekryteringsförfrågan väljer du den i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="da150-171">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="da150-172">Lägga till eller redigera en kandidatprofil</span><span class="sxs-lookup"><span data-stu-id="da150-172">Add or edit a candidate profile</span></span>

<span data-ttu-id="da150-173">Om din organisation har integrerats med ett annat program för att kunna hantera rekryteringsförfrågningar, vidarebefordras rekryteringsförfrågningar till programmet.</span><span class="sxs-lookup"><span data-stu-id="da150-173">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="da150-174">Programmet för rekrytering skickar sedan tillbaka informationen till Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da150-174">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="da150-175">I annat fall kan du följa dina interna rekryteringsprocesser och ange kandidatinformation manuellt.</span><span class="sxs-lookup"><span data-stu-id="da150-175">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="da150-176">Välj **Personalhantering**.</span><span class="sxs-lookup"><span data-stu-id="da150-176">Select **Personnel management**.</span></span>

2. <span data-ttu-id="da150-177">Markera **länkar**</span><span class="sxs-lookup"><span data-stu-id="da150-177">Select **Links**.</span></span>

3. <span data-ttu-id="da150-178">Under **Rekrytering** väljer du **Kandidater**.</span><span class="sxs-lookup"><span data-stu-id="da150-178">Under **Recruiting**, select **Candidates**.</span></span>

   ![Visa kandidater](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="da150-180">Om du vill lägga till en kandidat väljer du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="da150-180">To add a candidate, select **New**.</span></span> <span data-ttu-id="da150-181">Om du vill redigera en befintlig kandidat väljer du kandidaten från listan och väljer sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="da150-181">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="da150-182">Kandidatprofilen visas.</span><span class="sxs-lookup"><span data-stu-id="da150-182">The candidate profile appears.</span></span>

5. <span data-ttu-id="da150-183">Under **Kandidatsammanfattning** anger eller redigerar du kandidatinformationen efter behov.</span><span class="sxs-lookup"><span data-stu-id="da150-183">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="da150-184">Under **Rekryteringsförfrågan** väljer du en rekryteringsförfrågan som kandidaten ska kopplas till.</span><span class="sxs-lookup"><span data-stu-id="da150-184">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="da150-185">Fyll sedan i fälten **Uppskattat startdatum**, **Anställande chef**, **Befattning** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="da150-185">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Länka till rekryteringsförfrågan](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="da150-187">Fyll i all information i följande områden som du vill inkludera i kandidatens post:</span><span class="sxs-lookup"><span data-stu-id="da150-187">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="da150-188">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="da150-188">**Comments**</span></span>
   - <span data-ttu-id="da150-189">**Yrkeserfarenhet**</span><span class="sxs-lookup"><span data-stu-id="da150-189">**Professional experience**</span></span>
   - <span data-ttu-id="da150-190">**Kontaktinformation**</span><span class="sxs-lookup"><span data-stu-id="da150-190">**Contact information**</span></span>
   - <span data-ttu-id="da150-191">**Utbildning**</span><span class="sxs-lookup"><span data-stu-id="da150-191">**Education**</span></span>
   - <span data-ttu-id="da150-192">**Kompetenser**</span><span class="sxs-lookup"><span data-stu-id="da150-192">**Skills**</span></span>
   - <span data-ttu-id="da150-193">**Intyg**</span><span class="sxs-lookup"><span data-stu-id="da150-193">**Certificates**</span></span>
   - <span data-ttu-id="da150-194">**Kontroller**</span><span class="sxs-lookup"><span data-stu-id="da150-194">**Screenings**</span></span>

8. <span data-ttu-id="da150-195">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="da150-195">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="da150-196">Anställa en kandidat</span><span class="sxs-lookup"><span data-stu-id="da150-196">Hire a candidate</span></span>

<span data-ttu-id="da150-197">När du är redo att anställa en kandidat följer du den här proceduren för att överföra kandidaten till medarbetare.</span><span class="sxs-lookup"><span data-stu-id="da150-197">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="da150-198">I kandidatformuläret väljer du **Anställ**.</span><span class="sxs-lookup"><span data-stu-id="da150-198">On the candidate form, select **Hire**.</span></span>

   ![Anställa en kandidat](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="da150-200">I formuläret **Anställa ny arbetstagare**, under **Detaljer**, fyller du i alla fält.</span><span class="sxs-lookup"><span data-stu-id="da150-200">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Ange ny anställningsinformation](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="da150-202">Under **Befattningsdetaljer** verifierar och ändrar du information efter behov.</span><span class="sxs-lookup"><span data-stu-id="da150-202">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="da150-203">Under **Checklistor för registrering** väljer du relevanta registreringschecklistor för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="da150-203">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="da150-204">Välj **Fortsätt** om du vill skapa medarbetarposten.</span><span class="sxs-lookup"><span data-stu-id="da150-204">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="da150-205">Beroende på din organisations arbetsflöden kan kandidatposten gå igenom ytterligare godkännandesteg innan det blir en medarbetarpost.</span><span class="sxs-lookup"><span data-stu-id="da150-205">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="da150-206">Besluta att inte anställa en kandidat</span><span class="sxs-lookup"><span data-stu-id="da150-206">Decide not to hire a candidate</span></span>

<span data-ttu-id="da150-207">Om du väljer att inte anställa en kandidat följer du den här proceduren för att ta bort dem från granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="da150-207">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="da150-208">I kandidatformuläret väljer du **Anställ inte**.</span><span class="sxs-lookup"><span data-stu-id="da150-208">On the candidate form, select **Do not hire**.</span></span>

   ![Anställ inte kandidat](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="da150-210">Välj en **orsakskod** och ta med eventuella kommentarer.</span><span class="sxs-lookup"><span data-stu-id="da150-210">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="da150-211">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="da150-211">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="da150-212">Avvisa en kandidat</span><span class="sxs-lookup"><span data-stu-id="da150-212">Dismiss a candidate</span></span>

<span data-ttu-id="da150-213">Vid behov kan du avvisa en kandidat när du har anställt den.</span><span class="sxs-lookup"><span data-stu-id="da150-213">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="da150-214">En kandidat kan till exempel avvisa erbjudandet eller inte komma till arbetet den första dagen.</span><span class="sxs-lookup"><span data-stu-id="da150-214">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="da150-215">I kandidatformuläret väljer du **Avvisa kandidat**.</span><span class="sxs-lookup"><span data-stu-id="da150-215">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Avfärda kandidat](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="da150-217">Se även</span><span class="sxs-lookup"><span data-stu-id="da150-217">See also</span></span>

[<span data-ttu-id="da150-218">Konfigurera Common Data Service virtuella enheter</span><span class="sxs-lookup"><span data-stu-id="da150-218">Configure Common Data Service virtual entities</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="da150-219">Organisera personalen</span><span class="sxs-lookup"><span data-stu-id="da150-219">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="da150-220">Ställa in komponenter för ett jobb</span><span class="sxs-lookup"><span data-stu-id="da150-220">Set up the components of a job</span></span>](hr-personnel-jobs.md)