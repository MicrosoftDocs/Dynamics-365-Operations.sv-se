---
title: "Kassaprogram (POS) och språkinställningar för användare"
description: "Det här avsnittet beskriver hur du ändrar språkinställningarna i Retail Modern POS (MPOS) och Cloud POS."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: faf8cdcee70b55842072298b51789f6cd7a577af
ms.contentlocale: sv-se
ms.lasthandoff: 01/04/2019

---

# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Kassaprogram (POS) och språkinställningar för användare

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver hur du ändrar språkinställningarna i Retail Modern POS (MPOS) och Cloud POS.

## <a name="overview"></a>Översikt

Retail Modern POS (MPOS) och Cloud POS stöder miljöer där språkinställningar och översättningar kan variera mellan butiks- och användarinställningar. Exempelvis kan butiken finnas i ett område där engelska är vanligast för kunderna, men vissa arbetare föredrar att använda programmet med fransk översättning.

## <a name="data-language"></a>Data språk

Oavsett användarens inställningar använder MPOS och Cloud POS alltid butikens språkinställningar för att bestämma vilka översättningar som används för data. På så sätt får alla användare och kunder en enhetlig upplevelse. Exempel på data är:

- Produkter
- Attribut och värden
- Kategorinamn
- Skrivat ut eller emailed transaktionen inleveranser
- Betalningssätt namn
- Visning av meddelanden

Butikens språk används också för POS-inloggningsskärmen, eftersom användaren inte är känd innan du loggar in. Om en översättning inte är tillgänglig för butikens språk, återgår POS till företagets språk.

### <a name="configuring-the-stores-language-setting"></a>Konfigurera den stores språkinställning

Butikens språk är ställs in från Alla butiker på sidan **Alla butiker** på sidan **Butik** under **Allmänt &gt; Nationella inställningar &gt; Språk**. Använd listrutan för att välja språk för varje butik.

## <a name="user-interface-language"></a>Språk för användargränssnittet

Kassaanvändarens språkinställning anger vilka översättningar som används i programmets användargränssnitt. Det inkluderar alla etiketter, menyer och listor som inte betraktas som data. Ett undantag är den text som visas i på kassans knappsatser. Knappsatser stöder inte översättningar, och de visar alltid texten som definieras på knappen. För att stödja översatta knappar måste du kopiera och underhålla separata knappsatser och tilldela dem till användare enligt önskemål.

### <a name="configuring-the-users-language-setting"></a>Konfigurera användarens språk inställning

POS användarens språk är inställd på **Alla arbetare** på sidan **Arbetare** under **Butik &gt; Språk**. Detta är inte inställt på fliken Profil. Den här inställningen används inte av POS. Om användarens språk är inte inställd eller till ett språk där översättningar är inte tillgängliga, POS återgår till butiken språk.

|             | UI-språk                  | Data språk (produkter, kvitto format, radvisning etc.) |
|-------------|----------------------------|---------------------------------------------------------------|
| **Företag** | Standard                    | Standard                                                       |
| **Butik**   | Åsidosätter företaget          | Åsidosätter företaget                                             |
| **Användare**    | Åsidosätter butiken eller företaget | Aldrig                                                         |

