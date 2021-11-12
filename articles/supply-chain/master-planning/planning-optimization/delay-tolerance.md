---
title: Fördröjningstolerans (negativa dagar)
description: Det här avsnittet innehåller information om fördröjningstoleransberäkningen och hur den påverkar skapandet av planerad order i Planeringsoptimering.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ccf827983694eab2037c73aa3251846b051e66f1
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678577"
---
# <a name="delay-tolerance-negative-days"></a>Fördröjningstolerans (negativa dagar)

[!include [banner](../../includes/banner.md)]

Med funktionen för fördröjningstolerans kan ett värde för planeringsoptimering ta hänsyn till värdet för **Negativa dagar** som har angetts för disponeringsgrupper. Den används för att utöka den fördröjningstoleransperiod som används vid huvudplanering. På det här sättet kan du undvika att skapa nya leveransorder om befintlig leverans kommer att täcka efterfrågan efter en kort fördröjning. Syftet med funktionen är att avgöra om det är logiskt att skapa en ny leveransorder för en given efterfrågan.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om du vill göra funktionen för fördröjningstolerans tillgänglig i systemet går du till [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Negativa dagar för planeringsoptimering*.

## <a name="delay-tolerance-in-planning-optimization"></a>Fördröjningstolerans vid planeringsoptimering

Fördröjningstoleransen representerar antalet dagar efter den lead-tid du är villiga att vänta innan du beställer nya påfyllnader när befintlig leverans redan har planerats. Fördröjningstolerans definieras genom att använda kalenderdagar, inte arbetsdagar.

Vid huvudplaneringen, när systemet beräknar fördröjningstoleransen, tar det hänsyn till inställningen **Negativa dagar**. Du kan ange värdet **negativa dagar** på sidan **Disponeringsgrupper** eller på sidan **Artikeldisponering**.

Systemet kopplar förseningtoleransberäkningen till det *tidigaste påfyllnadsdatumet*, som är lika med dagens datum plus ledtiden. Fördröjningstoleransen beräknas med följande formel, där *max()* hittar det större av två värden:

*max(Tidigaste påfyllnadsdatum, Förfallodatum för efterfrågan)* – *Efterfrågans förfallodatum* + *Negativa dagar*

Formeln garanterar att huvudplaneringen inte skapar nya leveransorder när det finns tillräckligt med tillförsel under produktens produktionstid.

> [!NOTE]
> I beräkningen av fördröjningstoleransen i Planeringsoptimering används alltid den dynamiska beräkningen av negativa dagar från den inbyggda huvudplaneringen. Inställningen **Använd dynamiska negativa dagar** på sidan **Parametrar för huvudplanering** påverkar inte det här beteendet.

Om det befintliga tillgången innebär en efterfrågefördröjning som är mindre än eller lika med den beräknade fördröjningstoleransen, innebär Planeringsoptimering att det finns en befintlig tillgång till efterfrågan. I vissa fall är det bättre att försena efterfrågan än att sluta med överbehov.

Följande delgrupper ger exempel som visar hur fördröjningar tolerans påverkar skapandet av planerade order i Planeringsoptimering.

### <a name="example-1"></a>Exempel 1

En produkt har följande konfiguration:

- **Ledtid:** *10*
- **Negativa dagar:** *2*

Följande tillgång och efterfrågan finns för produkten:

- **Efterfrågan för idag:** En försäljningsorder för kvantiteten 10
- **Leverans om 12 dagar:** En inköpsorder med kvantiteten 10

Befintlig leverans kan täcka efterfrågan inom 12 dagar och den perioden är lika med fördröjningstoleransen. När huvudplaneringen körs skapas därför inga planerade order.

### <a name="example-2"></a>Exempel 2

En produkt har följande konfiguration:

- **Ledtid:** *10*
- **Negativa dagar:** *0*

Följande tillgång och efterfrågan finns för produkten:

- **Efterfrågan för idag:** En försäljningsorder för kvantiteten 10
- **Leverans om 12 dagar:** En inköpsorder med kvantiteten 10

Befintliga leveranser kan täcka efterfrågan endast efter 12 dagar. Fördröjningstoleransen är dock 10 dagar. När huvudplaneringen körs skapas därför en planerad order med kvantiteten 10.

### <a name="example-3"></a>Exempel 3

En produkt har följande konfiguration:

- **Ledtid:** *10*
- **Negativa dagar:** *2*

Följande tillgång och efterfrågan finns för produkten:

- **Efterfrågan om 11 dagar:** En försäljningsorder för kvantiteten 10
- **Leverans om 14 dagar:** En inköpsorder med kvantiteten 10

Befintliga leveranser kan täcka efterfrågan endast efter tre dagar. Fördröjningstoleransen är dock två dagar. (I det här fallet omfattar fördröjningstoleransen endast de två negativa dagarna. Efterfrågedatumet inkluderas inte eftersom det är efter produktens ledtid.) När huvudplaneringen körs skapas därför en planerad order med kvantiteten 10.
