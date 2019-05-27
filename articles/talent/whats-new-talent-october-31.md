---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (31 oktober 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6942f8e4dc86f18a081b347df0567b1358a87ab
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519146"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a><span data-ttu-id="96bdc-103">Nyheter och ändringar i Dynamics 365 for Talent Core HR (31 oktober 2018)</span><span class="sxs-lookup"><span data-stu-id="96bdc-103">What's new or changed in Dynamics 365 for Talent Core HR (October 31, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="96bdc-104">**Skapa 8.1.2031**</span><span class="sxs-lookup"><span data-stu-id="96bdc-104">**Build 8.1.2031**</span></span>

<span data-ttu-id="96bdc-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="96bdc-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="create-links-from-talent-to-finance-and-operations"></a><span data-ttu-id="96bdc-106">Skapa länkar från Talent till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="96bdc-106">Create links from Talent to Finance and Operations</span></span>
<span data-ttu-id="96bdc-107">Detta navigeringsfält låter dig koppla från Talent till Finance and Operations vilket ger dig direkt navigering till Finance and Operations-sidor.</span><span class="sxs-lookup"><span data-stu-id="96bdc-107">This new navigation functionality allows you to link from Talent to Finance and Operations, giving you direct navigation into Finance and Operations pages.</span></span> <span data-ttu-id="96bdc-108">När länkar är konfigurerade kan du kan ange namn och grupp för länken där länken ska visas i Talent och målsidan ska öppnas inne i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-108">When links are configured, you can specify the name and group of the link, where the link should surface in Talent, and the target page to be opened within Finance and Operations.</span></span>

#### <a name="coming-soon"></a><span data-ttu-id="96bdc-109">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="96bdc-109">Coming soon</span></span>
<span data-ttu-id="96bdc-110">Fältsammanhang läggs till i framtiden för att tillåta direkt navigering till motsvarande poster i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-110">Field context will be added in the future to allow for direct navigation to corresponding records in Finance and Operations.</span></span> <span data-ttu-id="96bdc-111">Du kan till exempel använda **Länk till fältet** för att ge kontext till att navigera direkt till en viss medarbetare eller position i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-111">For example, you can use **Link to field** to provide the context to navigate directly to a specific employee or position in Finance and Operations.</span></span>

### <a name="configure-target-systems"></a><span data-ttu-id="96bdc-112">Konfigurera målsystem</span><span class="sxs-lookup"><span data-stu-id="96bdc-112">Configure target systems</span></span>

<span data-ttu-id="96bdc-113">I Talent kan systemadministratörer definiera länkar som ska exponeras genom Arbetsyta för systemadministration.</span><span class="sxs-lookup"><span data-stu-id="96bdc-113">In Talent, system administrators can define links that will be surfaced through the System Administration workspace.</span></span> <span data-ttu-id="96bdc-114">En del av konfigurationen är de Finance and Operations-miljöer du vill navigera till som ”mål” för länken.</span><span class="sxs-lookup"><span data-stu-id="96bdc-114">Part of the configuration is the Finance and Operations environments that you would like to navigate to as the "target" of the link.</span></span> <span data-ttu-id="96bdc-115">Du kan göra detta genom att ge målsystemet ett namn och URL-adressen till Finance and Operations-miljön.</span><span class="sxs-lookup"><span data-stu-id="96bdc-115">You do this by giving the target system a name and providing the URL of the Finance and Operations environment.</span></span> <span data-ttu-id="96bdc-116">Här är ett exempel på en Finance and Operations-URL som du skulle tillhandahålla: https://devax00124aos.cloud.test.dynamics.com/.</span><span class="sxs-lookup"><span data-stu-id="96bdc-116">Here is an example of a Finance and Operations URL that you would provide: https://devax00124aos.cloud.test.dynamics.com/.</span></span> <span data-ttu-id="96bdc-117">När du har konfigurerat dina målsystem kan du definiera dina länkar.</span><span class="sxs-lookup"><span data-stu-id="96bdc-117">After you have configured your target systems,  you can define your links.</span></span>

### <a name="configure-links"></a><span data-ttu-id="96bdc-118">Konfigurera länkar</span><span class="sxs-lookup"><span data-stu-id="96bdc-118">Configure links</span></span>

<span data-ttu-id="96bdc-119">Varje länk som skapats måste ha följande information definierad.</span><span class="sxs-lookup"><span data-stu-id="96bdc-119">Each link that is created will have the following information defined.</span></span>

- <span data-ttu-id="96bdc-120">Länk - namnet på den länk som endast används för identifiering.</span><span class="sxs-lookup"><span data-stu-id="96bdc-120">Link - Name of the link, used for identification only.</span></span>

- <span data-ttu-id="96bdc-121">Aktivera den här länken - ställ in på **Ja** om du vill visa länken för användare av Talent.</span><span class="sxs-lookup"><span data-stu-id="96bdc-121">Enable this Link - Set to **Yes** if you want to display the link to users of Talent.</span></span>

- <span data-ttu-id="96bdc-122">Visningsnamn – definiera namnet som ska visas som en länk till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-122">Display name - Define the name that will appear as a link to Finance and Operations.</span></span> <span data-ttu-id="96bdc-123">Informationen har för närvarande inte översatts.</span><span class="sxs-lookup"><span data-stu-id="96bdc-123">This data is currently is not translated.</span></span>

- <span data-ttu-id="96bdc-124">Ytlänk på formulär - Välj vilken sida du vill visa länken på.</span><span class="sxs-lookup"><span data-stu-id="96bdc-124">Surface link on form - Choose which page you would like to display the link on.</span></span>

- <span data-ttu-id="96bdc-125">Grupp - grupper är inte obligatoriska, men om du vill organisera länkarna med hjälp av grupper väljer du en befintlig grupp eller skapar en ny en med hjälp av fältet **grupp**.</span><span class="sxs-lookup"><span data-stu-id="96bdc-125">Group - Groups are not required, but if you want to organize your links using groups, select an existing group or create a new one using the **Group** field.</span></span>

- <span data-ttu-id="96bdc-126">Målsystem - Välj vilket målsystem som skapades med alternativet **konfigurera målsystem**.</span><span class="sxs-lookup"><span data-stu-id="96bdc-126">Target system - Select the target system that was created using the **Configure target system** option.</span></span> <span data-ttu-id="96bdc-127">Detta är Finance and Operations-miljön som kommer att användas vid navigering med hjälp av länken.</span><span class="sxs-lookup"><span data-stu-id="96bdc-127">This will be the Finance and Operations environment that will be used when navigating by using the link.</span></span>

- <span data-ttu-id="96bdc-128">Använd användarens nuvarande företag, välj **Ja** om du vill använda användarens nuvarande företag när du navigerar till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-128">Use user's current Company - Select **Yes** if you would like to use the User's current company context when navigating to Finance and Operations.</span></span> <span data-ttu-id="96bdc-129">Om **Nej** är markerat kan du välja det företag som ska användas.</span><span class="sxs-lookup"><span data-stu-id="96bdc-129">If **No** is selected, then you can select the company that should be used.</span></span>

- <span data-ttu-id="96bdc-130">Målmenyalternativ - ange menyalternativet från Finance and Operation som länken ska användas för att navigera.</span><span class="sxs-lookup"><span data-stu-id="96bdc-130">Target menu item - Enter the menu item from Finance and Operation that the link should use when navigating.</span></span> <span data-ttu-id="96bdc-131">Menyalternativ som du kan navigera direkt till är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="96bdc-131">Menu items that you can directly navigate to are available.</span></span> <span data-ttu-id="96bdc-132">För att hitta det menyalternativ som krävs, öppna Finance and Operations och öppna den sida som är målet för navigeringen.</span><span class="sxs-lookup"><span data-stu-id="96bdc-132">To find the menu item required, open Finance and Operations and open the page that is the target of the navigation.</span></span> <span data-ttu-id="96bdc-133">Kopiera menyalternativet från URL:en.</span><span class="sxs-lookup"><span data-stu-id="96bdc-133">Copy the menu item from the URL.</span></span> <span data-ttu-id="96bdc-134">Om du till exempel vill att länken ska ta dig till medarbetarlistan i Finance and Operations anger du värdet som visas efter den ”&mi” i URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="96bdc-134">For example, if you want the link to take you to the employee list in Finance and Operations, enter the value that appears after the "&mi" in the URL.</span></span> <span data-ttu-id="96bdc-135">https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees.</span><span class="sxs-lookup"><span data-stu-id="96bdc-135">https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees.</span></span> <span data-ttu-id="96bdc-136">Menyalternativet för att navigera till listsidan för medarbetare i det här exemplet är: HcmWorkerListPage_Employees.</span><span class="sxs-lookup"><span data-stu-id="96bdc-136">The menu item to navigate to the employee list page in this example is: HcmWorkerListPage_Employees.</span></span>

- <span data-ttu-id="96bdc-137">Länk till datakälla – Välj den källa för data som länken refererar till.</span><span class="sxs-lookup"><span data-stu-id="96bdc-137">Link to data source - Select the source of data that the link is referencing.</span></span> <span data-ttu-id="96bdc-138">De vanligaste datakällorna såsom **arbetare** och **befattning** är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="96bdc-138">The most common sources like **Worker** and **Position** are available.</span></span>

- <span data-ttu-id="96bdc-139">Länk till fält - (kommer snart) detta fältval tillåter direkt navigering från en enskild post i Talent till en enskild post i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-139">Link to field - (Coming soon) This field selection will allow for direct navigation from a single record in Talent to a single record in Finance and Operations.</span></span>

### <a name="access-to-links"></a><span data-ttu-id="96bdc-140">Tillgång till länkar</span><span class="sxs-lookup"><span data-stu-id="96bdc-140">Access to links</span></span>

<span data-ttu-id="96bdc-141">Systemadministratörer vill se de nyligen skapta länkarna på de definierade sidorna även om alternativet **aktivera den här länken** är inställt på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="96bdc-141">System administrators will see the newly created links on the defined pages even if the **Enable this link** option is set to **No**.</span></span> <span data-ttu-id="96bdc-142">Detta kan användas för att testa länkar innan du visar dem för andra medarbetare.</span><span class="sxs-lookup"><span data-stu-id="96bdc-142">This can be used for testing links prior to surfacing them to other employees.</span></span> <span data-ttu-id="96bdc-143">Andra roller visar endast de konfigurerade länkarna när alternativet **aktivera den här länken** är inställd på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="96bdc-143">All other roles will only see the configured links after the **Enable this link** option is set to **Yes**.</span></span> <span data-ttu-id="96bdc-144">Medarbetare som har åtkomst till de sidor där länkarna exponeras kommer att ha åtkomst till länken.</span><span class="sxs-lookup"><span data-stu-id="96bdc-144">Employees who have access to the pages in which the links are surfaced will have access to the links.</span></span>

<span data-ttu-id="96bdc-145">Användare kan även ha säkerhetsbehörighet inom Finance and Operations definierade för att komma åt sidor i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="96bdc-145">Users can also have security rights within Finance and Operations defined to access the pages in Finance and Operations.</span></span> <span data-ttu-id="96bdc-146">Om inte visas en dialogruta för säkerhet när du använder länken.</span><span class="sxs-lookup"><span data-stu-id="96bdc-146">If they don't, a security dialog box will be displayed when using the link.</span></span>


## <a name="other-changesfixes"></a><span data-ttu-id="96bdc-147">Andra ändringar/korrigeringar</span><span class="sxs-lookup"><span data-stu-id="96bdc-147">Other changes/fixes</span></span>

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a><span data-ttu-id="96bdc-148">Befattningar med ett startdatum i framtiden kan inte tilldelas en nyanställd</span><span class="sxs-lookup"><span data-stu-id="96bdc-148">Positions with a future start date cannot be assigned to a new employee</span></span>

<span data-ttu-id="96bdc-149">Ändringar har gjorts för att tillåta medarbetarnas tilldelningar till framtida befattningar.</span><span class="sxs-lookup"><span data-stu-id="96bdc-149">Changes have been made to allow employee assignments to future-dated positions.</span></span> <span data-ttu-id="96bdc-150">Befattningar vars startdatum i framtiden kan väljas och medarbetares tilldelning görs när arbetsflödet sparas eller slutförs (om arbetsflödet är aktiverat).</span><span class="sxs-lookup"><span data-stu-id="96bdc-150">Positions that have start dates in the future can be selected and the employee assignment will be made upon save or completion of the workflow (if the workflow is enabled).</span></span>

### <a name="new-employee-cannot-be-assigned-existing-position"></a><span data-ttu-id="96bdc-151">Nya medarbetare kan inte tilldelas befintlig befattning</span><span class="sxs-lookup"><span data-stu-id="96bdc-151">New employee cannot be assigned existing position</span></span>

<span data-ttu-id="96bdc-152">Ändringar har gjorts så att nya medarbetares tilldelningen nu kan tilldelas befintliga positioner.</span><span class="sxs-lookup"><span data-stu-id="96bdc-152">Changes have been made so new employee assignment can now be assigned to existing positions.</span></span>

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a><span data-ttu-id="96bdc-153">Datum för tjänsteålder/kontorsadress försvinner när anställningens startdatum redan inträffat och posten sparas</span><span class="sxs-lookup"><span data-stu-id="96bdc-153">Seniority date/Office location disappears when the employment start date is in the past and the record is saved</span></span>

<span data-ttu-id="96bdc-154">Ändringar som har gjorts för att korrigera visningen av **Datum för tjänsteålder** och **Kontorsadress** när du sparar ändringar för tidigare anställda.</span><span class="sxs-lookup"><span data-stu-id="96bdc-154">Changes have been made to correct the visibilty of the **Senority date** and **Office location** when saving changes for past employees.</span></span>

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a><span data-ttu-id="96bdc-155">Det går inte att ange data för framtida anställningar på sidan för medarbetare</span><span class="sxs-lookup"><span data-stu-id="96bdc-155">Can't enter data for future-dated employments on the worker page</span></span>

<span data-ttu-id="96bdc-156">Anställningsuppgifter för framtida anställningar har inaktiverats på huvudsidan för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="96bdc-156">Employment data for future-dated employments has been disabled on the main worker page.</span></span> <span data-ttu-id="96bdc-157">Anställningsuppgifter kan anges via sidorna **Datumhanterare**.</span><span class="sxs-lookup"><span data-stu-id="96bdc-157">Employment data can be entered through the **Date Manager** pages.</span></span> <span data-ttu-id="96bdc-158">Ytterligare ändringar kommer göras i framtida versioner för att tillåta inmatning av anställningsuppgifter direkt under arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="96bdc-158">Additional changes will be made in future releases to enable entering employment data directly during the workflow process.</span></span>

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a><span data-ttu-id="96bdc-159">Lägg till ValidFrom och ValidTo i HcmPersonalContactPersonEntity</span><span class="sxs-lookup"><span data-stu-id="96bdc-159">Add ValidFrom and ValidTo to HcmPersonalContactPersonEntity</span></span>

<span data-ttu-id="96bdc-160">Entiteten Data Management Framework (DMF) HcmPersonalContactPersonEntity har uppdaterats att inkludera datum för ”giltig från” och ”giltig till” för att tillåta vissa scenarier för förmånsintegration.</span><span class="sxs-lookup"><span data-stu-id="96bdc-160">The Data Management Framework (DMF) entity HcmPersonalContactPersonEntity has been updated to include "valid from" and "valid to" dates to enable certain benefit integration scenarios.</span></span> 

## <a name="known-issue"></a><span data-ttu-id="96bdc-161">Kända problem</span><span class="sxs-lookup"><span data-stu-id="96bdc-161">Known issue</span></span>
- <span data-ttu-id="96bdc-162">**Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade.</span><span class="sxs-lookup"><span data-stu-id="96bdc-162">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="96bdc-163">**Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda.</span><span class="sxs-lookup"><span data-stu-id="96bdc-163">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="96bdc-164">Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras.</span><span class="sxs-lookup"><span data-stu-id="96bdc-164">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="96bdc-165">(Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)</span><span class="sxs-lookup"><span data-stu-id="96bdc-165">(This issue will be fixed in the next platform update.)</span></span>
