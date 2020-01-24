---
title: Utöka Talent med Power Apps och Power Automate
description: Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent som använder Microsoft Power Apps och Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 6c8a583a93c2ceb70d8c3b0e0047e2bf2047b56d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898327"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="071c6-103">Utöka Talent med Power Apps och Power Automate</span><span class="sxs-lookup"><span data-stu-id="071c6-103">Extend Talent with Power Apps and Power Automate</span></span>

<span data-ttu-id="071c6-104">Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent som använder Microsoft Power Apps och Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="071c6-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="071c6-105">Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="071c6-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="071c6-106">Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.</span><span class="sxs-lookup"><span data-stu-id="071c6-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="071c6-107">Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.</span><span class="sxs-lookup"><span data-stu-id="071c6-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="071c6-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="071c6-108">Prerequisites</span></span>

- <span data-ttu-id="071c6-109">Om du vill importera paket måste användarna ha behörighet **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="071c6-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="071c6-110">Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 utvärderingslicens för att exportera eller importera appar.</span><span class="sxs-lookup"><span data-stu-id="071c6-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="071c6-111">Power Automate – formuläret Ansluta</span><span class="sxs-lookup"><span data-stu-id="071c6-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="071c6-112">Mallen **Power Automate – formuläret Ansluta** kan användas för att läsa data från Microsoft Forms och lagra det i en Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="071c6-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="071c6-113">Den här mallen kan utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="071c6-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="071c6-114">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="071c6-114">Here are some examples:</span></span>

- <span data-ttu-id="071c6-115">Hämta kandidatens bedömningar.</span><span class="sxs-lookup"><span data-stu-id="071c6-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="071c6-116">Hämta resultaten från kursens enkäter.</span><span class="sxs-lookup"><span data-stu-id="071c6-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="071c6-117">Kompilera ett bibliotek med intervjufrågor för personaladministratörer (HR).</span><span class="sxs-lookup"><span data-stu-id="071c6-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="071c6-118">Hämta kandidatens utvärdering av intervjuprocessen</span><span class="sxs-lookup"><span data-stu-id="071c6-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="071c6-119">I Microsoft Dynamics 365: Attract, kan formulär visas i kandidatportalen och kandidater kan fylla i information.</span><span class="sxs-lookup"><span data-stu-id="071c6-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="071c6-120">Formulär kan också vara inbäddade som aktiviteter i en jobbmall.</span><span class="sxs-lookup"><span data-stu-id="071c6-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="071c6-121">När en kandidat skickar ett formulär, hämtar Microsoft Power Automate formuläröverföringen, läser in data och lagrar den Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="071c6-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="071c6-122">För att hämta mallen **Power Automate – formuläret Ansluta** och anpassad entitetsstruktur, gå till [Power Automate – formuläret Ansluta](https://go.microsoft.com/fwlink/?linkid=2081988) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-power-apps"></a><span data-ttu-id="071c6-123">Initiera och hämta parametrar som skickades till Power Apps</span><span class="sxs-lookup"><span data-stu-id="071c6-123">Initiate and Extract Parameters Passed to Power Apps</span></span>

