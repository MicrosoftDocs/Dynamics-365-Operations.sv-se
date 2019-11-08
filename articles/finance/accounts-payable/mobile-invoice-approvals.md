---
title: Mobila fakturagodkännanden
description: Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dd72c8a54498cc6ffae7125c5c2f44bfac5a5995
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658654"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="b444a-103">Mobila fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="b444a-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b444a-104">Med mobila funktioner kan en affärsanvändare skapa mobila funktioner.</span><span class="sxs-lookup"><span data-stu-id="b444a-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="b444a-105">För avancerade scenarier gör plattformen också att utvecklare kan utöka användningsområdena som de önskar.</span><span class="sxs-lookup"><span data-stu-id="b444a-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="b444a-106">Det mest effektiva sättet att lära sig nya koncept på mobilen är att gå igenom processen att skapa några scenarier.</span><span class="sxs-lookup"><span data-stu-id="b444a-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="b444a-107">Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall.</span><span class="sxs-lookup"><span data-stu-id="b444a-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="b444a-108">Det här avsnittet hjälper dig att skapa varianter på scenarier och kan även tillämpas på andra scenarier som inte är relaterade till leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b444a-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="b444a-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b444a-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="b444a-110">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="b444a-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="b444a-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b444a-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b444a-112">Mobil handbok - före läsning</span><span class="sxs-lookup"><span data-stu-id="b444a-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="b444a-113">Mobilplattform</span><span class="sxs-lookup"><span data-stu-id="b444a-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="b444a-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="b444a-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="b444a-115">En miljö som har version 1611 och plattformsuppdatering 3 (november 2016)</span><span class="sxs-lookup"><span data-stu-id="b444a-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="b444a-116">Installera snabbkorrigering KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="b444a-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="b444a-117">Uppgiftsinspelaren kan felaktigt spela in två Stäng-kommandon för listrutans dialogrutor. Detta ingår i plattformsuppdatering 3 (uppdatering november 2016).</span><span class="sxs-lookup"><span data-stu-id="b444a-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="b444a-118">Installera snabbkorrigering KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="b444a-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="b444a-119">Denna snabbkorrigering gör att bifogade filer kan visas på mobila klienten. Detta ingår i plattformsuppdatering 3 (uppdatering november 2016).</span><span class="sxs-lookup"><span data-stu-id="b444a-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="b444a-120">Installera snabbkorrigering KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="b444a-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="b444a-121">Programkoden för godkännandeprogrammet för mobila leverantörsfakturan. Detta ingår i version 7.0.1 (maj 2016).</span><span class="sxs-lookup"><span data-stu-id="b444a-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="b444a-122">En Android-, iOS- eller en Windows-enhet med mobilappen installerad</span><span class="sxs-lookup"><span data-stu-id="b444a-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="b444a-123">Sök efter appen i lämplig appbutik.</span><span class="sxs-lookup"><span data-stu-id="b444a-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="b444a-124">Introduktion</span><span class="sxs-lookup"><span data-stu-id="b444a-124">Introduction</span></span>
<span data-ttu-id="b444a-125">Mobila godkännanden för leverantörsfakturor kräver tre snabbkorrigeringar som nämns i avsnittet "Förutsättningar".</span><span class="sxs-lookup"><span data-stu-id="b444a-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="b444a-126">De här snabbkorrigeringarna innehåller inte en arbetsyta för fakturagodkännande.</span><span class="sxs-lookup"><span data-stu-id="b444a-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="b444a-127">Om du vill ta reda på vad en arbetsyta är i samband med mobil, läs mobila handbok som nämns i avsnittet "Förutsättningar".</span><span class="sxs-lookup"><span data-stu-id="b444a-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="b444a-128">Arbetsytan för fakturagodkännanden måste utformas.</span><span class="sxs-lookup"><span data-stu-id="b444a-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="b444a-129">Alla organisationer orkestrerar och definierar sin affärsprocess för leverantörsfakturor på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="b444a-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="b444a-130">Innan du börjar utforma en mobil upplevelse för godkännande av leverantörsfakturor bör du överväga följande aspekter i affärsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b444a-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="b444a-131">Tanken är att använda dessa datapunkter så mycket som möjligt för att optimera användarupplevelsen på enheten.</span><span class="sxs-lookup"><span data-stu-id="b444a-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="b444a-132">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="b444a-133">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="b444a-134">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="b444a-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="b444a-135">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="b444a-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="b444a-136">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="b444a-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="b444a-137">Om svaret på frågan är Ja, beakta följande:</span><span class="sxs-lookup"><span data-stu-id="b444a-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="b444a-138">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, delningar, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="b444a-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="b444a-139">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="b444a-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="b444a-140">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="b444a-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="b444a-141">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="b444a-142">Det här avsnittet förklarar inte hur du redigerar redovisningsfördelningar, eftersom den här funktionen inte stöds för närvarande för mobila scenarier.</span><span class="sxs-lookup"><span data-stu-id="b444a-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="b444a-143">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="b444a-144">Utformningen av den mobila upplevelsen för fakturagodkännanden varierar beroende på svaren på dessa frågor.</span><span class="sxs-lookup"><span data-stu-id="b444a-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="b444a-145">Målet är att optimera användarupplevelsen för affärsprocessen på mobil i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b444a-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="b444a-146">I resten av det här avsnittet beskrivs två varianter av scenario som baseras på olika svar på föregående frågor.</span><span class="sxs-lookup"><span data-stu-id="b444a-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="b444a-147">Som en allmän vägledning, när du arbetar med mobildesignern, se till att du "publicerar" ändringarna för att inte förlora uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="b444a-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="b444a-148">Utforma ett enkelt scenario för fakturagodkännande för Contoso</span><span class="sxs-lookup"><span data-stu-id="b444a-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b444a-149">Scenarioattribut</span><span class="sxs-lookup"><span data-stu-id="b444a-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="b444a-150">Besvara</span><span class="sxs-lookup"><span data-stu-id="b444a-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b444a-151">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="b444a-152">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="b444a-152">Vendor name</span></span></li>
<li><span data-ttu-id="b444a-153">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="b444a-153">Invoice total</span></span></li>
<li><span data-ttu-id="b444a-154">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="b444a-154">Invoice account</span></span></li>
<li><span data-ttu-id="b444a-155">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="b444a-155">Invoice number</span></span></li>
<li><span data-ttu-id="b444a-156">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="b444a-156">Invoice date</span></span></li>
<li><span data-ttu-id="b444a-157">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="b444a-157">Invoice description</span></span></li>
<li><span data-ttu-id="b444a-158">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="b444a-158">Due date</span></span></li>
<li><span data-ttu-id="b444a-159">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="b444a-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-160">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="b444a-161">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="b444a-161">Procurement category</span></span></li>
<li><span data-ttu-id="b444a-162">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b444a-162">Quantity</span></span></li>
<li><span data-ttu-id="b444a-163">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="b444a-163">Unit price</span></span></li>
<li><span data-ttu-id="b444a-164">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="b444a-164">Line net amount</span></span></li>
<li><span data-ttu-id="b444a-165">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="b444a-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-166">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="b444a-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="b444a-167">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="b444a-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="b444a-168">1</span><span class="sxs-lookup"><span data-stu-id="b444a-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-169">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="b444a-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="b444a-170">Ja</span><span class="sxs-lookup"><span data-stu-id="b444a-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-171">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="b444a-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="b444a-172">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="b444a-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="b444a-173">Slutligt pris: 2 Moms: 0 Avgifter: 0</span><span class="sxs-lookup"><span data-stu-id="b444a-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-174">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="b444a-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="b444a-175">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="b444a-176">Används inte</span><span class="sxs-lookup"><span data-stu-id="b444a-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-177">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="b444a-178">Ja</span><span class="sxs-lookup"><span data-stu-id="b444a-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="b444a-179">Skapa arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-179">Create the workspace</span></span>

