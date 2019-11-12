---
title: Inaktivera regler i konsekvenskontrollen för butikstransaktioner
description: I det här avsnittet beskrivs funktionen för att avaktivera regler för konsekvenskontroll av butikstransaktioner som infördes i Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586307"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Inaktivera regler i konsekvenskontrollen för butikstransaktioner 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Återförsäljare kan ha affärsscenarier och processer som är unika för dem. Därför gäller inte alla regler som ingår som standard i konsekvenskontrollen av butikstransaktioner för alla detaljhandlare. För att hantera skillnader innehåller Microsoft Dynamics 365 Retail funktioner som kan användas för att inaktivera regler som inte är tillämpliga.

Om du vill visa en lista över regler som är tillgängliga i konsekvenskontrollen av butikstransaktioner i din miljö, och se status för varje regel, gå till **Butik \> Administrationsinställningar \> Parametrar \> Butiksparametrar**, och välj fliken **Transaktionsvalidering**.

Som standard är status för varje regel inställd på **Aktiverad**. Därför används alla regler för att validera butikstransaktioner innan de hämtas till butiksutdragen. Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**. Inaktiverade regler beaktas inte när butikstransaktioner valideras under utdragsberäkningsprocessen.

Om du vill kringgå hela valideringsprocessen, oavsett vilka regler som aktiveras, går du till **Butik \> Administrationsinställningar \> Parametrar \> Butiksparametrar**, och sedan, på fliken **Transaktionsvalidering** ställer du in valet för **Inaktivera konsekvenskontroll för butikstransaktioner** på **Ja**. När alternativet är inställt på **Nej** kan det inte ställas tillbaka till **Ja** från användargränssnittet (UI).
