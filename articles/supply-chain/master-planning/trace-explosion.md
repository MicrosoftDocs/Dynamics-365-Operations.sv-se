---
title: Använd spårning för nedbrytning
description: Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75d994db80071c4ef9e23caf24cb4cadbc1473ad
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189902"
---
# <a name="use-tracing-for-explosion"></a>Använd spårning för nedbrytning

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan använda spårning för att undersöka orsakerna till resultatet av en ordernedbrytning.

Genom att aktivera spårning kan du visa information om vilka faktorer som bidrog till resultatet för nedbrytningen av en viss order. I följande exempel visas hur du kan använda spårningsinformationen:

-   Visa relationer mellan åtgärderna för planerade order för att optimera leveranskedjan och lagerreservationerna.
-   Visa relationer för order som redan har godkänts. Du kan fokusera på att automatiskt koppla härledda behov och sedan prioritera order mer exakt.
-   Simulera planläggningsresultat för att bestämma om planläggningsparametrarna är optimala.
-   Identifiera hur information, till exempel produktionsdatum, kvantiteter och prioritet för en order bestämts.

Du kan visa information om leveransplaner och åtgärder för en vald order. På sidan **Nedbrytning** finns spårningsinformation på fliken **Förklaring** i det övre fönstret. Spårning uppstår när du bryter ned en order. Om du vill börja spåra för ordern klickar du på **Uppdatera** och markerar kryssrutan **Aktivera spårning**. Du kan använda fältet **Sök text** för att söka i loggen efter specifik information. Sökresultatet markeras i trädet.

## <a name="additional-resources"></a>Ytterligare resurser

[Huvudplaner – översikt](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]