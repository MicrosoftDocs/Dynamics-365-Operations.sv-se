---
title: Dynamics 365 Talent till Dynamics 365 Finance-integrering av frågor och svar
description: Det här avsnittet beskriver vilken information som synkroniseras i en Talent och Finance-integrering.
author: andreabichsel
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-12-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5bb855e6dd7ff236b7bda9e59e12ed8cc8ab9bc9
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251025"
---
# <a name="dynamics-365-talent-to-dynamics-365-finance-integration-faq"></a><span data-ttu-id="836cc-103">Dynamics 365 Talent till Dynamics 365 Finance-integrering av frågor och svar</span><span class="sxs-lookup"><span data-stu-id="836cc-103">Dynamics 365 Talent to Dynamics 365 Finance integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="836cc-104">Det här avsnittet svarar på vanliga frågor om vilken information som synkroniseras när Dynamics 365 Talent är integrerad med Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-104">This topic answers common questions associated about what data is synchronized when Dynamics 365 Talent is integrated with Dynamics 365 Finance.</span></span>

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a><span data-ttu-id="836cc-105">Synkroniseras all data eller bara vissa datatabeller?</span><span class="sxs-lookup"><span data-stu-id="836cc-105">Is all data synchronized or just some data entities?</span></span>

<span data-ttu-id="836cc-106">För Core HR synkroniseras en delmängd data.</span><span class="sxs-lookup"><span data-stu-id="836cc-106">For Core HR, a subset of the data is synchronized.</span></span> <span data-ttu-id="836cc-107">En lista över alla enheter finns i [integrering från Dynamics 365 Talent till Dynamics 365 Finance](talent-financeandoperations-integration.md).</span><span class="sxs-lookup"><span data-stu-id="836cc-107">For a list of all the entities, see [Integration from Dynamics 365 Talent to Dynamics 365 Finance](talent-financeandoperations-integration.md).</span></span>

<span data-ttu-id="836cc-108">För Attract och Onboard, är all data inbyggd i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="836cc-108">For Attract and Onboard, all data is native to Common Data Service.</span></span>

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a><span data-ttu-id="836cc-109">Kan jag skapa en ny mappning utan att använda mallarna?</span><span class="sxs-lookup"><span data-stu-id="836cc-109">Can I create a new mapping without using the templates?</span></span>

