---
title: Översikt över teknisk förändringshantering (innehåller video)
description: Denna artikel innehåller en översikt över konstruktionsändringshantering som hjälper dig att planera och hantera produktversioner, samt att hantera ändringar av produktens livscykler och konstruktion.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6c9bfcdef91ad07b8346498b8944e1d741d623a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862668"
---
# <a name="engineering-change-management-overview"></a>Konstruktionsändringshantering – översikt

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Funktionssammanfattning

Dagens tillverkare kräver stark hantering av produktdata, versionskontroll och konstruktionsändringshantering för att lyckas i en värld av en värld av ständigt minskade produktlivscykler, ökade krav på kvalitet och tillförlitlighet och en ökad fokus på produktsäkerhet.

Konstruktionsändringshantering ger struktur och disciplin åt processen för produktdatahantering och gör att produkter kan definieras, frisläppas och revideras på ett kontrollerat sätt som stöds av arbetsflöden. Genom produktversioner och konstruktionsändringshantering kan du dokumentera, bedöma effekten av och tillämpa konstruktionsändringar under hela livscykeln för en produkt.

Konstruktionsändringshantering hjälper dig att planera och hantera produktversioner samt hantera ändringar av produktens livscykler och konstruktion. Nedan följer en lista över de viktigaste funktionerna:

- Produktversionering
- Förbättrad produktlanseringsfunktion som gör att du kan underhålla produktmalldata i en juridisk person (konstruktionsföretaget) och publicera den fullständigt konfigurerade frisläppta produkten till andra juridiska personer
- Regler för att validera att nödvändig information anges innan en produktversion aktiveras (beredskapskontroller)
- Förbättrad produktlivscykelhantering genom detaljerad kontroll över när en frisläppt produkt kan användas i specifika affärsprocesser
- Begäran om konstruktionsändring som stöds av arbetsflöden
- Konstruktionsändringsorder som stöds av arbetsflöden

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

