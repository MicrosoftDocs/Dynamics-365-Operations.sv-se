---
title: "POS-tillämpning och användaren språkinställningar"
description: "Det här avsnittet beskrivs hur du ändrar språkinställningar i Retail POS (MOPS Modern) och molnbaserad kassa."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>POS-tillämpning och användaren språkinställningar

Det här avsnittet beskrivs hur du ändrar språkinställningar i Retail POS (MOPS Modern) och molnbaserad kassa.

<a name="overview"></a>Översikt
========

Retail POS (MOPS Modern) och molnbaserad kassa stöder miljöer där språkinställningar och översättningar kan variera mellan butiks- och inställningar. Exempelvis kunde arkivet hittas inom områden där engelska är vanligast för kunderna, men vissa arbetare föredrar att använda programmet med fransk översättning.

## <a name="data-language"></a>Data språk
Oavsett användarens inställningar används MOPS och molnbaserad kassa alltid butikens språkinställningar för att bestämma översättningar används för data. Se till att alla användare och kunder får en enhetlig upplevelse av organisationen.  Exempel på data:

-   Produkter
-   Attribut och värden
-   Kategorinamn
-   Skrivat ut eller emailed transaktionen inleveranser
-   Betalningssätt namn
-   Visning av meddelanden

Butikens språk används också för POS-inloggning huvudskärmen eftersom användaren inte är känd innan du loggar in. Om en översättning inte är tillgänglig för butikens språk, återgår POS till företagets språk.

### <a name="configuring-the-stores-language-setting"></a>Konfigurera den stores språkinställning

Butikens språkinställning anges från **alla detaljhandel** på de **butik** sidan ** allmänna &gt;nationella inställningar &gt;språk. ** Använd rutan nedåt väljer språk för varje butik.

## <a name="user-interface-language"></a>Språk för användargränssnittet
POS användarens språkinställning anger översättningar används i programmets användargränssnitt. Detta inkluderar alla etiketter menyer och listor som inte betraktas som data. Ett undantag är den text som visas i knappsatser POS. Knappsatser stöder inte översättningar, och de visas alltid texten som definierats via knappen. För att stödja översatta knappar måste du kopiera och underhålla separat knappsatser och tilldela användare enligt önskemål.

### <a name="configuring-the-users-language-setting"></a>Konfigurera användarens språk inställning

POS användarens språkinställning anges från **alla arbetare** på de **arbetare** sidan **Retail &gt;språk**.  Den är inte inställd på huvudfliken profil.  Den här inställningen används inte av POS. Om användarens språk är inte inställd eller till ett språk där översättningar är inte tillgängliga, POS återgår till butiken språk.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **Användargränssnittets språk** ** **      | **Data språk (produkter, kvitto format, radvisning etc.)** |
| **Företag** | Standard                    | Standard                                                           |
| **Butik**   | Åsidosätter företaget          | Åsidosätter företaget                                                 |
| **User**    | Åsidosätter butiken eller företaget | Aldrig                                                             |




