---
title: "Mobila fakturagodkännanden"
description: "Det här avsnittet är avsett att beskriva hur du på ett praktiskt sätt skapar mobila scenarier i Dynamics 365 for Finance and Operations genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fc1483285d6ec675637c013af4949b9c7acf92b3
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="mobile-invoice-approvals"></a><span data-ttu-id="8aa3d-103">Mobila fakturagodkännanden</span><span class="sxs-lookup"><span data-stu-id="8aa3d-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8aa3d-104">Med mobila funktioner i Microsoft Dynamics 365 for Finance and Operations kan en affärsanvändare skapa mobila upplevelser.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-104">Mobile capabilities in Microsoft Dynamics 365 for Finance and Operations let a business user design mobile experiences.</span></span> <span data-ttu-id="8aa3d-105">För avancerade scenarier gör plattformen också att utvecklare kan utöka användningsområdena som de önskar.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="8aa3d-106">Det mest effektiva sättet att lära sig nya koncept på mobilen är att gå igenom processen att skapa några scenarier.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="8aa3d-107">Det här avsnittet är avsett att ge en praktisk metod för att skapa mobila scenarier genom att ta leverantörsfakturagodkännanden för mobila enheter som ett användningsfall.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="8aa3d-108">Det här avsnittet hjälper dig att skapa varianter på scenarier och kan även tillämpas på andra scenarier som inte är relaterade till leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="8aa3d-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8aa3d-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="8aa3d-110">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="8aa3d-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8aa3d-112">Mobil handbok - före läsning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="8aa3d-113">Mobil plattform</span><span class="sxs-lookup"><span data-stu-id="8aa3d-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="8aa3d-114">Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8aa3d-114">Dynamics 365 for Finance and Operations</span></span>                                                                             | <span data-ttu-id="8aa3d-115">En miljö med Microsoft Dynamics 365 for Operations version 1611 och plattformsuppdatering 3 för Microsoft Dynamics for Operations (november 2016)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-115">An environment that has Microsoft Dynamics 365 for Operations version 1611 and Microsoft Dynamics for Operations platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="8aa3d-116">Installera snabbkorrigering KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="8aa3d-117">Uppgiftsinspelaren kan felaktigt spela in två Stäng-kommandon för listrutans dialogrutor. Detta ingår i Dynamics 365 for Operation-plattformsuppdatering 3 (uppdatering november 2016)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-117">Task recorder can erroneously record two Close commands for dropdown dialogs this is included in Dynamics 365 for Operation platform update 3 (November 2016 update)</span></span> |
| <span data-ttu-id="8aa3d-118">Installera snabbkorrigering KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="8aa3d-119">Denna snabbkorrigering gör att bifogade filer kan visas på mobila klienten. Detta ingår i Dynamics 365 for Operation-plattformsuppdatering 3 (uppdatering november 2016).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-119">This hotfix enables attachments to be viewed on the mobile client this is included in Dynamics 365 for Operation platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="8aa3d-120">Installera snabbkorrigering KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="8aa3d-121">Programkoden för godkännandeprogrammet för mobila leverantörsfakturan. Detta ingår i Microsoft Dynamics AX-programmet 7.0.1 (maj 2016).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-121">Application code for the mobile vendor invoice approval application this is included in Microsoft Dynamics AX application 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="8aa3d-122">En Android-, iOS- eller en Windows-enhet med mobilappen installerad för Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8aa3d-122">An Android or iOS or a Windows device that has the mobile app installed for Finance and Operations</span></span> | <span data-ttu-id="8aa3d-123">Sök efter appen i lämplig appbutik.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="8aa3d-124">Introduktion</span><span class="sxs-lookup"><span data-stu-id="8aa3d-124">Introduction</span></span>
<span data-ttu-id="8aa3d-125">Mobila godkännanden för leverantörsfakturor kräver tre snabbkorrigeringar som nämns i avsnittet "Förutsättningar".</span><span class="sxs-lookup"><span data-stu-id="8aa3d-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="8aa3d-126">De här snabbkorrigeringarna innehåller inte en arbetsyta för fakturagodkännande.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="8aa3d-127">Om du vill ta reda på vad en arbetsyta är i samband med mobil, läs mobila handbok som nämns i avsnittet "Förutsättningar".</span><span class="sxs-lookup"><span data-stu-id="8aa3d-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="8aa3d-128">Arbetsytan för fakturagodkännanden måste utformas.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="8aa3d-129">Alla organisationer orkestrerar och definierar sin affärsprocess för leverantörsfakturor på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="8aa3d-130">Innan du börjar utforma en mobil upplevelse för godkännande av leverantörsfakturor bör du överväga följande aspekter i affärsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="8aa3d-131">Tanken är att använda dessa datapunkter så mycket som möjligt för att optimera användarupplevelsen på enheten.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="8aa3d-132">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="8aa3d-133">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="8aa3d-134">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="8aa3d-135">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="8aa3d-136">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="8aa3d-137">Om svaret på frågan är Ja, beakta följande:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="8aa3d-138">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, delningar, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="8aa3d-139">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="8aa3d-140">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="8aa3d-141">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="8aa3d-142">Det här avsnittet förklarar inte hur du redigerar redovisningsfördelningar, eftersom den här funktionen inte stöds för närvarande för mobila scenarier.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="8aa3d-143">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="8aa3d-144">Utformningen av den mobila upplevelsen för fakturagodkännanden varierar beroende på svaren på dessa frågor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="8aa3d-145">Målet är att optimera användarupplevelsen för affärsprocessen på mobil i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="8aa3d-146">I resten av det här avsnittet beskrivs två varianter av scenario som baseras på olika svar på föregående frågor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="8aa3d-147">Som en allmän vägledning, när du arbetar med mobildesignern, se till att du "publicerar" ändringarna för att inte förlora uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="8aa3d-148">Utforma ett enkelt scenario för fakturagodkännande för Contoso</span><span class="sxs-lookup"><span data-stu-id="8aa3d-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa3d-149">Scenarioattribut</span><span class="sxs-lookup"><span data-stu-id="8aa3d-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="8aa3d-150">Besvara</span><span class="sxs-lookup"><span data-stu-id="8aa3d-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8aa3d-151">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="8aa3d-152">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="8aa3d-152">Vendor name</span></span></li>
<li><span data-ttu-id="8aa3d-153">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="8aa3d-153">Invoice total</span></span></li>
<li><span data-ttu-id="8aa3d-154">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="8aa3d-154">Invoice account</span></span></li>
<li><span data-ttu-id="8aa3d-155">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="8aa3d-155">Invoice number</span></span></li>
<li><span data-ttu-id="8aa3d-156">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-156">Invoice date</span></span></li>
<li><span data-ttu-id="8aa3d-157">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-157">Invoice description</span></span></li>
<li><span data-ttu-id="8aa3d-158">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-158">Due date</span></span></li>
<li><span data-ttu-id="8aa3d-159">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="8aa3d-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-160">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="8aa3d-161">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="8aa3d-161">Procurement category</span></span></li>
<li><span data-ttu-id="8aa3d-162">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-162">Quantity</span></span></li>
<li><span data-ttu-id="8aa3d-163">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-163">Unit price</span></span></li>
<li><span data-ttu-id="8aa3d-164">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="8aa3d-164">Line net amount</span></span></li>
<li><span data-ttu-id="8aa3d-165">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="8aa3d-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-166">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="8aa3d-167">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="8aa3d-168">1</span><span class="sxs-lookup"><span data-stu-id="8aa3d-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-169">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="8aa3d-170">Ja</span><span class="sxs-lookup"><span data-stu-id="8aa3d-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-171">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="8aa3d-172">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="8aa3d-173">Slutligt pris: 2 Moms: 0 Avgifter: 0</span><span class="sxs-lookup"><span data-stu-id="8aa3d-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-174">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="8aa3d-175">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="8aa3d-176">Används inte</span><span class="sxs-lookup"><span data-stu-id="8aa3d-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-177">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="8aa3d-178">Ja</span><span class="sxs-lookup"><span data-stu-id="8aa3d-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="8aa3d-179">Skapa arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-179">Create the workspace</span></span>

