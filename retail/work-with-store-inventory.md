---
title: Hantera butikslager
description: "Den här artikeln beskrivs vilka typer av dokument som du kan använda för att hantera lager."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Hantera butikslager

Den här artikeln beskrivs vilka typer av dokument som du kan använda för att hantera lager.

Du kan använda följande typer av dokument för att hantera organisationens lager.

## <a name="purchase-orders"></a>Inköpsorder
Inköpsorder skapas på huvudkontoret. Om ett lagerställe retail ingår i inköpsorderrubriken, inlevereras ordern till arkivet med Modern POS (MOPS) eller molnbaserad kassa i Microsoft Dynamics 365 för verksamhet – Retail. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret, kvantiteter som tagits emot i butiken visas i Dynamics 365 för operationer i den **Inleverera nu** på inköpsordern.

## <a name="transfer-orders"></a>Överföringsorder
En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. Överföringsordern visas då i butiken som en begäran om plockning i MOPS eller molnbaserad kassa. När de kvantiteter som begärts plockas de åtagit sig och skickas till huvudkontoret. På huvudkontoret, hur många artiklar som har plockats i butiken visas i Dynamics 365 för operationer i den **Skeppa nu** på överföringsordern. En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. Överföringsordern visas då i butiken som tar emot begäran i MOPS eller molnbaserad kassa. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret, kvantiteter som tagits emot i butiken visas i Dynamics 365 för operationer i den **Inleverera nu** på överföringsordern.

## <a name="stock-counts"></a>Lagerinventeringar
Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade. Tidsplanerad inventering initieras på huvudkontoret och anger vilka artiklar som måste inventeras. Huvudkontoret skapar ett inventeringsdokument kan tas emot i butiken, där kvantiteterna som faktiskt lager behållning registreras i MOPS eller molnbaserad kassa. Ej tidsplanerade inventeringar initieras i butiken och kvantiteterna som faktiskt lager behållning uppdateras MOPS eller molnbaserad kassa. Till skillnad från tidsplanerade inventeringar har icke tidsplanerade inventeringar inte en fördefinierad lista över artiklar. När en lagerinventering oavsett typ utförs utfästs den och skickas till huvudkontoret. På huvudkontoret valideras och bokförs inventeringen.




