---
title: "Åtkomst till förhandsfunktioner i Dynamics 365 for Talent"
description: "Det här avsnittet beskriver hur en administratör kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning."
author: rschloma
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2e5dd8f852ac1a6c2997a50a60f03db6adfd218c
ms.openlocfilehash: 5500bfc1cdd1949d301ae82fad5506dfdbeb59f3
ms.contentlocale: sv-se
ms.lasthandoff: 05/01/2018

---

# <a name="access-preview-features-in-dynamics-365-for-talent"></a><span data-ttu-id="80000-103">Åtkomst till förhandsfunktioner i Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="80000-103">Access preview features in Dynamics 365 for Talent</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="80000-104">Som en del av vår kontinuerliga distribution av produktens funktioner, vill vi att kunder får nya funktioner så snart som möjligt.</span><span class="sxs-lookup"><span data-stu-id="80000-104">As part of our continuous rollout of product capabilities, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="80000-105">Administratörer kan se och använda funktioner för förhandsgranskning i datormiljön.</span><span class="sxs-lookup"><span data-stu-id="80000-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="80000-106">Dessa funktioner kan snart allmänt tillgänglig och har genomgått omfattande testning.</span><span class="sxs-lookup"><span data-stu-id="80000-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="80000-107">Vi söker bara en slutlig runda av feedback från kunder och validering innan vi vanligtvis frigörs.</span><span class="sxs-lookup"><span data-stu-id="80000-107">We are just looking for a final round of customer feedback and validation before we generally release them.</span></span>

<span data-ttu-id="80000-108">Det här avsnittet beskriver hur en administratör kan aktivera funktionen Förhandsgranska och visar funktionerna som är aktiverade för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="80000-108">This topic describes how an administrator can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="80000-109">Den här listan uppdateras funktioner släpps till normala tillgänglighet och nya funktioner som ges ut om du vill förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="80000-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="80000-110">Ingen anmälan görs när nya funktioner publiceras för att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="80000-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="80000-111">Användare börjar bara se funktionerna.</span><span class="sxs-lookup"><span data-stu-id="80000-111">Users will just start to see the features.</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="80000-112">Aktivera eller inaktivera funktioner för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="80000-112">Enable or disable preview features</span></span>

<span data-ttu-id="80000-113">Du kan använda inställningrn **förhandsgranskningsfunktioner** i administratörscenter för Microsoft Dynamics 365 for Talent för att aktivera eller inaktivera funktioner för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="80000-113">You can use the **Preview Features** setting in the Microsoft Dynamics 365 for Talent admin center to enable or disable preview features.</span></span> <span data-ttu-id="80000-114">Inställningen är avstängd som standard.</span><span class="sxs-lookup"><span data-stu-id="80000-114">By default, the setting is turned off.</span></span> <span data-ttu-id="80000-115">Åtgärden att aktivera eller inaktivera funktioner för förhandsgranskning är miljöspecifika.</span><span class="sxs-lookup"><span data-stu-id="80000-115">The action of enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80000-116">Genom att aktivera inställningen **förhandsgranskningsfunktioner** kan du aktivera förhandsgranskning för alla användare i organisationen i denna miljö.</span><span class="sxs-lookup"><span data-stu-id="80000-116">By turning on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="80000-117">Genom att inaktivera inställningen, inaktiveras förhandsgranskningsfunktioner och gör dem otillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="80000-117">By turning off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="80000-118">Förhandsgranskningsfunktioner har begränsad funktionalitet i Talent.</span><span class="sxs-lookup"><span data-stu-id="80000-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="80000-119">De använder färre sekretess- och säkerhetsfunktioner och de ingår inte i Talent servicenivåavtal.</span><span class="sxs-lookup"><span data-stu-id="80000-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement.</span></span> <span data-ttu-id="80000-120">Du bör inte använda funktioner för förhandsgranskning för att behandla personuppgifter (d.v.s. all information som kan identifiera dig) eller bearbeta andra data som omfattas av lagar och andra efterföljandekrav.</span><span class="sxs-lookup"><span data-stu-id="80000-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="enable-or-disable-preview-features-for-your-organization"></a><span data-ttu-id="80000-121">Aktivera eller inaktivera funktioner för förhandsgranskning för organisationen</span><span class="sxs-lookup"><span data-stu-id="80000-121">Enable or disable preview features for your organization</span></span>

#### <a name="attract"></a><span data-ttu-id="80000-122">Attract</span><span class="sxs-lookup"><span data-stu-id="80000-122">Attract</span></span>

