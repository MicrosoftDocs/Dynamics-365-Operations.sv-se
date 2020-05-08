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
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9dd80415f33a4d671bdc2662704799775daad177
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010564"
---
# <a name="understand-date-and-time-fields"></a>Förstå datum och tidfält

**Datum- och tidsfält** är ett grundläggande begrepp i Dynamics 365 Human Resources. Det är viktigt att du förstår hur du arbetar med **datum och tid** i Dynamics 365 Human Resources-formulär, Common Data Service och externa källor.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält

**Datum och tidsfält** innehåller tidszonsinformation medan **Datumfält** inte gör det. **Datum**-fält visar samma information på alla platser. När du anger ett datum i ett **datum**-fält skriver personal samma datum till databasen.

När data visas i ett **datum- och tidsfält** justerar personal datum och tid baserat på användarens tidszon i formuläret **Användaralternativ** (**Gemensamma > Inställningar > Användaralternativ**). Datum- och tidsinformationen du anger i fältet kanske inte är densamma som den information som skrivs till databasen.

[![Formuläret Användaralternativ](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Förstå Datum och tidsfält i formulär 

När du anger data i ett **Datum- och tidsfält** visas de data som visas på skärmen inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time). Data i **Datum- och tidsfält** lagras alltid som UTC.

[![Formuläret Arbetare](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Förstå Datum och tidsfält i databasen 

När personal skriver ett värde för **Datum och tid** i databasen lagras data i UTC. På så sätt kan användarna se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.
 
I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum. Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post som skapas att bara visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.
  
I exemplet nedan blir medarbetarens anställning 000724 aktiva samtidigt oavsett tidszon. Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon. Båda refererar till samma tidpunkt och inte ett särskilt datum. 

[![Formuläret Arbetare](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Datum- och tidsdata i Data Management Framework, Excel Common Data Service och Power BI 

Data Management Framework, Excel-tillägget, Common Data Service och Power BI-rapporter är utformade för att samverka med data direkt på databasnivå. Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.  
 
Data för **Datum och tid** som skickas via DMF, Excel eller Common Data Service antas finnas i UTC av databasen. Detta kan skapa viss förvirring när värdet för **datum och tid** inte visas som förväntat eftersom användaren som visar data inte har tidszonen inställd på UTC. 
 
Samma sak kan hända när data exporteras. Data för **Datum och tid** i den exporterade DMF-entiteten kan vara olika sedan vad som visas i Dynamics-klienten. 
 
När du använder externa källor som DMF för att visa eller redigera data, är det viktigt att komma ihåg att värdena för **datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator, eller deras aktuella inställningar för tidszon. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exempel på samma post som visas i olika produktområden 

**Personal med användarens tidszon inställd på UTC**

[![Formuläret Arbetare](./media/worker-form3.png)](./media/worker-form3.png)

**Personal med användarens tidszon inställd på GMT +12:00** 

[![Formuläret Arbetare](./media/worker-form4.png)](./media/worker-form4.png)

**Excel via OData**

[![Excel via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-mellanlagring**

[![DMF-mellanlagring](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-export**

[![DMF-mellanlagring](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Common Data Service**

[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Se även

[Data för datum och tid](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Användarens prioriterade tidszoner](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 