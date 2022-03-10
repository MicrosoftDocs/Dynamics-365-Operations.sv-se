---
title: Inaktivera regler som används i transaktionsvalideringsprocessen
description: Det här ämnet beskriver funktionen som inaktiverar transaktionsvalideringsregler i Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
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
ms.openlocfilehash: cdaea51b4c84e6a62f0eb9412315ae77b4c11503
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919537"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Inaktivera regler som används i transaktionsvalideringsprocessen

[!include [banner](../includes/banner.md)]

Återförsäljare kan ha affärsscenarier och processer som är unika för dem. Därför gäller inte alla regler som ingår i valideringsprocessen för handelstransaktioner för alla återförsäljare. För att hantera skillnader innehåller Microsoft Dynamics 365 Commerce funktioner som kan användas för att inaktivera regler som inte är tillämpliga.

Visa en lista med regler som finns tillgängliga i miljöns transaktionsvalideringsprocess och visa status för varje regel genom att öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar** och välja fliken **Transaktionsvalidering**. Alla aktiverade regler används till att validera transaktioner under processen **Validera butikstransaktioner** och måste passera för att samla in och bokföra transaktioner på ett transaktionsutdrag.

Som standard är status för varje regel inställd på **Aktiverad**. Därför används alla regler för att validera butikstransaktioner innan de går att hämta till handelstransaktionsutdragen. Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**. Inaktiverade regler beaktas inte när transaktioner valideras under processen **Validera butikstransaktioner**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
