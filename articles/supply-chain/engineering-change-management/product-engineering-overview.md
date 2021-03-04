---
title: Konstruktionsändringshantering – översikt
description: Det här ämnet innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f1aa04b472eaef7ed398f08a05d46bac2d589561
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514360"
---
# <a name="engineering-change-management-overview"></a>Konstruktionsändringshantering – översikt

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Funktionssammanfattning

Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.

Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa tekniska förändringar under hela livscykeln för en produkt.

Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och teknik. Nedan följer en lista över de viktigaste funktionerna:

- Produktversionering
- Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (det tekniska företaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer
- Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)
- Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser
- Begäran om teknisk ändring som stöds av arbetsflöden
- Teknisk ändringsändringsorder som stöds av arbetsflöden

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.

## <a name="turn-on-engineering-change-management-for-your-system"></a>Aktivera konstruktionsändringshantering för ditt system

Börja med att aktivera konstruktionsändringshantering genom att följa stegen nedan.

1. Gå till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Sök efter uppdateringar.
1. Aktivera funktionen med namnet **konstruktionsändringshantering**.

Aktivera sedan konfigurationsnyckeln för **konstruktionsändringshantering** genom att följa stegen nedan.

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Expandera noden **Handel** och markera kryssrutan **konstruktionsändringshantering**.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]