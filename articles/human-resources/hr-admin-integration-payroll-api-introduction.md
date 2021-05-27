---
title: Introduktion till API för löneintegrering
description: Detta ämne beskriver API för löneintregrering i Dynamics 365 Human Resources.
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
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a7be5ad42642de48ffdb2731a1300a953c5ede4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022773"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="156a3-103">Introduktion till API för löneintegrering</span><span class="sxs-lookup"><span data-stu-id="156a3-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="156a3-104">Detta dokument beskriver API för löneintregrering i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="156a3-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="156a3-105">Med API:t kan du effektivisera kompletta integreringar mellan Personal och associerade lönesystem.</span><span class="sxs-lookup"><span data-stu-id="156a3-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="156a3-106">Den integrerade erfarenheten startar i Personal med medarbetarprofil, löne- och avdragsinformation och bidragsinformation.</span><span class="sxs-lookup"><span data-stu-id="156a3-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="156a3-107">När du anställer en medarbetare och anger den nödvändiga profil- och löneinformationen i Personal hämtar lönesystemet denna information i samband med bearbetning av löner.</span><span class="sxs-lookup"><span data-stu-id="156a3-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="156a3-108">Eventuella uppdateringar av medarbetar- eller löneinformationen kan också användas vid senare lönekörningar.</span><span class="sxs-lookup"><span data-stu-id="156a3-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Löneintegreringsflöde](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="156a3-110">För att aktivera integreringen lägger Personal till följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="156a3-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="156a3-111">Funktion för att markera en medarbetare som betalningsredo</span><span class="sxs-lookup"><span data-stu-id="156a3-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="156a3-112">Ett integrations-API som öppnar den nya funktionen för integrering av program</span><span class="sxs-lookup"><span data-stu-id="156a3-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="156a3-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="156a3-113">Microsoft Dataverse</span></span>

<span data-ttu-id="156a3-114">Detta API bygger på Microsoft Dataverse (tidigare Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="156a3-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="156a3-115">All RESTful-interaktion med denna API sker via webb-API för Microsoft Dataverse, som använder OData.</span><span class="sxs-lookup"><span data-stu-id="156a3-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="156a3-116">Detta API är en underuppsättning av webb-API för Dataverse.</span><span class="sxs-lookup"><span data-stu-id="156a3-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="156a3-117">Webb-API för Dataverse definierar egenskaper såsom autentisering, serviceavtal, batch, samtidighetskontroll och felhantering.</span><span class="sxs-lookup"><span data-stu-id="156a3-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="156a3-118">Mer allmän information om webb-API för Microsoft Dataverse finns här:</span><span class="sxs-lookup"><span data-stu-id="156a3-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="156a3-119">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="156a3-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="156a3-120">Använd webb-API för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="156a3-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="156a3-121">Utvecklarguide för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="156a3-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="156a3-122">Dokumentationen innehåller information och utvecklarvägledning för användning av webb-API för Dataverse, bland annat följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="156a3-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="156a3-123">Autentisera till Microsoft Dataverse med hjälp av webb-API:t</span><span class="sxs-lookup"><span data-stu-id="156a3-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="156a3-124">Utföra åtgärder med hjälp av webb-API:t</span><span class="sxs-lookup"><span data-stu-id="156a3-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="156a3-125">Använda Postman med webb-API:t</span><span class="sxs-lookup"><span data-stu-id="156a3-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="156a3-126">Använda ändringsspårning för att synkronisera data med externa system</span><span class="sxs-lookup"><span data-stu-id="156a3-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="156a3-127">Virtuella register för Personal i Dataverse</span><span class="sxs-lookup"><span data-stu-id="156a3-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="156a3-128">Slutpunkterna för API för löneintegrering använder plattformsfunktionerna för virtuellt register i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="156a3-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="156a3-129">Som standard distribueras inte de virtuella registren och deras associerade API-slutpunkter för Personal-miljöer, vilket låter organisationer avgöra vilka OData-slutpunkter som ska visas för miljön.</span><span class="sxs-lookup"><span data-stu-id="156a3-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="156a3-130">Om du vill använda API:t måste de virtuella registren för Personal-entiteterna genereras för miljön.</span><span class="sxs-lookup"><span data-stu-id="156a3-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="156a3-131">Information om hur du genererar virtuella register för API:et finns i [Konfigurera virtuella Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="156a3-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="156a3-132">Datamodell</span><span class="sxs-lookup"><span data-stu-id="156a3-132">Data model</span></span>

<span data-ttu-id="156a3-133">Följande diagram visar relationer inom API:t.</span><span class="sxs-lookup"><span data-stu-id="156a3-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="156a3-134">Flera typer har utländska nycklar till andra, befintliga entiteter i Personal som inte visas här.</span><span class="sxs-lookup"><span data-stu-id="156a3-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="156a3-135">Detta dokument innehåller information om entiteter som är specifika för löneintegreringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="156a3-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="156a3-136">Det finns emellertid många andra entiteter i webb-API:t för Dataverse för Personal som också kan vara relevanta för din integrering.</span><span class="sxs-lookup"><span data-stu-id="156a3-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="156a3-137">Vissa av dessa entiteter refereras till i relationer med sekundärnycklar eller navigeringsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="156a3-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![API-datamodell för löneintegrering](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="156a3-139">Lönemedarbetare och relaterade entiteter</span><span class="sxs-lookup"><span data-stu-id="156a3-139">Payroll employee and related entities</span></span>

<span data-ttu-id="156a3-140">Enheter:</span><span class="sxs-lookup"><span data-stu-id="156a3-140">Entities:</span></span>

- [<span data-ttu-id="156a3-141">Lönemedarbetare</span><span class="sxs-lookup"><span data-stu-id="156a3-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="156a3-142">Lönearbetarens adress</span><span class="sxs-lookup"><span data-stu-id="156a3-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="156a3-143">Kompensationsplan med fast lön</span><span class="sxs-lookup"><span data-stu-id="156a3-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="156a3-144">Lönebefattningsjobb</span><span class="sxs-lookup"><span data-stu-id="156a3-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="156a3-145">Lönebefattning</span><span class="sxs-lookup"><span data-stu-id="156a3-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="156a3-146">Se även</span><span class="sxs-lookup"><span data-stu-id="156a3-146">See also</span></span>

[<span data-ttu-id="156a3-147">Generera och granska lönelisteentiteter</span><span class="sxs-lookup"><span data-stu-id="156a3-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="156a3-148">Konfigurera Personalparametrar</span><span class="sxs-lookup"><span data-stu-id="156a3-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="156a3-149">Konfigurera delade Personalparametrar</span><span class="sxs-lookup"><span data-stu-id="156a3-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="156a3-150">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="156a3-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="156a3-151">Använd webb-API för Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="156a3-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]