1.  <span data-ttu-id="b444a-180">I en webbläsare och logga in på programmet.</span><span class="sxs-lookup"><span data-stu-id="b444a-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="b444a-181">När du har loggat in kan du lägga till **&mode=mobile** till URL:en som visas i följande exempel, och uppdatera sidan: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="b444a-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="b444a-182">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**.</span><span class="sxs-lookup"><span data-stu-id="b444a-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="b444a-183">Mobilapps-designern måste visas precis som Uppgiftsinspelare visas.</span><span class="sxs-lookup"><span data-stu-id="b444a-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="b444a-184">Klicka på **Lägg till** för att skapa en ny arbetsyta.</span><span class="sxs-lookup"><span data-stu-id="b444a-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="b444a-185">Namnet på arbetsytan för det här exemplet anger du som **Mina godkännanden**.</span><span class="sxs-lookup"><span data-stu-id="b444a-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="b444a-186">Ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b444a-186">Enter a description.</span></span>
6.  <span data-ttu-id="b444a-187">Välj en färg på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-187">Select a workspace color.</span></span> <span data-ttu-id="b444a-188">Arbetsytans färg ska användas för övergripande stilen för den mobila upplevelsen för den här arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="b444a-189">Välj en ikon för arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="b444a-190">Klicka på **Klart**</span><span class="sxs-lookup"><span data-stu-id="b444a-190">Click **Done**</span></span>
9.  <span data-ttu-id="b444a-191">Klicka på **Publicera arbetsytan** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="b444a-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="b444a-192">Leverantörsfakturor som har tilldelats mig</span><span class="sxs-lookup"><span data-stu-id="b444a-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="b444a-193">Den första mobilsidan som du bör utforma är en lista med fakturor som har tilldelats till användaren för granskning.</span><span class="sxs-lookup"><span data-stu-id="b444a-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="b444a-194">Använd sidan **VendMobileInvoiceAssignedToMeListPage** när du designar den här mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="b444a-195">Innan du slutför den här proceduren, kontrollera att minst en leverantörsfaktura har tilldelats till dig för granskning, och att fakturaraden har två fördelningar.</span><span class="sxs-lookup"><span data-stu-id="b444a-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="b444a-196">Den här inställningen uppfyller kraven i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="b444a-197">Ersätt menyalternativets namn i URL:en med **VendMobileInvoiceAssignedToMeListPage** för att öppna mobilversionen av listsidan **Pågående leverantörsfakturor som tilldelats mig** i modulen **Leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="b444a-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="b444a-198">Beroende på hur många fakturor som du har i systemet tilldelade till dig, visas dessa fakturor på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="b444a-199">Om du vill hitta en specifik faktura kan du använda filtret till vänster.</span><span class="sxs-lookup"><span data-stu-id="b444a-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="b444a-200">Men i det här exemplet kräver vi inte en viss faktura.</span><span class="sxs-lookup"><span data-stu-id="b444a-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="b444a-201">Vi behöver bara en faktura som tilldelats dig som gör att du kan utforma mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="b444a-202">De nya sidor som är tillgängliga har utformats specifikt för utveckling av mobila scenarier för leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="b444a-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="b444a-203">Därför måste du använda dessa sidor.</span><span class="sxs-lookup"><span data-stu-id="b444a-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="b444a-204">URL:en bör likna följande URL och när du har angett den måste sidan som visas i illustrationen visas: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span><span class="sxs-lookup"><span data-stu-id="b444a-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span></span> 

    <span data-ttu-id="b444a-205">[![Sidan Pågående leverantörsfakturor tilldelade mig](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-205">[![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
    
2.  <span data-ttu-id="b444a-206">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**</span><span class="sxs-lookup"><span data-stu-id="b444a-206">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="b444a-207">Välj din arbetsyta och klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="b444a-207">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="b444a-208">Klicka på **Lägg till sida** för att skapa den första mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-208">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="b444a-209">Ange ett namn, till exempel **Mina leverantörsfakturor**, och en beskrivning, till exempel **Leverantörsfakturor som tilldelats mig för granskning**.</span><span class="sxs-lookup"><span data-stu-id="b444a-209">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="b444a-210">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b444a-210">Click **Done**.</span></span>
7.  <span data-ttu-id="b444a-211">I mobila designern, på fliken **Fält** klickar du på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="b444a-211">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="b444a-212">Kolumnerna på listsidan måste likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="b444a-212">The columns on the list page must resemble the following illustration.</span></span> 

    <span data-ttu-id="b444a-213">[![Kolumner på sidan Väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-213">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
    
8.  <span data-ttu-id="b444a-214">Lägg till de kolumner som krävs från listsidan som måste visas för användare på mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-214">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="b444a-215">Den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="b444a-215">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="b444a-216">Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen.</span><span class="sxs-lookup"><span data-stu-id="b444a-216">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="b444a-217">Utifrån kraven i det här scenariot krävs följande åtta fält.</span><span class="sxs-lookup"><span data-stu-id="b444a-217">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="b444a-218">Men vissa användare kanske anser att åtta fält är för mycket information på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="b444a-218">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="b444a-219">Därför visar vi bara de viktigaste fälten i vyn med mobillistan.</span><span class="sxs-lookup"><span data-stu-id="b444a-219">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="b444a-220">De återstående fälten visas i detaljvyn som vi utformar senare.</span><span class="sxs-lookup"><span data-stu-id="b444a-220">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="b444a-221">Nu lägger vi till följande fält.</span><span class="sxs-lookup"><span data-stu-id="b444a-221">For now, we will add the following fields.</span></span> <span data-ttu-id="b444a-222">Klicka på plustecknet (**+**) i dessa kolumner för att lägga till på mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-222">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="b444a-223">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="b444a-223">Vendor name</span></span>
    - <span data-ttu-id="b444a-224">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="b444a-224">Invoice total</span></span>
    - <span data-ttu-id="b444a-225">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="b444a-225">Invoice account</span></span>
    - <span data-ttu-id="b444a-226">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="b444a-226">Invoice number</span></span>
    - <span data-ttu-id="b444a-227">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="b444a-227">Invoice date</span></span>

  <span data-ttu-id="b444a-228">När fält läggs till måste mobilsidan likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="b444a-228">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    
   <span data-ttu-id="b444a-229">[![Sidan när fält har lagts till](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-229">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>

9.  <span data-ttu-id="b444a-230">Du måste även lägga till följande kolumner nu, så att vi kan aktivera arbetsflödesåtgärder senare.</span><span class="sxs-lookup"><span data-stu-id="b444a-230">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="b444a-231">Visa Slutför uppgift</span><span class="sxs-lookup"><span data-stu-id="b444a-231">Show complete task</span></span>
    - <span data-ttu-id="b444a-232">Visa Delegera uppgift</span><span class="sxs-lookup"><span data-stu-id="b444a-232">Show delegate task</span></span>
    - <span data-ttu-id="b444a-233">Visa Återkalla uppgift</span><span class="sxs-lookup"><span data-stu-id="b444a-233">Show recall task</span></span>
    - <span data-ttu-id="b444a-234">Visa Avvisa uppgift</span><span class="sxs-lookup"><span data-stu-id="b444a-234">Show reject task</span></span>
    - <span data-ttu-id="b444a-235">Visa Begär slutförandeuppgift</span><span class="sxs-lookup"><span data-stu-id="b444a-235">Show request completion task</span></span>
    - <span data-ttu-id="b444a-236">Visa Skicka uppgift igen</span><span class="sxs-lookup"><span data-stu-id="b444a-236">Show resubmit task</span></span>

10. <span data-ttu-id="b444a-237">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-237">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="b444a-238">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-238">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="b444a-239">Klicka på **Publicera arbetsytan** för att spara ditt arbete.</span><span class="sxs-lookup"><span data-stu-id="b444a-239">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="b444a-240">Aktivera **Visa fakturasumma i listan med pågående leverantörsfakturor** i parameterformuläret för leverantörsreskontra under **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="b444a-240">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="b444a-241">Observera att endast genom att aktivera den här parametern beräknas fakturasummor som ska visas på listsidan för pågående leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b444a-241">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="b444a-242">Detta är en ny funktion som en del av förutsättningen snabbkorrigering 3208224.</span><span class="sxs-lookup"><span data-stu-id="b444a-242">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="b444a-243">Detaljer om leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="b444a-243">Vendor invoice details</span></span>

<span data-ttu-id="b444a-244">Använd sidan **VendMobileInvoiceHeaderDetails** när du designar sidan med fakturadetaljer för mobil.</span><span class="sxs-lookup"><span data-stu-id="b444a-244">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="b444a-245">Observera att beroende på antalet fakturor som du har i systemet visar den här sidan den äldsta fakturan (faktura som först skapades).</span><span class="sxs-lookup"><span data-stu-id="b444a-245">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="b444a-246">Om du vill hitta en specifik faktura kan du använda filtret till vänster.</span><span class="sxs-lookup"><span data-stu-id="b444a-246">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="b444a-247">Men i det här exemplet kräver vi inte en viss faktura.</span><span class="sxs-lookup"><span data-stu-id="b444a-247">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="b444a-248">Vi behöver bara vissa fakturadata så att vi kan utforma mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-248">We just require some invoice data so that we can design the mobile page.</span></span> 

<span data-ttu-id="b444a-249">[![Sida för arbetsflöde](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-249">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="b444a-250">I URL:en ersätter du namnet på menyalternativet med **VendMobileInvoiceHeaderDetails** för att öppna formuläret</span><span class="sxs-lookup"><span data-stu-id="b444a-250">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>

2. <span data-ttu-id="b444a-251">Öppna mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="b444a-251">Open the mobile designer from the **Settings** (gear) button.</span></span>

3. <span data-ttu-id="b444a-252">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-252">Click the **Edit** button to start edit mode in the workspace.</span></span>

4. <span data-ttu-id="b444a-253">Välj sidan **Mina leverantörsfakturor** som du skapade tidigare och klicka sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b444a-253">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>

5. <span data-ttu-id="b444a-254">På fliken **Fält** klickar du på kolumnrubriken **Rutnät**.</span><span class="sxs-lookup"><span data-stu-id="b444a-254">On the **Fields** tab, click the **Grid** column heading.</span></span>

6. <span data-ttu-id="b444a-255">Klicka på **Egenskaper &gt;Lägg till sida**.</span><span class="sxs-lookup"><span data-stu-id="b444a-255">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="b444a-256">**Anmärkning:** När du klickar på rubriken **Rutnät** och lägger till en sida, etableras relationen med detaljsidan automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b444a-256">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>

7. <span data-ttu-id="b444a-257">Ange en sidrubrik, till exempel **Fakturadetaljer**, och en beskrivning, till exempel **Visa fakturahuvud och raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="b444a-257">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>

8. <span data-ttu-id="b444a-258">Klicka på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="b444a-258">Click **Select fields**.</span></span> <span data-ttu-id="b444a-259">Observera att den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="b444a-259">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="b444a-260">Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen.</span><span class="sxs-lookup"><span data-stu-id="b444a-260">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 

9. <span data-ttu-id="b444a-261">Lägg till följande fält från huvudet, baserat på förutsättningarna för det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="b444a-261">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="b444a-262">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="b444a-262">Vendor name</span></span>
   - <span data-ttu-id="b444a-263">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="b444a-263">Invoice total</span></span>
   - <span data-ttu-id="b444a-264">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="b444a-264">Invoice account</span></span>
   - <span data-ttu-id="b444a-265">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="b444a-265">Invoice number</span></span>
   - <span data-ttu-id="b444a-266">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="b444a-266">Invoice date</span></span>
   - <span data-ttu-id="b444a-267">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="b444a-267">Invoice description</span></span>
   - <span data-ttu-id="b444a-268">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="b444a-268">Due date</span></span>
   - <span data-ttu-id="b444a-269">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="b444a-269">Invoice currency</span></span>

10. <span data-ttu-id="b444a-270">Lägg till följande fält från radrutnätet på sidan:</span><span class="sxs-lookup"><span data-stu-id="b444a-270">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="b444a-271">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="b444a-271">Procurement category</span></span>
    - <span data-ttu-id="b444a-272">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b444a-272">Quantity</span></span>
    - <span data-ttu-id="b444a-273">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="b444a-273">Unit price</span></span>
    - <span data-ttu-id="b444a-274">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="b444a-274">Line net amount</span></span>
    - <span data-ttu-id="b444a-275">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="b444a-275">1099 amount</span></span>

11. <span data-ttu-id="b444a-276">När alla fält från de två föregående stegen har lagts till, klickar du på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b444a-276">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="b444a-277">Sidan måste likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="b444a-277">The page must resemble the following illustration.</span></span>
    
    <span data-ttu-id="b444a-278">[![Sidan när fält har lagts till](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-278">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>

12. <span data-ttu-id="b444a-279">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-279">Click **Done** to exit edit mode.</span></span>

13. <span data-ttu-id="b444a-280">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-280">Click **Back** and then **Done** to exit the workspace</span></span>

14. <span data-ttu-id="b444a-281">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-281">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="b444a-282">Arbetsflödesåtgärder</span><span class="sxs-lookup"><span data-stu-id="b444a-282">Workflow actions</span></span>

<span data-ttu-id="b444a-283">För att lägga till arbetsflödesåtgärder, använd sidan **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="b444a-283">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="b444a-284">Ersätt namnet på menyalternativet i URL-adressen precis som tidigare om du vill öppna sidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-284">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="b444a-285">Öppna sedan mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="b444a-285">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="b444a-286">Så här lägger du till arbetsflödesåtgärder på sidan med detaljer.</span><span class="sxs-lookup"><span data-stu-id="b444a-286">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="b444a-287">För att de arbetsflödesåtgärder som du tänker utforma för tillgängliga för dig, måste dina tilldelade fakturor ha lämplig status.</span><span class="sxs-lookup"><span data-stu-id="b444a-287">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="b444a-288">Registrera arbetsflödesåtgärder</span><span class="sxs-lookup"><span data-stu-id="b444a-288">Record workflow actions</span></span>
1.  <span data-ttu-id="b444a-289">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-289">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="b444a-290">Välj sidan **Fakturadetaljer** som du skapade tidigare och klicka sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b444a-290">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="b444a-291">Klicka på **Lägg till åtgärd** på fliken **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="b444a-291">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="b444a-292">Ange en rubrik för åtgärden, till exempel **Godkänn**, och en beskrivning, till exempel **Godkänn fakturan**.</span><span class="sxs-lookup"><span data-stu-id="b444a-292">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="b444a-293">Observera att rubriken för åtgärden som du anger här blir namnet på åtgärden som visas för användaren i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="b444a-293">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="b444a-294">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b444a-294">Click **Done**.</span></span>
6.  <span data-ttu-id="b444a-295">Klicka på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="b444a-295">Click **Select fields**.</span></span>
7.  <span data-ttu-id="b444a-296">Gå igenom arbetsflödesprocessen på sidan **VendMobileInvoiceHeaderDetails** sidan och slutför åtgärden som du vill registrera.</span><span class="sxs-lookup"><span data-stu-id="b444a-296">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="b444a-297">Kontrollera att du skriver kommentarer för arbetsflöde under den här processen så att ett kommentarsfält ingår också i mobila upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="b444a-297">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="b444a-298">När arbetsflödesåtgärden körs, klickar du på **Klart** för att slutföra uppgiften Välj fält.</span><span class="sxs-lookup"><span data-stu-id="b444a-298">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="b444a-299">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-299">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="b444a-300">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-300">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="b444a-301">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-301">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="b444a-302">Upprepa föregående steg för att registrera alla obligatoriska arbetsflödesåtgärder.</span><span class="sxs-lookup"><span data-stu-id="b444a-302">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="b444a-303">Skapa en .js-fil</span><span class="sxs-lookup"><span data-stu-id="b444a-303">Create a .js file</span></span>
1. <span data-ttu-id="b444a-304">Öppna Anteckningar eller Microsoft Visual Studio och klistra in följande kod.</span><span class="sxs-lookup"><span data-stu-id="b444a-304">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="b444a-305">Spara filen som en JS-fil.</span><span class="sxs-lookup"><span data-stu-id="b444a-305">Save the file as a .js file.</span></span> <span data-ttu-id="b444a-306">Koden utför följande:</span><span class="sxs-lookup"><span data-stu-id="b444a-306">This code does the following:</span></span>
    - <span data-ttu-id="b444a-307">Den döljer de extra arbetsflödesrelaterade kolumner som vi har lade till tidigare på mobillistsidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-307">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="b444a-308">Vi har lagt till kolumnerna så att appen har informationen i sammanhang och kan utföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="b444a-308">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="b444a-309">Utifrån vilket arbetsflödessteg som är aktivt, använder den logik för att visa enbart de åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="b444a-309">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="b444a-310">Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-310">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  <span data-ttu-id="b444a-311">Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik**</span><span class="sxs-lookup"><span data-stu-id="b444a-311">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="b444a-312">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-312">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="b444a-313">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-313">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="b444a-314">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-314">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="b444a-315">Leverantörsfakturabilagor</span><span class="sxs-lookup"><span data-stu-id="b444a-315">Vendor invoice attachments</span></span>

1. <span data-ttu-id="b444a-316">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**</span><span class="sxs-lookup"><span data-stu-id="b444a-316">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>

2. <span data-ttu-id="b444a-317">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-317">Click the **Edit** button to start edit mode in the workspace.</span></span>

3. <span data-ttu-id="b444a-318">Välj sidan <strong>Fakturadetaljer\*\* som du skapade tidigare och klicka sedan på \*\*Redigera</strong>.</span><span class="sxs-lookup"><span data-stu-id="b444a-318">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>

4. <span data-ttu-id="b444a-319">Ange alternativet **Dokumenthantering** till **Ja** enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="b444a-319">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="b444a-320">**Anmärkning:** Om det inte finns några inga krav på att visa bifogade filer på den mobila enheten kan du lämna detta alternativ inställt på **Nej**, vilket är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="b444a-320">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   
   ![Dokumenthantering](./media/docmanagement-216x300.png)

5. <span data-ttu-id="b444a-322">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-322">Click **Done** to exit edit mode.</span></span>

6. <span data-ttu-id="b444a-323">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-323">Click **Back** and then **Done** to exit the workspace</span></span>

7. <span data-ttu-id="b444a-324">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-324">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="b444a-325">Fördelningar av leverantörsfakturarader</span><span class="sxs-lookup"><span data-stu-id="b444a-325">Vendor invoice line distributions</span></span>

<span data-ttu-id="b444a-326">Kraven i det här scenariot bekräftar att endast det endast ska finnas fördelningar på radnivå, och att en faktura alltid bara har en rad.</span><span class="sxs-lookup"><span data-stu-id="b444a-326">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="b444a-327">Eftersom detta scenario är enkelt, måste användargränssnitt på den mobila enheten vara så enkelt att användaren inte behöver gå ned flera nivåer för att visa fördelningarna.</span><span class="sxs-lookup"><span data-stu-id="b444a-327">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="b444a-328">Leverantörsfakturor innehåller alternativet att visa alla fördelningar från fakturahuvudet.</span><span class="sxs-lookup"><span data-stu-id="b444a-328">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="b444a-329">Denna upplevelse är det vi behöver för det mobila scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-329">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="b444a-330">Därför använder vi sidan **VendMobileInvoiceAllDistributionTree** för att utforma den här delen av det mobila scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-330">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b444a-331">Att känna till kraven hjälper oss att avgöra vilken sida som ska användas och hur exakt mobila upplevelsen ska optimeras för användaren när vi utformar scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-331">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="b444a-332">I det andra scenariot utnyttjas en annan sida för att visa fördelningar, eftersom kraven är olika krav för det scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-332">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="b444a-333">Ersätt namnet på menyalternativet i URL-adressen precis som du gjorde tidigare.</span><span class="sxs-lookup"><span data-stu-id="b444a-333">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="b444a-334">Sidan som visas bör likna illustrationen.</span><span class="sxs-lookup"><span data-stu-id="b444a-334">The page that appears should resemble the following illustration.</span></span>

<span data-ttu-id="b444a-335">[![Sida med alla distributioner](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="b444a-335">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>

2.  <span data-ttu-id="b444a-336">Öppna mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="b444a-336">Open the mobile designer from the **Settings** (gear) button.</span></span>

3.  <span data-ttu-id="b444a-337">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-337">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="b444a-338">**Anmärkning:** Du ser att två nya sidor har skapats automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b444a-338">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="b444a-339">Dessa sidor skapas i systemet eftersom du aktiverade dokumenthantering i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b444a-339">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="b444a-340">Du kan ignorera dessa nya sidor.</span><span class="sxs-lookup"><span data-stu-id="b444a-340">You can ignore these new pages.</span></span>

4.  <span data-ttu-id="b444a-341">Klicka på **Lägg till sida**.</span><span class="sxs-lookup"><span data-stu-id="b444a-341">Click **Add page**.</span></span>

5.  <span data-ttu-id="b444a-342">Ange en sidrubrik som **Visa redovisning**, och en beskrivning, t.ex **Visa redovisning för fakturan**.</span><span class="sxs-lookup"><span data-stu-id="b444a-342">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>

6.  <span data-ttu-id="b444a-343">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b444a-343">Click **Done**.</span></span>

7.  <span data-ttu-id="b444a-344">På fliken **Fält** klickar du på **Välj fält**. Välj följande fält från fördelningssidan och klicka sedan på **Klart**:</span><span class="sxs-lookup"><span data-stu-id="b444a-344">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="b444a-345">Belopp</span><span class="sxs-lookup"><span data-stu-id="b444a-345">Amount</span></span>
    2.  <span data-ttu-id="b444a-346">Valuta</span><span class="sxs-lookup"><span data-stu-id="b444a-346">Currency</span></span>
    3.  <span data-ttu-id="b444a-347">Huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="b444a-347">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="b444a-348">Vi valde inte kolumnen **Beskrivning** i rutnätet för fördelningar, eftersom kraven i det här scenariot har bekräftat att det utökade priset är de enda belopp som det finns fördelningar för.</span><span class="sxs-lookup"><span data-stu-id="b444a-348">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="b444a-349">Därför behöver användaren inte något ytterligare fält för att fastställa beloppstypen som fördelningen gäller.</span><span class="sxs-lookup"><span data-stu-id="b444a-349">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="b444a-350">Men i nästa scenario **ska** vi använda den här informationen, kraven för det scenariot anger att andra beloppstyper har fördelningar (till exempel moms).</span><span class="sxs-lookup"><span data-stu-id="b444a-350">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>

8.  <span data-ttu-id="b444a-351">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-351">Click **Done** to exit edit mode.</span></span>

9.  <span data-ttu-id="b444a-352">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-352">Click **Back** and then **Done** to exit the workspace</span></span>

10. <span data-ttu-id="b444a-353">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-353">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="b444a-354">Mobilsidan **Visa redovisning** är för tillfället inte kopplad till någon av de mobilsidor som vi har utformat hittills.</span><span class="sxs-lookup"><span data-stu-id="b444a-354">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="b444a-355">Eftersom användaren ska kunna navigera till sidan **Visa redovisning** sidan från sidan **Fakturadetaljer** på den mobila enheten måste vi tillhandahålla navigering från sidan **Fakturadetaljer** till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="b444a-355">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="b444a-356">Vi fastställer den här navigeringen med hjälp av ytterligare logik via JavaScript.</span><span class="sxs-lookup"><span data-stu-id="b444a-356">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="b444a-357">Öppna den JS-fil som du skapade tidigare och lägg till de rader som markerats i koden nedan.</span><span class="sxs-lookup"><span data-stu-id="b444a-357">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="b444a-358">Den här koden gör två saker:</span><span class="sxs-lookup"><span data-stu-id="b444a-358">This code does two things:</span></span>
    1.  <span data-ttu-id="b444a-359">Det hjälper till att garantera att användaren inte kan bläddra direkt från arbetsytan till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="b444a-359">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="b444a-360">Den etablerar en navigeringskontroll från sidan **Fakturadetaljer** till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="b444a-360">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="b444a-361">Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="b444a-361">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  <span data-ttu-id="b444a-362">Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik** för att skriva över föregående kod</span><span class="sxs-lookup"><span data-stu-id="b444a-362">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="b444a-363">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="b444a-363">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="b444a-364">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="b444a-364">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="b444a-365">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="b444a-365">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="b444a-366">Validering</span><span class="sxs-lookup"><span data-stu-id="b444a-366">Validation</span></span>

<span data-ttu-id="b444a-367">Öppna appen från din mobila enhet och anslut till din instans.</span><span class="sxs-lookup"><span data-stu-id="b444a-367">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="b444a-368">Kontrollera att du loggar in till företaget där leverantörsfakturor har tilldelats dig för granskning.</span><span class="sxs-lookup"><span data-stu-id="b444a-368">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="b444a-369">Du ska kunna utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="b444a-369">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="b444a-370">Se arbetsytan **Mina godkännanden**.</span><span class="sxs-lookup"><span data-stu-id="b444a-370">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="b444a-371">Gå nedåt i arbetsytan **Mina godkännanden** och se sidan **Mina leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="b444a-371">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="b444a-372">Gå nedåt i sidan **Mina leverantörsfakturor** och se en lista med fakturor som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="b444a-372">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="b444a-373">Gå till en av fakturorna och visa huvud- och raddetaljer för fakturan.</span><span class="sxs-lookup"><span data-stu-id="b444a-373">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="b444a-374">På informationssidan visas en länk till bilagor. Använd den här länken för att navigera till listan med bifogade filer och visa de bifogade filerna.</span><span class="sxs-lookup"><span data-stu-id="b444a-374">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="b444a-375">På informationssidan visas en länk till sidan **Visa redovisning**. Använd den här länken för att navigera till fördelningssidan och visa fördelningarna.</span><span class="sxs-lookup"><span data-stu-id="b444a-375">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="b444a-376">På detaljsidan, klicka på menyn **Åtgärder** längst ned och utför arbetsflödesåtgärder som gäller för arbetsflödessteget.</span><span class="sxs-lookup"><span data-stu-id="b444a-376">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="b444a-377">Utforma ett komplext scenario för fakturagodkännande för Fabrikam</span><span class="sxs-lookup"><span data-stu-id="b444a-377">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b444a-378">Scenarioattribut</span><span class="sxs-lookup"><span data-stu-id="b444a-378">Scenario attribute</span></span></th>
<th><span data-ttu-id="b444a-379">Besvara</span><span class="sxs-lookup"><span data-stu-id="b444a-379">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b444a-380">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-380">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="b444a-381">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="b444a-381">Vendor name</span></span></li>
<li><span data-ttu-id="b444a-382">Fakturabelopp</span><span class="sxs-lookup"><span data-stu-id="b444a-382">Invoice amount</span></span></li>
<li><span data-ttu-id="b444a-383">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="b444a-383">Invoice account</span></span></li>
<li><span data-ttu-id="b444a-384">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="b444a-384">Invoice number</span></span></li>
<li><span data-ttu-id="b444a-385">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="b444a-385">Invoice date</span></span></li>
<li><span data-ttu-id="b444a-386">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="b444a-386">Invoice description</span></span></li>
<li><span data-ttu-id="b444a-387">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="b444a-387">Due date</span></span></li>
<li><span data-ttu-id="b444a-388">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="b444a-388">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-389">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="b444a-389">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="b444a-390">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="b444a-390">Procurement category</span></span></li>
<li><span data-ttu-id="b444a-391">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b444a-391">Quantity</span></span></li>
<li><span data-ttu-id="b444a-392">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="b444a-392">Unit price</span></span></li>
<li><span data-ttu-id="b444a-393">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="b444a-393">Line net amount</span></span></li>
<li><span data-ttu-id="b444a-394">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="b444a-394">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-395">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="b444a-395">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="b444a-396">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="b444a-396">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="b444a-397">5</span><span class="sxs-lookup"><span data-stu-id="b444a-397">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-398">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="b444a-398">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="b444a-399">Ja</span><span class="sxs-lookup"><span data-stu-id="b444a-399">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-400">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="b444a-400">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="b444a-401">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="b444a-401">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="b444a-402">Slutligt pris: 2 Moms: 2 Avgifter: 2</span><span class="sxs-lookup"><span data-stu-id="b444a-402">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b444a-403">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="b444a-403">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="b444a-404">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-404">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="b444a-405">Används inte</span><span class="sxs-lookup"><span data-stu-id="b444a-405">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b444a-406">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="b444a-406">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="b444a-407">Ja</span><span class="sxs-lookup"><span data-stu-id="b444a-407">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="b444a-408">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b444a-408">Next steps</span></span>

<span data-ttu-id="b444a-409">Följande ändringar kan göras för scenario 1, baserat på kraven för scenario 2.</span><span class="sxs-lookup"><span data-stu-id="b444a-409">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="b444a-410">Du kan använda det här avsnittet för att förbättra upplevelsen av mobilappen.</span><span class="sxs-lookup"><span data-stu-id="b444a-410">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="b444a-411">Eftersom flera fakturarader förväntas i scenario 2, hjälper följande ändringar i designen till att optimera användarupplevelsen på den mobila enheten:</span><span class="sxs-lookup"><span data-stu-id="b444a-411">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="b444a-412">I stället för att visa fakturarader på detaljsidan (som i scenario 1) kan användare välja att visa rader på en separat mobilsida.</span><span class="sxs-lookup"><span data-stu-id="b444a-412">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="b444a-413">Eftersom flera fakturarader förväntas i det här scenariot, och om sidan **VendMobileInvoiceAllDistributionTree** används för att utforma fördelningssidan för mobil (liksom i scenario 1), kan det vara förvirrande för användaren att korrelera rader till fördelningar.</span><span class="sxs-lookup"><span data-stu-id="b444a-413">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="b444a-414">Använd därför sidan **VendMobileInvoiceLineDistributionTree** sidan för att utforma fördelningssidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-414">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="b444a-415">Vi rekommenderar att fördelningarna visas i samband med en fakturarad i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="b444a-415">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="b444a-416">Kontrollera därför att användaren kan gå nedåt i en rad för att visa fördelningssidan.</span><span class="sxs-lookup"><span data-stu-id="b444a-416">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="b444a-417">Använd sidans länkfunktion för att upprätta detaljgranskningen, precis som du gjorde för huvud- och detaljsidorna i scenario 1.</span><span class="sxs-lookup"><span data-stu-id="b444a-417">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="b444a-418">Eftersom flera beloppstyper förväntas för fördelningar i scenario 2 (moms, tillägg och så vidare), kan det vara praktiskt att visa beskrivningen av beloppstypen.</span><span class="sxs-lookup"><span data-stu-id="b444a-418">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="b444a-419">(Vi uteslöt den här informationen i scenario 1.)</span><span class="sxs-lookup"><span data-stu-id="b444a-419">(We omitted this information in scenario 1.)</span></span>




