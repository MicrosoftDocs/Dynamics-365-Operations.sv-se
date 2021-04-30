---
title: Vanliga frågeställningar integration med Finance
description: Det här artikel beskriver vilken information som synkroniseras i en Personal- och Finance-integrering.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5befac6c72153332319eefc1aaeab30c33f4c69
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892261"
---
# <a name="integration-with-finance-faq"></a><span data-ttu-id="35fb2-103">Vanliga frågeställningar integration med Finance</span><span class="sxs-lookup"><span data-stu-id="35fb2-103">Integration with Finance FAQ</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="35fb2-104">Det här avsnittet svarar på vanliga frågeställningar om vilken information som synkroniseras när Dynamics 365 Human Resources är integrerad med Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-104">This topic answers common questions associated about what data is synchronized when Dynamics 365 Human Resources is integrated with Dynamics 365 Finance.</span></span>

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a><span data-ttu-id="35fb2-105">Kan jag redigera Dynamics 365 Talent-programanvändaren i Power Apps?</span><span class="sxs-lookup"><span data-stu-id="35fb2-105">Can I edit the Dynamics 365 Talent application user in Power Apps?</span></span>

<span data-ttu-id="35fb2-106">Nr</span><span class="sxs-lookup"><span data-stu-id="35fb2-106">No.</span></span> <span data-ttu-id="35fb2-107">Om du redigerar Personal-programanvändaren kan det hända att integreringen mellan Personal och Dataverse misslyckas.</span><span class="sxs-lookup"><span data-stu-id="35fb2-107">If you edit the Human Resources application user, the integration between Human Resources and Dataverse might fail.</span></span> <span data-ttu-id="35fb2-108">I följande tabell visas standardinställningarna för Talang-programanvändaren.</span><span class="sxs-lookup"><span data-stu-id="35fb2-108">The following table shows the default settings for the Talent application user.</span></span>

| <span data-ttu-id="35fb2-109">Fullständigt namn</span><span class="sxs-lookup"><span data-stu-id="35fb2-109">Full Name</span></span> | <span data-ttu-id="35fb2-110">Sökande-ID</span><span class="sxs-lookup"><span data-stu-id="35fb2-110">Application ID</span></span> | <span data-ttu-id="35fb2-111">Azure AD Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="35fb2-111">Azure AD Object ID</span></span> | <span data-ttu-id="35fb2-112">Sökande-ID URI</span><span class="sxs-lookup"><span data-stu-id="35fb2-112">Application ID URI</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="35fb2-113">Dynamics 365 för Talang</span><span class="sxs-lookup"><span data-stu-id="35fb2-113">Dynamics365 for Talent</span></span> | <span data-ttu-id="35fb2-114">f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="35fb2-114">f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span> | <span data-ttu-id="35fb2-115">27fd8129-4b3c-43f7-b1bf-47495d3a049b</span><span class="sxs-lookup"><span data-stu-id="35fb2-115">27fd8129-4b3c-43f7-b1bf-47495d3a049b</span></span> | <span data-ttu-id="35fb2-116">f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="35fb2-116">f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span> |

