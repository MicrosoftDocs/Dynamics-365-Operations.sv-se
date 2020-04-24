---
title: Transporthanteringsöversikt
description: Det här avsnittet innehåller en översikt över funktionen för transporthantering i Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3d8a34195edbae7daf1a9db4e236aad33f98d08
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201351"
---
# <a name="transportation-management-overview"></a>Transporthantering – översikt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över funktionen för transporthantering i Supply Chain Management.

Transporthantering låter dig använda företagets transporter och även identifiera leverantörs- och ruttlösningar för ingående och utgående order. Du kan till exempel identifiera det snabbaste flödet eller den minst kostsamma tariffen för en leverans. I tabellen nedan beskrivs de huvudsakliga scenarierna för att använda Transporthantering.

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
<td>Företagets egen flotta är tillgänglig för leverans/upphämtning och leveransavgifter skickas till kunder.</td>
<td>För utgående processer kan du använda transporthantering för att bestämma transportkostnaderna och skicka dem vidare till kunderna. Processen för avstämning av transportföretagets faktura krävs inte.</td>
</tr>
<tr class="odd">
<td>Företagets egen flotta är tillgänglig för leverans/upphämtning men leveransavgifter skickas inte till kunder, eftersom produktpriser inkluderar transport.</td>
<td>Många av transporthanteringsfunktionerna krävs inte. Du kan däremot använda transporthantering för att bestämma transporttarifferna och anpassa försäljningspriset efter detta.</td>
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

## <a name="planning-transportation-in-supply-chain-management"></a>Planera transporter i Supply Chain Management
I transporthantering, transportplaneringen baseras antingen på order eller på försändelserna som skapas baserat på dessa order. Försändelserna alltid finns någon gång i tiden men krävs inte för transportplanering. Överföringsorder är en del av det utgående scenariot och kan planeras tillsammans med försäljningsorder. 

![Lastuttag](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Ingående transport
När du beställer artiklar från en leverantör och artiklarna måste levereras till ditt lagerställe, kanske du vill ordna själva transporten av artiklarna. Du kan använda Supply Chain Management för att planera transporten och inleveransen av den ingående lasten. I bilden nedan visas affärsprocessflödet för planering av transport för en inkommande beläggning. 

![Affärsprocessflöde för transport av inkommande last](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Utgående transport
Du kan planera och bearbeta en utgående last för att skicka vissa artiklar från ett företags lager till en kund. Du kan använda Supply Chain Management för att planera transporten och leveransen av en utgående last. I bilden nedan visas affärsprocessflödet för planering och bearbetning av utgående beläggningar för leverans. 

![Planera och bearbeta utgående laster](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Lastuppbyggnad
Supply Chain Management innehåller en lastuppbyggnadsstrategi med namnet Volymbaserad lastuppbyggnadsstrategi. Denna strategi låter dig använda de angivna maximivärdena som specificerats för höjd och vikt i lastmallen eller så kan du åsidosätta inställningarna genom att ange nya värden. För att använda denna strategi, välj den i fältet **Lastuppbyggnadsstrategi** på snabbfliken **Inställningar** på sidan **Workbench för lastuppbyggnad**. Dessutom kan du lägga till dina egna uppbyggnadsstrategier genom att skapa en ny klass i programobjektträdet.