1.  <span data-ttu-id="8aa3d-180">Öppna Finance and Operations och logga in i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-180">In a browser, open Finance and Operations, and sign in.</span></span>
2.  <span data-ttu-id="8aa3d-181">När du har loggat in kan du lägga till **&mode=mobile** till URL:en som visas i följande exempel, och uppdatera sidan: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="8aa3d-182">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="8aa3d-183">Mobilapps-designern måste visas precis som Uppgiftsinspelare visas.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="8aa3d-184">Klicka på **Lägg till** för att skapa en ny arbetsyta.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="8aa3d-185">Namnet på arbetsytan för det här exemplet anger du som **Mina godkännanden**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="8aa3d-186">Ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-186">Enter a description.</span></span>
6.  <span data-ttu-id="8aa3d-187">Välj en färg på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-187">Select a workspace color.</span></span> <span data-ttu-id="8aa3d-188">Arbetsytans färg ska användas för övergripande stilen för den mobila upplevelsen för den här arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="8aa3d-189">Välj en ikon för arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="8aa3d-190">Klicka på **Klart**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-190">Click **Done**</span></span>
9.  <span data-ttu-id="8aa3d-191">Klicka på **Publicera arbetsytan** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="8aa3d-192">Leverantörsfakturor som har tilldelats mig</span><span class="sxs-lookup"><span data-stu-id="8aa3d-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="8aa3d-193">Den första mobilsidan som du bör utforma är en lista med fakturor som har tilldelats till användaren för granskning.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="8aa3d-194">Använd sidan **VendMobileInvoiceAssignedToMeListPage** i Finance and Operations när du designar den här mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page in Finance and Operations.</span></span> <span data-ttu-id="8aa3d-195">Innan du slutför den här proceduren, kontrollera att minst en leverantörsfaktura har tilldelats till dig för granskning, och att fakturaraden har två fördelningar.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="8aa3d-196">Den här inställningen uppfyller kraven i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="8aa3d-197">Ersätt menyalternativets namn i URL:en till Finance and Operations med **VendMobileInvoiceAssignedToMeListPage** för att öppna mobilversionen av listsidan **Pågående leverantörsfakturor som tilldelats mig** i modulen **Leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-197">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="8aa3d-198">Beroende på hur många fakturor som du har i systemet tilldelade till dig, visas dessa fakturor på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="8aa3d-199">Om du vill hitta en specifik faktura kan du använda filtret till vänster.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="8aa3d-200">Men i det här exemplet kräver vi inte en viss faktura.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="8aa3d-201">Vi behöver bara en faktura som tilldelats dig som gör att du kan utforma mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="8aa3d-202">De nya sidor som är tillgängliga har utformats specifikt för utveckling av mobila scenarier för leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="8aa3d-203">Därför måste du använda dessa sidor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="8aa3d-204">URL:en bör likna följande URL och när du har angett den måste sidan som visas i illustrationen visas: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
2.  <span data-ttu-id="8aa3d-205">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-205">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="8aa3d-206">Välj din arbetsyta och klicka på **Redigera**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-206">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="8aa3d-207">Klicka på **Lägg till sida** för att skapa den första mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-207">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="8aa3d-208">Ange ett namn, till exempel **Mina leverantörsfakturor**, och en beskrivning, till exempel **Leverantörsfakturor som tilldelats mig för granskning**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-208">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="8aa3d-209">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-209">Click **Done**.</span></span>
7.  <span data-ttu-id="8aa3d-210">I mobila designern, på fliken **Fält** klickar du på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-210">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="8aa3d-211">Kolumnerna på listsidan måste likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-211">The columns on the list page must resemble the following illustration.</span></span> <span data-ttu-id="8aa3d-212">[![Kolumner på sidan Väntande leverantörsfakturor som har tilldelats mig](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-212">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
8.  <span data-ttu-id="8aa3d-213">Lägg till de kolumner som krävs från listsidan som måste visas för användare på mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-213">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="8aa3d-214">Den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-214">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="8aa3d-215">Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-215">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="8aa3d-216">Utifrån kraven i det här scenariot krävs följande åtta fält.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-216">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="8aa3d-217">Men vissa användare kanske anser att åtta fält är för mycket information på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-217">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="8aa3d-218">Därför visar vi bara de viktigaste fälten i vyn med mobillistan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-218">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="8aa3d-219">De återstående fälten visas i detaljvyn som vi utformar senare.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-219">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="8aa3d-220">Nu lägger vi till följande fält.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-220">For now, we will add the following fields.</span></span> <span data-ttu-id="8aa3d-221">Klicka på plustecknet (**+**) i dessa kolumner för att lägga till på mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-221">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="8aa3d-222">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="8aa3d-222">Vendor name</span></span>
    - <span data-ttu-id="8aa3d-223">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="8aa3d-223">Invoice total</span></span>
    - <span data-ttu-id="8aa3d-224">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="8aa3d-224">Invoice account</span></span>
    - <span data-ttu-id="8aa3d-225">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="8aa3d-225">Invoice number</span></span>
    - <span data-ttu-id="8aa3d-226">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-226">Invoice date</span></span>

    <span data-ttu-id="8aa3d-227">När fält läggs till måste mobilsidan likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-227">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    <span data-ttu-id="8aa3d-228">[![Sidan när fält har lagts till](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-228">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>
9.  <span data-ttu-id="8aa3d-229">Du måste även lägga till följande kolumner nu, så att vi kan aktivera arbetsflödesåtgärder senare.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-229">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="8aa3d-230">Visa Slutför uppgift</span><span class="sxs-lookup"><span data-stu-id="8aa3d-230">Show complete task</span></span>
    - <span data-ttu-id="8aa3d-231">Visa Delegera uppgift</span><span class="sxs-lookup"><span data-stu-id="8aa3d-231">Show delegate task</span></span>
    - <span data-ttu-id="8aa3d-232">Visa Återkalla uppgift</span><span class="sxs-lookup"><span data-stu-id="8aa3d-232">Show recall task</span></span>
    - <span data-ttu-id="8aa3d-233">Visa Avvisa uppgift</span><span class="sxs-lookup"><span data-stu-id="8aa3d-233">Show reject task</span></span>
    - <span data-ttu-id="8aa3d-234">Visa Begär slutförandeuppgift</span><span class="sxs-lookup"><span data-stu-id="8aa3d-234">Show request completion task</span></span>
    - <span data-ttu-id="8aa3d-235">Visa Skicka uppgift igen</span><span class="sxs-lookup"><span data-stu-id="8aa3d-235">Show resubmit task</span></span>

10. <span data-ttu-id="8aa3d-236">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-236">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="8aa3d-237">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-237">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="8aa3d-238">Klicka på **Publicera arbetsytan** för att spara ditt arbete.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-238">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="8aa3d-239">Aktivera **Visa fakturasumma i listan med pågående leverantörsfakturor** i parameterformuläret för leverantörsreskontra under **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-239">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="8aa3d-240">Observera att endast genom att aktivera den här parametern beräknas fakturasummor som ska visas på listsidan för pågående leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-240">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="8aa3d-241">Detta är en ny funktion som en del av förutsättningen snabbkorrigering 3208224.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-241">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="8aa3d-242">Detaljer om leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="8aa3d-242">Vendor invoice details</span></span>

<span data-ttu-id="8aa3d-243">Använd sidan **VendMobileInvoiceHeaderDetails** i Finance and Operations när du designar sidan med fakturadetaljer för mobil.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-243">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="8aa3d-244">Observera att beroende på antalet fakturor som du har i systemet visar den här sidan den äldsta fakturan (faktura som först skapades).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-244">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="8aa3d-245">Om du vill hitta en specifik faktura kan du använda filtret till vänster.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-245">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="8aa3d-246">Men i det här exemplet kräver vi inte en viss faktura.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-246">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="8aa3d-247">Vi behöver bara vissa fakturadata så att vi kan utforma mobilsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-247">We just require some invoice data so that we can design the mobile page.</span></span> <span data-ttu-id="8aa3d-248">[![Sida för arbetsflöde](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-248">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="8aa3d-249">I URL:en för Finance and Operations ersätter du namnet på menyalternativet med **VendMobileInvoiceHeaderDetails** för att öppna formuläret</span><span class="sxs-lookup"><span data-stu-id="8aa3d-249">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>
2. <span data-ttu-id="8aa3d-250">Öppna mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-250">Open the mobile designer from the **Settings** (gear) button.</span></span>
3. <span data-ttu-id="8aa3d-251">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-251">Click the **Edit** button to start edit mode in the workspace.</span></span>
4. <span data-ttu-id="8aa3d-252">Välj sidan **Mina leverantörsfakturor** som du skapade tidigare och klicka sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-252">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>
5. <span data-ttu-id="8aa3d-253">På fliken **Fält** klickar du på kolumnrubriken **Rutnät**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-253">On the **Fields** tab, click the **Grid** column heading.</span></span>
6. <span data-ttu-id="8aa3d-254">Klicka på **Egenskaper &gt;Lägg till sida**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-254">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="8aa3d-255">**Anmärkning:** När du klickar på rubriken **Rutnät** och lägger till en sida, etableras relationen med detaljsidan automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-255">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>
7. <span data-ttu-id="8aa3d-256">Ange en sidrubrik, till exempel **Fakturadetaljer**, och en beskrivning, till exempel **Visa fakturahuvud och raddetaljer**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-256">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>
8. <span data-ttu-id="8aa3d-257">Klicka på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-257">Click **Select fields**.</span></span> <span data-ttu-id="8aa3d-258">Observera att den ordning som du lägger till i är den ordning i vilken fälten visas för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-258">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="8aa3d-259">Det enda sättet att ändra ordningen på fälten blir genom att välja alla fält igen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-259">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 
9. <span data-ttu-id="8aa3d-260">Lägg till följande fält från huvudet, baserat på förutsättningarna för det här scenariot:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-260">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="8aa3d-261">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="8aa3d-261">Vendor name</span></span>
   - <span data-ttu-id="8aa3d-262">Fakturatotal</span><span class="sxs-lookup"><span data-stu-id="8aa3d-262">Invoice total</span></span>
   - <span data-ttu-id="8aa3d-263">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="8aa3d-263">Invoice account</span></span>
   - <span data-ttu-id="8aa3d-264">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="8aa3d-264">Invoice number</span></span>
   - <span data-ttu-id="8aa3d-265">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-265">Invoice date</span></span>
   - <span data-ttu-id="8aa3d-266">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-266">Invoice description</span></span>
   - <span data-ttu-id="8aa3d-267">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-267">Due date</span></span>
   - <span data-ttu-id="8aa3d-268">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="8aa3d-268">Invoice currency</span></span>

10. <span data-ttu-id="8aa3d-269">Lägg till följande fält från radrutnätet på sidan:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-269">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="8aa3d-270">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="8aa3d-270">Procurement category</span></span>
    - <span data-ttu-id="8aa3d-271">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-271">Quantity</span></span>
    - <span data-ttu-id="8aa3d-272">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-272">Unit price</span></span>
    - <span data-ttu-id="8aa3d-273">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="8aa3d-273">Line net amount</span></span>
    - <span data-ttu-id="8aa3d-274">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="8aa3d-274">1099 amount</span></span>

11. <span data-ttu-id="8aa3d-275">När alla fält från de två föregående stegen har lagts till, klickar du på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-275">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="8aa3d-276">Sidan måste likna följande illustration.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-276">The page must resemble the following illustration.</span></span>
    <span data-ttu-id="8aa3d-277">[![Sidan när fält har lagts till](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-277">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>
12. <span data-ttu-id="8aa3d-278">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-278">Click **Done** to exit edit mode.</span></span>
13. <span data-ttu-id="8aa3d-279">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-279">Click **Back** and then **Done** to exit the workspace</span></span>
14. <span data-ttu-id="8aa3d-280">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-280">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="8aa3d-281">Arbetsflödesåtgärder</span><span class="sxs-lookup"><span data-stu-id="8aa3d-281">Workflow actions</span></span>

<span data-ttu-id="8aa3d-282">Om du vill lägga till arbetsflödesåtgärder, använd sidan **VendMobileInvoiceHeaderDetails** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-282">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="8aa3d-283">Ersätt namnet på menyalternativet i URL-adressen precis som tidigare om du vill öppna sidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-283">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="8aa3d-284">Öppna sedan mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-284">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="8aa3d-285">Så här lägger du till arbetsflödesåtgärder på sidan med detaljer.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-285">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="8aa3d-286">För att de arbetsflödesåtgärder som du tänker utforma för tillgängliga för dig, måste dina tilldelade fakturor ha lämplig status.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-286">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="8aa3d-287">Registrera arbetsflödesåtgärder</span><span class="sxs-lookup"><span data-stu-id="8aa3d-287">Record workflow actions</span></span>
1.  <span data-ttu-id="8aa3d-288">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-288">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="8aa3d-289">Välj sidan **Fakturadetaljer** som du skapade tidigare och klicka sedan på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-289">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="8aa3d-290">Klicka på **Lägg till åtgärd** på fliken **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-290">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="8aa3d-291">Ange en rubrik för åtgärden, till exempel **Godkänn**, och en beskrivning, till exempel **Godkänn fakturan**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-291">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="8aa3d-292">Observera att rubriken för åtgärden som du anger här blir namnet på åtgärden som visas för användaren i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-292">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="8aa3d-293">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-293">Click **Done**.</span></span>
6.  <span data-ttu-id="8aa3d-294">Klicka på **Välj fält**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-294">Click **Select fields**.</span></span>
7.  <span data-ttu-id="8aa3d-295">Gå igenom arbetsflödesprocessen på sidan **VendMobileInvoiceHeaderDetails** sidan och slutför åtgärden som du vill registrera.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-295">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="8aa3d-296">Kontrollera att du skriver kommentarer för arbetsflöde under den här processen så att ett kommentarsfält ingår också i mobila upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-296">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="8aa3d-297">När arbetsflödesåtgärden körs, klickar du på **Klart** för att slutföra uppgiften Välj fält.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-297">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="8aa3d-298">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-298">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="8aa3d-299">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-299">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="8aa3d-300">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-300">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="8aa3d-301">Upprepa föregående steg för att registrera alla obligatoriska arbetsflödesåtgärder.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-301">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="8aa3d-302">Skapa en .js-fil</span><span class="sxs-lookup"><span data-stu-id="8aa3d-302">Create a .js file</span></span>
1. <span data-ttu-id="8aa3d-303">Öppna Anteckningar eller Microsoft Visual Studio och klistra in följande kod.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-303">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="8aa3d-304">Spara filen som en JS-fil.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-304">Save the file as a .js file.</span></span> <span data-ttu-id="8aa3d-305">Koden utför följande:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-305">This code does the following:</span></span>
    - <span data-ttu-id="8aa3d-306">Den döljer de extra arbetsflödesrelaterade kolumner som vi har lade till tidigare på mobillistsidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-306">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="8aa3d-307">Vi har lagt till kolumnerna så att appen har informationen i sammanhang och kan utföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-307">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="8aa3d-308">Utifrån vilket arbetsflödessteg som är aktivt, använder den logik för att visa enbart de åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-308">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa3d-309">Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-309">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="8aa3d-310">Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-310">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="8aa3d-311">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-311">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="8aa3d-312">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-312">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="8aa3d-313">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-313">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="8aa3d-314">Leverantörsfakturabilagor</span><span class="sxs-lookup"><span data-stu-id="8aa3d-314">Vendor invoice attachments</span></span>

1. <span data-ttu-id="8aa3d-315">Klicka på knappen **Inställningar** (kugghjul) i det övre högra hörnet på sidan och klicka sedan på **Mobilapp**</span><span class="sxs-lookup"><span data-stu-id="8aa3d-315">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
2. <span data-ttu-id="8aa3d-316">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-316">Click the **Edit** button to start edit mode in the workspace.</span></span>
3. <span data-ttu-id="8aa3d-317">Välj sidan <strong>Fakturadetaljer** som du skapade tidigare och klicka sedan på **Redigera</strong>.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-317">Select the <strong>Invoice details **page that you created earlier, and then click **Edit</strong>.</span></span>
4. <span data-ttu-id="8aa3d-318">Ange alternativet **Dokumenthantering** till **Ja** enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-318">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="8aa3d-319">**Anmärkning:** Om det inte finns några inga krav på att visa bifogade filer på den mobila enheten kan du lämna detta alternativ inställt på **Nej**, vilket är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-319">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   <span data-ttu-id="8aa3d-320">![Dokumenthantering](./media/docmanagement-216x300.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-320">![Document management](./media/docmanagement-216x300.png)</span></span>
5. <span data-ttu-id="8aa3d-321">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-321">Click **Done** to exit edit mode.</span></span>
6. <span data-ttu-id="8aa3d-322">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-322">Click **Back** and then **Done** to exit the workspace</span></span>
7. <span data-ttu-id="8aa3d-323">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-323">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="8aa3d-324">Fördelningar av leverantörsfakturarader</span><span class="sxs-lookup"><span data-stu-id="8aa3d-324">Vendor invoice line distributions</span></span>

<span data-ttu-id="8aa3d-325">Kraven i det här scenariot bekräftar att endast det endast ska finnas fördelningar på radnivå, och att en faktura alltid bara har en rad.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-325">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="8aa3d-326">Eftersom detta scenario är enkelt, måste användargränssnitt på den mobila enheten vara så enkelt att användaren inte behöver gå ned flera nivåer för att visa fördelningarna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-326">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="8aa3d-327">Leverantörsfakturor i Finance and Operations innehåller alternativet att visa alla fördelningar från fakturahuvudet.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-327">Vendor invoices in Finance and Operations include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="8aa3d-328">Denna upplevelse är det vi behöver för det mobila scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-328">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="8aa3d-329">Därför använder vi sidan **VendMobileInvoiceAllDistributionTree** för att utforma den här delen av det mobila scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-329">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8aa3d-330">Att känna till kraven hjälper oss att avgöra vilken sida som ska användas och hur exakt mobila upplevelsen ska optimeras för användaren när vi utformar scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-330">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="8aa3d-331">I det andra scenariot utnyttjas en annan sida för att visa fördelningar, eftersom kraven är olika krav för det scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-331">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="8aa3d-332">Ersätt namnet på menyalternativet i URL-adressen precis som du gjorde tidigare.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-332">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="8aa3d-333">Sidan som visas bör likna illustrationen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-333">The page that appears should resemble the following illustration.</span></span>
<span data-ttu-id="8aa3d-334">[![Sida med alla distributioner](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-334">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>
2.  <span data-ttu-id="8aa3d-335">Öppna mobildesignern med knappen **Inställningar** (kugghjul).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-335">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="8aa3d-336">Klicka på knappen **Redigera** för att starta redigeringsläget i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-336">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="8aa3d-337">**Anmärkning:** Du ser att två nya sidor har skapats automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-337">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="8aa3d-338">Dessa sidor skapas i systemet eftersom du aktiverade dokumenthantering i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-338">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="8aa3d-339">Du kan ignorera dessa nya sidor.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-339">You can ignore these new pages.</span></span>
4.  <span data-ttu-id="8aa3d-340">Klicka på **Lägg till sida**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-340">Click **Add page**.</span></span>
5.  <span data-ttu-id="8aa3d-341">Ange en sidrubrik som **Visa redovisning**, och en beskrivning, t.ex **Visa redovisning för fakturan**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-341">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>
6.  <span data-ttu-id="8aa3d-342">Klicka på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-342">Click **Done**.</span></span>
7.  <span data-ttu-id="8aa3d-343">På fliken **Fält** klickar du på **Välj fält**. Välj följande fält från fördelningssidan och klicka sedan på **Klart**:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-343">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="8aa3d-344">Belopp</span><span class="sxs-lookup"><span data-stu-id="8aa3d-344">Amount</span></span>
    2.  <span data-ttu-id="8aa3d-345">Valuta</span><span class="sxs-lookup"><span data-stu-id="8aa3d-345">Currency</span></span>
    3.  <span data-ttu-id="8aa3d-346">Huvudbokskonto</span><span class="sxs-lookup"><span data-stu-id="8aa3d-346">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="8aa3d-347">Vi valde inte kolumnen **Beskrivning** i rutnätet för fördelningar, eftersom kraven i det här scenariot har bekräftat att det utökade priset är de enda belopp som det finns fördelningar för.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-347">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="8aa3d-348">Därför behöver användaren inte något ytterligare fält för att fastställa beloppstypen som fördelningen gäller.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-348">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="8aa3d-349">Men i nästa scenario **ska** vi använda den här informationen, kraven för det scenariot anger att andra beloppstyper har fördelningar (till exempel moms).</span><span class="sxs-lookup"><span data-stu-id="8aa3d-349">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>
8.  <span data-ttu-id="8aa3d-350">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-350">Click **Done** to exit edit mode.</span></span>
9.  <span data-ttu-id="8aa3d-351">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-351">Click **Back** and then **Done** to exit the workspace</span></span>
10. <span data-ttu-id="8aa3d-352">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-352">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="8aa3d-353">Mobilsidan **Visa redovisning** är för tillfället inte kopplad till någon av de mobilsidor som vi har utformat hittills.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-353">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="8aa3d-354">Eftersom användaren ska kunna navigera till sidan **Visa redovisning** sidan från sidan **Fakturadetaljer** på den mobila enheten måste vi tillhandahålla navigering från sidan **Fakturadetaljer** till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-354">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="8aa3d-355">Vi fastställer den här navigeringen med hjälp av ytterligare logik via JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-355">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="8aa3d-356">Öppna den JS-fil som du skapade tidigare och lägg till de rader som markerats i koden nedan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-356">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="8aa3d-357">Den här koden gör två saker:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-357">This code does two things:</span></span>
    1.  <span data-ttu-id="8aa3d-358">Det hjälper till att garantera att användaren inte kan bläddra direkt från arbetsytan till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-358">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="8aa3d-359">Den etablerar en navigeringskontroll från sidan **Fakturadetaljer** till sidan **Visa redovisning**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-359">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="8aa3d-360">Namnet på sidorna och andra kontroller i koden måste överensstämma med namnen i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-360">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="8aa3d-361">Ladda upp kodfilen till arbetsytan genom att välja fliken **Logik** för att skriva över föregående kod</span><span class="sxs-lookup"><span data-stu-id="8aa3d-361">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="8aa3d-362">Klicka på **Klart** för att avsluta redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-362">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="8aa3d-363">Klicka på **Tillbaka** och sedan på **Klart** för att lämna arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8aa3d-363">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="8aa3d-364">Klicka på **Publicera arbetsytan** för att spara ditt arbete</span><span class="sxs-lookup"><span data-stu-id="8aa3d-364">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="8aa3d-365">Validering</span><span class="sxs-lookup"><span data-stu-id="8aa3d-365">Validation</span></span>

<span data-ttu-id="8aa3d-366">Öppna appen från din mobila enhet och anslut till din Finance and Operations-instans.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-366">From your mobile device, open the app, and connect to your Finance and Operations instance.</span></span> <span data-ttu-id="8aa3d-367">Kontrollera att du loggar in till företaget där leverantörsfakturor har tilldelats dig för granskning.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-367">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="8aa3d-368">Du ska kunna utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-368">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="8aa3d-369">Se arbetsytan **Mina godkännanden**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-369">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="8aa3d-370">Gå nedåt i arbetsytan **Mina godkännanden** och se sidan **Mina leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-370">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="8aa3d-371">Gå nedåt i sidan **Mina leverantörsfakturor** och se en lista med fakturor som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-371">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="8aa3d-372">Gå till en av fakturorna och visa huvud- och raddetaljer för fakturan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-372">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="8aa3d-373">På informationssidan visas en länk till bilagor. Använd den här länken för att navigera till listan med bifogade filer och visa de bifogade filerna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-373">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="8aa3d-374">På informationssidan visas en länk till sidan **Visa redovisning**. Använd den här länken för att navigera till fördelningssidan och visa fördelningarna.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-374">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="8aa3d-375">På detaljsidan, klicka på menyn **Åtgärder** längst ned och utför arbetsflödesåtgärder som gäller för arbetsflödessteget.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-375">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="8aa3d-376">Utforma ett komplext scenario för fakturagodkännande för Fabrikam</span><span class="sxs-lookup"><span data-stu-id="8aa3d-376">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa3d-377">Scenarioattribut</span><span class="sxs-lookup"><span data-stu-id="8aa3d-377">Scenario attribute</span></span></th>
<th><span data-ttu-id="8aa3d-378">Besvara</span><span class="sxs-lookup"><span data-stu-id="8aa3d-378">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8aa3d-379">Vilka fält från fakturahuvudet vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-379">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="8aa3d-380">Leverantörsnamn</span><span class="sxs-lookup"><span data-stu-id="8aa3d-380">Vendor name</span></span></li>
<li><span data-ttu-id="8aa3d-381">Fakturabelopp</span><span class="sxs-lookup"><span data-stu-id="8aa3d-381">Invoice amount</span></span></li>
<li><span data-ttu-id="8aa3d-382">Fakturakonto</span><span class="sxs-lookup"><span data-stu-id="8aa3d-382">Invoice account</span></span></li>
<li><span data-ttu-id="8aa3d-383">Fakturanummer</span><span class="sxs-lookup"><span data-stu-id="8aa3d-383">Invoice number</span></span></li>
<li><span data-ttu-id="8aa3d-384">Fakturadatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-384">Invoice date</span></span></li>
<li><span data-ttu-id="8aa3d-385">Fakturabeskrivning</span><span class="sxs-lookup"><span data-stu-id="8aa3d-385">Invoice description</span></span></li>
<li><span data-ttu-id="8aa3d-386">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="8aa3d-386">Due date</span></span></li>
<li><span data-ttu-id="8aa3d-387">Fakturavaluta</span><span class="sxs-lookup"><span data-stu-id="8aa3d-387">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-388">Vilka fält från fakturaraderna vill användaren ha i mobilupplevelsen, och i vilken ordning?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-388">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="8aa3d-389">Anskaffningskategori</span><span class="sxs-lookup"><span data-stu-id="8aa3d-389">Procurement category</span></span></li>
<li><span data-ttu-id="8aa3d-390">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-390">Quantity</span></span></li>
<li><span data-ttu-id="8aa3d-391">Pris per enhet</span><span class="sxs-lookup"><span data-stu-id="8aa3d-391">Unit price</span></span></li>
<li><span data-ttu-id="8aa3d-392">Nettobelopp för rad</span><span class="sxs-lookup"><span data-stu-id="8aa3d-392">Line net amount</span></span></li>
<li><span data-ttu-id="8aa3d-393">1099-belopp</span><span class="sxs-lookup"><span data-stu-id="8aa3d-393">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-394">Hur många rader finns det i en faktura?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-394">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="8aa3d-395">Använd 80-20-regeln här och optimera för 80 procent.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-395">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="8aa3d-396">5</span><span class="sxs-lookup"><span data-stu-id="8aa3d-396">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-397">Vill användarna ha redovisningsfördelningar (fakturakodning) på den mobila enheten vid granskningar?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-397">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="8aa3d-398">Ja</span><span class="sxs-lookup"><span data-stu-id="8aa3d-398">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-399">Hur många redovisningsfördelningar (slutligt pris, moms, avgifter, och så vidare) finns det för en fakturarad?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-399">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="8aa3d-400">Återigen, använd 80-20-regeln.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-400">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="8aa3d-401">Slutligt pris: 2 Moms: 2 Avgifter: 2</span><span class="sxs-lookup"><span data-stu-id="8aa3d-401">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8aa3d-402">Har fakturorna också redovisningsfördelningar i fakturahuvudet?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-402">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="8aa3d-403">Om så är fallet ska dessa redovisningsfördelningar finnas på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-403">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="8aa3d-404">Används inte</span><span class="sxs-lookup"><span data-stu-id="8aa3d-404">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8aa3d-405">Vill användarna se bilagor för fakturan på enheten?</span><span class="sxs-lookup"><span data-stu-id="8aa3d-405">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="8aa3d-406">Ja</span><span class="sxs-lookup"><span data-stu-id="8aa3d-406">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="8aa3d-407">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8aa3d-407">Next steps</span></span>

<span data-ttu-id="8aa3d-408">Följande ändringar kan göras för scenario 1, baserat på kraven för scenario 2.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-408">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="8aa3d-409">Du kan använda det här avsnittet för att förbättra upplevelsen av mobilappen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-409">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="8aa3d-410">Eftersom flera fakturarader förväntas i scenario 2, hjälper följande ändringar i designen till att optimera användarupplevelsen på den mobila enheten:</span><span class="sxs-lookup"><span data-stu-id="8aa3d-410">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="8aa3d-411">I stället för att visa fakturarader på detaljsidan (som i scenario 1) kan användare välja att visa rader på en separat mobilsida.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-411">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="8aa3d-412">Eftersom flera fakturarader förväntas i det här scenariot, och om sidan **VendMobileInvoiceAllDistributionTree** används för att utforma fördelningssidan för mobil (liksom i scenario 1), kan det vara förvirrande för användaren att korrelera rader till fördelningar.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-412">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="8aa3d-413">Använd därför sidan **VendMobileInvoiceLineDistributionTree** sidan för att utforma fördelningssidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-413">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="8aa3d-414">Vi rekommenderar att fördelningarna visas i samband med en fakturarad i det här scenariot.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-414">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="8aa3d-415">Kontrollera därför att användaren kan gå nedåt i en rad för att visa fördelningssidan.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-415">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="8aa3d-416">Använd sidans länkfunktion för att upprätta detaljgranskningen, precis som du gjorde för huvud- och detaljsidorna i scenario 1.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-416">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="8aa3d-417">Eftersom flera beloppstyper förväntas för fördelningar i scenario 2 (moms, tillägg och så vidare), kan det vara praktiskt att visa beskrivningen av beloppstypen.</span><span class="sxs-lookup"><span data-stu-id="8aa3d-417">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="8aa3d-418">(Vi uteslöt den här informationen i scenario 1.)</span><span class="sxs-lookup"><span data-stu-id="8aa3d-418">(We omitted this information in scenario 1.)</span></span>