![Standardinställningar för Talang-programanvändare](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a><span data-ttu-id="35fb2-118">Synkroniseras all data eller bara vissa datatabeller?</span><span class="sxs-lookup"><span data-stu-id="35fb2-118">Is all data synchronized or just some data entities?</span></span>

<span data-ttu-id="35fb2-119">E delmängd data synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="35fb2-119">A subset of the data is synchronized.</span></span> <span data-ttu-id="35fb2-120">En lista över alla enheter finns i [integrering med Dynamics 365 Finance](hr-admin-integration-finance.md).</span><span class="sxs-lookup"><span data-stu-id="35fb2-120">For a list of all the entities, see [Integration with Dynamics 365 Finance](hr-admin-integration-finance.md).</span></span>

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a><span data-ttu-id="35fb2-121">Varför visas inga data synkroniserade till Dataverse?</span><span class="sxs-lookup"><span data-stu-id="35fb2-121">Why don't I see any data synced to Dataverse?</span></span>

<span data-ttu-id="35fb2-122">Som standard är Dataverse-integrationen inaktiverad i nya miljöer som inte innehåller de tillhandahållna demodata.</span><span class="sxs-lookup"><span data-stu-id="35fb2-122">By default, the Dataverse integration is turned off in new environments that don't include the provided demo data.</span></span> <span data-ttu-id="35fb2-123">Som standard är den aktiverad i nya miljöer där demodata ingår och datasynkroniseringen börjar när miljön etableras.</span><span class="sxs-lookup"><span data-stu-id="35fb2-123">By default, it's turned on in new environments that include demo data, and data synchronization begins when the environment is provisioned.</span></span> <span data-ttu-id="35fb2-124">När din miljö är redo att synkronisera data kan du aktivera integrationen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-124">After your environment is ready to sync data, you can turn on the integration.</span></span> <span data-ttu-id="35fb2-125">Mer information finns i avsnittet [Konfigurera Dataverse-integration](hr-admin-integration-common-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="35fb2-125">For more information, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md).</span></span>

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a><span data-ttu-id="35fb2-126">Kan jag skapa en ny mappning utan att använda mallarna?</span><span class="sxs-lookup"><span data-stu-id="35fb2-126">Can I create a new mapping without using the templates?</span></span>

<span data-ttu-id="35fb2-127">Mallar är startpunkten.</span><span class="sxs-lookup"><span data-stu-id="35fb2-127">Templates are the starting point.</span></span> <span data-ttu-id="35fb2-128">Du kan skapa en egen mall, men det behövs alltid en mall när du skapar ett projekt för integration.</span><span class="sxs-lookup"><span data-stu-id="35fb2-128">You can create your own template, but a template is always needed when creating an integration project.</span></span> <span data-ttu-id="35fb2-129">Mer information om projekt, mallar och dataintegration (DI) finns i [integrera data i Microsoft Dataverse](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="35fb2-129">For more information about data integrator (DI), templates, and projects, see [Integrate data into Microsoft Dataverse](/powerapps/administrator/data-integrator).</span></span>

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a><span data-ttu-id="35fb2-130">Kan jag mappa ekonomiska dimensioner för överföring mellan Personal och Finance?</span><span class="sxs-lookup"><span data-stu-id="35fb2-130">Can I map financial dimensions to transfer between Human Resources and Finance?</span></span>

<span data-ttu-id="35fb2-131">Ekonomiska dimensioner finns inte för närvarande i Dataverse och ingår därför inte i standardmallen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-131">Financial dimensions aren’t currently in Dataverse and as a result aren’t part of the default template.</span></span> <span data-ttu-id="35fb2-132">Mallen är planerad men det finns för närvarande ingen tidslinje när den släpps.</span><span class="sxs-lookup"><span data-stu-id="35fb2-132">This entity is planned, but currently no release timeline is available.</span></span>

<span data-ttu-id="35fb2-133">För data som finns i Finance men inte finns i Personal, länkar ihop de två systemen med hjälp av **konfigurerar länkar** i Personal.</span><span class="sxs-lookup"><span data-stu-id="35fb2-133">For data that resides in Finance but does not exist in Human Resources, link the two systems together by using **Configure Links** in Human Resources.</span></span>

![Mappa ekonomiska dimensioner](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a><span data-ttu-id="35fb2-135">Ibland när jag importerar anställda blir de inaktiva arbetare i Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-135">Sometimes when I import employees, they go into inactive workers in Finance.</span></span> <span data-ttu-id="35fb2-136">Varför?</span><span class="sxs-lookup"><span data-stu-id="35fb2-136">Why?</span></span>

<span data-ttu-id="35fb2-137">Du får det här felet om medarbetaren inte har en aktiv informationspost i Personal.</span><span class="sxs-lookup"><span data-stu-id="35fb2-137">You may get this error if employees don’t have an active employment detail record in Human Resources.</span></span> <span data-ttu-id="35fb2-138">Du löser problemet genom att gå till **Personalhantering \> Medarbetare \> Anställningshistorik \> Datumhanterare** och kontrollera att det finns en aktiv informationspost för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="35fb2-138">To resolve this, go to **Personnel Management \> Employees \> Employment History \> Date Manager**, and verify that there is an active employment detail record.</span></span>

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a><span data-ttu-id="35fb2-139">Om jag väljer att endast mappa en delmängd av fält kommer ändringar som görs i ett icke-mappat fält utlösa en synkronisering?</span><span class="sxs-lookup"><span data-stu-id="35fb2-139">If I select to map only a subset of fields, will changes made to non-mapped fields trigger a sync?</span></span>

<span data-ttu-id="35fb2-140">Datasynkronisering efter körning av tidsplan.</span><span class="sxs-lookup"><span data-stu-id="35fb2-140">Data sync follows the execution schedule.</span></span> <span data-ttu-id="35fb2-141">Integreringen kommer att hämta en post om ett fält i posten ändras oavsett om fältet är en del av integreringsmappningen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-141">The integration will pick up a record if any field in the record changes regardless if the field is part of integration mapping.</span></span>

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a><span data-ttu-id="35fb2-142">Hur skickar jag endast aktiva ändringar av anställda och inte de avslutade posterna?</span><span class="sxs-lookup"><span data-stu-id="35fb2-142">How can I send only active worker changes and not the terminated records?</span></span>

<span data-ttu-id="35fb2-143">Med hjälp av "Avancerad fråga" kan du filtrera och omforma källdata innan du skickar den till destinationen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-143">With the use of "Advanced query", you can filter and reshape source data before passing it into the destination.</span></span>

![Avancerad fråga för aktiva medarbetare](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a><span data-ttu-id="35fb2-145">Kan jag ange vilka fält som ska skickas till Finance för en viss enhet?</span><span class="sxs-lookup"><span data-stu-id="35fb2-145">Can I specify which fields to send to Finance for a specific entity?</span></span>

<span data-ttu-id="35fb2-146">Fält kan läggas till eller tas bort från integrationsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="35fb2-146">Fields can be added or removed from the integration task.</span></span> <span data-ttu-id="35fb2-147">Samtliga datafält i Dataverse-registret kommer inte att fyllas i från Personal.</span><span class="sxs-lookup"><span data-stu-id="35fb2-147">Not all data fields that exist on the Dataverse table will be populated from Human Resources.</span></span>
<span data-ttu-id="35fb2-148">Ytterligare data kan fyllas i via Power Apps.</span><span class="sxs-lookup"><span data-stu-id="35fb2-148">Additional data can be populated via Power Apps.</span></span>

![Lägg till eller ta bort fält till och från från integrationsaktiviteten.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a><span data-ttu-id="35fb2-150">Jag har ställt in integration som ett batchjobb, men Personal förlorade anslutningen till destinationssystemet.</span><span class="sxs-lookup"><span data-stu-id="35fb2-150">I set up integration as a batch job, but Human Resources lost connection to the destination system.</span></span> <span data-ttu-id="35fb2-151">Hur kan jag skicka samma uppsättning ändringar till destinationssystemet</span><span class="sxs-lookup"><span data-stu-id="35fb2-151">How can I send the same set of changes to the destination system?</span></span>

<span data-ttu-id="35fb2-152">Inga särskilda inställningar krävs för undantagshantering.</span><span class="sxs-lookup"><span data-stu-id="35fb2-152">No special setup is required for exception handling.</span></span> <span data-ttu-id="35fb2-153">Dataintegration kommer automatiskt att fånga och rapportera fel som uppstår vid källan och målet och tillåter manuella försök.</span><span class="sxs-lookup"><span data-stu-id="35fb2-153">The Data Integrator will automatically catch and report errors which occur at the source and destination and will allow manual retries.</span></span> <span data-ttu-id="35fb2-154">Det tillåter emellertid inte manuell datakorrigering.</span><span class="sxs-lookup"><span data-stu-id="35fb2-154">However, it doesn’t allow manual data correction.</span></span> <span data-ttu-id="35fb2-155">Om datauppdateringar krävs som ska ske antingen på källan eller destinationen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-155">If data updates are needed, that should happen either at the source or the destination.</span></span>

## <a name="can-i-set-up-bi-directional-integration"></a><span data-ttu-id="35fb2-156">Kan jag ställa in dubbelriktad integrering?</span><span class="sxs-lookup"><span data-stu-id="35fb2-156">Can I set up bi-directional integration?</span></span>

<span data-ttu-id="35fb2-157">Nej, integrationen är för närvarande enkelriktad (Personal till Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="35fb2-157">No, integration is currently one-way (Human Resources to Finance and Operations).</span></span> <span data-ttu-id="35fb2-158">Det finns en standardmall för att skicka data från Personal till Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-158">However, there is a default template available to send data from Human Resources to Finance.</span></span>

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a><span data-ttu-id="35fb2-159">Kan jag tillåta postborttagning som en del av min integration?</span><span class="sxs-lookup"><span data-stu-id="35fb2-159">Can I allow record deletion as part of my integration?</span></span>

<span data-ttu-id="35fb2-160">Nej, dataintegration kommer inte att fånga borttagna poster för dataöverföring.</span><span class="sxs-lookup"><span data-stu-id="35fb2-160">No, Data Integrator will not capture deleted records for data transfer.</span></span> <span data-ttu-id="35fb2-161">Endast skapande av data och uppdateringar (UPSERT) ingår för närvarande.</span><span class="sxs-lookup"><span data-stu-id="35fb2-161">Only data creation and updates (UPSERT) are currently included.</span></span>

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a><span data-ttu-id="35fb2-162">Kan jag köra om felaktig körning?</span><span class="sxs-lookup"><span data-stu-id="35fb2-162">Can I rerun the errored execution?</span></span> <span data-ttu-id="35fb2-163">I så fall skickar den en fullständig fil eller bara ändringarna?</span><span class="sxs-lookup"><span data-stu-id="35fb2-163">If so, will it send a full file or only the changes?</span></span>

<span data-ttu-id="35fb2-164">Den första körningen av dataintegration är alltid en fullständig körning.</span><span class="sxs-lookup"><span data-stu-id="35fb2-164">The first run of Data Integrator is always a full run.</span></span> <span data-ttu-id="35fb2-165">Efterföljande körningar baseras på ändringsspårning.</span><span class="sxs-lookup"><span data-stu-id="35fb2-165">Subsequent runs are based on change tracking.</span></span> <span data-ttu-id="35fb2-166">När en felkörning utförs, extraherar den posterna i körningen och skickar ut de senaste ändringarna från Dataverse.</span><span class="sxs-lookup"><span data-stu-id="35fb2-166">When an error run is executed, it extracts the records in scope of the run and sends out the most recent changes from Dataverse.</span></span>

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a><span data-ttu-id="35fb2-167">När jag sparar projektet visas felmeddelandet: ”projektet har mappningsfel”.</span><span class="sxs-lookup"><span data-stu-id="35fb2-167">When I save the project, I get the error: “Project has mapping errors."</span></span> <span data-ttu-id="35fb2-168">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-168">What do I do?</span></span>

<span data-ttu-id="35fb2-169">Kontrollera inställningarna för integrationsnycklarna, gör eventuella nödvändiga ändringar i inställningarna och uppdatera enheterna i projektet.</span><span class="sxs-lookup"><span data-stu-id="35fb2-169">Check the setup of your integration keys, make any required changes to the setup, then refresh the entities in the project.</span></span>

<span data-ttu-id="35fb2-170">När du använder standardmallen importeras integrationsnycklar automatiskt.</span><span class="sxs-lookup"><span data-stu-id="35fb2-170">When the default template is used, the integration keys will be automatically imported.</span></span> <span data-ttu-id="35fb2-171">Det här problemet kan uppstå när nya uppgifter läggs till i den befintliga mallen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-171">This issue may occur when new tasks are added to the existing template.</span></span>

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a><span data-ttu-id="35fb2-172">Om jag har N antal juridiska personer där arbetstagarna har anställning måste jag skapa en mappning för var och en av dem?</span><span class="sxs-lookup"><span data-stu-id="35fb2-172">If I have N number of legal entities where workers have employments, do I need to create a mapping for each of them?</span></span>

<span data-ttu-id="35fb2-173">Ja, för varje juridisk person i Finance behöver du ett separat integrationsprojekt i dataintegration.</span><span class="sxs-lookup"><span data-stu-id="35fb2-173">Yes, for each legal entity in Finance, you'll need a separate integration project in the data integration.</span></span>

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a><span data-ttu-id="35fb2-174">Behöver jag överföra data som inte ingår i standardmallen som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35fb2-174">I need to transfer data that is not part of the default template provided by Microsoft.</span></span> <span data-ttu-id="35fb2-175">Kan jag göra det?</span><span class="sxs-lookup"><span data-stu-id="35fb2-175">Can I do this?</span></span>

<span data-ttu-id="35fb2-176">Ja, fält kan läggas till eller tas bort från den nuvarande mallen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-176">Yes, fields can be added to or removed from the existing template.</span></span> <span data-ttu-id="35fb2-177">Mallen kan ändras så att den inkluderar ytterligare data från andra Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="35fb2-177">The template can be modified to include additional data from other Dataverse tables.</span></span> <span data-ttu-id="35fb2-178">Enheten måste ha Dataverse inkluderad i mallen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-178">The entity must be in Dataverse for it to be included in the template.</span></span> 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a><span data-ttu-id="35fb2-179">Jag skapade precis nya miljöer för Finance och Personal och jag får felet ”datavärdet strider mot integritetsbegränsningar”.</span><span class="sxs-lookup"><span data-stu-id="35fb2-179">I just created new Finance and Human Resources environments, and I'm getting the error "The data value violates integrity constraints."</span></span> <span data-ttu-id="35fb2-180">Varför?</span><span class="sxs-lookup"><span data-stu-id="35fb2-180">Why?</span></span>

<span data-ttu-id="35fb2-181">Orsaker till felet kan vara:</span><span class="sxs-lookup"><span data-stu-id="35fb2-181">Reasons for this error can include:</span></span>

- <span data-ttu-id="35fb2-182">Dataöverföring resulterade i dubbla extraheringar av poster vid källan (Dataverse).</span><span class="sxs-lookup"><span data-stu-id="35fb2-182">The data transfer resulted in duplicate records extraction at the source (Dataverse).</span></span>

- <span data-ttu-id="35fb2-183">Dataöverföringen har null-värden för fält som behövs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35fb2-183">The data transfer has null values for fields that are required in Finance and Operations.</span></span> <span data-ttu-id="35fb2-184">Verifiera data på Dataverse som uppfyller behovet av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35fb2-184">Verify the data that is in Dataverse and meets the requirements of Finance and Operations.</span></span>

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a><span data-ttu-id="35fb2-185">Om det finns exekveringsfel och anställningsidentifikationen inte synkroniserades, hur hittar jag det historikjobb som har misslyckad medarbetarpost?</span><span class="sxs-lookup"><span data-stu-id="35fb2-185">If there are execution errors and the Employee ID didn't sync, how do I find the history job which has the failed employee record?</span></span>

<span data-ttu-id="35fb2-186">dataintegrerare skapar flera projekt i Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-186">Data Integrator will create multiple projects in Finance.</span></span> <span data-ttu-id="35fb2-187">Förhållandet mellan dataintegrerare-uppgiften och Finance-projektet är en till en.</span><span class="sxs-lookup"><span data-stu-id="35fb2-187">The relationship between the Data Integrator task and the Finance project is one to one.</span></span>

<span data-ttu-id="35fb2-188">Spåra tiden från tidigare dataintegrerare körningshistorik och letar upp index -1 projekt i Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-188">Trace the time from the Data Integrator execution history and look for the index -1 project in Finance.</span></span> <span data-ttu-id="35fb2-189">Om aktivitetens nummer är 9 i dataintegrerare är index i Finance är 8.</span><span class="sxs-lookup"><span data-stu-id="35fb2-189">If the task number is 9 in Data Integrator, the index in Finance is 8.</span></span>

1. <span data-ttu-id="35fb2-190">Hämta uppgiftsindex från dataintegrerare (i det här exemplet ”9”).</span><span class="sxs-lookup"><span data-stu-id="35fb2-190">Capture the task index from Data Integrator (in this example it is "9").</span></span>

    ![Hämta uppgiftsindex från dataintegrerare](media/CaptureTaskIndex.png)

2. <span data-ttu-id="35fb2-192">Spåra körningstiden för projektet.</span><span class="sxs-lookup"><span data-stu-id="35fb2-192">Track the execution time of the project.</span></span>

    ![Spåra körningstiden för projektet](media/CaptureTimeOfExecution.png)

3. <span data-ttu-id="35fb2-194">I Finance identifierar du index -1.</span><span class="sxs-lookup"><span data-stu-id="35fb2-194">In Finance, identify index - 1.</span></span> <span data-ttu-id="35fb2-195">I detta exempel matchar projektet med suffixet ”8” och körningstiden för index ”0”-projekt matchar med körningstid i steg 2.</span><span class="sxs-lookup"><span data-stu-id="35fb2-195">In this example, the project with suffix "8" and execution time of index "0" project matches with the execution time in Step 2.</span></span>

    ![Identifiera index.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a><span data-ttu-id="35fb2-197">När du har integrerat Personal och Finance visas inte mina Personal uppgifter i Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-197">After integrating Human Resources and Finance, I don’t see my Human Resources data in Finance.</span></span> <span data-ttu-id="35fb2-198">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-198">What do I do?</span></span>

<span data-ttu-id="35fb2-199">Integrering med Finance är en tvåstegsprocess.</span><span class="sxs-lookup"><span data-stu-id="35fb2-199">The integration to Finance is a two-step process.</span></span> <span data-ttu-id="35fb2-200">Kontrollera först att Personal-data är uppdaterade och finns tillgänglig i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="35fb2-200">First, verify that the Human Resources data is updated and available in Dataverse.</span></span> <span data-ttu-id="35fb2-201">Detta är en synkronisering nästan i realtid och kan verifieras i Power Apps genom att granska datan i dataregistren.</span><span class="sxs-lookup"><span data-stu-id="35fb2-201">This is a near real-time sync and can be verified in Power Apps by looking at the data within the data tables.</span></span>

![Data i Dataverse](media/DataInCDS.png)

<span data-ttu-id="35fb2-203">Om data inte visas som förväntat i Dataverse, kontrollerar du att enheten stöds i integrationen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-203">If the data is not appearing as expected in Dataverse, verify that the entity is supported in the integration.</span></span> <span data-ttu-id="35fb2-204">Om du vill inkludera ytterligare information i Dataverse krävs en ändring på Microsoft-sidan.</span><span class="sxs-lookup"><span data-stu-id="35fb2-204">To include additional data in Dataverse, a change will be required on the Microsoft side.</span></span>

<span data-ttu-id="35fb2-205">Om enheten stöds och data som finns på Dataverse, verifiera att mappningen är korrekt i dataintegrerare.</span><span class="sxs-lookup"><span data-stu-id="35fb2-205">If the entity is supported and the data is available in Dataverse, verify the mapping is correct in Data Integrator.</span></span> <span data-ttu-id="35fb2-206">Om integratormappningen ser bra ut, verifiera att datahanteringsjobb har körts.</span><span class="sxs-lookup"><span data-stu-id="35fb2-206">If the integrator mapping looks okay, then verify the data management jobs have successfully run.</span></span> <span data-ttu-id="35fb2-207">Fel kan uppstå vid körning av batch-jobb.</span><span class="sxs-lookup"><span data-stu-id="35fb2-207">Errors may occur during the execution of the batch jobs.</span></span> <span data-ttu-id="35fb2-208">Mer information om hur du använder datahantering finns i [Datahantering](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="35fb2-208">For more information about Data Management, see [Data management](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).</span></span>

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a><span data-ttu-id="35fb2-209">Adresser för mina medarbetare är felaktiga när jag har importerat dem till Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-209">The addresses for my employees are incorrect after I import them into Finance.</span></span> <span data-ttu-id="35fb2-210">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-210">What should I do?</span></span>

<span data-ttu-id="35fb2-211">Nummerserien för **plats-ID** använder samma mönster i både Personal och Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-211">The number sequence for **Location ID** uses the same pattern in both Human Resources and Finance.</span></span> <span data-ttu-id="35fb2-212">Nummerserien måste vara unika på båda sidor så att det inte finns några adresskollisioner när du integrerar data från Dataverse till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35fb2-212">The number sequence needs to be unique on both sides so there are no address collisions when integrating data from Dataverse to Finance and Operations.</span></span>

<span data-ttu-id="35fb2-213">Under implementering av Personal, verifiera att nummerserier inte är desamma i Personal and Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-213">During implementation of Human Resources, verify that the number sequences are not the same in Human Resources and Finance.</span></span> <span data-ttu-id="35fb2-214">Verifiera att alla nummerserier inte är identiska där data kan behållas i båda systemen.</span><span class="sxs-lookup"><span data-stu-id="35fb2-214">Validate that all number sequences are not identical where data may be maintained in both systems.</span></span>

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a><span data-ttu-id="35fb2-215">När jag skapar min anslutning visas inte anslutningen i listrutan för anslutning.</span><span class="sxs-lookup"><span data-stu-id="35fb2-215">When creating my connection set, I am unable to see the connection in the Connection drop-down list.</span></span> <span data-ttu-id="35fb2-216">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-216">What do I do?</span></span>

<span data-ttu-id="35fb2-217">Se till att du väljer Dynamics 365 Finance och Dataverse när du skapar anslutningarna.</span><span class="sxs-lookup"><span data-stu-id="35fb2-217">Make sure when creating your connections, you choose Dynamics 365 Finance and Dataverse.</span></span>

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a><span data-ttu-id="35fb2-218">Vid synkronisering av anställningar får jag felet ”CompanyInfo_FK finns inte” eller ”värdet 12/31/2154 11:59:59 pm i fältet Slutdatum för anställning saknas i den relaterade tabellen Anställning. Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-218">When syncing employments, I get the errors “CompanyInfo_FK doesn’t exist" or “The value '12/31/2154 11:59:59 pm' in field 'Employment end date' is not found in the related table 'Employment'.” What should I do?</span></span>

<span data-ttu-id="35fb2-219">Se till att du mappar till rätt juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="35fb2-219">Ensure that you are mapping to the correct legal entities.</span></span> <span data-ttu-id="35fb2-220">Synkronisering av juridisk person ingår inte i standardmallen, så det är normalt att varje juridisk person som finns i Personal och Dataverse även finns i Finance.</span><span class="sxs-lookup"><span data-stu-id="35fb2-220">Legal entity syncing is not part of the default template, so it is expected that each legal entity that is present in Human Resources and Dataverse is also present in Finance.</span></span>
<span data-ttu-id="35fb2-221">Se också till att du väljer rätt juridiska personer för associerad anslutningsinställning.</span><span class="sxs-lookup"><span data-stu-id="35fb2-221">Also, make sure that you are selecting the correct legal entities for the associated Connection Set.</span></span>

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a><span data-ttu-id="35fb2-222">Efter installationen av mitt projekt verkar fältmappningen för Finance vara tom.</span><span class="sxs-lookup"><span data-stu-id="35fb2-222">After setting up my project, the field mapping for Finance appears to be empty.</span></span> <span data-ttu-id="35fb2-223">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="35fb2-223">What should I do?</span></span>

<span data-ttu-id="35fb2-224">Uppdatera datatabellerna i Finance genom att gå till **datahantering \> ramverksparametrar \> entitetsinställningar \> uppdatera entitetslistan.**</span><span class="sxs-lookup"><span data-stu-id="35fb2-224">Refresh the data entities in Finance by going to **Data management \> Framework Parameters \> Entity settings \> Refresh entity list.**</span></span> <span data-ttu-id="35fb2-225">Detta tar några minuter att slutföra och sedan visas mappningarna.</span><span class="sxs-lookup"><span data-stu-id="35fb2-225">This should take a couple of minutes to complete, then you should see those mappings.</span></span> <span data-ttu-id="35fb2-226">Problemet uppstår när nya projekt skapas.</span><span class="sxs-lookup"><span data-stu-id="35fb2-226">This issue occurs when new projects are created.</span></span>

![Saknad fältmappning](media/MissingFieldMapping.png)

## <a name="additional-resources"></a><span data-ttu-id="35fb2-228">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="35fb2-228">Additional resources</span></span>

- <span data-ttu-id="35fb2-229">Dataintegrerare (DI):</span><span class="sxs-lookup"><span data-stu-id="35fb2-229">Data Integrator (DI):</span></span> 

  - [<span data-ttu-id="35fb2-230">Integrera data i Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="35fb2-230">Integrate data into Microsoft Dataverse</span></span>](/powerapps/administrator/data-integrator)

  - [<span data-ttu-id="35fb2-231">dataintegrerare felhantering och felsökning</span><span class="sxs-lookup"><span data-stu-id="35fb2-231">Data Integrator error management and troubleshooting</span></span>](/powerapps/administrator/data-integrator-error-management)

  - [<span data-ttu-id="35fb2-232">Svara på DSR-förfrågningar för systemgenererade loggar i Power Apps, Microsoft Power Automate och Dataverse</span><span class="sxs-lookup"><span data-stu-id="35fb2-232">Responding to DSR requests for system-generated logs in Power Apps, Microsoft Power Automate, and Dataverse</span></span>](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- <span data-ttu-id="35fb2-233">Datahantering</span><span class="sxs-lookup"><span data-stu-id="35fb2-233">Data Management:</span></span>

  - [<span data-ttu-id="35fb2-234">Datahantering</span><span class="sxs-lookup"><span data-stu-id="35fb2-234">Data management</span></span>](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]