---
title: Förstå datum och tidfält
description: Förstå vad som ska förväntas när datum- och tidsfält används i Microsoft Dynamics 365 Human Resources. Få klarhet i vad du ska förvänta dig när du interagerar med datum- och tidsformulär i personal, en extern källa eller Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: be1e28d0b842184ce3c4f7bd9748f5e76ac67489
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430105"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="cc6f5-104">Förstå datum och tidfält</span><span class="sxs-lookup"><span data-stu-id="cc6f5-104">Understand Date and Time fields</span></span>

<span data-ttu-id="cc6f5-105">**Datum- och tidsfält** är ett grundläggande begrepp i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="cc6f5-106">Det är viktigt att du förstår hur du arbetar med **datum och tid** i Dynamics 365 Human Resources-formulär, Common Data Service och externa källor.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-106">It's important to understand how to work with **Date and Time** data in Dynamics 365 Human Resources forms, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="cc6f5-107">Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält</span><span class="sxs-lookup"><span data-stu-id="cc6f5-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="cc6f5-108">**Datum och tidsfält** innehåller tidszonsinformation medan **Datumfält** inte gör det.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="cc6f5-109">**Datum**-fält visar samma information på alla platser.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="cc6f5-110">När du anger ett datum i ett **datum**-fält skriver personal samma datum till databasen.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-110">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="cc6f5-111">När data visas i ett **datum- och tidsfält** justerar personal datum och tid baserat på användarens tidszon i formuläret **Användaralternativ** (**Gemensamma > Inställningar > Användaralternativ**).</span><span class="sxs-lookup"><span data-stu-id="cc6f5-111">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="cc6f5-112">Datum- och tidsinformationen du anger i fältet kanske inte är densamma som den information som skrivs till databasen.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="cc6f5-113">[![Formuläret Användaralternativ](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="cc6f5-114">Förstå Datum och tidsfält i formulär</span><span class="sxs-lookup"><span data-stu-id="cc6f5-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="cc6f5-115">När du anger data i ett **Datum- och tidsfält** visas de data som visas på skärmen inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="cc6f5-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="cc6f5-116">Data i **Datum- och tidsfält** lagras alltid som UTC.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="cc6f5-117">[![Formuläret Arbetare](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="cc6f5-118">Förstå Datum och tidsfält i databasen</span><span class="sxs-lookup"><span data-stu-id="cc6f5-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="cc6f5-119">När personal skriver ett värde för **Datum och tid** i databasen lagras data i UTC.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-119">When Human Resources writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="cc6f5-120">På så sätt kan användarna se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="cc6f5-121">I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="cc6f5-122">Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post som skapas att bara visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="cc6f5-123">I exemplet nedan blir medarbetarens anställning 000724 aktiva samtidigt oavsett tidszon.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="cc6f5-124">Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="cc6f5-125">Båda refererar till samma tidpunkt och inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="cc6f5-126">[![Formuläret Arbetare](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="cc6f5-127">Datum- och tidsdata i Data Management Framework, Excel Common Data Service och Power BI</span><span class="sxs-lookup"><span data-stu-id="cc6f5-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="cc6f5-128">Data Management Framework, Excel-tillägget, Common Data Service och Power BI-rapporter är utformade för att samverka med data direkt på databasnivå.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="cc6f5-129">Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="cc6f5-130">Data för **Datum och tid** som skickas via DMF, Excel eller Common Data Service antas finnas i UTC av databasen.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="cc6f5-131">Detta kan skapa viss förvirring när värdet för **datum och tid** inte visas som förväntat eftersom användaren som visar data inte har tidszonen inställd på UTC.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="cc6f5-132">Samma sak kan hända när data exporteras.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="cc6f5-133">Data för **Datum och tid** i den exporterade DMF-entiteten kan vara olika sedan vad som visas i Dynamics-klienten.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="cc6f5-134">När du använder externa källor som DMF för att visa eller redigera data, är det viktigt att komma ihåg att värdena för **datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator, eller deras aktuella inställningar för tidszon.</span><span class="sxs-lookup"><span data-stu-id="cc6f5-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="cc6f5-135">Exempel på samma post som visas i olika produktområden</span><span class="sxs-lookup"><span data-stu-id="cc6f5-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="cc6f5-136">**Personal med användarens tidszon inställd på UTC**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-136">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="cc6f5-137">[![Formuläret Arbetare](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="cc6f5-138">**Personal med användarens tidszon inställd på GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-138">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="cc6f5-139">[![Formuläret Arbetare](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="cc6f5-140">**Excel via OData**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-140">**Excel Via OData**</span></span>

<span data-ttu-id="cc6f5-141">[![Excel via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="cc6f5-142">**DMF-mellanlagring**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-142">**DMF Staging**</span></span>

<span data-ttu-id="cc6f5-143">[![DMF-mellanlagring](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="cc6f5-144">**DMF-export**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-144">**DMF Export**</span></span>

<span data-ttu-id="cc6f5-145">[![DMF-mellanlagring](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="cc6f5-146">**Excel via Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="cc6f5-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="cc6f5-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="cc6f5-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="cc6f5-148">Se även</span><span class="sxs-lookup"><span data-stu-id="cc6f5-148">See also</span></span>

[<span data-ttu-id="cc6f5-149">Data för datum och tid</span><span class="sxs-lookup"><span data-stu-id="cc6f5-149">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="cc6f5-150">Användarens prioriterade tidszoner</span><span class="sxs-lookup"><span data-stu-id="cc6f5-150">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