<span data-ttu-id="071c6-124">Mallen **starta och hämta parametrar som skickades till Power Apps** kan användas som utgångspunkt för vissa Power Apps-situationer som är specifika för Attract.</span><span class="sxs-lookup"><span data-stu-id="071c6-124">The **Initiate and Extract Parameters Passed to Power Apps** template can be used as a starting point for any Power Apps scenario that is specific to Attract.</span></span> <span data-ttu-id="071c6-125">Den innehåller alla standardparametrar som skickas av Attract, t.ex. **Jobbansökan**, **kandidat-ID**, och **JobID**.</span><span class="sxs-lookup"><span data-stu-id="071c6-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="071c6-126">Den här mallen kan användas för att hämta kandidatens bedömningsformulär, så att en anställande chef kan visa den bedömning som en kandidat har fyllt i.</span><span class="sxs-lookup"><span data-stu-id="071c6-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="071c6-127">Appar som har skapats med hjälp av Power Apps kan vara inbäddade i jobbmallen i Attract.</span><span class="sxs-lookup"><span data-stu-id="071c6-127">Apps that are created by using Power Apps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="071c6-128">För att hämta mallen **initiera och hämta parametrar som skickades till Power Apps** och anpassad entitetsstruktur, gå till [starta och hämta parametrar som skickades till Power Apps](https://go.microsoft.com/fwlink/?linkid=2081991) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-128">To download the **Initiate and Extract Parameters Passed to Power Apps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Power Apps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="071c6-129">Integration med Office 365</span><span class="sxs-lookup"><span data-stu-id="071c6-129">Integration with Office 365</span></span>

<span data-ttu-id="071c6-130">Appen **Integrering med Office 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="071c6-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="071c6-131">Den refererar till arbetare i Talent för att hämta instämplings- och utstämplingsinformation och undantagsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="071c6-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="071c6-132">Instämplings- och utstämplingsinformation lagras i anpassade Common Data Service-enheter.</span><span class="sxs-lookup"><span data-stu-id="071c6-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="071c6-133">Förutsättningen är att rubrikerna fylls i från tredjepartssystem via integrering.</span><span class="sxs-lookup"><span data-stu-id="071c6-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="071c6-134">Den här appen kan utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="071c6-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="071c6-135">Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.</span><span class="sxs-lookup"><span data-stu-id="071c6-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="071c6-136">För att hämta appen **integrering med Office 365** och anpassad entitetsstruktur, gå till [Integrering med Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--email-notification"></a><span data-ttu-id="071c6-137">Power Automate – E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="071c6-137">Power Automate – Email Notification</span></span>

<span data-ttu-id="071c6-138">Mallen **Power Automate – e-postmeddelanden** kan användas för e-postmeddelandescenarier.</span><span class="sxs-lookup"><span data-stu-id="071c6-138">The **Power Automate – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="071c6-139">Den kan användas för att utlösa e-postmeddelanden till kandidater som anställningsteamet avvisar under någon fas i rekryteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="071c6-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="071c6-140">Den här mallen kan utökas för att spåra ändringar i kandidatfasen genom hela rekryteringsprocessen och skicka meddelanden till anställningsteamet och kandidaterna.</span><span class="sxs-lookup"><span data-stu-id="071c6-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="071c6-141">I allmänhet kan flöden för entiteter som är lagrade i Common Data Service ställas in för att skicka meddelanden om händelser som inträffar i Core HR, Attract eller Onboard.</span><span class="sxs-lookup"><span data-stu-id="071c6-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Onboard.</span></span>

<span data-ttu-id="071c6-142">För att hämta mallen **Power Automate – e-postmeddelanden** gå till [Power Automate – e-postmeddelanden](https://go.microsoft.com/fwlink/?linkid=2082103) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-142">To download the **Power Automate – Email Notification** template, go to [Power Automate – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="071c6-143">Power Automate – anslut och kör SQL</span><span class="sxs-lookup"><span data-stu-id="071c6-143">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="071c6-144">Mallen **Power Automate – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.</span><span class="sxs-lookup"><span data-stu-id="071c6-144">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="071c6-145">Även om den här mallen har utformats för att läsa och uppdatera SQL-register kan den utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="071c6-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="071c6-146">Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Common Data Service med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.</span><span class="sxs-lookup"><span data-stu-id="071c6-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="071c6-147">För att hämta mallen **Power Automate – ansluta och köra SQL** gå till [Power Automate – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-147">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="071c6-148">Power Automate – SharePoint-integration</span><span class="sxs-lookup"><span data-stu-id="071c6-148">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="071c6-149">Mallen **Power Automate – SharePoint-integration** kan användas för att läsa in data från en Microsoft SharePoint-lista, jämföra listan med fältvärden för någon Common Data Service entitet och skicka resultatet av jämförelsen som ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="071c6-149">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="071c6-150">En organisation kan ha en uppsättning med kunskaper som den kräver snarast.</span><span class="sxs-lookup"><span data-stu-id="071c6-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="071c6-151">Dessa kunskaper kan lagras i SharePoint som en SharePoint lista.</span><span class="sxs-lookup"><span data-stu-id="071c6-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="071c6-152">Då en kandidat ansöker om ett jobb som en uppsättning kunskaper anges för, om det finns en betydande matchning mellan kandidatens kunskaper och de kunskaper som är lagrade i SharePoint skickas ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="071c6-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="071c6-153">På så sätt fylls befattningar som krävs snarast snabbare eftersom meddelanden hjälper rekryterare att kontakta och anställa kandidater i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="071c6-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="071c6-154">Den här mallen kan utökas så att den kan användas för vissa situationer som omfattar SharePoint-integration.</span><span class="sxs-lookup"><span data-stu-id="071c6-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="071c6-155">För att hämta mallen **Power Automate – SharePoint-integration** gå till [Power Automate – SharePoint-integration](https://go.microsoft.com/fwlink/?linkid=2082109) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-155">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="071c6-156">Appen Hänvisning</span><span class="sxs-lookup"><span data-stu-id="071c6-156">Referral App</span></span>
<span data-ttu-id="071c6-157">Du kan använda appen Hänvisning för att lägga till kandidater till en delad talangpool.</span><span class="sxs-lookup"><span data-stu-id="071c6-157">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="071c6-158">Hänvisaren kan ange **förnamn**, **efternamn**, **e-postadress** och **Linkedln-adress** när han eller hon skickar en kandidat.</span><span class="sxs-lookup"><span data-stu-id="071c6-158">The referrer can enter **Firstname**, **Lastname**, **Email**, and **Linkedln URL** when submitting a candidate.</span></span> <span data-ttu-id="071c6-159">Kandidatens metadata för källan fylls sedan i med hänvisarens information.</span><span class="sxs-lookup"><span data-stu-id="071c6-159">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="071c6-160">Du kan bädda in den här appen i Självbetjäning för medarbetare (ESS) för att skicka referenser eller använda den som en hyperlänk i företagsportalen och köra den som en fristående app.</span><span class="sxs-lookup"><span data-stu-id="071c6-160">You can embed this app in Employee self-service (ESS) for submitting referrals, or you can be use it as a hyperlink in the Corporate Portal and run as a stand-alone app.</span></span>

<span data-ttu-id="071c6-161">Hämta **Appen Hänvisning** genom att gå till [Dynamics 365 Talent utbyggbarhetslösning: appen Hänvisning](https://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) i Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="071c6-161">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) on the Microsoft Download Center.</span></span> <span data-ttu-id="071c6-162">Du kan importera den här appen och anpassa den om du vill lägga till fler funktioner.</span><span class="sxs-lookup"><span data-stu-id="071c6-162">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="071c6-163">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="071c6-163">Additional resources</span></span>

[<span data-ttu-id="071c6-164">Appen Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="071c6-164">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="071c6-165">Migrera mellan innehavare och program</span><span class="sxs-lookup"><span data-stu-id="071c6-165">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
