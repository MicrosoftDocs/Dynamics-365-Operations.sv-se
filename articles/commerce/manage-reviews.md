---
title: Hantera omdömen och recensioner
description: I det här avsnittet beskrivs hur du hanterar värderingar och recensioner med hjälp av Microsoft Dynamics 365 Commerce klassificeringar och recensioner.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027252"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="ffc6e-103">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ffc6e-104">I det här avsnittet beskrivs hur du hanterar värderingar och recensioner med hjälp av Microsoft Dynamics 365 Commerce klassificeringar och recensioner.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="ffc6e-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ffc6e-105">Overview</span></span>

<span data-ttu-id="ffc6e-106">Dynamics 365 Commerce använder Microsoft Azure kognitiva tjänster för att automatiskt moderera granskningstext genom att ta bort redigering av svordomar.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="ffc6e-107">Dessutom kan moderatorerna använda redigeringsverktyget för klassificeringar och recensioner för följande manuella uppgifter:</span><span class="sxs-lookup"><span data-stu-id="ffc6e-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="ffc6e-108">Moderera granskningar genom att svara på dem eller ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="ffc6e-109">Ta bort en kunds recensioner på kundens begäran.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="ffc6e-110">Massimport av omdömen och granskningsdata för alla produkter i en Microsoft Power BI-mall, så att trender för omdömen och recensioner kan analyseras.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="ffc6e-111">Åtkomstklassificering och granskning av redigeringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="ffc6e-112">Om du vill få åtkomst till klassificeringsfunktioner och recensioner av redigeringsfunktionerna i verktyget för webbplatshantering i e-handel följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-113">Logga in på [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ffc6e-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="ffc6e-114">Öppna det projekt som innehåller den miljö där du vill initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="ffc6e-115">Välj miljön avsnittet **miljöer**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="ffc6e-116">Under **Miljöfunktioner**, välj **Butik – hantera**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="ffc6e-117">På fliken **e-handel** under **länkar** väljer du **Hanteringsverktyg för näthandelsplats**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="ffc6e-118">Läs en recension</span><span class="sxs-lookup"><span data-stu-id="ffc6e-118">Read a review</span></span> 

1. <span data-ttu-id="ffc6e-119">Gå till **start \> recensioner \> moderator**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="ffc6e-120">Använd sökfältet högst upp till höger på sidan om du vill filtrera granskningarna som visas i produkt-ID, produktnamn eller granska text.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="ffc6e-121">Med hjälp av fler filter kan du begränsa granskningarna efter period, klassificering, kanal eller problemstatus (tas upp, svaras eller rapporteras).</span><span class="sxs-lookup"><span data-stu-id="ffc6e-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Startsida för moderator](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="ffc6e-123">Besvara på en recension</span><span class="sxs-lookup"><span data-stu-id="ffc6e-123">Respond to a review</span></span> 

<span data-ttu-id="ffc6e-124">Ibland kan kunder som köpte en produkt uttrycka sig eller vara missnöjda, eller så förstår de inte hur produkten används.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="ffc6e-125">Som moderator kan du publicera ett svar på en recension.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="ffc6e-126">Det här svaret visas tillsammans med recensionen på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="ffc6e-127">Följ de här stegen om du vill svara på en recension.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-128">Gå till **start \> recensioner \> moderator**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="ffc6e-129">Sök efter och välj den recension som kräver ett svar.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="ffc6e-130">I egenskapsrutan till höger, välj egenskapen **Lägg till ett svar**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="ffc6e-131">Ange svarstexten och namnet som ska visas för den svarande.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="ffc6e-132">Namnet på standardsvarande är **moderator**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="ffc6e-133">Välj **Publicera svar** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-133">When you've finished, select **Post response**.</span></span>

![Besvara en recension](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="ffc6e-135">Ta ner en recension</span><span class="sxs-lookup"><span data-stu-id="ffc6e-135">Take down a review</span></span> 

<span data-ttu-id="ffc6e-136">Ibland finns det en affärsjustering för moderatorer som kan ta ned kundens recension.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="ffc6e-137">Följ de här stegen om du vill ta ned en recension.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-138">Gå till **start \> recensioner \> moderator**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="ffc6e-139">Sök efter och välj den recension som måste tas ned.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="ffc6e-140">I egenskapsrutan till höger väljer du en orsak till nedtagning och väljer sedan **Ta ned**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="ffc6e-141">Ta bort en kunds recensioner på kundens begäran.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="ffc6e-142">Ibland vill kunderna ha sina värderingar och granska data permanent från en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="ffc6e-143">En moderator som tar emot en begäran om borttagning från en kund kan ta bort kundens data genom att använda funktionen borttagning av recension.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="ffc6e-144">För att kunna söka efter och ta bort en kunds data måste moderatorn ange e-postadressen som kunden använde för att logga in och ge recensioner.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="ffc6e-145">Om du vill söka efter och ta bort kunddata gör du följande:</span><span class="sxs-lookup"><span data-stu-id="ffc6e-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-146">Gå till **start \> recensioner \> ta bort**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="ffc6e-147">I fältet **Sök efter användare via e-postadress**, ange kundens e-postadress och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="ffc6e-148">Om kunden har en recensionsaktivitet (t.ex. skicka recensioner, röster om användbarheten hos en annan kunds recension eller kommentarer om en annan kunds recension) visas resultatet.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="ffc6e-149">För varje artikel finns det en **borttagnings**-knapp.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="ffc6e-150">Välj **ta bort** för varje artikel som måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="ffc6e-151">Välj **ja** när du ombeds bekräfta att det är klart.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Ta bort kunddata](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="ffc6e-153">Det kan ta upp till sju dagar innan data tas bort helt från systemet.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="ffc6e-154">Moderatorer bör meddela kunderna om denna fördröjning.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="ffc6e-155">Om kunder har ändrat sina namn i sina kontoinställningar kan flera artiklar visas i sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="ffc6e-156">Om du vill ta bort kundens data fullständigt måste moderatorn välja **ta bort** för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="ffc6e-157">Hämta klassificerings- och granskningsdata</span><span class="sxs-lookup"><span data-stu-id="ffc6e-157">Download ratings and reviews data</span></span>

<span data-ttu-id="ffc6e-158">Med klassificerings- och granskningsverktyget kan moderatorer importera klassificeringar och granska data i bulk, så att de kan analysera trender.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="ffc6e-159">En Power BI-mall som innehåller grundläggande mått finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="ffc6e-160">Moderatorerna kan använda den här mallen för att ansluta data i massimporterade och visa en instrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="ffc6e-161">De behöver inte skapa en egen instrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="ffc6e-162">Moderatorerna kan också anpassa Power BI-mallen efter specifika behov.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="ffc6e-163">Hämta klassificerings- och recensioner av data enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-164">Gå till **start \> recensioner \> rapporter**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="ffc6e-165">Välj **hämta klassificeringsdata** om du vill hämta klassificeringar och granska data i bulk i CSV-format (kommaavgränsade värden).</span><span class="sxs-lookup"><span data-stu-id="ffc6e-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="ffc6e-166">Visa trender för omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-166">View ratings and reviews trends</span></span>

<span data-ttu-id="ffc6e-167">Moderatorerna kan hämta Power BI-mallen så att de kan visa trender på en instrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="ffc6e-168">För att visa klassificerings- och recensionstrender, följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="ffc6e-169">Gå till **start \> recensioner \> rapporter**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="ffc6e-170">Välj **PowerBI-mall** om du vill hämta mallen.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-170">Select **PowerBI template** to download the template.</span></span>

    ![Hämta Power BI-mallen](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="ffc6e-172">Öppna den hämtade mallen med hjälp av Power BI-appen.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="ffc6e-173">Stäng dialogrutan **åtkomst till webbinnehåll** som visas och stäng sedan felmeddelandet "uppdatera" som visas.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="ffc6e-174">Gå till sidan **Start**, välj **Redigera frågor** och sedan **inställningar av datakälla**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="ffc6e-175">I dialogrutan **inställningar av datakälla** välj **ändra källa**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="ffc6e-176">I fältet **URL** anger du sökvägen till de granskningsdata som du hämtade i föregående procedur (t.ex. **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="ffc6e-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![URL-fält i dialogrutan kommaavgränsade värden](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="ffc6e-178">Välj **OK** och sedan **Tillämpa ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="ffc6e-179">Det tar en till två minuter innan ändringarna i datakällan tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="ffc6e-180">Välj **Trendark** om du vill visa trender och recensioner.</span><span class="sxs-lookup"><span data-stu-id="ffc6e-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Trender för omdömen och recensioner](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="ffc6e-182">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ffc6e-182">Additional resources</span></span>

[<span data-ttu-id="ffc6e-183">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="ffc6e-184">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="ffc6e-185">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ffc6e-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="ffc6e-186">Synkronisera produktklassificeringar i Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="ffc6e-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