<span data-ttu-id="836cc-110">Mallar är startpunkten.</span><span class="sxs-lookup"><span data-stu-id="836cc-110">Templates are the starting point.</span></span> <span data-ttu-id="836cc-111">Du kan skapa en egen mall, men det behövs alltid en mall när du skapar ett projekt för integration.</span><span class="sxs-lookup"><span data-stu-id="836cc-111">You can create your own template, but a template is always needed when creating an integration project.</span></span> <span data-ttu-id="836cc-112">Mer information om projekt, mallar och dataintegration (DI) finns i [integrera data i Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="836cc-112">For more information about data integrator (DI), templates, and projects, see [Integrate data into Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="can-i-map-financial-dimensions-to-transfer-between-talent-and-finance"></a><span data-ttu-id="836cc-113">Kan jag mappa ekonomiska dimensioner för överföring mellan Talent och Finance?</span><span class="sxs-lookup"><span data-stu-id="836cc-113">Can I map financial dimensions to transfer between Talent and Finance?</span></span>

<span data-ttu-id="836cc-114">Ekonomiska dimensioner finns inte för närvarande i Common Data Service och ingår därför inte i standardmallen.</span><span class="sxs-lookup"><span data-stu-id="836cc-114">Financial dimensions aren’t currently in Common Data Service and as a result aren’t part of the default template.</span></span> <span data-ttu-id="836cc-115">Mallen är planerad men det finns för närvarande ingen tidslinje när den släpps.</span><span class="sxs-lookup"><span data-stu-id="836cc-115">This entity is planned, but currently no release timeline is available.</span></span>

<span data-ttu-id="836cc-116">För data som finns i Finance men inte finns i Talent, länkar ihop de två systemen med hjälp av **konfigurerar länkar** i Talent.</span><span class="sxs-lookup"><span data-stu-id="836cc-116">For data that resides in Finance but does not exist in Talent, link the two systems together by using **Configure Links** in Talent.</span></span> <span data-ttu-id="836cc-117">Mer information om hur du konfigurerar länkar mellan Talent och Finance finns i [Vad är nytt eller ändrat i Dynamics 365 Talent: Core HR (31 oktober 2018)](whats-new-talent-october-31.md).</span><span class="sxs-lookup"><span data-stu-id="836cc-117">For more information about how to configure links between Talent and Finance, see [What's new or changed in Dynamics 365 Talent: Core HR (October 31, 2018)](whats-new-talent-october-31.md).</span></span>

![Mappa ekonomiska dimensioner](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a><span data-ttu-id="836cc-119">Ibland när jag importerar anställda blir de inaktiva arbetare i Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-119">Sometimes when I import employees, they go into inactive workers in Finance.</span></span> <span data-ttu-id="836cc-120">Varför?</span><span class="sxs-lookup"><span data-stu-id="836cc-120">Why?</span></span>

<span data-ttu-id="836cc-121">Du får det här felet om medarbetaren inte har en aktiv informationspost i Talent.</span><span class="sxs-lookup"><span data-stu-id="836cc-121">You may get this error if employees don’t have an active employment detail record in Talent.</span></span> <span data-ttu-id="836cc-122">Du löser problemet genom att gå till **Personalhantering \> Medarbetare \> Anställningshistorik \> Datumhanterare** och kontrollera att det finns en aktiv informationspost för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="836cc-122">To resolve this, go to **Personnel Management \> Employees \> Employment History \> Date Manager**, and verify that there is an active employment detail record.</span></span>

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a><span data-ttu-id="836cc-123">Om jag väljer att endast mappa en delmängd av fält kommer ändringar som görs i ett icke-mappat fält utlösa en synkronisering?</span><span class="sxs-lookup"><span data-stu-id="836cc-123">If I select to map only a subset of fields, will changes made to non-mapped fields trigger a sync?</span></span>

<span data-ttu-id="836cc-124">Datasynkronisering efter körning av tidsplan.</span><span class="sxs-lookup"><span data-stu-id="836cc-124">Data sync follows the execution schedule.</span></span> <span data-ttu-id="836cc-125">Integreringen kommer att hämta en post om ett fält i posten ändras oavsett om fältet är en del av integreringsmappningen.</span><span class="sxs-lookup"><span data-stu-id="836cc-125">The integration will pick up a record if any field in the record changes regardless if the field is part of integration mapping.</span></span>

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a><span data-ttu-id="836cc-126">Hur skickar jag endast aktiva ändringar av anställda och inte de avslutade posterna?</span><span class="sxs-lookup"><span data-stu-id="836cc-126">How can I send only active worker changes and not the terminated records?</span></span>

<span data-ttu-id="836cc-127">Med hjälp av "Avancerad fråga" kan du filtrera och omforma källdata innan du skickar den till destinationen.</span><span class="sxs-lookup"><span data-stu-id="836cc-127">With the use of "Advanced query", you can filter and reshape source data before passing it into the destination.</span></span>

![Avancerad fråga för aktiva medarbetare](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a><span data-ttu-id="836cc-129">Kan jag ange vilka fält som ska skickas till Finance för en viss enhet?</span><span class="sxs-lookup"><span data-stu-id="836cc-129">Can I specify which fields to send to Finance for a specific entity?</span></span>

<span data-ttu-id="836cc-130">Fält kan läggas till eller tas bort från integrationsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="836cc-130">Fields can be added or removed from the integration task.</span></span> <span data-ttu-id="836cc-131">Alla fält som existerar på entiteten Common Data Service fylls i från Core HR.</span><span class="sxs-lookup"><span data-stu-id="836cc-131">Not all data fields that exist on the Common Data Service entity will be populated from Core HR.</span></span>
<span data-ttu-id="836cc-132">Ytterligare data kan fyllas i via PowerApps.</span><span class="sxs-lookup"><span data-stu-id="836cc-132">Additional data can be populated via PowerApps.</span></span>

![Lägg till eller ta bort fält till och från från integrationsaktiviteten.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-talent-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a><span data-ttu-id="836cc-134">Jag har ställt in integration som ett batchjobb, men Talent förlorade anslutningen till destinationssystemet.</span><span class="sxs-lookup"><span data-stu-id="836cc-134">I set up integration as a batch job, but Talent lost connection to the destination system.</span></span> <span data-ttu-id="836cc-135">Hur kan jag skicka samma uppsättning ändringar till destinationssystemet</span><span class="sxs-lookup"><span data-stu-id="836cc-135">How can I send the same set of changes to the destination system?</span></span>

<span data-ttu-id="836cc-136">Inga särskilda inställningar krävs för undantagshantering.</span><span class="sxs-lookup"><span data-stu-id="836cc-136">No special setup is required for exception handling.</span></span> <span data-ttu-id="836cc-137">Dataintegration kommer automatiskt att fånga och rapportera fel som uppstår vid källan och målet och tillåter manuella försök.</span><span class="sxs-lookup"><span data-stu-id="836cc-137">The Data Integrator will automatically catch and report errors which occur at the source and destination and will allow manual retries.</span></span> <span data-ttu-id="836cc-138">Det tillåter emellertid inte manuell datakorrigering.</span><span class="sxs-lookup"><span data-stu-id="836cc-138">However, it doesn’t allow manual data correction.</span></span> <span data-ttu-id="836cc-139">Om datauppdateringar krävs som ska ske antingen på källan eller destinationen.</span><span class="sxs-lookup"><span data-stu-id="836cc-139">If data updates are needed, that should happen either at the source or the destination.</span></span>

## <a name="can-i-set-up-bi-directional-integration"></a><span data-ttu-id="836cc-140">Kan jag ställa in dubbelriktad integrering?</span><span class="sxs-lookup"><span data-stu-id="836cc-140">Can I set up bi-directional integration?</span></span>

<span data-ttu-id="836cc-141">Nej, integrering är för närvarande ensidig (Talent to Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="836cc-141">No, integration is currently one-way (Talent to Finance and Operations).</span></span> <span data-ttu-id="836cc-142">Det finns en standardmall för att skicka data från Talent till Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-142">However, there is a default template available to send data from Talent to Finance.</span></span>

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a><span data-ttu-id="836cc-143">Kan jag tillåta postborttagning som en del av min integration?</span><span class="sxs-lookup"><span data-stu-id="836cc-143">Can I allow record deletion as part of my integration?</span></span>

<span data-ttu-id="836cc-144">Nej, dataintegration kommer inte att fånga borttagna poster för dataöverföring.</span><span class="sxs-lookup"><span data-stu-id="836cc-144">No, Data Integrator will not capture deleted records for data transfer.</span></span> <span data-ttu-id="836cc-145">Endast skapande av data och uppdateringar (UPSERT) ingår för närvarande.</span><span class="sxs-lookup"><span data-stu-id="836cc-145">Only data creation and updates (UPSERT) are currently included.</span></span>

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a><span data-ttu-id="836cc-146">Kan jag köra om felaktig körning?</span><span class="sxs-lookup"><span data-stu-id="836cc-146">Can I rerun the errored execution?</span></span> <span data-ttu-id="836cc-147">I så fall skickar den en fullständig fil eller bara ändringarna?</span><span class="sxs-lookup"><span data-stu-id="836cc-147">If so, will it send a full file or only the changes?</span></span>

<span data-ttu-id="836cc-148">Den första körningen av dataintegration är alltid en fullständig körning.</span><span class="sxs-lookup"><span data-stu-id="836cc-148">The first run of Data Integrator is always a full run.</span></span> <span data-ttu-id="836cc-149">Efterföljande körningar baseras på ändringsspårning.</span><span class="sxs-lookup"><span data-stu-id="836cc-149">Subsequent runs are based on change tracking.</span></span> <span data-ttu-id="836cc-150">När en felkörning utförs, extraherar den posterna i körningen och skickar ut de senaste ändringarna från Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="836cc-150">When an error run is executed, it extracts the records in scope of the run and sends out the most recent changes from Common Data Service.</span></span>

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a><span data-ttu-id="836cc-151">När jag sparar projektet visas felmeddelandet: ”projektet har mappningsfel”.</span><span class="sxs-lookup"><span data-stu-id="836cc-151">When I save the project, I get the error: “Project has mapping errors."</span></span> <span data-ttu-id="836cc-152">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-152">What do I do?</span></span>

<span data-ttu-id="836cc-153">Kontrollera inställningarna för integrationsnycklarna, gör eventuella nödvändiga ändringar i inställningarna och uppdatera enheterna i projektet.</span><span class="sxs-lookup"><span data-stu-id="836cc-153">Check the setup of your integration keys, make any required changes to the setup, then refresh the entities in the project.</span></span>

<span data-ttu-id="836cc-154">När du använder standardmallen importeras integrationsnycklar automatiskt.</span><span class="sxs-lookup"><span data-stu-id="836cc-154">When the default template is used, the integration keys will be automatically imported.</span></span> <span data-ttu-id="836cc-155">Det här problemet kan uppstå när nya uppgifter läggs till i den befintliga mallen.</span><span class="sxs-lookup"><span data-stu-id="836cc-155">This issue may occur when new tasks are added to the existing template.</span></span>

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a><span data-ttu-id="836cc-156">Om jag har N antal juridiska personer där arbetstagarna har anställning måste jag skapa en mappning för var och en av dem?</span><span class="sxs-lookup"><span data-stu-id="836cc-156">If I have N number of legal entities where workers have employments, do I need to create a mapping for each of them?</span></span>

<span data-ttu-id="836cc-157">Ja, för varje juridisk person i Finance behöver du ett separat integrationsprojekt i dataintegration.</span><span class="sxs-lookup"><span data-stu-id="836cc-157">Yes, for each legal entity in Finance, you'll need a separate integration project in the data integration.</span></span>

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a><span data-ttu-id="836cc-158">Behöver jag överföra data som inte ingår i standardmallen som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="836cc-158">I need to transfer data that is not part of the default template provided by Microsoft.</span></span> <span data-ttu-id="836cc-159">Kan jag göra det?</span><span class="sxs-lookup"><span data-stu-id="836cc-159">Can I do this?</span></span>

<span data-ttu-id="836cc-160">Ja, fält kan läggas till eller tas bort från den nuvarande mallen.</span><span class="sxs-lookup"><span data-stu-id="836cc-160">Yes, fields can be added to or removed from the existing template.</span></span> <span data-ttu-id="836cc-161">Mallen kan ändras så att den inkluderar ytterligare data från andra Common Data Service-entiteter.</span><span class="sxs-lookup"><span data-stu-id="836cc-161">The template can be modified to include additional data from other Common Data Service entities.</span></span> <span data-ttu-id="836cc-162">Enheten måste ha Common Data Service inkluderad i mallen.</span><span class="sxs-lookup"><span data-stu-id="836cc-162">The entity must be in Common Data Service for it to be included in the template.</span></span> 

## <a name="i-just-created-new-finance-and-talent-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a><span data-ttu-id="836cc-163">Jag skapade precis nya miljöer för Finance och Talent och jag får felet ”datavärdet strider mot integritetsbegränsningar”.</span><span class="sxs-lookup"><span data-stu-id="836cc-163">I just created new Finance and Talent environments, and I'm getting the error "The data value violates integrity constraints."</span></span> <span data-ttu-id="836cc-164">Varför?</span><span class="sxs-lookup"><span data-stu-id="836cc-164">Why?</span></span>

<span data-ttu-id="836cc-165">Orsaker till felet kan vara:</span><span class="sxs-lookup"><span data-stu-id="836cc-165">Reasons for this error can include:</span></span>

- <span data-ttu-id="836cc-166">Dataöverföring resulterade i dubbla extraheringar av poster vid källan (Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="836cc-166">The data transfer resulted in duplicate records extraction at the source (Common Data Service).</span></span>

- <span data-ttu-id="836cc-167">Dataöverföringen har null-värden för fält som behövs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="836cc-167">The data transfer has null values for fields that are required in Finance and Operations.</span></span> <span data-ttu-id="836cc-168">Verifiera data på Common Data Service som uppfyller behovet av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="836cc-168">Verify the data that is in Common Data Service and meets the requirements of Finance and Operations.</span></span>

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a><span data-ttu-id="836cc-169">Om det finns exekveringsfel och anställningsidentifikationen inte synkroniserades, hur hittar jag det historikjobb som har misslyckad medarbetarpost?</span><span class="sxs-lookup"><span data-stu-id="836cc-169">If there are execution errors and the Employee ID didn't sync, how do I find the history job which has the failed employee record?</span></span>

<span data-ttu-id="836cc-170">dataintegrerare skapar flera projekt i Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-170">Data Integrator will create multiple projects in Finance.</span></span> <span data-ttu-id="836cc-171">Förhållandet mellan dataintegrerare-uppgiften och Finance-projektet är en till en.</span><span class="sxs-lookup"><span data-stu-id="836cc-171">The relationship between the Data Integrator task and the Finance project is one to one.</span></span>

<span data-ttu-id="836cc-172">Spåra tiden från tidigare dataintegrerare körningshistorik och letar upp index -1 projekt i Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-172">Trace the time from the Data Integrator execution history and look for the index -1 project in Finance.</span></span> <span data-ttu-id="836cc-173">Om aktivitetens nummer är 9 i dataintegrerare är index i Finance är 8.</span><span class="sxs-lookup"><span data-stu-id="836cc-173">If the task number is 9 in Data Integrator, the index in Finance is 8.</span></span>

1. <span data-ttu-id="836cc-174">Hämta uppgiftsindex från dataintegrerare (i det här exemplet ”9”).</span><span class="sxs-lookup"><span data-stu-id="836cc-174">Capture the task index from Data Integrator (in this example it is "9").</span></span>

![Hämta uppgiftsindex från dataintegrerare](media/CaptureTaskIndex.png)

2. <span data-ttu-id="836cc-176">Spåra körningstiden för projektet.</span><span class="sxs-lookup"><span data-stu-id="836cc-176">Track the execution time of the project.</span></span>

![Spåra körningstiden för projektet](media/CaptureTimeOfExecution.png)

3. <span data-ttu-id="836cc-178">I Finance identifierar du index -1.</span><span class="sxs-lookup"><span data-stu-id="836cc-178">In Finance, identify index - 1.</span></span> <span data-ttu-id="836cc-179">I detta exempel matchar projektet med suffixet ”8” och körningstiden för index ”0”-projekt matchar med körningstid i steg 2.</span><span class="sxs-lookup"><span data-stu-id="836cc-179">In this example, the project with suffix "8" and execution time of index "0" project matches with the execution time in Step 2.</span></span>

![Identifiera index.](media/IdentifyIndex.png)

## <a name="after-integrating-talent-and-finance-i-dont-see-my-talent-data-in-finance-what-do-i-do"></a><span data-ttu-id="836cc-181">När du integrerar Talent och Finance ser jag inte mina Talent-data i Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-181">After integrating Talent and Finance, I don’t see my Talent data in Finance.</span></span> <span data-ttu-id="836cc-182">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-182">What do I do?</span></span>

<span data-ttu-id="836cc-183">Integrering med Finance är en tvåstegsprocess.</span><span class="sxs-lookup"><span data-stu-id="836cc-183">The integration to Finance is a two-step process.</span></span> <span data-ttu-id="836cc-184">Kontrollera först att Talent-data är uppdaterade och finns tillgänglig i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="836cc-184">First, verify that the Talent data is updated and available in Common Data Service.</span></span> <span data-ttu-id="836cc-185">Detta är en synkronisering nästan i realtid och kan kontrolleras i PowerApps genom att granska data i datatabellerna.</span><span class="sxs-lookup"><span data-stu-id="836cc-185">This is a near real-time sync and can be verified in PowerApps by looking at the data within the data entities.</span></span>

![Data i Common Data Service](media/DataInCDS.png)

<span data-ttu-id="836cc-187">Om data inte visas som förväntat i Common Data Service, kontrollerar du att enheten stöds i integrationen.</span><span class="sxs-lookup"><span data-stu-id="836cc-187">If the data is not appearing as expected in Common Data Service, verify that the entity is supported in the integration.</span></span> <span data-ttu-id="836cc-188">Om du vill inkludera ytterligare information i Common Data Service krävs en ändring på Microsoft-sidan.</span><span class="sxs-lookup"><span data-stu-id="836cc-188">To include additional data in Common Data Service, a change will be required on the Microsoft side.</span></span>

<span data-ttu-id="836cc-189">Om enheten stöds och data som finns på Common Data Service, verifiera att mappningen är korrekt i dataintegrerare.</span><span class="sxs-lookup"><span data-stu-id="836cc-189">If the entity is supported and the data is available in Common Data Service, verify the mapping is correct in Data Integrator.</span></span> <span data-ttu-id="836cc-190">Om integratormappningen ser bra ut, verifiera att datahanteringsjobb har körts.</span><span class="sxs-lookup"><span data-stu-id="836cc-190">If the integrator mapping looks okay, then verify the data management jobs have successfully run.</span></span> <span data-ttu-id="836cc-191">Fel kan uppstå vid körning av batch-jobb.</span><span class="sxs-lookup"><span data-stu-id="836cc-191">Errors may occur during the execution of the batch jobs.</span></span> <span data-ttu-id="836cc-192">Mer information om hur du använder datahantering finns i [Datahantering](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).</span><span class="sxs-lookup"><span data-stu-id="836cc-192">For more information about Data Management, see [Data management](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).</span></span>

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a><span data-ttu-id="836cc-193">Adresser för mina medarbetare är felaktiga när jag har importerat dem till Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-193">The addresses for my employees are incorrect after I import them into Finance.</span></span> <span data-ttu-id="836cc-194">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-194">What should I do?</span></span>

<span data-ttu-id="836cc-195">Nummerserien för **plats-ID** använder samma mönster i både Talent och Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-195">The number sequence for **Location ID** uses the same pattern in both Talent and Finance.</span></span> <span data-ttu-id="836cc-196">Nummerserien måste vara unika på båda sidor så att det inte finns några adresskollisioner när du integrerar data från Common Data Service till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="836cc-196">The number sequence needs to be unique on both sides so there are no address collisions when integrating data from Common Data Service to Finance and Operations.</span></span>

<span data-ttu-id="836cc-197">Under implementering av Talent, verifiera att nummerserier inte är desamma i Talent och Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-197">During implementation of Talent, verify that the number sequences are not the same in Talent and Finance.</span></span> <span data-ttu-id="836cc-198">Verifiera att alla nummerserier inte är identiska där data kan behållas i båda systemen.</span><span class="sxs-lookup"><span data-stu-id="836cc-198">Validate that all number sequences are not identical where data may be maintained in both systems.</span></span>

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a><span data-ttu-id="836cc-199">När jag skapar min anslutning visas inte anslutningen i listrutan för anslutning.</span><span class="sxs-lookup"><span data-stu-id="836cc-199">When creating my connection set, I am unable to see the connection in the Connection drop-down list.</span></span> <span data-ttu-id="836cc-200">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-200">What do I do?</span></span>

<span data-ttu-id="836cc-201">Se till att du väljer Dynamics 365 Finance och Common Data Service när du skapar anslutningarna.</span><span class="sxs-lookup"><span data-stu-id="836cc-201">Make sure when creating your connections, you choose Dynamics 365 Finance and Common Data Service.</span></span>

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a><span data-ttu-id="836cc-202">Vid synkronisering av anställningar får jag felet ”CompanyInfo_FK finns inte” eller ”värdet 12/31/2154 11:59:59 pm i fältet Slutdatum för anställning saknas i den relaterade tabellen Anställning. Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-202">When syncing employments, I get the errors “CompanyInfo_FK doesn’t exist" or “The value '12/31/2154 11:59:59 pm' in field 'Employment end date' is not found in the related table 'Employment'.” What should I do?</span></span>

<span data-ttu-id="836cc-203">Se till att du mappar till rätt juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="836cc-203">Ensure that you are mapping to the correct legal entities.</span></span> <span data-ttu-id="836cc-204">Synkronisering av juridisk person ingår inte i standardmallen, så det är normalt att varje juridisk person som finns i Talent och Common Data Service även finns i Finance.</span><span class="sxs-lookup"><span data-stu-id="836cc-204">Legal entity syncing is not part of the default template, so it is expected that each legal entity that is present in Talent and Common Data Service is also present in Finance.</span></span>
<span data-ttu-id="836cc-205">Se också till att du väljer rätt juridiska personer för associerad anslutningsinställning.</span><span class="sxs-lookup"><span data-stu-id="836cc-205">Also, make sure that you are selecting the correct legal entities for the associated Connection Set.</span></span>

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a><span data-ttu-id="836cc-206">Efter installationen av mitt projekt verkar fältmappningen för Finance vara tom.</span><span class="sxs-lookup"><span data-stu-id="836cc-206">After setting up my project, the field mapping for Finance appears to be empty.</span></span> <span data-ttu-id="836cc-207">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="836cc-207">What should I do?</span></span>

<span data-ttu-id="836cc-208">Uppdatera datatabellerna i Finance genom att gå till **datahantering \> ramverksparametrar \> entitetsinställningar \> uppdatera entitetslistan.**</span><span class="sxs-lookup"><span data-stu-id="836cc-208">Refresh the data entities in Finance by going to **Data management \> Framework Parameters \> Entity settings \> Refresh entity list.**</span></span> <span data-ttu-id="836cc-209">Detta tar några minuter att slutföra och sedan visas mappningarna.</span><span class="sxs-lookup"><span data-stu-id="836cc-209">This should take a couple of minutes to complete, then you should see those mappings.</span></span> <span data-ttu-id="836cc-210">Problemet uppstår när nya projekt skapas.</span><span class="sxs-lookup"><span data-stu-id="836cc-210">This issue occurs when new projects are created.</span></span>

![Saknad fältmappning](media/MissingFieldMapping.png)

## <a name="additional-resources"></a><span data-ttu-id="836cc-212">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="836cc-212">Additional resources</span></span>

- <span data-ttu-id="836cc-213">Dataintegrerare (DI):</span><span class="sxs-lookup"><span data-stu-id="836cc-213">Data Integrator (DI):</span></span> 

  - [<span data-ttu-id="836cc-214">Integrera data i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="836cc-214">Integrate data into Common Data Service</span></span>](https://docs.microsoft.com/powerapps/administrator/data-integrator)

  - [<span data-ttu-id="836cc-215">dataintegrerare felhantering och felsökning</span><span class="sxs-lookup"><span data-stu-id="836cc-215">Data Integrator error management and troubleshooting</span></span>](https://docs.microsoft.com/powerapps/administrator/data-integrator-error-management)

  - [<span data-ttu-id="836cc-216">Svara på DSR-förfrågningar för systemgenererade loggar i PowerApps, Microsoft Flow och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="836cc-216">Responding to DSR requests for system-generated logs in PowerApps, Microsoft Flow, and Common Data Service</span></span>](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- <span data-ttu-id="836cc-217">Datahantering</span><span class="sxs-lookup"><span data-stu-id="836cc-217">Data Management:</span></span>

  - [<span data-ttu-id="836cc-218">Datahantering</span><span class="sxs-lookup"><span data-stu-id="836cc-218">Data management</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)
