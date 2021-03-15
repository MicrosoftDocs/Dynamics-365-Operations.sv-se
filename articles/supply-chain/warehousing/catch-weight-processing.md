---
title: Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning
description: Detta avsnitt beskriver hur man använder mallar och placering direktiven för att bestämma hur och var arbetet utförs i lagret.
author: perlynne
manager: tfehr
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy, TMSLoadBuildWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 6ecadb06adce5a0cbf1614c7da8fc65cb801e249
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001188"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning

[!include [banner](../includes/banner.md)]


## <a name="feature-exposure"></a>Funktionen exponering

Om du vill använda lagerstyrning för att bearbeta produkt i faktisk/nominell vikt måste du använda en licensnyckelkonfiguration för att aktivera funktionen. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**. Klicka sedan på fliken **konfigurationsnycklar**, expandera **handel \> hantering av lager och transport** och markera kryssrutan för **faktisk/nominell vikt för lagerstället**.

> [!NOTE]
> Både **hantering av lager och transport** licensnyckeln för konfiguration och **Processfördelning \> faktisk/nominell vikt** måste också aktiveras. Om du vill ställa in konfigurationsnycklarna för faktisk/nominell vikt måste du också aktivera funktionen med hjälp av arbetsytan **funktionshantering**. Huvudfunktionen som måste aktiveras är **Bearbetning av produkt i faktisk/nominell vikt med lagerstyrning**. Två relaterade funktioner som du kanske vill aktivera är **lagerstatusändringar för produkter för faktisk/nominell vikt** och **Använd befintliga koder för faktisk/nominell vikt vid rapportering av tillverkningsorder som färdiga**.

Efter att licenskonfigurationens nyckel är inaktiverad, när du skapar en frisläppt produkt, kan du välja **faktisk/nominell vikt**. Du kan också koppla frisläppt produkt till en lagringsdimension som parametern **använda processer för lagerhantering** väljs för.

Innan du kan använda produkten i lagerstyrning, måste du göra vissa grundläggande produktspecifika inställningar för faktisk/nominell vikt:

- Definiera konverteringen mellan enheten för faktisk/nominell vikt (låda) och lagerenheten (kilogram \[kg\]) som en del av en definition för enhetskonvertering.
- Ange minimi- eller maximivikttoleranser som del av inställningen av faktisk/nominell viktenhet.
- Skapa en enhetssekvensgrupp där faktisk/nominell viktenheten definieras som den lägsta lagerhållningsenhet (SKU).
- Ställ in en policy för hantering av faktisk/nominell vikt.