1. <span data-ttu-id="80000-123">Logga in på Microsoft Dynamics 365 for Talent: Attract</span><span class="sxs-lookup"><span data-stu-id="80000-123">Sign in to Microsoft Dynamics 365 for Talent: Attract.</span></span>
2. <span data-ttu-id="80000-124">I menyn **inställningar** (växel-symbol) i det övre högra hörnet väljer du **administrationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="80000-124">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin settings**.</span></span>
3. <span data-ttu-id="80000-125">På fliken **Funktionshantering** väljer du alternativet bredvid **Förhandsgranskningsfunktioner** så att det blir blått.</span><span class="sxs-lookup"><span data-stu-id="80000-125">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue.</span></span>
4. <span data-ttu-id="80000-126">Uppdatera webbläsaren för att starta och se de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="80000-126">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="80000-127">(Användare som redan har loggat in ser funktionerna nästa gång de loggar in och de kan uppdatera webbläsaren om du vill se funktionerna direkt.)</span><span class="sxs-lookup"><span data-stu-id="80000-127">(Any users who are already signed in will see the features the next time that they sign in, or they can refresh their browser to see the features immediately.)</span></span>

#### <a name="core-hr"></a><span data-ttu-id="80000-128">Grundläggande personal</span><span class="sxs-lookup"><span data-stu-id="80000-128">Core HR</span></span>

1. <span data-ttu-id="80000-129">Logga in på Talent.</span><span class="sxs-lookup"><span data-stu-id="80000-129">Sign in to Talent.</span></span> <span data-ttu-id="80000-130">Arbetsytan för grundläggande personal öppnas, som du utför resten av stegen från.</span><span class="sxs-lookup"><span data-stu-id="80000-130">The core Human resources workspace will open, from which you'll complete the remaining steps.</span></span> 
2. <span data-ttu-id="80000-131">Välj **Systemadministration \> Länkar systemparametrar**.</span><span class="sxs-lookup"><span data-stu-id="80000-131">Select **System administration \> Links System parameters**.</span></span>
3. <span data-ttu-id="80000-132">På sidan **systemparametrar**på fliken **Förhandsgranskningsfunktioner** anger du **aktivera förhandsgranskningsläget för alla användare** till **Ja** för att göra förhandsgranskningsfunktionerna tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="80000-132">On the **System Parameters page**, on the **Preview features** tab, set the **Enable preview mode for all users** option to **Yes** to make preview features available.</span></span>

> [!NOTE]
> <span data-ttu-id="80000-133">Inaktivera förhandsgranskningsfunktioner med samma grundläggande steg.</span><span class="sxs-lookup"><span data-stu-id="80000-133">To disable preview features, use the same basic steps.</span></span> <span data-ttu-id="80000-134">När du inaktiverar förhandsgranskningsfunktioner blir de otillgängliga för användarna och fel kan inträffa i processer som är associerade med funktionerna.</span><span class="sxs-lookup"><span data-stu-id="80000-134">When you disable preview features, they become inaccessible to your users, and errors might occur in processes that are associated with the features.</span></span>

## <a name="features-that-are-currently-in-preview"></a><span data-ttu-id="80000-135">Funktioner som är i förhandsgranskning nu.</span><span class="sxs-lookup"><span data-stu-id="80000-135">Features that are currently in preview</span></span>

### <a name="attract"></a><span data-ttu-id="80000-136">Attract</span><span class="sxs-lookup"><span data-stu-id="80000-136">Attract</span></span>

