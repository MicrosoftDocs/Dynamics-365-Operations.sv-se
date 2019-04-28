---
title: Publicera jobb på externa karriärwebbplatser från Attract
description: Det här avsnittet beskriver hur du använder Dynamics 365 for Talent - Attract att publicera jobb till externa rekryteringswebbplatser
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2019
ms.locfileid: "993678"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="7a48f-103">Publicera jobb på externa karriärwebbplatser från Attract</span><span class="sxs-lookup"><span data-stu-id="7a48f-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a48f-104">Du vill få dina lediga befattningar framför så många kvalificerade kandidater som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7a48f-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="7a48f-105">Rekryteringswebbplatser som Broadbean hjälper dig att uppnå det här målet.</span><span class="sxs-lookup"><span data-stu-id="7a48f-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="7a48f-106">Microsoft Dynamics 365 Talent: Attract låter dig nu publicera jobb på Broadbean och Microsoft tillhandahåller ständigt nya erbjudanden inom detta område.</span><span class="sxs-lookup"><span data-stu-id="7a48f-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="7a48f-107">Publicera jobb på Broadbean</span><span class="sxs-lookup"><span data-stu-id="7a48f-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="7a48f-108">Innan du kan publicera jobb till Broadbean, måste du konfigurera Broadbean-integrationen.</span><span class="sxs-lookup"><span data-stu-id="7a48f-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="7a48f-109">Om du vill skicka jobb till externa platser måste du ha [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="7a48f-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="7a48f-110">Den här funktionen är för närvarande i förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="7a48f-110">This feature is currently in preview.</span></span> <span data-ttu-id="7a48f-111">Om du vill prova den måste du [aktivera den i Attract administrationsinställningar](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="7a48f-111">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="7a48f-112">Konfigurera Broadbean-integration</span><span class="sxs-lookup"><span data-stu-id="7a48f-112">Configure Broadbean integration</span></span>

1. <span data-ttu-id="7a48f-113">Logga in på Attract som en administratör.</span><span class="sxs-lookup"><span data-stu-id="7a48f-113">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="7a48f-114">Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet på sidan och välj sedan **administratörscenter**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-114">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="7a48f-115">På fliken **Inställningar av jobbtavla** i avsnittet **Aktivera Broadbean-integration** aktiverar du integrationen.</span><span class="sxs-lookup"><span data-stu-id="7a48f-115">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="7a48f-116">Kontakta Broadbean och skriv sedan in informationen i **Användarnamn, klient-ID, krypteringstoken**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-116">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="7a48f-117">Inloggningsinformationen för Broadbean är känslig och konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="7a48f-117">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="7a48f-118">Därför ska den sparas och delas ansvarsfullt.</span><span class="sxs-lookup"><span data-stu-id="7a48f-118">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="7a48f-119">Alla som har en administratörsroll i Attract kan visa denna inloggningsinformation.</span><span class="sxs-lookup"><span data-stu-id="7a48f-119">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="7a48f-120">Microsoft och Attract är inte involverade i att skapa och underhålla dessa värden.</span><span class="sxs-lookup"><span data-stu-id="7a48f-120">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="7a48f-121">Det är ditt ansvar att hålla dem uppdaterade i Attract och arbeta med Broadbean för att åtgärda problem som rör dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="7a48f-121">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="7a48f-122">Publicera jobb på Broadbean</span><span class="sxs-lookup"><span data-stu-id="7a48f-122">Post a job to Broadbean</span></span>

<span data-ttu-id="7a48f-123">När Broadbean har aktiverats kan rekryterare och administratörer publicera ett jobb på den.</span><span class="sxs-lookup"><span data-stu-id="7a48f-123">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="7a48f-124">Du måste ha en svars-URL för jobbet.</span><span class="sxs-lookup"><span data-stu-id="7a48f-124">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="7a48f-125">I Attract öppnar du det jobb som du vill publicera i Broadbean.</span><span class="sxs-lookup"><span data-stu-id="7a48f-125">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="7a48f-126">I avsnittet **bokföringar** väljer du knappen **bokför nu** som motsvarar Broadbean.</span><span class="sxs-lookup"><span data-stu-id="7a48f-126">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="7a48f-127">Följ anvisningarna i Broadbean-fönstret.</span><span class="sxs-lookup"><span data-stu-id="7a48f-127">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="7a48f-128">Attract skickar följande information till Broadbean:</span><span class="sxs-lookup"><span data-stu-id="7a48f-128">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="7a48f-129">ID för begäran</span><span class="sxs-lookup"><span data-stu-id="7a48f-129">Request ID</span></span>
- <span data-ttu-id="7a48f-130">Jobbtitel</span><span class="sxs-lookup"><span data-stu-id="7a48f-130">Job title</span></span>
- <span data-ttu-id="7a48f-131">Jobbeskrivning</span><span class="sxs-lookup"><span data-stu-id="7a48f-131">Job description</span></span>
- <span data-ttu-id="7a48f-132">Plats för jobbet</span><span class="sxs-lookup"><span data-stu-id="7a48f-132">Job location</span></span>
- <span data-ttu-id="7a48f-133">Svars-URL</span><span class="sxs-lookup"><span data-stu-id="7a48f-133">Apply URL</span></span>
- <span data-ttu-id="7a48f-134">Rekryteringsinformation</span><span class="sxs-lookup"><span data-stu-id="7a48f-134">Recruiter information</span></span>

<span data-ttu-id="7a48f-135">Efter att Broadbean slutför publiceringen visar avsnittet **Publiceringar** av jobbet i Attract Broadbean status som **publicerad**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-135">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="7a48f-136">Broadbean kräver fältet **bransch**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-136">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="7a48f-137">För närvarande är detta fält som standard inställt på **IT**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-137">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="7a48f-138">Du kan emellertid ändra värdet till rätt branschen i fönstret för Broadbean jobbpublicering.</span><span class="sxs-lookup"><span data-stu-id="7a48f-138">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="7a48f-139">Det tar en stund för Broadbean att slutföra publicering av jobbet till alla jobbtavlor som du har valt.</span><span class="sxs-lookup"><span data-stu-id="7a48f-139">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="7a48f-140">Därför kan finnas det en fördröjning innan Attract ger en statusuppdatering för jobbet.</span><span class="sxs-lookup"><span data-stu-id="7a48f-140">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="7a48f-141">Visa en Broadbean jobbpublicering</span><span class="sxs-lookup"><span data-stu-id="7a48f-141">View a Broadbean job posting</span></span>

<span data-ttu-id="7a48f-142">När du har publicerat ett jobb till Broadbean kan du visa det från Attract.</span><span class="sxs-lookup"><span data-stu-id="7a48f-142">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="7a48f-143">I Attract öppnar du det jobb som du vill visa i Broadbean.</span><span class="sxs-lookup"><span data-stu-id="7a48f-143">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="7a48f-144">I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **visa**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-144">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="7a48f-145">Broadbean jobbpublicering visas i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="7a48f-145">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="7a48f-146">Uppdatera en Broadbean jobbpublicering</span><span class="sxs-lookup"><span data-stu-id="7a48f-146">Update a Broadbean job posting</span></span>

<span data-ttu-id="7a48f-147">Du kan uppdatera en Broadbean jobbpublicering på två sätt.</span><span class="sxs-lookup"><span data-stu-id="7a48f-147">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="7a48f-148">I Attract öppnar du det jobb som du vill uppdatera.</span><span class="sxs-lookup"><span data-stu-id="7a48f-148">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="7a48f-149">I avsnittet **bokföringar** väljer du knappen **uppdatera publicering** som motsvarar Broadbean.</span><span class="sxs-lookup"><span data-stu-id="7a48f-149">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="7a48f-150">Redigera publiceringen i Broadbean-fönstret.</span><span class="sxs-lookup"><span data-stu-id="7a48f-150">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="7a48f-151">–eller–</span><span class="sxs-lookup"><span data-stu-id="7a48f-151">–or–</span></span>

1. <span data-ttu-id="7a48f-152">I Attract öppnar du det jobb som du vill visa i Broadbean.</span><span class="sxs-lookup"><span data-stu-id="7a48f-152">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="7a48f-153">I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **visa**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-153">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="7a48f-154">Redigera informationen för projektet i Broadbean-fönstret och publicera sedan jobbet igen.</span><span class="sxs-lookup"><span data-stu-id="7a48f-154">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="7a48f-155">Jobbdetaljer i Attract ändras inte.</span><span class="sxs-lookup"><span data-stu-id="7a48f-155">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="7a48f-156">Ta bort en Broadbean jobbpublicering</span><span class="sxs-lookup"><span data-stu-id="7a48f-156">Remove a Broadbean job posting</span></span>

<span data-ttu-id="7a48f-157">Du kan ta bort en jobbpublicering från Broadbean som du behöver.</span><span class="sxs-lookup"><span data-stu-id="7a48f-157">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="7a48f-158">I Attract öppnar du det jobb som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7a48f-158">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="7a48f-159">I avsnittet **publiceringar** väljer du ellips-knappen (**...**) som motsvarar Broadbean och markerar sedan **ta bort publicering**.</span><span class="sxs-lookup"><span data-stu-id="7a48f-159">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="7a48f-160">När Broadbean tar bort jobbet har Broadbean-artikeln i Attract en **Publicera nu**-knapp.</span><span class="sxs-lookup"><span data-stu-id="7a48f-160">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="7a48f-161">Förekomsten av den här knappen anger att jobbet har tagits bort och kan publiceras igen.</span><span class="sxs-lookup"><span data-stu-id="7a48f-161">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="7a48f-162">Felsöka Broadbean-integrering</span><span class="sxs-lookup"><span data-stu-id="7a48f-162">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="7a48f-163">Om du har problem med att publicera ett jobb i Broadbean kan du försöka med följande steg.</span><span class="sxs-lookup"><span data-stu-id="7a48f-163">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="7a48f-164">Kontrollera att autentiseringsuppgifterna för Broadbean som du angav i Attract är korrekta.</span><span class="sxs-lookup"><span data-stu-id="7a48f-164">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="7a48f-165">Om autentiseringsuppgifterna är korrekta kan du kontakta [Broadbean-support](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="7a48f-165">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="7a48f-166">Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="7a48f-166">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
