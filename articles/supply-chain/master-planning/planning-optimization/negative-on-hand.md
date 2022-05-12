---
title: Planera med negativ lagerbehållning
description: Det här ämnet förklarar hur negativ behållning hanteras när du använder planeringsoptimering.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: bb837a38485bad2b9b76a5e4f20d311c0281e192
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625405"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planera med negativ lagerbehållning

[!include [banner](../../includes/banner.md)]

Om systemet visar en negativ total lagerbehållning behandlas kvantiteten som 0 (noll) i planeringsmotorn för att undvika överleverans. Så här fungerar funktionen:

1. Funktionen för planeringsoptimering aggregerar lagerbehållningen till den lägsta nivån av disponeringsdimensioner. (Till exempel om *plats* är inte en disponeringsdimensionen, planerar optimeringsaggregat för närvarande kvantiteter vid nivå *lagerställe*.)
1. Om den sammanlagda lagerbehållningen på den lägsta nivån för disponering är negativ, förutsätter systemet att lagerbehållningen verkligen är 0 (noll).

> [!IMPORTANT]
> Planeringssystemet kan bara vara precis så exakt som indata. Om inmatningsdata är felaktiga kommer negativa poster för lagerbehållning att visa att lagerinformationen i Microsoft Dynamics 365 Supply Chain Management inte är synkroniserad med den verkliga världen. Därför är det fel på planeringsresultatet. Om du vill få ett exakt planeringsresultat bör du minimera antalet poster som visar en negativ lagerbehållning.

## <a name="example-1"></a>Exempel 1

Lagerställe 13 konfigureras på följande sätt:

- **Disponeringskod:** Min./Max.
- **Minimum:** 15 stycken
- **Maximum:** 25 stycken

Disponeringsdimensionernas sista nivå är *lagerställe* och följande kvantiteter på lagerbehållning registreras på nivån *plats*:

- **Plats 1, lagerställe 13, plats 1:** 20 stycken.
- **Plats 1 lagerställe 13, plats 2:** &minus;8 stycken.

Därför är den aggregerade lagerbehållningen för lagerställe 13 är 12 stycken. (= 20 stycken. &minus; 8 stycken).

I det här fallet använder planeringsmotorn en samlad lagerbehållning på 12 stycken. för lagerställe 13.

Resultatet blir en planerad order på 13 stycken. (= 25 stycken. &minus; 12 stycken) för att fylla på lagerställe 13 från 12 stycken. till 25 stycken.

## <a name="example-2"></a>Exempel 2

Lagerställe 13 konfigureras på följande sätt:

- **Disponeringskod:** Min./Max.
- **Minimum:** 15 stycken.
- **Maximum:** 25 stycken

Disponeringsdimensionernas sista nivå är *lagerställe* och följande kvantiteter på lagerbehållning registreras på nivån *plats*:

- **Plats 1, lagerställe 13, plats 1:** 4 stycken.
- **Plats 1 lagerställe 13, plats 2:** &minus;8 stycken.

Därför är den aggregerade lagerbehållningen 13 är &minus;4 stycken. (= 4 stycken. &minus; 8 stycken). Med andra ord är det mindre än 0 (noll).

I det här fallet förutsätter planeringsmotorn att lagerbehållningen för lagerställe 13 är 0 stycken. i stället för &minus; 4 stycken.

Resultatet blir en planerad order på 25 stycken. (= 25 stycken. &minus; 0 stycken) för att fylla på lagerställe 13 från 0 stycken. till 25 stycken.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planering när det finns en reservation mot negativ lagerbehållning

Om du justerar lager när det finns fysiska reservationer kan det leda till en situation där en order fysiskt reserveras mot negativt lager. I det här fallet måste du ha leverans för att täcka den reserverade kvantiteten, eftersom det finns en fysisk reservation. Påfyllnad krävs därför, så att systemet antingen skapar en planerad order för att fylla på den kvantitet som inte kunde täckas av den befintliga lagerbehållningen, eller så täcker den med en befintlig order för artikeln.

I följande exempel illustreras scenariot.

### <a name="example"></a>Exempel

Systemet konfigureras så här:

- Produkt *FG* finns och har *10* st. av lagerbehållning.
- Produktkonfigurationen tillåter fysiskt negativt lager.
- Det finns en försäljningsorder med en kvantitet *10* st. av produkten *FG*.
- Försäljningsorderkvantiteten reserveras fysiskt mot befintlig lagerbehållning.

Du justerar sedan kvantiteten för produkt *FG* så lagerbehållningen blir 5. Eftersom beställningsproduktlagret är 5, reserveras försäljningsorder kvantiteten nu mot kvantitet som inte finns tillgänglig (det skulle vara liknande om beställningen var 0, i vilket fall försäljningsordern skulle reserveras mot negativt lager ). Om du kör huvudplanering nu, en planerad beställning av kvantitet 5 för *FG* kommer att skapas för att leverera försäljningsordern, eftersom Planeringsoptimering alltid kommer att använda befintligt utbud eller skapa en ny planerad order för att tillhandahålla den fysiska reservationen.

## <a name="related-resources"></a>Relaterade resurser

- [Planeringsoptimering – översikt](planning-optimization-overview.md)
- [Kom i gång med planeringsoptimering](get-started.md)
- [Planera analys av optimeringsanpassning](planning-optimization-fit-analysis.md)
- [Visa planhistorik och planeringsloggar](plan-history-logs.md)
- [Annullera ett planeringsjobb](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
