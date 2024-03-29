---
title: Ordlista för sidmodell
description: I denna artikel beskrivs de olika element som används på sidorna på en Microsoft Dynamics 365 Commerce-webbplats.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: intro-internal
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: a4c2a29e8c2112622b5e30064e26523b4f9e2d5a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281438"
---
# <a name="page-model-glossary"></a>Ordlista för sidmodell


[!include [banner](includes/banner.md)]

I denna artikel beskrivs de olika element som används på sidorna på en Microsoft Dynamics 365 Commerce-webbplats.

## <a name="page-element-definitions"></a>Definitioner för sidelement

Följande tabell innehåller en sammanfattning av termer som du bör känna till när du ändrar utseende, känsla och innehåll på din webbplats. Mer ingående förklaringar och procedurer följer du länkarna.

| Villkor | Beskrivning och anteckningar |
|------|-----------------------|
| [Modul](work-with-modules.md) | <p>**Definition:** moduler är byggblock som kan redigeras och utgöra basen för en webbsida. Exempel på detta är rubrik-, fokus- och karusellmoduler.</p><p>**Där den väljs:** distribuerade moduler kan väljas och konfigureras i olika steg i arbetsflödet för webbplatsredigering, t.ex. mall-, layout-, sid- och fragmentutvecklingsfaser.</p><p>**Där den redigeras:** anpassade moduler skapas i kod med hjälp av SDK (Software Development Kit). De överförs sedan till din webbplats, där de blir tillgängliga för markering.</p> |
| Modulegenskap | <p>**Definition:** modulegenskaper är specifika inställningar som definieras av modulen. De kan redigeras i redigeringsverktygen för näthandel. Modulegenskaper används till exempel för att ange rubrik och bakgrundsbild för en webbannons.</p><p>**Där det konfigureras:** modulegenskaper väljs och konfigureras i egenskapsrutan som visas i redigeringsmiljön (redigerare) för mallar, layouter, sidor, fragment och appinställningar.</p> |
| [Mall](templates-layouts-overview.md) | <p>**Definition:** mallarna definierar de kombinationer och alternativ för moduler som ska användas för en kategori av sidor (t.ex. marknadsföringssidor, kategorisidor och produktsidor).</p><p>**Där det är valt:** Mallar kan väljas under arbetsflöden för skapande av sidor eller layout.</p><p>**Där den redigeras:** mallar skapas i redigeraren för mallar. Ingen kod krävs för att skapa eller ändra dem.</p> |
| [Layout](templates-layouts-overview.md) | <p>**Definition:** layouter definierar det slutliga urvalet och arrangemanget av moduler från den överordnade mallens alternativuppsättning. En layout kan konfigureras för en enskild sida (*anpassad layout*), eller så kan den delas av flera sidor (*förvald layout*).</p><p>**Där den har valts:** layouten kan väljas vid skapande av ny sida eller när en annan layout krävs för en befintlig sida.</p><p>**Där den redigeras:** Layouter skapas i layoutredigeraren. Ingen kod krävs för att skapa eller ändra dem.</p> |
| [Sidinstans](modify-existing-page.md) | <p>**Definition:** sidförekomster definierar det slutliga, platsspecifika lokalanpassade innehållet för en enda sida. Det här innehållet hämtas från värdena för modulens egenskaper.</p><p>**Där den väljs:** sidor markeras när URL:er tilldelas.</p><p>**Där den redigeras:** Sidor redigeras i sidredigeraren. Ingen kod krävs för att skapa eller ändra dem.</p> |
| [Tema](select-site-theme.md) | <p>**Definition:** teman definierar övergripande formatmall (CSS) och bestämmer utseendet på de moduler som återges på en sida.</p><p>**Där den väljs:** när ett tema har överförts till din webbplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS) kan det väljas som en egenskap för modul för sidbehållare.</p><p>**Där den redigeras:** teman skapas och redigeras för närvarande med hjälp av SDK. De överförs sedan till din webbplats med hjälp av LCS.</p> |
| [Fragment](work-with-fragments.md) | <p>**Definition:** fragment är helt konfigurerade moduler som har lokalanpassat innehåll som kan återanvändas och uppdateras centralt på flera sidor. Ett fragment som skapas från en huvudmodul kan till exempel användas i alla mallar och på alla sidor på webbplatsen och de uppdateras centralt på en och samma plats.</p><p>**Där den har valts:** fragment kan väljas där moduler kan väljas. De kan ersättas med en modul för att öka effektiviteten genom återanvändning och centraliserad redigering.</p><p>**Där den redigeras:** Fragment redigeras i fragmentredigeraren. Ingen kod krävs för att skapa eller ändra dem.</p> |
| [URL](create-page-URL.md) | <p>**Definition:** URL:er (Uniform Resource Locators) är adresser som pekar mot webbsidor eller andra URL-adresser.</p><p>**Där den väljs:** URL:er markeras när länkar mellan sidor krävs.</p><p>**Där den redigeras:** URL redigeras i URL-redigeraren. Ingen kod krävs för att skapa eller ändra dem.</p> |
| Tillgång | <p>**Definition:** tillgångar är binära filer som har filnamntillägget .jpg, .docx, .pdf eller .mpg.</p><p>**Där den väljs:** tillgångar väljs som modulegenskaper för moduler som kräver dem.</p><p>**Där den redigeras:** tillgångar överförs och tillhörande metadata redigeras i resurshanteraren.</p> |

## <a name="additional-resources"></a>Ytterligare resurser

[Sätt att lägga till innehåll](add-manage-content.md)

[Dokumentera tillstånd och livscykel](document-states-overview.md)

[Arbeta med publiceringsgrupper](publish-groups.md)

[Aktivera och använda delning av flera kanaler](cross-channel-sharing.md)

[Arbeta med moduler](work-with-modules.md)

[Arbeta med fragment](work-with-fragments.md)

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Anpassa webbplatsnavigeringen](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
