---
title: Fördröjningstolerans (negativa dagar)
description: Denna artikel innehåller information om fördröjningstoleransberäkningen och hur denna påverkar skapandet av planerad order i Planeringsoptimering.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e1c9a9b618184303efe2bd10975e46423cca9ccc
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219980"
---
# <a name="delay-tolerance-negative-days"></a>Fördröjningstolerans (negativa dagar)

[!include [banner](../../includes/banner.md)]

Med funktionen för fördröjningstolerans kan ett värde för Planeringsoptimering ta hänsyn till värdet för **Negativa dagar** som har angetts för disponeringsgrupper, artikeldisponering och/eller översiktsplaner. Den används för att utöka den fördröjningstoleransperiod som används vid huvudplanering. På det här sättet kan du undvika att skapa nya leveransorder om befintlig leverans kommer att täcka efterfrågan efter en kort fördröjning. Syftet med funktionen är att avgöra om det är logiskt att skapa en ny leveransorder för en given efterfrågan.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om du vill göra funktionen för fördröjningstolerans tillgänglig i systemet går du till [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen:

- *Negativa dagar för planeringsoptimering* – Med den här funktionen aktiveras inställningar för negativa dagar för disponeringsgrupper och artikel disponering.
- *Leveransautomatisering på beställning* – Med den här funktionen aktiveras inställningar för huvudplaner i negativa dagar. (Mer information finns i [Leveransautomatisering på beställning](../make-to-order-supply-automation.md).)

## <a name="delay-tolerance-in-planning-optimization"></a>Fördröjningstolerans vid Planeringsoptimering

Fördröjningstoleransen representerar antalet dagar efter den lead-tid du är villiga att vänta innan du beställer nya påfyllnader när befintlig leverans redan har planerats. Fördröjningstolerans definieras genom att använda kalenderdagar, inte arbetsdagar.

Vid huvudplaneringen, när systemet beräknar fördröjningstoleransen, tar det hänsyn till inställningen **Negativa dagar**. Du kan ange värdet **negativa dagar** på sidan **Disponeringsgrupper** eller på sidan **Artikeldisponering** eller **Huvudplaner**. Om negativa dagar tilldelas på mer än en nivå används följande hierarki för att avgöra vilken inställning som ska användas:

- Om negativa dagar har aktiverats på sidan **Huvudplaner** åsidosätter den inställningen alla andra negativa dagar när planen körs.
- Om negativa dagar har konfigurerats på sidan **Artikel disponering** åsidosätter den inställningen för disponeringsgrupp.
- Negativa dagar som konfigureras på sidan **Disponeringsgrupper** gäller bara om negativa dagar inte har konfigurerats för en relevant artikel eller plan.

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
