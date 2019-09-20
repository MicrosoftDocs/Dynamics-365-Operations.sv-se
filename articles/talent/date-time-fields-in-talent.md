---
title: Arbeta med datum och tid i Microsoft Dynamics 365 for Talent
description: Förstå vad som ska förväntas när datum- och tidsfält används i Microsoft Dynamics 365 for Talent. Få klarhet i vad du ska förvänta dig när du interagerar med datum- och tidsformulär i Dynamics 365 for Talent, en extern källa eller Common Data Service.
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
ms.openlocfilehash: b4c652992272ed1a5aecbb4c78f0d11f077149d1
ms.sourcegitcommit: 46bded82aa072adfedcf443629c2adc69f512c09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/26/2019
ms.locfileid: "1791232"
---
# <a name="date-and-time-fields-in-talent"></a>Datum och tidfält i Talent

[!include [banner](includes/banner.md)]

**Datum- och tidsfält** är ett grundläggande begrepp i Dynamics 365 for Talent. Det är viktigt att du förstår hur du arbetar med data för **datum och tid** i ett Dynamics 365-formulär, Common Data Service och externa källor.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält

**Datum och tidsfält** innehåller tidszonsinformation medan **Datumfält** inte gör det. **Datum**-fält visar samma information på alla platser. När du anger ett datum i ett **datum**-fält skriver Talent samma datum till databasen.

När data visas i ett **datum- och tidsfält** justerar Talent datum och tid baserat på användarens tidszon i formuläret **Användaralternativ** (**Gemensamma > Inställningar > Användaralternativ**). Datum- och tidsinformationen du anger i fältet kanske inte är densamma som den information som skrivs till databasen.

[![Formuläret Användaralternativ](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Förstå Datum och tidsfält i formulär 

När du anger data i ett **Datum- och tidsfält** visas de data som visas på skärmen inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time). Data i **Datum- och tidsfält** lagras alltid som UTC.

[![Formuläret Arbetare](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Förstå Datum och tidsfält i databasen 

När Talent skriver ett värde för **Datum och tid** i databasen lagras data i UTC. På så sätt kan användarna se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.
 
I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum. Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post som skapas att bara visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.
  
I exemplet nedan blir medarbetarens anställning 000724 aktiva samtidigt oavsett tidszon. Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon. Båda refererar till samma tidpunkt och inte ett särskilt datum. 

[![Formuläret Arbetare](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Datum- och tidsdata i Data Management Framework, Excel Common Data Service och Power BI 

Data Management Framework, Excel-tillägget, Common Data Service och Power BI-rapporter är utformade för att samverka med data direkt på databasnivå. Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.  
 
Data för **Datum och tid** som skickas via DMF, Excel eller Common Data Service antas finnas i UTC av databasen. Detta kan skapa viss förvirring när värdet för **datum och tid** inte visas som förväntat eftersom användaren som visar data inte har tidszonen inställd på UTC. 
 
Samma sak kan hända när data exporteras. Data för **Datum och tid** i den exporterade DMF-entiteten kan vara olika sedan vad som visas i Dynamics-klienten. 
 
När du använder externa källor som DMF för att visa eller redigera data, är det viktigt att komma ihåg att värdena för **datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator, eller deras aktuella inställningar för tidszon. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exempel på samma post som visas i olika produktområden 

**Talent med användarens tidszon inställd på UTC**

[![Formuläret Arbetare](./media/worker-form3.png)](./media/worker-form3.png)

**Talent med användarens tidszon inställd på GMT +12:00** 

[![Formuläret Arbetare](./media/worker-form4.png)](./media/worker-form4.png)

**Excel via OData**

[![Excel via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-mellanlagring**

[![DMF-mellanlagring](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-export**

[![DMF-mellanlagring](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Common Data Service**

[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>Se även

[Data för datum och tid](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Användarens prioriterade tidszoner](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
