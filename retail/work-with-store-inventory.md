---
title: Hantera butikslager
description: "Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 42091a5ec94bae3015fd9afca3ddcf1ef24f6eb4
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="manage-store-inventory"></a>Hantera butikslager

[!include[banner](includes/banner.md)]


Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.

Du kan använda följande typer av dokument för att hantera organisationens lager.

## <a name="purchase-orders"></a>Inköpsorder
Inköpsorder skapas på huvudkontoret. Om ett lagerställe ingår i inköpsorderrubriken kan ordern tas emot i butiken med hjälp av Modern POS (MOPS) eller Cloud POS i Microsoft Dynamics 365 for Retail. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som togs emot i butiken i Dynamics 365 for Retail i fältet **Inleverera nu** på inköpsordern.

## <a name="transfer-orders"></a>Överföringsorder
En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. I det här fallet visas överföringsordern i butiken som en plockningsförfrågan i MOPS eller i Cloud POS. När de kvantiteter som förfrågats har plockats, utfästs de och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som plockades i butiken i Dynamics 365 for Retail i fältet **Leverera nu** på överföringsordern. En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. I det här fallet visas överföringsordern i butiken som en inleveransförfrågan i MOPS eller i Cloud POS. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som togs emot i butiken i Dynamics 365 for Retail i fältet **Inleverera nu** på inköpsordern.

## <a name="stock-counts"></a>Lagerinventeringar
Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade. Tidsplanerad inventering initieras på huvudkontoret och anger vilka artiklar som måste inventeras. Huvudkontoret skapar ett inventeringsdokument som kan inlevereras till butiken, där de faktiska lagerkvantiteterna förs in i MPOS eller Cloud POS. Ej schemalagda lagerinventeringar initieras i butiken och de faktiska lagerkvantiteter uppdateras antingen i MPOS eller Cloud POS. Till skillnad från schemalagda inventeringar har ej schemalagda inventeringar inte en fördefinierad lista över artiklar. När en lagerinventering oavsett typ utförs utfästs den och skickas till huvudkontoret. På huvudkontoret valideras och bokförs inventeringen.

## <a name="inventory-lookup"></a>Lagersökning
Den aktuella produktkvantiteten för flera butiker och lagerställen kan visas på sidan Lagersökning. Utöver det aktuella lagersaldot kan framtida ATP-kvantiteter visas för varje enskild butik. Välj den butik du vill visa ATP för och klicka sedan på **Visa tillgänglighet i butiken**.





