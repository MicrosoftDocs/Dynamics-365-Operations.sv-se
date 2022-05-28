---
title: Uppdatera spårning för införsel
description: I det här avsnittet beskrivs hur du ställer in och kör periodisk uppgift för Uppdateringsspårning vid införsel.
author: Weijiesa
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f02ba71b4eb32551cebc6cf160f0285eac8ae7ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673982"
---
# <a name="update-tracking-for-put-away"></a>Uppdatera spårning för införsel

[!include [banner](../includes/banner.md)]

Periodisk uppgift för *Uppdateringsspårning vid införsel* har utformats för att köras som ett återkommande batchjobb nattetid. Den identifierar vilka färder som tagit emot alla lagertransaktioner och vilka färder som inte har något värde för det faktiska slutdatumet. Det ställer sedan in det faktiska slutdatumet som innevarande datum efter behov.

*Containeraktiviteter* skapas för varje *del* av en resa för varje *leveranscontainer*. Dessa värden definieras av den resemall som väljs när en färd skapas. För varje containeraktivitetspost kan värden anges för fälten **Startdatum**, **Uppskattat slutdatum** och **Faktiskt slutdatum**. Fälten kan uppdateras när bekräftelse kommer att en del av resan har startat eller slutförts.

Vanligtvis tillhandahålls information som är relaterad till bekräftade datum av tredje part, som en fraktspeditör, eftersom dessa åtgärder underhålls utanför Microsoft Dynamics 365 Supply Chain Management. Information från en tredje part behöver dock inte spåra inleverans av varor från en del av resa till lagerstället (enligt markering vid varuinförsel). Därför kan spårning avgöras utifrån information i Dynamics 365 Supply Chain Management.

Följ dessa steg för att ställa in och köra periodisk uppgift för *Uppdateringsspårning vid införsel*:

1. Gå till **Hemtagningskostnad \> Periodiska uppgifter \> Uppdateringsspårning vid införsel**.
1. Ange följande fält i avsnittet **Parametrar** i dialogrutan **Uppdateringsspårning vid införsel**:

    - **Del** – Välj det unika ID-namnet/-numret för den del av en resa som du vill uppdatera spårning för. Det valda värdet måste representera färdens ankomst till lagerstället.
    - **Aktivitet** – Välj den aktivitet som utfördes under den valda delen. Dessa värden tilldelas per färdmallsrad i spårningscentret.

1. För att begränsa mängden poster som ska ingå i uppdateringen ska du välja knappen **Filter** på snabbfliken **Poster att inkludera**. En standard frågedialogruta visas där du kan definiera urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som för andra typer av frågor i Supply Chain Management. Fälten här är skrivskyddade och visar värden som är relaterade till frågan.
1. På snabbfliken **Kör i bakgrunden** ställer du in alternativ för batch och tidsplanering efter behov, på samma sätt som du kan göra för andra jobbtyper i Supply Chain Management.
1. Välj **OK** för att använda dina inställningar och för att köra eller tidsplanera uppdateringen.
