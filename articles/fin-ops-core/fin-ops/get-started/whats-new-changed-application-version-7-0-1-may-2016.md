---
title: Nyheter och ändringar i Dynamics AX programvaruversion 7.0.1 (maj 2016)
description: Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics AX programvaruversion 7.0.1. Den här versionen släpptes i maj 2016 och har en versionsnummer 7.0.1265.23014.
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 94cebad528facc5537226a3faa5ea9be8448092e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267213"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Nyheter och ändringar i AX programvaruversion 7.0.1 (maj 2016)

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics AX programvaruversion 7.0.1. Den här versionen släpptes i maj 2016 och har en versionsnummer 7.0.1265.23014.

## <a name="electronic-reporting-er"></a>Elektronisk rapportering (ER)

| Vad kan du göra? | Varför är detta viktigt? |
|------------------|------------------------|
| Konfigurera en dialogruta för körtid för att skapa elektronisk rapporteringsrapporter (ER), så att användaren kan markera valfria ekonomiska dimensioner. | Vid körning kan användaren markera flera ekonomiska dimensioner i dialogrutan för att köra en ER-rapport. Information om valda ekonomiska dimensioner visas i det elektroniska dokument som skapas. |
| Konfigurera åtkomst till flera ekonomiska dimensioner vid utformningen av en ER rapport, via en enda mappning till valfri datakälla. | Samma konfiguration för en ER-rapport kan användas för att skapa elektroniska dokument som innehåller transaktionsdata tillsammans med information om ekonomiska dimensioner, oavsett antalet ekonomiska dimensioner som antingen har valts av användaren eller som har konfigureras för den aktuella juridiska personen eller instansen. |
| Konfigurera en ER-rapport för att ange data i dynamiskt skapade kolumner i ett elektroniskt dokument som har skapats i OPENXML-kalkylbladsformat. | En ER-rapport kan överföra data till ett OPENXML-kalkylblad som skapas genom att kopiera kolumner horisontellt. Därför kan samma ER-rapportkonfiguration återanvändas för att skapa elektroniska dokument som har olika antal dynamiskt skapade kolumner. |
| Konfigurera ER-mål så att resultatet av ett utdataformat dirigeras till specifika mål: fil, E-post eller arkiv (Microsoft SharePoint-mapp eller Microsoft Azure Storage). | Tidigare visades en meddelanderuta som krävde en användaråtgärd för att spara eller öppna en fil när du körde en ER-konfiguration. Nu kan du förkonfigurera ett mål för varje formatkonfiguration och utdatakomponent (en mapp eller en fil) separat. Användare med rätt behörighet kan även ändra inställningar för mål vid körning. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>Kassa – Microsoft Dynamics AX Retail

| Vad kan du göra? | Varför är detta viktigt? |
|------------------|------------------------|
| Använd Google Chrome-webbläsare. | Återförsäljare kan nu starta molnbaserade kassor från Chrome-webbläsaren och utnyttja alla funktioner som finns i Microsoft Edge- och Internet Explorer-versionen av den molnbaserade kassan. |

## <a name="financial-reporting"></a>Ekonomisk rapportering

| Vad kan du göra? | Varför är detta viktigt? |
|------------------|------------------------|
| Återskapa ekonomiska rapporteringsdatamart. | När du flyttar databaser för Dynamics AX mellan olika miljöer eller gör andra invasiva ändringar i miljön kan ekonomiska rapporteringsdatabasen behöva återskapas. Ett Windows PowerShell-skript tillhandahålls nu för att återskapa databasen åt dig. |
| Du kan inte längre välja alternativ för rapportdesigner som inte är giltiga. | Flera rapportdesigneralternativ som användes i marknadsversionerna av Management Reporter gäller inte i den här versionen av Dynamics AX. De här alternativen har relaterats till ekonomisk rapportdesign, utleverans och länkning. De här alternativen har tagits bort från den ekonomiska rapportdesignen för att förhindra användarfel. |

## <a name="financial-management"></a>Ekonomisk styrning

| Vad kan du göra? | Varför är detta viktigt? |
|------------------|------------------------|
| Skapa betalningskontrollfiler för leverantörsreskontrabetalningar. | Betalningskontrollfiler kan skapas för att förhindra checkbedrägerier. |

## <a name="warehouse-and-production"></a>Lagerställe och produktion

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definiera en policy för lagerarbete som styr skapandet av arbete för en uppsättning produkter på särskilda platser.</td>
<td>Lagerställeprocesser inkluderar inte alltid arbete. Genom att använda den nya policyn för lagerarbete kan du förhindra att arbeten skapas för råmaterialhämtning och inlagring av färdiga varor för en uppsättning produkter på specifika platser.</td>
</tr>
<tr>
<td>Ange att en produktionsutleveransplatsen inte är registreringsskyltsstyrd.</td>
<td>Du kan nu ange att en produktutleveransplats inte är registreringsskyltsstyrd. Funktionen är exempelvis användbar när en överordnad tillverkningsorder rapporterar artiklar som färdiga direkt till en plats som fungerar som en produktionsinleveransplats för en underordnad tillverkningsorder.</td>
</tr>
<tr>
<td>Stöd för strukturer som innehåller artiklar med olika dimensioner av samma artikel.</td>
<td>När du använder en eller flera av produktdimensionerna i produktionen kan situationer uppstå då du vill producera en artikel utifrån en annan variant av samma artikel. Mer information finns i <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">den här bloggen</a>.</td>
</tr>
<tr>
<td>Produktionsorder med cirkulära strukturer på den första nivån av deras strukturer är undantagna från strukturlistenivåberäkning för materialresursplanering.</td>
<td>Det går inte att tilldela rätt strukturlistenivåer till produktvarianter för produktionsorder som orsaka loopar i strukturlistehierarkin.</td>
</tr>
<tr>
<td>Beräkna olika strukturlistenivåer för materialresursplanering och kostnadsberäkning:
<ul>
<li>För materialresursplanering beräknas strukturlistenivåer i den nya tabellen <strong>ReqItemLevel</strong>. Avslutade tillverkningsorder ignoreras i beräkningen.</li>
<li>För beräkning av produktionskostnaden beräknas strukturlistenivåer i <strong>InventTable</strong>. Avslutade tillverkningsorder inkluderas i beräkningen.</li>
</ul>
</td>
<td>
<ul>
<li>När du kör materialresursplanering, till exempel huvudplaneringsplanläggning och explosion, behöver enbart strukturlistenivåer som används för materialresursplanering beräknas. Det finns med andra ord ingen anledning att beräkna strukturlistenivåer som används för beräkning av produktionskostnader</li>
<li>När du kör kostnadsoperationer, till exempel lagerstängning, behöver enbart strukturlistenivåer som används för beräkning för produktionskostnader beräknas om.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ytterligare resurser

[Nyheter och ändringar på hemsidan för Ekonomi och drift](whats-new-changed.md)

[Nya eller uppdaterade uppgiftsguider (maj 2016)](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
