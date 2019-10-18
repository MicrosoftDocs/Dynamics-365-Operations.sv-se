---
title: Arbeta med datum och tid i Microsoft Dynamics 365 Talent
description: Förstå vad som ska förväntas när datum- och tidsfält används i Microsoft Dynamics 365 Talent. Få klarhet i vad du ska förvänta dig när du interagerar med datum- och tidsformulär i Talent, en extern källa eller Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
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
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a1d1a47bfe6bd58b1e1a0d4d46c2133f3bf48ad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2007977"
---
# <a name="date-and-time-fields-in-talent"></a><span data-ttu-id="3f60b-104">Datum och tidfält i Talent</span><span class="sxs-lookup"><span data-stu-id="3f60b-104">Date and Time fields in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3f60b-105">**Datum- och tidsfält** är ett grundläggande begrepp i Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="3f60b-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Talent.</span></span> <span data-ttu-id="3f60b-106">Det är viktigt att du förstår hur du arbetar med data för **datum och tid** i ett Dynamics 365-formulär, Common Data Service och externa källor.</span><span class="sxs-lookup"><span data-stu-id="3f60b-106">It's important to understand how to work with **Date and Time** data in a Dynamics 365 form, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="3f60b-107">Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält</span><span class="sxs-lookup"><span data-stu-id="3f60b-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="3f60b-108">**Datum och tidsfält** innehåller tidszonsinformation medan **Datumfält** inte gör det.</span><span class="sxs-lookup"><span data-stu-id="3f60b-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="3f60b-109">**Datum**-fält visar samma information på alla platser.</span><span class="sxs-lookup"><span data-stu-id="3f60b-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="3f60b-110">När du anger ett datum i ett **datum**-fält skriver Talent samma datum till databasen.</span><span class="sxs-lookup"><span data-stu-id="3f60b-110">When you enter a date into a **Date** field, Talent writes that same date to the database.</span></span>

<span data-ttu-id="3f60b-111">När data visas i ett **datum- och tidsfält** justerar Talent datum och tid baserat på användarens tidszon i formuläret **Användaralternativ** (**Gemensamma > Inställningar > Användaralternativ**).</span><span class="sxs-lookup"><span data-stu-id="3f60b-111">When displaying data in a **Date and Time** field, Talent adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="3f60b-112">Datum- och tidsinformationen du anger i fältet kanske inte är densamma som den information som skrivs till databasen.</span><span class="sxs-lookup"><span data-stu-id="3f60b-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="3f60b-113">[![Formuläret Användaralternativ](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="3f60b-114">Förstå Datum och tidsfält i formulär</span><span class="sxs-lookup"><span data-stu-id="3f60b-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="3f60b-115">När du anger data i ett **Datum- och tidsfält** visas de data som visas på skärmen inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="3f60b-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3f60b-116">Data i **Datum- och tidsfält** lagras alltid som UTC.</span><span class="sxs-lookup"><span data-stu-id="3f60b-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="3f60b-117">[![Formuläret Arbetare](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="3f60b-118">Förstå Datum och tidsfält i databasen</span><span class="sxs-lookup"><span data-stu-id="3f60b-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="3f60b-119">När Talent skriver ett värde för **Datum och tid** i databasen lagras data i UTC.</span><span class="sxs-lookup"><span data-stu-id="3f60b-119">When Talent writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="3f60b-120">På så sätt kan användarna se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="3f60b-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="3f60b-121">I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="3f60b-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="3f60b-122">Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post som skapas att bara visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="3f60b-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="3f60b-123">I exemplet nedan blir medarbetarens anställning 000724 aktiva samtidigt oavsett tidszon.</span><span class="sxs-lookup"><span data-stu-id="3f60b-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="3f60b-124">Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon.</span><span class="sxs-lookup"><span data-stu-id="3f60b-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="3f60b-125">Båda refererar till samma tidpunkt och inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="3f60b-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="3f60b-126">[![Formuläret Arbetare](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="3f60b-127">Datum- och tidsdata i Data Management Framework, Excel Common Data Service och Power BI</span><span class="sxs-lookup"><span data-stu-id="3f60b-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="3f60b-128">Data Management Framework, Excel-tillägget, Common Data Service och Power BI-rapporter är utformade för att samverka med data direkt på databasnivå.</span><span class="sxs-lookup"><span data-stu-id="3f60b-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="3f60b-129">Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.</span><span class="sxs-lookup"><span data-stu-id="3f60b-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="3f60b-130">Data för **Datum och tid** som skickas via DMF, Excel eller Common Data Service antas finnas i UTC av databasen.</span><span class="sxs-lookup"><span data-stu-id="3f60b-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="3f60b-131">Detta kan skapa viss förvirring när värdet för **datum och tid** inte visas som förväntat eftersom användaren som visar data inte har tidszonen inställd på UTC.</span><span class="sxs-lookup"><span data-stu-id="3f60b-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="3f60b-132">Samma sak kan hända när data exporteras.</span><span class="sxs-lookup"><span data-stu-id="3f60b-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="3f60b-133">Data för **Datum och tid** i den exporterade DMF-entiteten kan vara olika sedan vad som visas i Dynamics-klienten.</span><span class="sxs-lookup"><span data-stu-id="3f60b-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="3f60b-134">När du använder externa källor som DMF för att visa eller redigera data, är det viktigt att komma ihåg att värdena för **datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator, eller deras aktuella inställningar för tidszon.</span><span class="sxs-lookup"><span data-stu-id="3f60b-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="3f60b-135">Exempel på samma post som visas i olika produktområden</span><span class="sxs-lookup"><span data-stu-id="3f60b-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="3f60b-136">**Talent med användarens tidszon inställd på UTC**</span><span class="sxs-lookup"><span data-stu-id="3f60b-136">**Talent with user time zone set to UTC**</span></span>

<span data-ttu-id="3f60b-137">[![Formuläret Arbetare](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="3f60b-138">**Talent med användarens tidszon inställd på GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="3f60b-138">**Talent with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="3f60b-139">[![Formuläret Arbetare](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="3f60b-140">**Excel via OData**</span><span class="sxs-lookup"><span data-stu-id="3f60b-140">**Excel Via OData**</span></span>

<span data-ttu-id="3f60b-141">[![Excel via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="3f60b-142">**DMF-mellanlagring**</span><span class="sxs-lookup"><span data-stu-id="3f60b-142">**DMF Staging**</span></span>

<span data-ttu-id="3f60b-143">[![DMF-mellanlagring](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="3f60b-144">**DMF-export**</span><span class="sxs-lookup"><span data-stu-id="3f60b-144">**DMF Export**</span></span>

<span data-ttu-id="3f60b-145">[![DMF-mellanlagring](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="3f60b-146">**Excel via Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="3f60b-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="3f60b-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="3f60b-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

### <a name="see-also"></a><span data-ttu-id="3f60b-148">Se även</span><span class="sxs-lookup"><span data-stu-id="3f60b-148">See also</span></span>

[<span data-ttu-id="3f60b-149">Data för datum och tid</span><span class="sxs-lookup"><span data-stu-id="3f60b-149">Date and time data</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="3f60b-150">Användarens prioriterade tidszoner</span><span class="sxs-lookup"><span data-stu-id="3f60b-150">User preferred time zones</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