Föregående video ([ändra hanteringsfunktioner i Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) finns med i [Finance and Operations spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som är tillgänglig på YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Aktivera funktionerna för konstruktionsändringshantering för ditt system

Innan du kan använda hantering av konstruktionsändringar måste du aktivera både funktionen *Konstruktionsändringshantering* och dess konfigurationsnyckel. Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera både funktionen för *produktversionsdimension* och dess konfigurationsnyckel. När dessa förutsättningar har konfigurerats efter behov kan du aktivera ytterligare valfria funktioner för konstruktionsändringshantering.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Aktivera och inaktivera de grundläggande funktionerna för konstruktionsändringshantering

Aktivera och inaktivera de grundläggande funktionerna för konstruktionsändringshantering med följande steg. Från och med version 10.0.25 av Supply Chain Management aktiveras funktionen *Konstruktionsändringshantering* som standard.

1. Gå till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Sök efter uppdateringar.
1. Aktivera eller inaktivera funktionen med namnet *Konstruktionsändringshantering*.
1. Om du även vill spåra versionsdimensionen för produkter i transaktioner (valfritt), måste du också aktivera funktionen för *produktdimensionsversion*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>Aktivera eller inaktivera de konfigurationsnycklar som behövs

Sätt sedan på konfigurationstangenterna genom att följa dessa steg. Dessa är inte aktiverade som standard.

1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Expandera noden **Commerce**.
1. Aktivera eller inaktivera konfigurationsnyckeln för huvudfunktionen genom att markera kryssrutan **Konstruktionsändringshantering**.
1. Expandera noden **Tillägg för teknik för ändringshantering** och markera eller avmarkera följande kryssrutor efter behov (beroende på vilka funktioner du vill använda):

    - **Attributsökning** – Markera den här kryssrutan om du vill aktivera [attributsökningsfunktionen](engineering-attributes-and-search.md). Vi rekommenderar att du aktiverar funktionen, men du kan avmarkera kryssrutan om du inte vill använda den.
    - **Ändringshantering för processtillverkning** – Markera den här kryssrutan om du vill använda funktioner för teknikändringshantering för att hantera ändringar i formler för processtillverkning. Om du inte behöver hantera recept kan du avmarkera den här kryssrutan. Mer information finns i [Hantera ändringar i formler och deras ingredienser](manage-formula-changes.md).

1. Om du även vill använda versionsdimensionen ska du välja kryssrutan **Produktdimension – Version**. (Den här kryssrutan är längre ned i listan och inte kapslad under nod **Konstruktionsändringshantering**.) Du kan avmarkera den här kryssrutan om du inte behöver den här funktionen.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Databasen måste synkroniseras för att säkerställa att konfigurationsnycklarna är uppdaterad för att återspegla dina ändringar. Gör något av följande steg beroende på vilken typ av miljö du arbetar i:
    - **För nivå 1 (utveckling) miljöer**: Öppna ditt projekt i Microsoft Visual Studio och välj sedan **Dynamics 365 \> Synkronisera databasen \> Synkronisera**.
    - **För nivå 2 (och högre) miljöer**: Databasen synkroniseras automatiskt när du sätter miljön in och ut ur underhållsläge, så du kan hoppa över det här steget.

### <a name="turn-on-additional-engineering-change-management-features"></a>Aktivera de ytterligare funktionerna för konstruktionsändringshantering

När du har aktiverat de grundläggande funktionerna för konstruktionsändringshantering och aktiverar deras konfigurationsnycklar, läggs flera ytterligare och valfria funktioner för konstruktionsändringshantering till i funktionshanteringen. Var och en av dessa funktioner visas under modulen **Konstruktionsändringshantering**. I tabellen nedan beskrivs de olika valfria funktionerna och här finns länkar till mer information. Från och med Supply Chain Management version 10.0.25 aktiveras alla dessa funktioner som standard, men du kan ändå välja att stänga av dem.

| Funktionsnamn i funktionshantering | Beskrivning | Funktionens tillstånd |
|---|---|---|
| Aktivera ändringshantering för befintliga produkter | <p>Med hjälp av den här funktionen kan du konvertera befintliga produkter till konstruktionsprodukter så att du kan börja hantera dem genom att använda konstruktionsändringshantering.</p><p>För mer information, se [Aktivera ändringshantering för befintliga produkter](change-management-existing-products.md).</p> |
| Konstruktionsmeddelanden för produktion | <p>När en produkt ändras inom konstruktion kan det vara viktigt att meddela produktionen om dessa ändringar. På det sättet kan produktionsarbetare vidta lämpliga åtgärder, till exempel ersättning av komponenter, strukturlisteersättning eller flödesersättning. Med hjälp av den här funktionen kan du meddela produktionen om förändringar av produkter som tillverkas.</p><p>För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md).</p> |
| Förbättrat attributarv för konstruktionsändringshantering | <p>Den här funktionen förenklar hanteringen av attribut för färdiga varor eller mellanliggande artiklar. När den här funktionen är aktiverad är det enklare att identifiera alla attribut som tillhör en artikel, och du kan välja de attribut som ska spridas från den artikeln till den överordnade artikeln. Den här funktionen är användbar när en del av en färdig vara, till exempel är ömtålig, giftig eller brandfarlig eftersom du lätt kan identifiera det ömtåliga, giftiga eller brandfarliga attributet och sprida det till det färdiga varan.</p><p>Mer information finns i [Konstruktionsattribut och sökning efter konstruktionsattribut](engineering-attributes-and-search.md).</p> |
| Kontroller av produktberedskap | <p>Med funktionen kan du också konfigurera beredskapskontroller för standardprodukter (icke-konstruktions). Använd produktberedskapskontroller för att se till att varje produkt är fullständigt definierad och alla nödvändiga policyer har konfigurerats innan produkten görs tillgänglig och används i transaktioner. Om du inaktiverar den här funktionen efter att du har använt den under en tid, raderas alla befintliga beredskapskontroller för standardprodukter.</p><p>Mer information finns i [Produktberedskap](product-readiness.md).</p> |
| Hantera formeländringar och deras ingredienser | <p>Med hjälp av den här funktionen kan du spåra ändringar av formelingredienser, samprodukter och biprodukter.</p><p>Mer information finns i [Hantera ändringar i formler och deras ingredienser](manage-formula-changes.md).</p> |
| Variantgenerering för tekniska produkter | <p>Med hjälp av den här funktionen kan du skapa varianter för produktionsprodukter baserade på tillgängliga dimensionsvärden.</p><p>Mer information finns i [Generera varianter för tekniska produkter](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
