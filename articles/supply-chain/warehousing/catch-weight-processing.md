---
title: Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning
description: Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.
author: perlynne
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: ed588ea28bec3e734f9648c1fbd7551ab0b3cdda
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836127"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/pivate-preview-banner.md)]


## <a name="feature-exposure"></a>Funktionen exponering

Om du vill använda lagerstyrning för att bearbeta produkt i faktisk/nominell vikt måste du använda en licensnyckelkonfiguration för att aktivera funktionen. (Gå till **Systemadministration \> Inställningar \> Licenskonfiguration**. Klicka sedan på fliken **konfigurationsnycklar**, expandera **handel \> hantering av lager och transport** och markera kryssrutan för **faktisk/nominell vikt för lagerstället**).

> [!NOTE]
> Både **hantering av lager och transport** licensnyckeln för konfiguration och **Processfördelning \> faktisk/nominell vikt** måste också aktiveras.

Efter att licenskonfigurationens nyckel är inaktiverad, när du skapar en frisläppt produkt, kan du välja **faktisk/nominell vikt**. Du kan också koppla frisläppt produkt till en lagringsdimension som parametern **använda processer för lagerhantering** väljs för.

Innan du kan använda produkten i lagerstyrning, måste du göra vissa grundläggande produktspecifika inställningar för faktisk/nominell vikt:

- Definiera konverteringen mellan enheten för faktisk/nominell vikt (låda) och lagerenheten (kilogram \[kg\]) som en del av en definition för enhetskonvertering.
- Ange minimi- eller maximivikttoleranser som del av inställningen av faktisk/nominell viktenhet.
- Skapa en enhetssekvensgrupp där faktisk/nominell viktenheten definieras som den lägsta lagerhållningsenhet (SKU).
- Ställ in en policy för hantering av faktisk/nominell vikt.

