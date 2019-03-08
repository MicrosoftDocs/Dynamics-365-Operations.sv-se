---
title: Lagerhantering
description: Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "339244"
---
# <a name="store-inventory-management"></a>Lagerhantering

[!include [banner](includes/banner.md)]

Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.

Du kan använda följande typer av dokument för att hantera organisationens lager.

När du arbetar med lager i Dynamics 365 for Retail och använder kassaprogrammet är det viktigt att komma ihåg att kassan ger begränsat stöd för lagerdimensioner och vissa lagerartikeltyper.  

Kassalösningen stöder inte följande artikelkonfigurationer:
- Strukturlisteartiklar (utom produktpaket som använder vissa komponenter i strukturlisteramverk)
- Fångstviktartiklar
- Batch-kontrollerade artiklar

Kassaprogrammet stöder för närvarande inte följande spårningsdimensioner i kassan:
- Spårningsdimensionsgrupp
- Ägardimension

Kassalösning ger begränsat stöd för följande dimensioner. Begränsat stöd anger att kassan som standard några av dessa dimensioner till lagertransaktioner baserat på grossistförsäljning/installationsprogrammet automatiskt. Kassan stöder inte helt dimensionerna på ett sätt som de stöds om en försäljningstransaktion anges manuellt i ERP. 

- Plats
- Registreringsskylt (gäller endast när **Använda lagerhanteringsprocessen** har aktiverats på artikeln och den butikslagerställe)
- Serienummer
- Lagerstatus

> [!NOTE]
> Alla organisationer måste testa artikelkonfigurationer via kassan i utvecklings- eller testmiljöer innan du distribuerar dem till produktion. Testa dina objekt genom att utföra regelbundna hämtköp genom att genomföra och skapa kundorder (om tillämpligt) till kassan med dina artiklar. Testning måste inkludera en fullständig process för bokföring av utdrag i en testmiljö och kontrollera att det inte finns några problem.
> Konfigurera artiklar på ett sätt som inte stöds av kassaprogrammet utan lämplig testning kan resultera i att processen för bokföring av utdrag misslyckas i produktionen, utan ett enkelt sätt att lösa problem. Partner eller kundanpassningar av programmet kan också anses låta dessa bokföringsprocesser slutföras. Om du inte behöver göra anpassningar måste organisationen säkerställa att produktkonfigurationen för produkterna har gjorts på ett sätt som stöds som standard kassaprogram/skapande av order/bokföringsprocessen för utdrag.

## <a name="purchase-orders"></a>Inköpsorder

Inköpsorder skapas på huvudkontoret. Om ett lagerställe ingår i inköpsorderrubriken kan ordern tas emot i butiken med hjälp av Modern POS (MOPS) eller Cloud POS i Microsoft Dynamics 365 for Retail. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som togs emot i butiken i fältet Dynamics 365 for Retail i fältet **Inleverera nu** på inköpsordern.

## <a name="transfer-orders"></a>Överföringsorder

En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. I det här fallet visas överföringsordern i butiken som en plockningsförfrågan i MOPS eller i Cloud POS. När de kvantiteter som förfrågats har plockats, utfästs de och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som plockades i butiken i fältet Dynamics 365 for Retail i fältet **Leverera nu** på överföringsordern. En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från. I det här fallet visas överföringsordern i butiken som en inleveransförfrågan i MOPS eller i Cloud POS. När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering. Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret. På huvudkontoret visas kvantiteterna som togs emot i butiken i fältet Dynamics 365 for Retail i fältet **Inleverera nu** på överföringsordern.

## <a name="stock-counts"></a>Lagerinventeringar

Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade. Tidsplanerad inventering initieras på huvudkontoret och anger vilka artiklar som måste inventeras. Huvudkontoret skapar ett inventeringsdokument som kan inlevereras till butiken, där de faktiska lagerkvantiteterna förs in i MPOS eller Cloud POS. Ej schemalagda lagerinventeringar initieras i butiken och de faktiska lagerkvantiteter uppdateras antingen i MPOS eller Cloud POS. Till skillnad från schemalagda inventeringar har ej schemalagda inventeringar inte en fördefinierad lista över artiklar. När en lagerinventering oavsett typ utförs utfästs den och skickas till huvudkontoret. På huvudkontoret valideras och bokförs inventeringen.

## <a name="inventory-lookup"></a>Lagersökning

Den aktuella produktkvantiteten för flera butiker och lagerställen kan visas på sidan Lagersökning. Utöver det aktuella lagersaldot kan framtida ATP-kvantiteter visas för varje enskild butik. Välj den butik du vill visa ATP för och klicka sedan på **Visa tillgänglighet i butiken**.