- <span data-ttu-id="80000-137">**Jobbmallar** – nu kan du skapa mallar för anställningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="80000-137">**Job templates** – You can now create hiring process templates.</span></span> <span data-ttu-id="80000-138">Användare kan redan anpassa anställningsprocessen för ett specifikt jobb.</span><span class="sxs-lookup"><span data-stu-id="80000-138">Users can already customize the hiring process for a specific job.</span></span> <span data-ttu-id="80000-139">De kan nu skapa mallar för den processen och välja lämplig mall när ett visst jobb skapas.</span><span class="sxs-lookup"><span data-stu-id="80000-139">However, they can now create templates for the process and then select the appropriate template when a specific job is created.</span></span> <span data-ttu-id="80000-140">Därför hjälper den här funktionen till att effektivisera jobbinställningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="80000-140">Therefore, this feature helps streamline the job setup process.</span></span>
- <span data-ttu-id="80000-141">**Karriärplats** – aktuell version av karriärplats visar bara en lista över alla lediga jobb.</span><span class="sxs-lookup"><span data-stu-id="80000-141">**Career site** – The current version of the career site just lists all open jobs.</span></span> <span data-ttu-id="80000-142">Dock läggs mer kapacitet till webbplatsen i framtiden.</span><span class="sxs-lookup"><span data-stu-id="80000-142">However, more capabilities will be added to the site in the future.</span></span> <span data-ttu-id="80000-143">Jobb kan markeras som antingen interna eller externa.</span><span class="sxs-lookup"><span data-stu-id="80000-143">Jobs can be marked as either internal or external.</span></span> <span data-ttu-id="80000-144">Interna användare som loggar in på webbplatsen ser både interna projekt och externa jobb.</span><span class="sxs-lookup"><span data-stu-id="80000-144">Internal users who sign in to the site will see both internal jobs and external jobs.</span></span> <span data-ttu-id="80000-145">Men icke interna användare och användare som inte är inloggade ser endast externa jobb.</span><span class="sxs-lookup"><span data-stu-id="80000-145">However, non-internal users and users who aren't signed in will see only external jobs.</span></span>
- <span data-ttu-id="80000-146">**Jobbpublicering** – nu kan du publicera jobb på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="80000-146">**Job posting** – You can now post jobs to the career site.</span></span>
- <span data-ttu-id="80000-147">**LinkedIn jobbpublicering** – nu kan du publicera jobb på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="80000-147">**LinkedIn job posting** – You can now post jobs to LinkedIn.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80000-148">Jobb som har publicerats visas bara för kunder som prenumererar på en eller flera LinkedIn-jobblistor.</span><span class="sxs-lookup"><span data-stu-id="80000-148">Jobs that are posted are visible only to customers who subscribe to one or more LinkedIn job listing products.</span></span> <span data-ttu-id="80000-149">Annars ser kunder endast ett jobb om de uttryckligen söker efter det.</span><span class="sxs-lookup"><span data-stu-id="80000-149">Otherwise, customers see a job only if they explicitly search for it.</span></span> <span data-ttu-id="80000-150">Det uppstår en fördröjning när jobb publiceras på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="80000-150">There is a delay when jobs are posted to LinkedIn.</span></span> <span data-ttu-id="80000-151">Ett jobb kan ta flera timmar visas när det har publiceras från Attract.</span><span class="sxs-lookup"><span data-stu-id="80000-151">A job might take up to a few hours to appear after it's posted from Attract.</span></span>

- <span data-ttu-id="80000-152">**Kandidatsökning** – både interna och externa kandidater kan nu söka direkt från jobbsidan på karriärwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="80000-152">**Candidate apply** – Both internal and external candidates can now apply directly from the job page on the career site.</span></span>
- <span data-ttu-id="80000-153">**Bedömningar** – som en del av den konfigurerbara anställningsprocessen för ett visst jobb eller när en jobbmall används har nu användarna tillgång till en ny aktivitetstyp för **bedömning**.</span><span class="sxs-lookup"><span data-stu-id="80000-153">**Assessments** – As part of the configurable hiring process, either for a specific a job or when a job template is used, users now have access to a new **Assessment** activity type.</span></span> <span data-ttu-id="80000-154">De kan sedan använda projektet: ”Gauge” appen i Talent för att skapa grundläggande bedömningar som du kan skicka till sökande.</span><span class="sxs-lookup"><span data-stu-id="80000-154">They can then use the Project: "Gauge" app in Talent to build basic assessments that they can send to candidates.</span></span> <span data-ttu-id="80000-155">Projekt: ”Gauge” är också i förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="80000-155">Project: "Gauge" is also in public preview.</span></span> <span data-ttu-id="80000-156">Ytterligare providers läggs till i framtiden.</span><span class="sxs-lookup"><span data-stu-id="80000-156">Additional providers will be added in the future.</span></span>
- <span data-ttu-id="80000-157">**Projekt: ”Gauge”** – projekt: ”Gauge” är ett program i Talent där användarna kan skapa enkla bedömningar och undersökningar.</span><span class="sxs-lookup"><span data-stu-id="80000-157">**Project: "Gauge"** – Project: "Gauge" is an app in Talent that lets users create simple assessments or surveys.</span></span>
- <span data-ttu-id="80000-158">**Erbjudandehantering** – användarna kan nu skapa erbjudanden från mallar som inkluderar platshållare.</span><span class="sxs-lookup"><span data-stu-id="80000-158">**Offer management** – Users can now create offer letters from templates that include placeholders.</span></span> <span data-ttu-id="80000-159">När ansökande avancerar framåt till erbjudandefasen, kan rekryterare och anställande chefer använda erbjudandeverktyget för att förbereda ansökandes formella erbjudande via mallar, skicka erbjudande för internt godkännande och slutligen skicka erbjudandet till ansökande för underskrift.</span><span class="sxs-lookup"><span data-stu-id="80000-159">As candidates advance to the Offer stage, recruiters and hiring managers can use the Offer tool to prepare a candidate's formal offer via templates, send the offer for internal approval, and finally send the offer to the candidate for signature.</span></span> <span data-ttu-id="80000-160">Många nya funktioner läggs till erbjudandeverktyget med tiden och förhandsgranskningsfunktionen uppdateras med de här funktionerna när vi är klara att släppas för att förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="80000-160">Many new capabilities will be added to the Offer tool over time, and the preview feature will be updated with these capabilities as we are ready to release them to preview.</span></span>

