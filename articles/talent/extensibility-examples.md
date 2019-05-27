---
title: Utöka Talent genom att använda PowerApps och Microsoft Flow- exempelscenarier
description: Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 for Talent som använder Microsoft PowerApps och Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 03/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 0aa3578047b9397682a7039d0dbcc05cc1b167e4
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/12/2019
ms.locfileid: "949930"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="69716-103">Utöka Talent genom att använda PowerApps och Microsoft Flow- exempelscenarier</span><span class="sxs-lookup"><span data-stu-id="69716-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="69716-104">Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 for Talent som använder Microsoft PowerApps och Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="69716-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="69716-105">Du kan importera lösningspaketet som associeras med varje exempel i din PowerApps-miljö.</span><span class="sxs-lookup"><span data-stu-id="69716-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="69716-106">Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.</span><span class="sxs-lookup"><span data-stu-id="69716-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69716-107">Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.</span><span class="sxs-lookup"><span data-stu-id="69716-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="69716-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="69716-108">Prerequisites</span></span>

- <span data-ttu-id="69716-109">Om du vill importera paket måste användarna ha behörighet **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="69716-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="69716-110">Användare måste ha en PowerApps Plan 2-licens eller en PowerApps Plan 2 utvärderingslicens för att exportera eller importera appar.</span><span class="sxs-lookup"><span data-stu-id="69716-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="69716-111">Flöde – formuläret Ansluta</span><span class="sxs-lookup"><span data-stu-id="69716-111">Flow – Form Connect</span></span>

<span data-ttu-id="69716-112">Mallen **flöde – formuläret Ansluta** kan användas för att läsa data från Microsoft Forms och lagra det i en Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="69716-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="69716-113">Den här mallen kan utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="69716-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="69716-114">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="69716-114">Here are some examples:</span></span>

