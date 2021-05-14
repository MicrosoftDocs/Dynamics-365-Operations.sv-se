---
title: Konstruktionsändringshantering – översikt
description: Det här ämnet innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947530"
---
# <a name="engineering-change-management-overview"></a>Konstruktionsändringshantering – översikt

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Funktionssammanfattning

Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.

Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden.Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa konstruktionsändringar under hela livscykeln för en produkt.

Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion. Nedan följer en lista över de viktigaste funktionerna:

- Produktversionering
- Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (konstruktionsföretaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer
- Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)
- Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser
- Begäran om konstruktionsändring som stöds av arbetsflöden
- Konstruktionsändringsorder som stöds av arbetsflöden

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Aktivera funktionerna för konstruktionsändringshantering och versionsdimensioner för ditt system

Innan du kan använda hantering av konstruktionsändringar måste du aktivera både funktionen *Konstruktionsändringshantering* och dess konfigurationsnyckel. Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera funktionen för *produktversionsdimension* och dess konfigurationsnyckel.

Sätt först på funktionerna genom att följa dessa steg.

1. Gå till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Sök efter uppdateringar.
1. Aktivera funktionen med namnet **Konstruktionsändringshantering**.
1. Om du vill använda den, ska du även aktivera funktionen med namnet **Produktdimensionsversion**.

Sätt sedan på konfigurationstangenterna genom att följa dessa steg.

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Expandera noden **Commerce**.
1. Aktivera konfigurationsnyckeln för huvudfunktionen genom att markera kryssrutan **Konstruktionsändringshantering**. (Det är inte nödvändigt att expandera noden om du inte även vill inaktivera en eller båda av dess delfunktioner.)
1. Om du även vill använda versionsdimensionen ska du välja kryssrutan **Produktdimension – Version**. (Denna kryssruta finns längre ned i listan, inte inkapslad under noden **Konstruktionsändringshantering**.)
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> Från och med april 2022 aktiveras licensnycklarna för både **Konstruktionsändringshantering** och **Produktdimension – Version** som standard för alla nya installationer, men de kan fortfarande inaktiveras vid behov.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
