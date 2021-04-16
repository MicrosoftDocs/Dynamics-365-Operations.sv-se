---
title: Introduktion av API för integrering av system för sökandespårning
description: Detta ämne beskriver API för integrering av system för sökandespårning (ATS) för Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 599f9728019cd6bc59c59a4f08df06c6c9c9ac31
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798443"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="a742f-103">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="a742f-103">Applicant Tracking System integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a742f-104">Detta ämne beskriver API för integrering av system för sökandespårning (ATS) för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a742f-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="a742f-105">Syftet med API:et är att möjliggöra effektiviserad integrering mellan Dynamics 365 Human Resources och ATS-partner.</span><span class="sxs-lookup"><span data-stu-id="a742f-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![ATS-integreringsflöde](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="a742f-107">Den integrerade erfarenheten börjar i Personal när en anställningsansvarig skapar en rekryteringsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a742f-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="a742f-108">När begäran har aktiverats hämtar ATS uppgifter om förfrågningen för att skapa ett rekryteringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="a742f-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="a742f-109">Därefter följer det rekryteringsförloppet för att välja och anställa en kandidat för befattningen/befattningarna.</span><span class="sxs-lookup"><span data-stu-id="a742f-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="a742f-110">Slutligen slutför ATS integreringen genom att skicka den valda kandidatens post till Personal.</span><span class="sxs-lookup"><span data-stu-id="a742f-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="a742f-111">Kandidatposten kan sedan gå igenom fler registreringsvalideringar och arbetsflöden för att skapa medarbetarposten.</span><span class="sxs-lookup"><span data-stu-id="a742f-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="a742f-112">För att aktivera integreringen har Personal lagt till följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="a742f-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="a742f-113">Funktion för att skapa en rekryteringsbegäran.</span><span class="sxs-lookup"><span data-stu-id="a742f-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="a742f-114">En expanderad kandidatprofil och relaterade arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="a742f-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="a742f-115">Ett integrations-API som öppnar den nya funktionen för integrering av program.</span><span class="sxs-lookup"><span data-stu-id="a742f-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="a742f-116">Mer information om hur du ställer in och använder funktionen för rekryteringsbegäran och kandidater finns i [Rekrytera jobbkandidater](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="a742f-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="a742f-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a742f-117">Microsoft Dataverse</span></span>

<span data-ttu-id="a742f-118">Detta API bygger på Microsoft Dataverse (tidigare Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="a742f-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="a742f-119">All RESTful-interaktion med denna API sker via webb-API för Microsoft Dataverse, som använder OData.</span><span class="sxs-lookup"><span data-stu-id="a742f-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="a742f-120">Detta API är en underuppsättning av webb-API för Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a742f-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="a742f-121">Webb-API för Dataverse definierar egenskaper såsom autentisering, serviceavtal, batch, samtidighetskontroll och felhantering.</span><span class="sxs-lookup"><span data-stu-id="a742f-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="a742f-122">Mer allmän information om webb-API för Microsoft Dataverse finns här:</span><span class="sxs-lookup"><span data-stu-id="a742f-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="a742f-123">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="a742f-123">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="a742f-124">Använd webb-API för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a742f-124">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="a742f-125">Utvecklarguide för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a742f-125">Microsoft Dataverse developer guide</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform)

