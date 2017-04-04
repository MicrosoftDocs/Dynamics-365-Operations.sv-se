---
title: "Transporthanteringsöversikt"
description: "I det här avsnittet finns en översikt över transporthanteringsfunktionen i Microsoft Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3136fd95c4c56495a391668d6c854a6ae1e36479
ms.lasthandoff: 03/31/2017


---

# <a name="transportation-management-overview"></a>Transporthanteringsöversikt

I det här avsnittet finns en översikt över transporthanteringsfunktionen i Microsoft Dynamics 365 for Operations.

Transporthantering låter dig hantera företagets transporter och även identifiera leverantörs- och ruttlösningar för ingående och utgående order. Du kan till exempel identifiera det snabbaste flödet eller den minst kostsamma tariffen för en leverans. I tabellen nedan beskrivs de huvudsakliga scenarierna för att använda Transporthantering i Microsoft Dynamics 365 for Operations

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Hur transporthantering kan hjälpa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Använd externa logistikleverantörer för transportaktiviteter.</td>
<td>Använd transporthantering för ingående och/eller utgående transporter.</td>
</tr>
<tr class="even">
<td>Företagets egen flotta är tillgänglig för leverans/upphämtning och leveransavgifter skickas till kunder.</td>
<td>För utgående processer kan du använda transporthantering för att bestämma transportkostnaderna och skicka dem vidare till kunderna. Processen för avstämning av transportföretagets faktura krävs inte.</td>
</tr>
<tr class="odd">
<td>Företagets egen flotta är tillgänglig för leverans/upphämtning men leveransavgifter skickas inte till kunder, eftersom produktpriser inkluderar transport.</td>
<td>Många av transporthanteringsfunktionerna krävs inte. Du kan däremot använda transporthantering för att bestämma transporttarifferna och anpassa försäljningspriset efter detta.</td>
</tr>
<tr class="even">
<td>Logistiktjänst tillhandahålls av en annan juridisk person inom samma företag.</td>
<td><ul>
<li>Du kan använda transporthantering genom att hantera den andra juridiska personen som alla andra transportföretag. Du kan inte automatisera de ekonomiska transaktionerna mellan juridiska personer. Därför måste du hantera dessa transaktioner manuellt (exempelvis genom att skapa en inköpsorder).</li>
<li>I den juridiska person som tillhandahåller logistiktjänsterna, transporthantering kan användas för att bestämma transporttariffer.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-dynamics-365-for-operations"></a>Planera transporter i Dynamics 365 for Operations
I transporthantering, transportplaneringen baseras antingen på order eller på försändelserna som skapas baserat på dessa order. Försändelserna alltid finns någon gång i tiden men krävs inte för transportplanering. Överföringsorder är en del av det utgående scenariot och kan planeras tillsammans med försäljningsorder. 

![Läs in ritningen](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Ingående transport
När du beställer artiklar från en leverantör och artiklarna måste levereras till lagret, kanske du vill ordna transporten av artiklarna själv. Du kan använda Dynamics 365 för att planera transporter och mottagande av inkommande belastningen. I bilden nedan visas affärsprocessflödet för planering av transport för en inkommande beläggning. 

![Affärsprocessflöde för transport av inkommande last](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Utgående transport
Du kan planera och bearbeta en utgående last för att skicka vissa artiklar från ett företags lager till en kund. Du kan använda Dynamics 365 for Operations för att planera transporten och leveransen av en utgående last. I bilden nedan visas affärsprocessflödet för planering och bearbetning av utgående beläggningar för leverans. 

![Planering och bearbeta utgående läses in](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Lastuppbyggnad
Dynamics 365 for Operations innehåller en lastuppbyggnadsstrategi med namnet Volymbaserad lastuppbyggnadsstrategi. Denna strategi låter dig använda de angivna maximivärdena som specificerats för höjd och vikt i lastmallen eller så kan du åsidosätta inställningarna genom att ange nya värden. För att använda denna strategi, välj den i fältet **Lastuppbyggnadsstrategi** på snabbfliken **Inställningar** på sidan **Workbench för lastuppbyggnad**. Dessutom kan du lägga till dina egna uppbyggnadsstrategier genom att skapa en ny klass i programobjektträdet.