Mer information finns i [ställa in och underhålla artiklar i faktisk/nominell vikt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Transaktionjusteringar

Eftersom vikten av lagret när det gäller i ett lagerställe kan skilja sig från vikt när lagret utfärdas från lagerstället, måste bearbetning av produkt med faktisk/nominell vikt justera lagret.

> [!NOTE]
> Den mobila enhetens aktivitet utlöser transaktionsjusteringarna endast om avvikelsemetoden för utgående vikt i artikelns hanteringsprincip för faktisk/nominell vikt är **Tillåt viktavvikelse**.

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

Om den faktiska vikten registreras in på förpackningsstationen under packning av behållar ombeds lagerarbetare att inte hämta vikten vid plockningsarbete. I stället används genomsnittlig vikt för fysiskt lager som vikt för det plockade lagret som leder till packningsområdet. Det här konceptet gäller även för faktisk/nominell vikt artiklar som spåras med koder. För kodspårade artiklar avgör dessa parametrar när koden registreras. Koden kan hämtas antingen vid en plockningstid genom att använda den mobila enheten eller under den manuella packningen.

> [!NOTE]
> Eftersom alternativet **förpackning** gör att inventeringen uppdateras med den genomsnittliga plockade vikten, kan detta utlösa en avvikelse som skulle kunna orsaka en justering av faktisk/nominell vikt och/eller en skillnad mellan lagerbehållningens vikt och kod för faktisk/nominell vikt.

För interna lagerhanteringsprocesser som räkning och justeringskorrigeringar är det möjligt att definiera om vikten ska registreras eller inte. Om inte registrerad ska nominell vikt användas. Med andra alternativ kan du fånga faktisk/nominell vikt och kvantitet per inventering.

Du kan definiera hur vikt registreras. I den ena av två huvudsakliga flöden fångstvikt taggar spåras och används för att hämta vikt. I det andra flödet spåras inte faktisk/nominell vikt.

- **Ja** - artikel används i faktisk/nominell vikt taggar. Varje taggnummer motsvarar en enhet för faktisk/nominell vikt (låda) och en vikt och annan information som är associerad med taggen. Vikten som är associerad med taggen används för utgående processer.
- **Nej** – artikeln använder inte nominella vikttaggar. Inkommande och utgående vägningsprocesser baseras på den faktiska vikten som registreras under varje process.

Processen för att spåra faktisk/nominell vikt kan användas för artiklar där vikten inte förändras under lagringsperiodens. Vikten registreras bara i processer för ankommande lager. Under den utgående processen kommer taggar för faktisk/nominell vikt bara att skannas och vikterna som är associerade med taggarna kommer att användas för utgående transaktionsbehandling.

En annan viktig parameter som är relaterad till bearbetningen av koder för faktisk/nominell vikt är **spårnings metod för kod för faktisk/nominell vikt**. Koder kan antingen spåras eller spåras helt eller delvis. Om en kod endast spåras delvis kommer produktdimensioner, spårningsdimensioner och lagerstatus att spåras. Om en kod spåras helt kommer produktdimensioner, spårningsdimensioner och **alla** lagerdimensioner att spåras.

När en artikel är en kod, spåras dessutom en parameter för **Inhämtningsmetod för utgående vikt**. Du kan ställa in den här parametern så att du alltid uppmanas att ange koden för utgående transaktioner från den mobila enheten. Du kan också ställa in parametern så att du bara uppmanas att ange koder när de behövs. Det finns till exempel fem koder för faktisk/nominell vikt i lagret på en viss registreringsskylt och du har angett att du vill plocka alla fem koder från registreringsskylten. I detta fall, om parametern **Inhämtningsmetod för utgående vikt** anges till **endast fråga efter kod vid behov** plockas de fem koderna automatiskt. Du behöver inte skanna varje kod. Om parametern är inställd på att **Fråga alltid efter kod** måste du skanna varje kod, även om alla fem koderna hämtas.

> [!NOTE]
> Som regel sparas och uppdateras koderna endast på menyalternativen på den mobila enheten. Det finns dock några situationer där koderna har fångats in någon annanstans (t.ex. från den manuella förpackningsstationen). Vanligtvis ska menyalternativen på den mobila enheten användas för alla lageraktiviteter om koder används.

### <a name="how-to-capture-catch-weight"></a>Så här registrerar du faktisk/nominell vikt

**När spårning av taggar för faktisk/nominell vikt används** måste taggen alltid skapas för varje faktisk/nominell viktenhet som tas emot och varje tagg måste alltid associeras med en vikt.

Till exempel **Låda** är faktisk/nominell viktenheten och du får en lastpall med åtta lådor. I det här fallet måste åtta unika taggar för faktisk/nominell vikt skapas och en vikt måste vara associerad med varje tagg. Beroende på taggen för inkommande faktisk/nominell vikt måste antingen vikten för alla åtta lådor registreras och den genomsnittliga vikten som sedan kan distribueras till varje låda eller en unik vikt registreras in för varje låda.
När du använder funktionen **Använd befintliga koder för faktisk/nominell vikt vid rapportering av tillverkningsorder som färdiga** med processen aktiverad via en menyartikel på en mobil enhet, uppdateras lagret baserat på den befintliga informationen på fliken om faktisk/nominell vikt. Detta innebär att modulen för lagerstyrning inte ber om att fånga upp taggdata för faktisk/nominell vikt som en del av en produktions rapport som en avslutad operation.

**När spårning av tagg för faktisk/nominell vikt inte används** registreras vikten för varje dimensionsuppsättning (till exempel för varje registreringsskylt och spårningsdimension). Du kan också registrera vikten in baserat på aggregerad nivå, t.ex. fem registreringsskyltar (lastpallar).

För metoderna för insamling av utgående vikt, kan du med alternativet **Per enhet för faktisk/nominell vikt** ange att vägningen ska göras för varje enhet för faktisk/nominell vikt (t.ex. per låda). Med alternativet **per plockningsenhet** kan du ange att vikten ska fångas in baserat på den kvantitet som ska plockas (t.ex. tre lådor). Observera att för plocknings- och interna förflyttningsprocessen ska genomsnittsvikten användas om alternativet **inte registrerad** används.

Flera inhämtningsmetoder för vikter anges på hanteringspolicyn för artiklar i faktisk/nominell vikt. Varje metodparameter för viktinhämtning används i olika transaktioner. I följande tabell sammanfattas de parametrar som används för transaktionerna.

| Metod                                     | Transaktion                                |
|--------------------------------------------|--------------------------------------------|
| Inhämtningsmetod för utgående vikt           | Försäljningsplockning, överföringsplockning            |
| Inhämtningsmetod för produktionsplockningsvikt | Produktionsplockning, produktionsförbrukning |
| Inhämtningsmetod för förflyttningsvikt           | Rörelse                                   |
| När korrigering av vikt ska inhämtas       | Justeringar, beräkning                      |
| Inhämtningsmetod för inventeringsvikt           | Inventering                                   |
| Inhämtningsmetod för lagerställets överföringsvikt | Överföring lagerställe                         |

För att förhindra att lagerstyrningens plockningsprocesser samlar in vikter som orsakar för justeringar av vinst/förlust för faktisk/nominell vikt kan utgående viktavvikelsemetod användas. Utgående viktavvikelsemetod gäller under följande mobila enhetsprocesser: försäljningsplockning, överföringsplockning, produktionsplockning, transporter, inventering och lageröverföringar. Du kan använda alternativet **begränsa viktavvikelse** om fångstviktartikel inte ändras under lagerstället och om justering av vinst/förlust för faktisk/nominell vikt inte behövs. Du kan använda alternativet **Tillåt viktavvikelse** om vikten kan ändras, och om justering av vinst/förlust på faktisk/nominell vikt krävs när en viktvariation registreras.

## <a name="unsupported-scenarios"></a>Scenarier som inte stöds

Alla arbetsflöden stöder inte bearbetning av produkt i faktisk/nominell vikt med lagerstyrning. Följande begränsningar gäller för tillfället. De gäller för alla artiklar i faktisk/nominell vikt, oavsett om de är kodade eller inte.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Bearbetning av produkt i faktisk/nominell vikt med lagerstyrningsprocesser

- Endast formelbearbetning stöds för produkter med faktisk/nominell viktfaktisk/nominell vikt (inte strukturlista).
- Produkter med faktisk/nominell vikt kan inte associeras med en spårningsdimensionsgrupp med dimensionsägare.
- Produkter med faktisk/nominell vikt kan inte användas som tjänster.
- Produkter med faktisk/nominell vikt kan endast användas som ”produkter som finns i lager” som del av artikelmodellgruppen.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att spåra ”Aktiv i försäljningsprocessen”.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer. Därför kan inte produkter föras över från ”tom” till ett serienummer som en del av plockning/packningsprocessen.
- Produker med faktisk/nominell vikt kan inte användas tillsammans med funktionen för att registrera serienummer före förbrukning.
- Produkter med faktisk/nominell vikt som är variantaktiverade kan inte användas tillsammans med funktionen för att konvertera en variant av måttenhet.
- En produkt med faktisk/nominell vikt kan inte markeras som produktpaket i handel.
- Produkt med faktisk/nominell vikt kan bara användas med en enhetssekvensgrupp med faktisk/nominell vikthanteringsenheter och som har som lägst sekvens av faktisk/nominell viktenhet.
- För produkter med faktisk/nominell vikt får lagerenheten endast omvandlas till faktisk/nominell viktenhet om konvertering ger en nominell kvantitet som är mer än 1.
- Inställningen av streckkoder för produkter med faktisk/nominell vikt stöder inte en variabel inställning.

### <a name="order-processing"></a>Orderbehandling

- Skapandet av leveransavisering (ASN/förpackningsstruktur) stöder inte information om vikt.
- Orderkvantiteten måste underhållas utifrån faktisk/nominell viktenheten.

### <a name="inbound-warehouse-processing"></a>Bearbetning av ingående lagerställe

- Ta emot registreringsskyltar kräver att vikter tilldelas under registreringen, eftersom viktinformation inte stöds som en del av leveransaviseringen. Processer för taggar för faktisk/nominell vikt när taggnummer måste tilldelas manuellt per faktisk/nominell vikt.
- Kontrollen av ankommande kvalitetskontroll stöds inte för produkter av faktisk/nominell vikt. Om kvalitetskontrollen är konfigurerad hoppas det över.

### <a name="inventory-and-warehouse-operations"></a>Operationer för lager och lagerställen

- Skapa karantänorder manuellt stöds inte för produkter med faktisk/nominell vikt.
- Manuell lagerförflyttning relaterad till öppet arbete stöds inte för produkter med faktisk/nominell vikt.
- Inläsningen av registreringsskylt initierar lagerställe stöds inte för produkter med faktisk/nominell vikt.
- Batchbalanseringsprocesser stöds inte för produkter med faktisk/nominell vikt.
- Hantering av fysiskt negativt lager stöds inte för produkter med faktisk/nominell vikt.
- Lagermarkering kan inte användas för produkter med faktisk/nominell vikt.

### <a name="outbound-warehouse-processing"></a>Bearbetning av utgående lagerställe

- Funktionen för plockning av kluster stöds inte för produkter med faktisk/nominell vikt.
- Lagerbearbetning för plocka och packa stöds inte för produkter med faktisk/nominell vikt.
- Produkter med faktisk/nominell vikt som definieras i en arbetsmall kan inte köras automatiskt.
- För produkter med faktisk/nominell vikt stöder inte systemet manuell stationsbearbetning plockarbete i förpackade behållare skapas när behållare stängs.
- Funktionen för skanning styckvis stöds inte för produkter med faktisk/nominell vikt.

### <a name="production-processing"></a>Produktionsprocess

- För produkter med faktisk/nominell vikt stöds endast batchorder för formelprodukter.
- Kanban-funktionen stöds inte för produkter med faktisk/nominell vikt.
- Serienummer kan inte registreras före förbrukning för produkter med faktisk/nominell vikt.
- Funktionen för återföring av registreringsskylt från produktion stöds inte för produkter med faktisk/nominell vikt.
- Produkter med faktisk/nominell vikt kan rapporteras som färdig registreras efter serienummer.

### <a name="transportation-management-processing"></a>Transporthanteringsprocesser

- Workbench för lastuppbyggnad stöds inte för produkter med faktisk/nominell vikt.
- Rader för transportförfrågan stöds inte för produkter med faktisk/nominell vikt.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Andra begränsningar och beteenden för processer med produkter med faktisk/nominell vikt med lagerstyrning

- Vid plockningsprocesser där användaren inte ombeds att identifiera spårningsdimensioner sker viktfördelningen utifrån den genomsnittliga vikten. Detta beteende uppstår när exempelvis en kombination av spårningsdimensioner används på samma plats och efter att en användare bearbetar plockning lämnas endast en spårningsdimension kvar på platsen.
- När lagret reserveras för en produkt med faktisk/nominell vikt som är konfigurerad för lagerhanteringsprocesser görs bokningen baserat på den minsta vikten som definieras, även om den här kvantiteten är den sista hanteringskvantiteten. Detta beteende skiljer sig från funktionen för artiklar som inte är konfigurerade för hantering av lagerprocesser. Det finns ett undantag till den här begränsningen. För produktionsplockning används den faktiska vikten för den senaste hanteringen av en produkt av faktisk/nominell vikt som är serienummerkontrollerad.
- Processer som använder vikten som en del av kapacitetsberäkningar (vågtröskelvärden, arbetets maximala raster, maximal kapacitet för behållare, lastningskapacitet för platsen och så vidare) använder inte lagrets faktiska vikt. I stället baseras processer på vikten av fysisk hantering som är definierad för produkten.
- I allmänhet stöds inte handelsfunktionen för produkter med faktisk/nominell vikt.
- För produkter med faktisk/nominell vikt går det inte att uppdatera lagerstatus från **ändring av lagerstatus**.

### <a name="catch-weight-tags"></a>Koder för faktisk/nominell vikt

En kod för faktisk/nominell vikt kan skapas med en lagerstyrningsapprocess, skapas manuellt i formuläret eller skapas med en dataentitetsprocess. Om en kod för nominell vikt blir associerad med en inkommande källdokumentrad, till exempel inköpsorderrad, kommer koden att registreras. Om raden används för utgående bearbetning kommer märket att uppdateras som levererat.

Utöver de begränsningar som för närvarande gäller för produkter med faktisk/nominell vikt har kodade produkter med faktisk/nominell vikt andra begränsningar som gäller för närvarande.

- Alla manuella uppdateringar av lagret (dvs. uppdateringar som inte görs med en mobil enhet) måste inkludera motsvarande manuella uppdateringar av de tillhörande koderna för faktisk/nominell vikt eftersom dessa uppdateringar inte utförs automatiskt. Manuella justeringsjournaler uppdaterar till exempel lager, men inte tillhörande koder för faktisk/nominell vikt.
- Du måste uppdatera koderna för faktisk/nominell vikt manuellt för att återspegla lagerpåfyllnadsarbete. Detta beror på att systemet inte kan hämta vikter under bearbetningen av påfyllningsarbetet och därför registrerar genomsnittsvikten i stället.
- Inleverans av blandade registreringsskyltar stöds inte för artiklar för faktisk/nominell vikt med kod.
- När mottagning av försäljningsreturorder registreras kan koder för faktisk/nominell vikt registreras. Däremot verifierar inte processen att den returnerade koden är samma kod som ursprungligen levererades för en försäljningsorder.
- Menyalternativet mobil enhet som innehåller aktivitetskoden **Registrera materialförbrukning** stöder inte registrering av koder för faktisk/nominell vikt.
- Även om inventeringsprocesser stöds för kodade artiklar med faktisk/nominell vikt, är de begränsade. Du kan till exempel använda alternativen för mobila enheter för att räkna upp kodade artiklar med faktisk/nominell vikt och den genomsnittliga vikten används. Koder för faktisk/nominell vikt uppdateras dock inte automatiskt av inventeringstransaktionen. När inventeringstransaktionen har slutförts måste koderna för faktisk/nominell vikt uppdateras manuellt så att de återspeglar lagret. Om artiklar som inte ursprungligen var på en plats räknas till den platsen, används den nominella vikten.
- Konsolidering av registreringsskylt har inte stöd för kodade artiklar med faktisk/nominell vikt.
- Funktionen för återför arbete stöds inte för artiklar med faktisk/nominell vikt som är kodnummerspårade.

> [!NOTE]
> Den föregående informationen om koderna för faktisk/nominell vikt är endast giltig om produkten med faktisk/nominell vikt har en spårningsmetod för kod för faktisk/nominell vikt som är helt spårad (det vill säga om parametern **spårningsmetod för kod för faktisk/nominell vikt** för hanteringspolicyn anges till **produktdimensioner, spårningsdimensioner och alla lagerdimensioner**). Om artikeln med faktisk/nominell vikt endast delvis kodspåras (det vill säga om parametern **spårningsmetod för kod för faktisk/nominell vikt** för hanteringspolicyn för faktisk/nominell vikt anges till **produktdimensioner, spårningsdimensioner och lagerstatus**), gäller ytterligare begränsningar. Eftersom visningen går förlorad mellan koden och lagret i det här fallet, stöds inte vissa ytterligare scenarier.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]