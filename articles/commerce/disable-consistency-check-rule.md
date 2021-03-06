---
title: Inaktivera regler i konsekvenskontrollen för butikstransaktioner
description: Det här avsnittet beskriver funktionen som inaktiverar regler för konsekvenskontroll av transaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: ce2abe7e15773edc3122a1bfdf40f3b830e8790e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792905"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Inaktivera regler i konsekvenskontrollen för butikstransaktioner 

[!include [banner](../includes/banner.md)]

Återförsäljare kan ha affärsscenarier och processer som är unika för dem. Därför gäller inte alla regler som ingår som standard i konsekvenskontrollen av handelstransaktioner för alla detaljhandlare. För att hantera skillnader innehåller Microsoft Dynamics 365 Commerce funktioner som kan användas för att inaktivera regler som inte är tillämpliga.

Om du vill visa en lista över regler som är tillgängliga i konsekvenskontrollen av butikstransaktioner i din miljö, och se status för varje regel, gå till **Retail och Commerce \> Administrationsinställningar \> Parametrar \> Commerce-parametrar**, och välj fliken **Transaktionsvalidering**.

Som standard är status för varje regel inställd på **Aktiverad**. Därför används alla regler för att validera butikstransaktioner innan de hämtas till butiksutdragen. Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**. Inaktiverade regler beaktas inte när transaktioner valideras under utdragsberäkningsprocessen.

Om du vill kringgå hela valideringsprocessen, oavsett vilka regler som aktiveras, går du till **Retail och Commerce \> Administrationsinställningar \> Parametrar \> Commerce-parametrar**, och sedan, på fliken **Transaktionsvalidering** ställer du in valet för **Inaktivera konsekvenskontroll för Commerce-transaktioner** på **Ja**. När alternativet är inställt på **Nej** kan det inte ställas tillbaka till **Ja** från användargränssnittet (UI).


[!INCLUDE[footer-include](../includes/footer-banner.md)]