---
title: Översikt över mallar och layouter
description: I denna artikel beskrivs mallar och layouter i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 12/12/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: e0bf7e942339775b2e9ee15060d555be07c1cdc5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277944"
---
# <a name="templates-and-layouts-overview"></a>Översikt över mallar och layouter


[!include [banner](includes/banner.md)]

Mallar är grundläggande element i Microsoft Dynamics 365 Commerce sidmodell. Om målet är att maximera effektiviteten och kontinuiteten för arbetsflöden för webbplatsredigering är det viktigt att du lär dig hur du kan dra nytta av mallarna för webbplatsen. Tidiga beslut om mallstrukturlistan är viktiga och kan märkbart påverka kostnader och rörlighet för dagliga, säsongsmässiga och platsbaserade varumärkesuppdateringar. Välstrukturerade mallar har även andra fördelar. De kan till exempel hjälpa till att förbättra SEO-poängen (Search Engine Optimization) för hela webbplatsen och minska antalet fel.

Ett bra sätt att börja arbeta med mallar är att förstå de funktionella fördelarna med mallar och layouter, skillnaderna mellan dem och hierarkin.

Följande bild visar sidmodellens hierarki bakom en återgiven webbsida.

![Diagram för sidmodell.](../commerce/media/page-model-diagram.png)

| Enhet        | Basfunktion |
|---------------|----------------|
| Mall      | Mallar definierar modulens alternativ och grundläggande ställningar för en uppsättning layouter och sidinstanser. |
| Layout        | Layouter definierar det slutliga urvalet och arrangemanget av moduler för en sida eller en uppsättning sidor. |
| Sidinstans | Sidinstanser definierar data och innehåll för specifika sidor. |

## <a name="templates"></a>Mallar

Mallarna finns högst upp i Dynamics 365 Commerce sidans modellhierarki och representerar ett viktigt tidigt steg för webbplatskonfigurationen. Mallar hjälper till att kontrollera överensstämmelsen i en familj med underordnade layouter och sidor genom att definiera grundläggande struktur och redigeringsalternativ för att förenkla arbetsflöden för skapande av layout och skapande av sidor. Med hjälp av mallarna kan du förenkla processen för redigering genom fördefinierade, centralt hanterade element (t.ex. sidhuvuden och sidfötter) och guidade redigeringsflöden som hjälper till att garantera att alternativen för modulkonfiguration är anpassade.

### <a name="controlling-consistency"></a>Kontrollera konsekvens

När du utformar en mall är det större affärsbeslut du måste göra hur stor kontroll mallen ska ha över processen för att skapa sidan. En mall som lämnar allting öppet för en underordnad författare är det enklaste sättet att skapa en mall, men det kan också finnas långsiktiga följder för underhållet av sidor som skapas från den. En välskriven mall ger vägledning och en strömlinjeformad redigeringsupplevelse, men den ger också författarna tillräckligt mycket flexibilitet så att de kan slutföra sin uppgift. Alla dessa aspekter beror på den kontrollnivå som mallen gäller för.

Med hjälp av mallar kan innehållsförfattare bli mer effektiva och hålla sig à jour på följande sätt:

- Begränsa de moduler som kan användas på en sida.
- Föreslå standardval för moduler och konfiguration.
- Uttryckligen göra vissa modul- och konfigurationsval som kontrolleras på sidnivå. Den här processen kallas även *låsning* av en inställning.

Följande exempel visar hur en grundläggande mall (mall X) kan konfigureras:

- Alla underordnade layouter för mall X måste ha en rubrikbehållare, en brödtextbehållare och en sidfotsbehållare.
- I mall X är konfigurationen av rubrikbehållaren låst och kan bara ändras i mall X. Alla underordnade layouter och sidor har alltid den här rubriken.
- Brödtextbehållaren måste innehålla minst en modul och upp till tio moduler. Dessa moduler definieras av underordnade layouter och sidor.
- För brödtextbehållaren finns det en fokus-, funktions-, karusell- och banderollmodul.
- En sidfotsbehållare konfigureras i mall X, men kan åsidosättas med efterföljande layouter och sidor.

Mallen i det här exemplet definierar en enkel struktur och en uppsättning alternativ för författare av underordnade innehåll. Lägg märke till att vissa delar av en sida (i det här fallet rubriken) är fullständigt definierade och låsta i mallen, och att de inte kan ändras av efterföljande författare. Andra delar (i det här fallet brödtext) kan definieras av en underordnad författare inom särskilda riktlinjer (i det här fallet ett minsta antal och högsta antal moduler av specifika typer). Och andra delar (i det här fallet sidfoten) definieras i mallen men kan åsidosättas av författare som är underordnade.

Ett viktigt första steg för webbplats- och varumärkesadministratörer är att fastställa rätt balans mellan begränsning och flexibilitet för underordnade layouter och sidförfattare. När mallar används är saldot helt konfigurerbart. Det påverkar om sidelementen har uppdaterats centralt (låsts i mallen) eller till enskilda underordnade nivåer som är lägre i sidhierarkin.

Om du vill börja använda mallar [arbeta med mallar](work-with-templates.md).

## <a name="layouts"></a>Layouter

