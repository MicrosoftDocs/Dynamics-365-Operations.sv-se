---
title: Inaktivera regler som används i transaktionsvalideringsprocessen
description: Den här artikeln beskriver funktionen som inaktiverar transaktionsvalideringsregler i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884888"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Inaktivera regler som används i transaktionsvalideringsprocessen

[!include [banner](../includes/banner.md)]

Återförsäljare kan ha affärsscenarier och processer som är unika för dem. Därför gäller inte alla regler som ingår i valideringsprocessen för handelstransaktioner för alla återförsäljare. För att hantera skillnader innehåller Microsoft Dynamics 365 Commerce funktioner som kan användas för att inaktivera regler som inte är tillämpliga.

Visa en lista med regler som finns tillgängliga i miljöns transaktionsvalideringsprocess och visa status för varje regel genom att öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar** och välja fliken **Transaktionsvalidering**. Alla aktiverade regler används till att validera transaktioner under processen **Validera butikstransaktioner** och måste passera för att samla in och bokföra transaktioner på ett transaktionsutdrag.

Som standard är status för varje regel inställd på **Aktiverad**. Därför används alla regler för att validera butikstransaktioner innan de går att hämta till handelstransaktionsutdragen. Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**. Inaktiverade regler beaktas inte när transaktioner valideras under processen **Validera butikstransaktioner**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