<span data-ttu-id="a742f-126">Dokumentationen ovan innehåller information och utvecklarvägledning om hur du använder webb-API för Dataverse, exempelvis [hanterar autentiseringar](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [genomför åtgärder](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [använder Postman med API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) samt [använder ändringsspårnings- eller delta-tokens](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) med API:t.</span><span class="sxs-lookup"><span data-stu-id="a742f-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="a742f-127">Alternativuppsättningar</span><span class="sxs-lookup"><span data-stu-id="a742f-127">Option sets</span></span>

<span data-ttu-id="a742f-128">Datamodellen för den API för ATS-integrering som beskrivs i det här dokumentet innehåller alternativuppsättningar som tillhandahåller fasta värden associerade med entitetsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="a742f-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="a742f-129">Mer information om hur du arbetar med alternativuppsättningar i webb-API för Dataverse finns i [Skapa och uppdatera alternativuppsättningar med hjälp av webb-API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="a742f-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="a742f-130">Alternativuppsättningar definieras för respektive Dataverse-miljö.</span><span class="sxs-lookup"><span data-stu-id="a742f-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="a742f-131">Virtuella register för Personal i Dataverse</span><span class="sxs-lookup"><span data-stu-id="a742f-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="a742f-132">Slutpunkterna för API för ATS-integration använder plattformsfunktionerna för det virtuella registret i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a742f-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="a742f-133">Som standard distribueras inte de virtuella registren och deras associerade API-slutpunkter för Personal-miljöer, vilket låter organisationer att avgöra vilka OData-slutpunkter som ska visas för miljön.</span><span class="sxs-lookup"><span data-stu-id="a742f-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="a742f-134">Om du vill använda API:t måste de virtuella registren för Personal-entiteterna genereras för miljön.</span><span class="sxs-lookup"><span data-stu-id="a742f-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="a742f-135">Information om hur du genererar virtuella register för API:et finns i [Konfigurera virtuella Dataverse-register](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="a742f-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

## <a name="data-model"></a><span data-ttu-id="a742f-136">Datamodell</span><span class="sxs-lookup"><span data-stu-id="a742f-136">Data model</span></span>

<span data-ttu-id="a742f-137">Datamodellen centreras kring två huvudentiteter:</span><span class="sxs-lookup"><span data-stu-id="a742f-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="a742f-138">**RecruitingRequest** representerar en begäran till en ATS att rekrytera för en eller flera öppna befattningar. En exempelfråga finns i [Exempelfråga för Rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="a742f-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="a742f-139">**CandidateToHire** representerar detaljer om en kandidat som har accepterat ett erbjudande om en befattning.</span><span class="sxs-lookup"><span data-stu-id="a742f-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="a742f-140">**Person** representerar den person som är kandidat.</span><span class="sxs-lookup"><span data-stu-id="a742f-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="a742f-141">En person kan ha flera roller i företaget, till exempel kandidat, medarbetare, anställd eller entreprenör.</span><span class="sxs-lookup"><span data-stu-id="a742f-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="a742f-142">För en exempelfråga, se [Exempelfråga för Kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="a742f-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="a742f-143">Följande diagram visar relationer inom API:t.</span><span class="sxs-lookup"><span data-stu-id="a742f-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="a742f-144">Flera typer har utländska nycklar till andra, befintliga entiteter i Personal som inte visas här.</span><span class="sxs-lookup"><span data-stu-id="a742f-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="a742f-145">Detta dokument innehåller information om entiteter som är specifika för rekryteringintegreringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="a742f-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="a742f-146">Det finns dock många andra entiteter i webb-API:t för Dataverse för Dynamics 365 Human Resources som också kan vara relevanta för din integrering.</span><span class="sxs-lookup"><span data-stu-id="a742f-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="a742f-147">Du kanske till exempel också behöver detaljer för medarbetare, jobb, befattningar eller andra entiteter som inte har definierats här.</span><span class="sxs-lookup"><span data-stu-id="a742f-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="a742f-148">Många av dessa entiteter refereras i relationer med utländska nycklar eller navigeringsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="a742f-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![API-datamodell för ATS-integrering](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="a742f-150">Rekryteringsbegäran och relaterade entiteter och alternativuppsättningar</span><span class="sxs-lookup"><span data-stu-id="a742f-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="a742f-151">Exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="a742f-151">Example query:</span></span> 

- [<span data-ttu-id="a742f-152">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="a742f-153">Enheter:</span><span class="sxs-lookup"><span data-stu-id="a742f-153">Entities:</span></span>

- [<span data-ttu-id="a742f-154">Rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="a742f-155">Befattning för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="a742f-156">Färdighet för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="a742f-157">Utbildning för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="a742f-158">Plats för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="a742f-159">Alternativuppsättningar:</span><span class="sxs-lookup"><span data-stu-id="a742f-159">Option sets:</span></span>

- [<span data-ttu-id="a742f-160">Befrielsestatus för jobb</span><span class="sxs-lookup"><span data-stu-id="a742f-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="a742f-161">Befattningsstatus för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="a742f-162">Status för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="a742f-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="a742f-163">Kategori för lagstadgade jobb</span><span class="sxs-lookup"><span data-stu-id="a742f-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="a742f-164">Kandidat att anställa och relaterade enheter och alternativuppsättningar</span><span class="sxs-lookup"><span data-stu-id="a742f-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="a742f-165">Exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="a742f-165">Example query:</span></span>

- [<span data-ttu-id="a742f-166">Exempelfråga för kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="a742f-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="a742f-167">Enheter:</span><span class="sxs-lookup"><span data-stu-id="a742f-167">Entities:</span></span>

- [<span data-ttu-id="a742f-168">Kandidat att anställa</span><span class="sxs-lookup"><span data-stu-id="a742f-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="a742f-169">Person</span><span class="sxs-lookup"><span data-stu-id="a742f-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="a742f-170">Personens utbildning</span><span class="sxs-lookup"><span data-stu-id="a742f-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="a742f-171">Personens yrkeserfarenhet</span><span class="sxs-lookup"><span data-stu-id="a742f-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="a742f-172">Personens adress</span><span class="sxs-lookup"><span data-stu-id="a742f-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="a742f-173">Partens kontakt</span><span class="sxs-lookup"><span data-stu-id="a742f-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="a742f-174">Personens färdighet</span><span class="sxs-lookup"><span data-stu-id="a742f-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="a742f-175">Bedömningsnivå</span><span class="sxs-lookup"><span data-stu-id="a742f-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="a742f-176">Personens certifikat</span><span class="sxs-lookup"><span data-stu-id="a742f-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="a742f-177">Certifikattyp</span><span class="sxs-lookup"><span data-stu-id="a742f-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="a742f-178">Personkontroller</span><span class="sxs-lookup"><span data-stu-id="a742f-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="a742f-179">Kontrolltyper</span><span class="sxs-lookup"><span data-stu-id="a742f-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="a742f-180">Personens ID-nummer</span><span class="sxs-lookup"><span data-stu-id="a742f-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="a742f-181">Alternativuppsättningar:</span><span class="sxs-lookup"><span data-stu-id="a742f-181">Option sets:</span></span>

- [<span data-ttu-id="a742f-182">Resultat för integration av sökande</span><span class="sxs-lookup"><span data-stu-id="a742f-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="a742f-183">Tomt Ja nej</span><span class="sxs-lookup"><span data-stu-id="a742f-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="a742f-184">Slutförandestatus</span><span class="sxs-lookup"><span data-stu-id="a742f-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="a742f-185">Kontakttyp</span><span class="sxs-lookup"><span data-stu-id="a742f-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="a742f-186">Bas för utbildningskredit</span><span class="sxs-lookup"><span data-stu-id="a742f-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="a742f-187">Kön</span><span class="sxs-lookup"><span data-stu-id="a742f-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="a742f-188">Civilstånd</span><span class="sxs-lookup"><span data-stu-id="a742f-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="a742f-189">Månader under året</span><span class="sxs-lookup"><span data-stu-id="a742f-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="a742f-190">Nej Ja</span><span class="sxs-lookup"><span data-stu-id="a742f-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="a742f-191">Periodenhet</span><span class="sxs-lookup"><span data-stu-id="a742f-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="a742f-192">Kontrollfrekvens</span><span class="sxs-lookup"><span data-stu-id="a742f-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="a742f-193">Kontrollfrekvens genereras från</span><span class="sxs-lookup"><span data-stu-id="a742f-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="a742f-194">Typ av färdighetsnivå</span><span class="sxs-lookup"><span data-stu-id="a742f-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="a742f-195">Se även</span><span class="sxs-lookup"><span data-stu-id="a742f-195">See also</span></span>

[<span data-ttu-id="a742f-196">Rekrytera jobbkandidater</span><span class="sxs-lookup"><span data-stu-id="a742f-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="a742f-197">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="a742f-197">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="a742f-198">Använd webb-API för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="a742f-198">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="a742f-199">Skapa och uppdatera alternativuppsättningar med hjälp av webb-API:t</span><span class="sxs-lookup"><span data-stu-id="a742f-199">Create and update option sets using the Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]