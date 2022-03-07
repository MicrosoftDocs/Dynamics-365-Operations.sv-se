---
title: Platsprofilen tillåter inte negativt lager, men negativ lagerbehållning är tillåten
description: Alternativet Tillåt negativt lager för lagerställeprofilen är inställt på Nej, men systemet tillåter fortfarande negativ lagerbehållning.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026913"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>Platsprofilen tillåter inte negativt lager, men negativ lagerbehållning är tillåten

KB-nummer: 4613622

## <a name="symptoms"></a>Symtom

Alternativet **Tillåt negativt lager** för lagerställeprofilen är inställt på *Nej*, men systemet tillåter fortfarande negativ lagerbehållning.

## <a name="example-scenario"></a>Exempelscenario

För statligt reglerade transaktioner måste systemet kunna registrera negativt lager för att bokföra förluster. Du vill att en artikel ska kunna visa negativt lager, men bara på angivna platser, till exempel tankar. Men om artikelmodellgruppen tillåter negativt lager upptäcker du att det inte spelar någon roll om lagerstället är inställt på att tillåta negativt lager. Om artikeln har ställts in så att negativt lager inte tillåts spelar det ingen roll hur lagerställesprofilen ställs in.

## <a name="resolution"></a>Upplösning

Inställningen **Tillåt negativt lager** från lagerställeprofilen gäller endast lagerprocesser, till exempel plockning. Artikelmodellgrupper som är inställda på att tillåta negativt lager påverkar dock alla processer från modulerna Lagerhantering och Lagerställeshantering, och lagerställesprofilen åsidosätter inte inställningen.

Du kan styra om ett lagerställe får ha negativt lager. Ange att artikelmodellgrupperna inte ska tillåta negativt fysiskt lager och ange endast det relevanta lagerstället så att negativt lager tillåts.