- <span data-ttu-id="69716-115">Hämta kandidatens bedömningar.</span><span class="sxs-lookup"><span data-stu-id="69716-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="69716-116">Hämta resultaten från kursens enkäter.</span><span class="sxs-lookup"><span data-stu-id="69716-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="69716-117">Kompilera ett bibliotek med intervjufrågor för personaladministratörer (HR).</span><span class="sxs-lookup"><span data-stu-id="69716-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="69716-118">Hämta kandidatens utvärdering av intervjuprocessen</span><span class="sxs-lookup"><span data-stu-id="69716-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="69716-119">I Microsoft Dynamics 365: Attract, kan formulär visas i kandidatportalen och kandidater kan fylla i information.</span><span class="sxs-lookup"><span data-stu-id="69716-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="69716-120">Formulär kan också vara inbäddade som aktiviteter i en jobbmall.</span><span class="sxs-lookup"><span data-stu-id="69716-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="69716-121">När en kandidat skickar ett formulär, hämtar Microsoft Flow formuläröverföringen, läser in data och lagrar den Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="69716-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="69716-122">För att hämta mallen **flöde – formuläret Ansluta** och anpassad entitetsstruktur, gå till [flöde – formuläret Ansluta](https://go.microsoft.com/fwlink/?linkid=2081988) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="69716-123">Initiera och hämta parametrar som skickades till Powerapps</span><span class="sxs-lookup"><span data-stu-id="69716-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="69716-124">Mallen **starta och hämta parametrar som skickades till Powerapps** kan användas som utgångspunkt för vissa PowerApps-situationer som är specifika för Attract.</span><span class="sxs-lookup"><span data-stu-id="69716-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="69716-125">Den innehåller alla standardparametrar som skickas av Attract, t.ex. **Jobbansökan**, **kandidat-ID**, och **JobID**.</span><span class="sxs-lookup"><span data-stu-id="69716-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="69716-126">Den här mallen kan användas för att hämta kandidatens bedömningsformulär, så att en anställande chef kan visa den bedömning som en kandidat har fyllt i.</span><span class="sxs-lookup"><span data-stu-id="69716-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="69716-127">Appar som har skapats med hjälp av PowerApps kan vara inbäddade i jobbmallen i Attract.</span><span class="sxs-lookup"><span data-stu-id="69716-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="69716-128">För att hämta mallen **initiera och hämta parametrar som skickades till Powerapps** och anpassad entitetsstruktur, gå till [starta och hämta parametrar som skickades till Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="69716-129">Integration med Office 365</span><span class="sxs-lookup"><span data-stu-id="69716-129">Integration with Office 365</span></span>

<span data-ttu-id="69716-130">Appen **Integrering med Office 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="69716-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="69716-131">Den refererar till arbetare i Talent för att hämta instämplings- och utstämplingsinformation och undantagsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="69716-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="69716-132">Instämplings- och utstämplingsinformation lagras i anpassade Common Data Service-enheter.</span><span class="sxs-lookup"><span data-stu-id="69716-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="69716-133">Förutsättningen är att rubrikerna fylls i från tredjepartssystem via integrering.</span><span class="sxs-lookup"><span data-stu-id="69716-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="69716-134">Den här appen kan utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="69716-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="69716-135">Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.</span><span class="sxs-lookup"><span data-stu-id="69716-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="69716-136">För att hämta appen **integrering med Office 365** och anpassad entitetsstruktur, gå till [Integrering med Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="69716-137">Föde - E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="69716-137">Flow – Email Notification</span></span>

<span data-ttu-id="69716-138">Mallen **Flöde – e-postmeddelanden** kan användas för e-postmeddelandescenarier.</span><span class="sxs-lookup"><span data-stu-id="69716-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="69716-139">Den kan användas för att utlösa e-postmeddelanden till kandidater som anställningsteamet avvisar under någon fas i rekryteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="69716-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="69716-140">Den här mallen kan utökas för att spåra ändringar i kandidatfasen genom hela rekryteringsprocessen och skicka meddelanden till anställningsteamet och kandidaterna.</span><span class="sxs-lookup"><span data-stu-id="69716-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="69716-141">I allmänhet kan flöden för entiteter som är lagrade i Common Data Service ställas in för att skicka meddelanden om händelser som inträffar i Core HR, Attract eller Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="69716-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="69716-142">För att hämta mallen **Flöde – e-postmeddelanden**, gå till [Flöde – e-postmeddelanden](https://go.microsoft.com/fwlink/?linkid=2082103) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="69716-143">Flöde – anslut och kör SQL</span><span class="sxs-lookup"><span data-stu-id="69716-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="69716-144">Mallen **Flöde – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.</span><span class="sxs-lookup"><span data-stu-id="69716-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="69716-145">Även om den här mallen har utformats för att läsa och uppdatera SQL-register kan den utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="69716-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="69716-146">Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Common Data Service med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69716-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="69716-147">För att hämta mallen **flöde – ansluta och köra SQL**, gå till [flöde – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="69716-148">Flöde SharePoint-integrering</span><span class="sxs-lookup"><span data-stu-id="69716-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="69716-149">Mallen **Flöde – SharePoint integrering** kan användas för att läsa in data från en Microsoft SharePoint-lista, jämföra listan med fältvärden för någon Common Data Service entitet och skicka resultatet av jämförelsen som ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="69716-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="69716-150">En organisation kan ha en uppsättning med kunskaper som den kräver snarast.</span><span class="sxs-lookup"><span data-stu-id="69716-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="69716-151">Dessa kunskaper kan lagras i SharePoint som en SharePoint lista.</span><span class="sxs-lookup"><span data-stu-id="69716-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="69716-152">Då en kandidat ansöker om ett jobb som en uppsättning kunskaper anges för, om det finns en betydande matchning mellan kandidatens kunskaper och de kunskaper som är lagrade i SharePoint skickas ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="69716-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="69716-153">På så sätt fylls befattningar som krävs snarast snabbare eftersom meddelanden hjälper rekryterare att kontakta och anställa kandidater i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="69716-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="69716-154">Den här mallen kan utökas så att den kan användas för vissa situationer som omfattar SharePoint-integration.</span><span class="sxs-lookup"><span data-stu-id="69716-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="69716-155">För att hämta mallen **Flöde – SharePoint Integration**, gå till [Flöde – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="69716-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>



## <a name="additional-resources"></a><span data-ttu-id="69716-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="69716-156">Additional resources</span></span>

[<span data-ttu-id="69716-157">Appen Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="69716-157">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="69716-158">Migrera mellan innehavare och program</span><span class="sxs-lookup"><span data-stu-id="69716-158">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)