### <a name="core-hr"></a><span data-ttu-id="80000-161">Grundläggande personal</span><span class="sxs-lookup"><span data-stu-id="80000-161">Core HR</span></span>

- <span data-ttu-id="80000-162">**Öppna anmälan** – Öppna anmälan ger anställda en enkel, egen erfarenhet för val av förmånerna.</span><span class="sxs-lookup"><span data-stu-id="80000-162">**Open Enrollment** – Benefits open enrollment gives employees a simple, self-service experience for selecting their benefits.</span></span> <span data-ttu-id="80000-163">Personaladministratörer kan konfigurera förmåner i den öppna anmälningsprocessen för organisationen och anmälningsupplevelse för medarbetare med hjälp av en enkel guidad lösning.</span><span class="sxs-lookup"><span data-stu-id="80000-163">Human Resource (HR) administrators can configure the benefits open enrollment process for their organization, and the enrollment experience for employees, by using an easy-to-follow guided solution.</span></span>

## <a name="feedback"></a><span data-ttu-id="80000-164">Feedback</span><span class="sxs-lookup"><span data-stu-id="80000-164">Feedback</span></span>

<span data-ttu-id="80000-165">Oavsett om feedback är positiv eller negativ vill vi gärna höra från dig om hur du använder funktionerna för förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="80000-165">Regardless of whether the feedback is positive or negative, we want to hear from you about your use of the preview features.</span></span> <span data-ttu-id="80000-166">Vi rekommenderar att du regelbundet publicerar feedback på följande webbplatser när du använder dessa eller andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="80000-166">We encourage you to regularly post your feedback on the following sites as you use these or any other features.</span></span>

- <span data-ttu-id="80000-167">[Gemenskap](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – webbplatsen är ett utmärkt verktyg där användare kan diskutera fall, ställa frågor och få hjälp från andra användare.</span><span class="sxs-lookup"><span data-stu-id="80000-167">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="80000-168">Använd följande webbplatser för att komma med förslag om produkter.</span><span class="sxs-lookup"><span data-stu-id="80000-168">Use the following sites to suggest product ideas.</span></span> <span data-ttu-id="80000-169">Meddela oss om funktioner som du vill ska visas i produkten och även de ändringar som du tror ska göras av befintliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="80000-169">Let us know about features that you want to see in the product, and also any changes that you think should be made to existing features.</span></span>

    - [<span data-ttu-id="80000-170">Ge dig idéer</span><span class="sxs-lookup"><span data-stu-id="80000-170">Attract Ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="80000-171">Grundläggande personal</span><span class="sxs-lookup"><span data-stu-id="80000-171">Core HR</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

<span data-ttu-id="80000-172">Inkludera inte personuppgifter (all information som kan identifiera dig) i feedback eller produktomdömen.</span><span class="sxs-lookup"><span data-stu-id="80000-172">Don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="80000-173">Information som samlas in kan analyseras ytterligare och den används inte för att besvara frågor under tillämplig sekretesslagstiftning.</span><span class="sxs-lookup"><span data-stu-id="80000-173">Information that is collected might be analyzed further, and it won't be used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="80000-174">Personuppgifter som samlas in separat under programmen som ingår i den [sekretesspolicyn för Microsoft ](https://privacy.microsoft.com/en-us/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="80000-174">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="80000-175">Sätt ett bokmärke i detta ämne och gå tillbaka ofta för att hålla dig uppdaterad om nya funktioner för förhandsgranskning som vi släpper.</span><span class="sxs-lookup"><span data-stu-id="80000-175">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>