Layouter är nästa nivå i sidmodellens hierarki, under mallar. En mall definierar alla moduler som är tillåtna för en sida, men en layout är ett explicit urval och arrangemang av moduler. Sidor är nästa nivå i sidmodellens hierarki, under layouter. De definierar det lokalanpassade innehållet för modulerna som väljs i layouten.

Följande exempel bygger på mallen från föregående avsnitt och visar hur en grundläggande layout kan konfigureras:

- Den överordnade mallen för layouten kräver att brödtextbehållaren har mellan en och tio moduler. Modulerna kan bara vara fokus-, funktions-, karusell- och banderollmoduler. Därför kan layouten definiera följande urval och arrangemang för moduler:

    - Den första modulen i brödtextbehållaren är en webbannons, som följs av en fokusmodul och två funktionsmoduler.
    - Den första funktionsmodulen är vänsterjusterad och den andra modulen är högerjusterad.

- Även om en standardsidfoten är ärvd från den överordnade mallen, lämnade mallförfattaren sidfoten olåst. Därför kan layouten åsidosättas genom att ett annat sidfotsavsnitt definieras.

Layouten i det här exemplet definierar den slutliga ordningen för moduler för underordnade sidor. Precis som en mall kan en layout definiera standardformat eller låsta modulegenskaper som alltid ska ärvas av underordnade sidor (t.ex. justeringen av funktionsmodulen). Det faktiska innehållet eller data för varje modul i layouten definieras sedan längre ned i hierarkin, i varje instans av underordnad sida. En viktig skillnad här är att layouterna inte direkt innehåller lokaliseringsbara innehåll, medan deras underordnade sidor gör det. Layoutens primära funktion är att definiera den slutliga ordningen och standardkonfigurationen av moduler för underordnade sidor.

Den här hierarkin är kraftfull av två skäl. För det första behandlas layouter som delar samma överordnade mall som kompatibla med layoutväxlingsscenarier. Därför kan layouten för en sida ändras till en annan layout från samma mall, utan att sidnivåinnehållet måste redigeras på nytt. Du kan dra nytta av den här möjligheten att göra säsongsmässiga designuppdateringar, experimentera eller göra en omdefiniering av en permanent webbplats. För det andra kan du med hjälp av layouten ändra delade element centralt för en grupp med sidor utan att behöva uppdatera enskilda sidor. Om en produktkategori till exempel har 1 000 sidor som delar samma layout, kan modulerna ordnas om i layouten och den här ändringen återspeglas i alla 1 000 underordnade sidor.

Genom att förstå den här hierarkin kan du ge en smidig och effektiv webbplatsstruktur som hjälper till att spara kostnader, är skalbar och ger bättre resultat allt eftersom webbplatsen utvecklas över tiden.

### <a name="preset-and-custom-layouts"></a>Förinställda och anpassade layouter

Layouterna på din webbplats kan vara antingen *förinställda* eller *anpassade*:

- **Förinställda layouter** gör det möjligt att skapa ett arbetsflöde där alla moduler redan är markerade och ordnade, och endast datainmatning krävs. Det här tillvägagångssättet gör det enklare att spara tid när många sidor måste ha samma krav på layouten. Förinställda layouter har en 1:n-relation till sina underordnade sidor. Därför kan en enda förinställd layout användas för att styra modulen för hundratals eller tusentals underordnade sidor centralt.
- **Anpassade layouter** är i huvudsak layouter för engångsbruk som är inbäddade på en sida. De visas inte som ett alternativ när andra nya sidor skapas eller när du växlar mellan olika layouter. Fördelen med den här metoden är att en författare kan experimentera genom att redigera en sida som använder en anpassad layout. Om författaren vill återanvända layouten för andra sidor kan den enkelt konverteras till en förinställd layout. Den nya förinställda layouten visas sedan som ett alternativ i arbetsflöden för sid skapande och i layoutändringar för sidor från samma mall. Omvänt kan förinställda layouter förgrenas i anpassade layouter. På så sätt kan en författare bryta en sida utanför den förinställda layouten och skapa en ny anpassad layout med en enda användning. (Den nya anpassade layouten är fortfarande bunden av eventuella begränsningar i den överordnade mallen.)

Förinställd layout och anpassade layouter redigeras i olika delar av redigeringsverktygen. Eftersom anpassade layouter inte är beroende av andra sidor redigeras de direkt i sidredigeraren. I detta fall är det oftast genomskinligt att använda en layout för användaren och den visas bara i egenskaper på sidnivå och genom åtgärderna för layoutalternativ. Eftersom ändringar av förinställda layouter kan påverka många underordnade sidor måste de dock redigeras i layoutredigeraren, där publiceringsåtgärder ser hela den fullständiga effekten på underordnade sidor.

I följande illustrationer visas scenarierna för förinställda och anpassade layouter.

![Förinställda och anpassade layoutscenarier.](../commerce/media/template-figure1.png)

Information om hur du använder förinställda layouter finns i [arbeta med förinställda layouter](work-with-layouts.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Arbeta med mallar](work-with-templates.md)

[Arbeta med förinställda layouter](work-with-layouts.md)

[Arbeta med publiceringsgrupper](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