Mer information finns i [ställa in och underhålla artiklar i faktisk/nominell vikt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Transaktionjusteringar

Eftersom vikten av lagret när det gäller i ett lagerställe kan skilja sig från vikt när lagret utfärdas från lagerstället, måste bearbetning av produkt med faktisk/nominell vikt justera lagret.

**Exempel 1**

Under produktionsprocessen **rapportera som färdig** måste den inkommande vikten av en registreringsskylt som innehåller åtta rutor hos en produkt faktisk/nominell vikt registreras som 80,1 kg. Registreringsskylt lagras direkt i området för färdiga varor och under lagringsperioden, försvinner viss vikt i luften.

Vikten av samma registreringsskylt fångas senare som en del av en process, plockning försäljningsorder som 79,8 kg. Därför har du i systemet en viktskillnad som en del av fysiska dimensionsuppsättningen.

I det här fallet justeras skillnaden automatiskt genom att bokföra en transaktion för saknade 0,3 kg.

**Exempel 2**

I dess definition ställs en produkt in för att klara en lägsta vikt på 8 kg och en maximal vikt på 12 kg för enhet för faktisk/nominell vikt **låda**.

Du har två lådor av produkten och de har 16 kg registrerad vikt. Om lagerarbetare plockar väger en av lådorna och vikt registreras som 9 kg, väger återstående fält 7 kg. Men eftersom 7 kg är lägre än lägsta vikten, gör systemet en automatisk justering för att öka vikten på lagerbehållningen med 1 kg.

Om du vill ställa in kontona justeringarna bokförs på Gå till **kostnadshantering \> Ställ in policyer för redovisningsintegrering \> bokföring**. Klicka sedan på fliken **lager**, ange följande konton:

- Förlustkonto för faktisk/nominell vikt
- Vinstkonto för faktisk/nominell vikt

## <a name="catch-weight-item-handling-policy"></a>Hanteringspolicy för artiklar i faktisk/nominell vikt

Hanteringspolicy för artikel med faktisk/nominell vikt definierar två primära flöden för lagerställehantering för artiklar: när vikten på artiklarna registreras och hur den hämtas.

Du kan definiera när vikt registreras för orderbehandling för försäljning och överföring. Vikten kan hämtas under någon av följande processer:

- **Plockning** – vikten registreras under första plockningsraderna för orderarbete.
- **Packning** – vikten registreras under manuell packning. (Du måste skicka artiklar till en förpackningsstation.)

Om den faktiska vikten registreras in på förpackningsstationen under packning av behållar ombeds lagerarbetare att inte hämta vikten vid plockningsarbete. I stället används genomsnittlig vikt för fysiskt lager som vikt för det plockade lagret som leder till packningsområdet.

För interna lagerhanteringsprocesser som räkning och justeringskorrigeringar är det möjligt att definiera om vikten ska registreras eller inte. Om inte registrerad ska nominell vikt användas.

Du kan definiera hur vikt registreras. I den ena av två huvudsakliga flöden fångstvikt taggar spåras och används för att hämta vikt. I det andra flödet spåras inte faktisk/nominell vikt.

- **Ja** - artikel används i faktisk/nominell vikt taggar. Varje taggnummer motsvarar en enhet för faktisk/nominell vikt (låda) och en vikt och annan information som är associerad med taggen. Vikten som är associerad med taggen används för utgående processer.
- **Nej** – artikeln använder inte nominella vikttaggar. Inkommande och utgående vägningsprocesser baseras på den faktiska vikten som registreras under varje process.

Processen för att spåra faktisk/nominell vikt kan användas för artiklar där vikten inte förändras under lagringsperiodens. Vikten registreras bara i processer för ankommande lager. Under den utgående processen kommer taggar för faktisk/nominell vikt bara att skannas och vikterna som är associerade med taggarna kommer att användas för utgående transaktionsbehandling.

### <a name="how-to-capture-catch-weight"></a>Så här registrerar du faktisk/nominell vikt

När spårning av taggar för faktisk/nominell vikt används måste taggen alltid skapas för varje faktisk/nominell viktenhet som tas emot och varje tagg måste alltid associeras med en vikt.

Till exempel **Låda** är faktisk/nominell viktenheten och du får en lastpall med åtta lådor. I det här fallet måste åtta unika taggar för faktisk/nominell vikt skapas och en vikt måste vara associerad med varje tagg. Beroende på taggen för inkommande faktisk/nominell vikt måste antingen vikten för alla åtta lådor registreras och den genomsnittliga vikten som sedan kan distribueras till varje låda eller en unik vikt registreras in för varje låda.

När spårning av tagg för faktisk/nominell vikt inte används registreras vikten för varje dimensionsuppsättning (till exempel för varje registreringsskylt och spårningsdimension). Du kan också registrera vikten in baserat på aggregerad nivå, t.ex. fem registreringsskyltar (lastpallar).

För metoder för att registrera utgående vikt, kan du ange om vägning utförs för varje faktisk/nominell viktenhet (det vill säga varje låda), eller om vikten registreras baserat på den kvantitet som plockas (t.ex. tre lådor). Observera att för plocknings- och interna förflyttningsprocessen ska genomsnittsvikten användas om alternativet **inte registrerad** används.

För att begränsa att lagerstyrningens plockningsprocesser samlar in vikter som resulterar i för justeringar av vinst/förlust för faktisk/nominell vikt kan utgående viktavvikelsemetod användas.

## <a name="supported-scenarios"></a>Stödda scenarier

Alla arbetsflöden stöder inte bearbetning av produkt i faktisk/nominell vikt med lagerstyrning. Följande begränsningar gäller för tillfället.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Bearbetning av produkt i faktisk/nominell vikt med lagerstyrningsprocesser

- För produkter med faktisk/nominell vikt kan inte lagringsdimensionsgruppen för artiklar ändras (så att lagerprocess hantering kan användas för dem).
- Endast formelbearbetning stöds för produkter med faktisk/nominell viktfaktisk/nominell vikt (inte strukturlista).
- Produkter med faktisk/nominell vikt kan inte associeras med en spårningsdimensionsgrupp med dimensionsägare.
- Produkter med faktisk/nominell vikt kan inte användas som tjänster.
- Produkter med faktisk/nominell vikt kan endast användas som ”produkter som finns i lager” som del av artikelmodellgruppen.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att spåra ”Aktiv i försäljningsprocessen”.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer. Därför kan inte produkter föras över från ”tom” till ett serienummer som en del av plockning/packningsprocessen.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer före förbrukning.
- Produkter med faktisk/nominell vikt som är variantaktiverade kan inte användas tillsammans med funktionen för att konvertera en variant av måttenhet.
- En produkt med faktisk/nominell vikt kan inte markeras som produktpaket.
- Produkt med faktisk/nominell vikt kan bara användas med en enhetssekvensgrupp med faktisk/nominell vikthanteringsenheter och som har som lägst sekvens av faktisk/nominell viktenhet.
- För produkter med faktisk/nominell vikt får lagerenheten endast omvandlas till faktisk/nominell viktenhet om konvertering ger en nominell kvantitet som är mer än 1.
- Inställningen av streckkoder för produkter med faktisk/nominell vikt stöder inte en variabel inställning.
 
### <a name="order-processing"></a>Orderbehandling

- Skapandet av leveransavisering (ASN/förpackningsstruktur) stöder inte information om vikt.
- Orderkvantiteten måste underhållas utifrån faktisk/nominell viktenheten.
 
### <a name="inbound-warehouse-processing"></a>Bearbetning av ingående lagerställe

- Ta emot registreringsskyltar kräver att vikter tilldelas under registreringen, eftersom viktinformation inte stöds som en del av leveransaviseringen. Processer för taggar för faktisk/nominell vikt när taggnummer måste tilldelas manuellt per faktisk/nominell vikt.
 
### <a name="inventory-and-warehouse-operations"></a>Operationer för lager och lagerställen

- Skapa karantänorder manuellt stöds inte för produkter med faktisk/nominell vikt.
- Manuell lagerförflyttning relaterad till arbete stöds inte för produkter med faktisk/nominell vikt.
- Konsolidering av licensskyltar stöds inte för produkter med faktisk/nominell vikt.
- Inläsningen av registreringsskylt initierar lagerställe stöds inte för produkter med faktisk/nominell vikt.
- Batchbalanseringsprocesser stöds inte för produkter med faktisk/nominell vikt.
- Hantering av fysiskt negativt lager stöds inte för produkter med faktisk/nominell vikt.
- Lagermarkering kan inte användas för produkter med faktisk/nominell vikt.
 
### <a name="outbound-warehouse-processing"></a>Bearbetning av utgående lagerställe

- Funktionen för plockning av kluster stöds inte för produkter med faktisk/nominell vikt.
- Lagerbearbetning för plocka och packa stöds inte för produkter med faktisk/nominell vikt.
- Produkter med faktisk/nominell vikt som definieras i en arbetsmall kan köras automatiskt.
- Funktionen för återföringsarbete stöds inte för produkter med faktisk/nominell vikt.
- För produkter med faktisk/nominell vikt stöds inte manuell stationsbearbetning där arbete skapas när behållare stängs.
- Funktionen för skanning styckvis stöds inte för produkter med faktisk/nominell vikt.
 
### <a name="production-processing"></a>Produktionsprocess

- För produkter med faktisk/nominell vikt stöds endast batchorder för formelprodukter.
- Kanban-funktionen stöds inte för produkter med faktisk/nominell vikt.
- Serienummer kan inte registreras före förbrukning för produkter med faktisk/nominell vikt.
- Funktionen för återföring av registreringsskylt stöds inte för produkter med faktisk/nominell vikt.
- Produkter med faktisk/nominell vikt kan inte rapporteras som färdig registreras efter serienummer.

### <a name="transportation-management-processing"></a>Transporthanteringsprocesser

- Workbench för lastuppbyggnad stöds inte för produkter med faktisk/nominell vikt.
- Rader för transportförfrågan stöds inte för produkter med faktisk/nominell vikt.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Andra begränsningar och beteenden för processer med produkter med faktisk/nominell vikt med lagerstyrning

- Vid plockningsprocesser där användaren inte ombeds att identifiera spårningsdimensioner sker viktfördelningen utifrån den genomsnittliga vikten. Detta beteende uppstår när exempelvis en kombination av spårningsdimensioner används på samma plats och efter att en användare bearbetar plockning lämnas endast en spårningsdimension kvar på platsen.
- När lagret reserveras för en produkt med faktisk/nominell vikt som är konfigurerad för lagerhanteringsprocesser görs bokningen baserat på den minsta vikten som definieras, även om den här kvantiteten är den sista hanteringskvantiteten. Detta beteende skiljer sig från funktionen för artiklar som inte är konfigurerade för hantering av lagerprocesser.
- Processer som använder vikten som en del av kapacitetsberäkningar (vågtröskelvärden, arbetets maximala raster, maximal kapacitet för behållare, lastningskapacitet för platsen och så vidare) använder inte lagrets faktiska vikt. I stället baseras processer på vikten av fysisk hantering som är definierad för produkten.
- I allmänhet stöds inte butiksfunktionen för produkter med faktisk/nominell vikt.
 
### <a name="catch-weight-tags"></a>Taggar för faktisk/nominell vikt

Funktionerna för taggar för faktisk/nominell vikt stöds för närvarande bara som en del av följande scenarier:

- När bearbetning av inköpsorder för inleverans via lagerapp.
- När bearbetning av mottagande av last via lagerapp.
- För inleverans av registreringsskylt relaterad till inköpsorderns last, begärs vikttilldelning under inleveransen. Däremot för inleverans av överföringsorder används vikt från försändelsedata för överföringsordern.
- För överföringsorder och radmottagning som kommer från en hanteringsprocess för icke-lagerställe.
- Behandlingen av inleverans av försäljningsreturorder kan registrera taggar för faktisk/nominell vikt, men bearbetningen kommer inte att valideras om taggarna är samma taggar som ursprungligen skickades för en viss försäljningsorderrad.
- När bearbetning av lagerstatus ändras via appen lagerställe.
- När lagerställeöverföring görs via appen lagerställe.
- Vid bearbetning av justering in och ut via appen lagerställe.
- När plockningsarbete bearbetas för försäljnings- och överföringsorder. (Observera att taggar för faktisk/nominell vikt inte kan registreras för plockning av produktionskomponent).
- När plockade kvantiteter minskas från lastrader, oavsett om behållare används.
- När produkter som är förpackade i behållare på en förpackningsstation.
- När behållare öppnas på nytt.
- När formelprodukter rapporteras som färdiga via appen lagerställe.
- När transporten läses in bearbetas via appen lagerställe.

En kod för faktisk/nominell vikt kan skapas antingen med en lagerstyrningsapprocess, skapas manuellt i formuläret eller skapas med en dataentitetsprocess. Om en kod för nominell vikt blir associerad med en inkommande källdokumentrad, till exempel inköpsorderrad, kommer koden att registreras. Om raden används för utgående bearbetning. Koden uppdateras som levererad.
