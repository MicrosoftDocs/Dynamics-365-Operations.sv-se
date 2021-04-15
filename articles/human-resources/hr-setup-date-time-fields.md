---
title: Förstå datum och tidfält
description: Förstå vad som ska förväntas när datum- och tidsfält används i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: efda2b54f9228ac539e6ba2d18f85bf3ad15a6ff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802441"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="455fa-103">Förstå Datum- och tid-fält</span><span class="sxs-lookup"><span data-stu-id="455fa-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="455fa-104">**Datum- och tidsfält** är ett grundläggande begrepp i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="455fa-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="455fa-105">Det är viktigt att du förstår hur du arbetar med **Datum och tid**-data i formulär, Dataverse samt externa resurser.</span><span class="sxs-lookup"><span data-stu-id="455fa-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="455fa-106">Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält</span><span class="sxs-lookup"><span data-stu-id="455fa-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="455fa-107">**Datum och tidsfält** innehåller tidszonsinformation medan **Datumfält** inte gör det.</span><span class="sxs-lookup"><span data-stu-id="455fa-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="455fa-108">**Datum**-fält visar samma information på alla platser.</span><span class="sxs-lookup"><span data-stu-id="455fa-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="455fa-109">När du anger ett datum i ett **datum**-fält skriver personal samma datum till databasen.</span><span class="sxs-lookup"><span data-stu-id="455fa-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="455fa-110">När data visas i ett **datum- och tidsfält** justerar personal datum och tid baserat på användarens tidszon i formuläret **Användaralternativ** (**Gemensamma > Inställningar > Användaralternativ**).</span><span class="sxs-lookup"><span data-stu-id="455fa-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="455fa-111">Datum- och tidsinformationen du anger i fältet kanske inte är densamma som den information som skrivs till databasen.</span><span class="sxs-lookup"><span data-stu-id="455fa-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="455fa-112">[![Formuläret Användaralternativ](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="455fa-113">Förstå Datum och tidsfält i formulär</span><span class="sxs-lookup"><span data-stu-id="455fa-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="455fa-114">Den data för **Datum och tidsfält** som visas på skärmen är inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="455fa-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="455fa-115">Data i **Datum- och tidsfält** lagras alltid som UTC.</span><span class="sxs-lookup"><span data-stu-id="455fa-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="455fa-116">[![Medarbetarformulär UTC](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="455fa-117">Förstå Datum och tidsfält i databasen</span><span class="sxs-lookup"><span data-stu-id="455fa-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="455fa-118">När Personal skriver ett värde för **Datum och tid** i databasen, lagras datan i UTC.</span><span class="sxs-lookup"><span data-stu-id="455fa-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="455fa-119">På så sätt kan användarna se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="455fa-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="455fa-120">I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="455fa-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="455fa-121">Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post att visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="455fa-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="455fa-122">I exemplet nedan blir medarbetarens anställning 000724 aktiva samtidigt oavsett tidszon.</span><span class="sxs-lookup"><span data-stu-id="455fa-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="455fa-123">Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon.</span><span class="sxs-lookup"><span data-stu-id="455fa-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="455fa-124">Båda refererar till samma tidpunkt och inte ett särskilt datum.</span><span class="sxs-lookup"><span data-stu-id="455fa-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="455fa-125">[![Medarbetarformulär GMT](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="455fa-126">Datum- och tidsdata i Data Management Framework, Excel Dataverse och Power BI</span><span class="sxs-lookup"><span data-stu-id="455fa-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="455fa-127">Data Management Framework, Excel-tillägget, Dataverse och Power BI-rapporter är utformade för att samverka med data direkt på databasnivå.</span><span class="sxs-lookup"><span data-stu-id="455fa-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="455fa-128">Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.</span><span class="sxs-lookup"><span data-stu-id="455fa-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="455fa-129">Data för **Datum och tid** som skickas via DMF, Excel eller Dataverse antas finnas i UTC av databasen.</span><span class="sxs-lookup"><span data-stu-id="455fa-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="455fa-130">Detta kan skapa viss förvirring när värdet för **datum och tid** inte visas som förväntat eftersom användaren som visar data inte har tidszonen inställd på UTC.</span><span class="sxs-lookup"><span data-stu-id="455fa-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="455fa-131">Samma sak kan hända när data exporteras.</span><span class="sxs-lookup"><span data-stu-id="455fa-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="455fa-132">Data för **Datum och tid** i den exporterade DMF-entiteten kan variera i jämförelse med det som visas i Dynamics-klienten.</span><span class="sxs-lookup"><span data-stu-id="455fa-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="455fa-133">När du använder externa källor som DMF för att visa eller redigera data är det viktigt att komma ihåg att värdena för **Datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator eller deras aktuella användarinställningar för tidszon.</span><span class="sxs-lookup"><span data-stu-id="455fa-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="455fa-134">Exempel på samma post som visas i olika produktområden</span><span class="sxs-lookup"><span data-stu-id="455fa-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="455fa-135">**Personal med användarens tidszon inställd på UTC**</span><span class="sxs-lookup"><span data-stu-id="455fa-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="455fa-136">[![Medarbetarformulär inställt på UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="455fa-137">**Personal med användarens tidszon inställd på GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="455fa-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="455fa-138">[![Medarbetarformulär inställt på GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="455fa-139">**Excel via OData**</span><span class="sxs-lookup"><span data-stu-id="455fa-139">**Excel Via OData**</span></span>

<span data-ttu-id="455fa-140">[![Excel via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="455fa-141">**DMF-mellanlagring**</span><span class="sxs-lookup"><span data-stu-id="455fa-141">**DMF Staging**</span></span>

<span data-ttu-id="455fa-142">[![DMF-mellanlagring](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="455fa-143">**DMF-export**</span><span class="sxs-lookup"><span data-stu-id="455fa-143">**DMF Export**</span></span>

<span data-ttu-id="455fa-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="455fa-145">**Excel via Dataverse**</span><span class="sxs-lookup"><span data-stu-id="455fa-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="455fa-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="455fa-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="455fa-147">Se även</span><span class="sxs-lookup"><span data-stu-id="455fa-147">See also</span></span>

[<span data-ttu-id="455fa-148">Data för datum och tid</span><span class="sxs-lookup"><span data-stu-id="455fa-148">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="455fa-149">Användarens prioriterade tidszoner</span><span class="sxs-lookup"><span data-stu-id="455fa-149">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]