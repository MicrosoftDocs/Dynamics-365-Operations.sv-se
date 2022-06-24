---
title: Förstå Datum- och tid-fält
description: Detta ämne förklarar vad som kan förväntas när du använder datum- och tidsfält används i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e314efa5ac08288bc7d00c197be59ba9decac203
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856321"
---
# <a name="understand-date-and-time-fields"></a>Förstå Datum- och tid-fält

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Fälten **Datum och tid** är ett grundläggande begrepp i Microsoft Dynamics 365 Human Resources. Det är viktigt att du förstår hur du arbetar med **Datum och tid**-data i på sidor, i Dataverse samt i externa resurser.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Förstå skillnaden mellan datatyperna Datum och Datum och tidsfält

Fälten **Datum och tid** innehåller tidszonsinformation, medan fältet **Datum** inte gör det. Fältet **Datum** visar samma information på alla platser. När du anger ett datum i ett **Datum**-fält skrivs samma datum till databasen.

När data visas i ett **Datum och tid**-fält justeras datum och tid beroende på användarens tidszon som valts på sidan **Användaralternativ** (**Gemensamt \> Inställningar \> Användaralternativ**). Datum- och tidsinformationen som du anger i fältet kanske inte är densamma som den information som skrivs till databasen.

[![Sidan Användaralternativ.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>Förstå Datum och tid-fält på sidor 

Den data för **Datum och tidsfält** som visas på skärmen är inte desamma som de data som lagras i databasen om användarens tidszon inte är inställd på UTC-tid (Coordinated Universal Time). Data i **Datum- och tidsfält** lagras alltid som UTC.

[![UTC-sida för arbetare.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Förstå Datum och tidsfält i databasen 

När ett värde för **Datum och tid** skrivs till databasen lagras uppgifterna som UTC. Användarna kan därför se alla data för **Datum och tid** i relation till tidszonen som har definierats i deras användaralternativ.
 
I exemplet ovan är starttiden en tidpunkt, inte ett särskilt datum. Genom att ändra tidszonen för den inloggade användaren från GMT +12:00 till GMT UTC kommer samma post att visa 04/30/2019 12:00:00 i stället för 05/01/2019 12:00:00.

I exemplet nedan blir medarbetarens anställning 000724 aktiv samtidigt oavsett tidszon. Medarbetaren aktiveras 04/30/2019 i GMT-zonen, som är samma som 05/01/2019 i GMT +12:00 tidszon. Båda refererar till samma tidpunkt och inte ett särskilt datum. 

[![GMT-sida för arbetare.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Datum- och tidsdata i Data Management Framework, Excel Dataverse och Power BI 

Data Management Framework (DMF), Excel-tillägget, Dataverse och Power BI-rapporter är alla utformade för att samverka med data direkt på databasnivå. Eftersom det inte finns någon klient för att justera data för **Datum och tid** till användarens tidszon är alla värden för **Datum och tid** i UTC, vilket kan leda till felaktiga antaganden när du anger eller visar data.
 
När data för **Datum och tid** skickas via DMF, Excel eller Dataverse antar databasen att den befinner sig i UTC. Om de användare som visar datan inte har sin respektive tidson inställd som UTC-tidszon visas emellertid inte inskickat värde för **Datum och tid** som förväntat, och användarna kan därför bli förvirrade. 
 
Samma sak kan hända när data exporteras. Data för **Datum och tid** i den exporterade DMF-entiteten kan variera i jämförelse med det som visas i Dynamics-klienten. 
 
När du använder externa källor som DMF för att visa eller redigera data är det viktigt att komma ihåg att värdena för **Datum och tid** betraktas som standard för UTC oavsett tidszonen för användarens dator eller deras aktuella användarinställningar för tidszon. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exempel på samma post som visas i olika produktområden 

**Personal med användarens tidszon inställd på UTC**

[![Medarbetarsida inställd på UTC.](./media/worker-form3.png)](./media/worker-form3.png)

**Personal med användarens tidszon inställd på GMT +12:00** 

[![Medarbetarsida inställd på GMT.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel via OData**

[![Excel via OData.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-mellanlagring**

[![DMF-mellanlagring.](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-export**

[![DMF-export.](./media/DMFExport.png)](./media/DMFExport.png)

**Excel via Dataverse**

[![Excel via Dataverse.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Se även

[Data för datum och tid](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Användarens prioriterade tidszoner](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
