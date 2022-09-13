---
title: Prissättningsinställningar
description: I den här artikeln beskrivs olika inställningar för prissättning och rabatthantering i Microsoft Dynamics 365 Commerce headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 4bc8cb16e7960d26adbb9590b4ad83cf46b02838
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410785"
---
# <a name="pricing-settings"></a>Prissättningsinställningar

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln beskrivs olika inställningar för prissättning och rabatthantering i Microsoft Dynamics 365 Commerce headquarters. Med dessa inställningar kan organisationer definiera prissättningsbeteendet i sin Handelslösning för att uppfylla specifika affärsbehov.

## <a name="company-level-pricing-settings"></a>Inställningar för prissättning på företagsnivå

De flesta prisinställningar finns på företagsnivå och finns på **Handelsparametrar \> Priser och rabatter** i Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Kontrolläge för bästa pris och sammansatt concurrency

Inställningen **Kontrolläge för bästa pris och sammansatt concurrency** avgör hur prissättningsmotorn behandlar flera rabatter i **bästa pris** eller **sammansatt** concurrency-läge. 

Om parametern är inställd på **Bästa pris och sammansatt inom prioritet, aldrig sammansatt mellan prioriteter** är alla **sammansatta** rabatter som har samma prissättningsprioritet sammansatta. Det sammansatta resultatet konkurrerar sedan med rabatter **bästa pris** som har samma prissättningsprioritet, det bästa priset tillämpas och alla rabatter som har lägre prisprioritet ignoreras.

Om parametern anges till **Bästa pris endast inom prioritet, alltid sammansatt mellan prioriteter**, alla **sammansatta** rabatter behandlas som **bästa pris** rabatter. Inom en prisprioritet kommer endast en enda rabatt att vinnas. Om denna enstaka rabatt är ett **bästa pris** eller **sammansatt** rabatt är den sammansatt med alla ytterligare **bästa pris** eller **sammansatta**  rabatter som har en lägre prissättningsprioritet.

### <a name="discount-compound-behavior"></a>Beteende för sammansatt rabatt

Inställningen **Beteende för sammansatt rabatt** bestämmer hur prissättningsmotorn beräknar flera sammansatta rabatter.

Om parametern är inställd på **Sammansatt** tillämpas en rabatt på en annan rabatt på ett sådant sätt. Om det är inställt på **Sammansatt på det ursprungliga priset** behandlas alla rabatter oberoende av varandra och tillämpas på samma ursprungliga pris.

Till exempel vill du sammansätta 10-procentrabatt och 20-procentrabatter för en produkt som har ett ursprungligt pris 100 $. Om du ställer in parametern **Beteende för sammansatt rabatt** till **Sammansatt**, blir det slutliga priset 72 $ (100 $ &times; 90 % &times; 80 %). Om du ställer in den på **Sammansatt på det ursprungliga priset**, blir det slutliga priset 70 $ (100 $ – 10 $ – 20 $).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Aktivera konkurrens mellan exklusiv tröskel och andra periodiska rabatter

Om parametern **Aktivera konkurrens mellan exklusiv tröskel och andra periodiska rabatter** ställs in på **Ja**, prissättningsmotorn gör att exklusiva tröskelrabatter konkurrerar med exklusiva icke-tröskelrabatter. Prisprioritet gäller fortfarande. Beteendet för **bästa pris** och **sammansatta** tröskelvärde rabatter förblir som är. Med andra ord konkurrerar de inte med de icke-tröskelrabatter.

### <a name="manual-line-discount-and-system-discount"></a>Manuell radrabatt och systemrabatt

Den **manuella radrabatten och systemrabattinställningen** avgör hur prissättningsmotorn tillämpar en manuell radrabatt och en systemrabatt på samma rad. Den manuella radrabatten kan räknas in ovanpå systemrabatten eller så kan den ersätta systemrabatten. När den manuella radrabatten och systemrabatten blandas, följer beräkningslogiken inställningen **Beteende för sammansatt rabatt**. En manuell totalrabatt som gäller för hela ordern har ingen hänsyn till inställningen.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Behåll artiklar på samma försäljningsrad för avrundning av rabattpris

Ibland kan beloppet för ett kvantitetsrabattbelopp inte delas med den kvalificerade kvantiteten (till exempel om rabattbeloppet tas 10 $ tre inköpta enheter). I så fall bestämmer inställningen **Behåll artiklar på samma försäljningsrad för avrundning av rabattpris** bestämmer hur prissättningsmotorn gäller och fördelar rabattbeloppet. Om parametern ställs in på **Ja**, tillämpas rabattbeloppet som helhet och delas inte upp. Om det ställs in på **Nej** delas rabattbeloppet upp över den kvalificerade kvantiteten och avrundas. Till exempel delas ett rabattbelopp 10 $ rabatt för tre enheter upp i 3,33 $ ut för en enhet, 3,33 $ ut för den andra enheten och 3,34 $ ut för den tredje enheten.

### <a name="apply-discounts-to-key-in-price-products"></a>Tillämpa rabatter på "ange pris"-produkter

Inställningen **Använd rabatter för att ange prisprodukter** bestämmer om rabatter kan användas tillsammans med "key-in-priser" som anges i kassan (POS). Inställning **Ange pris** i produktkonfigurationen avgör om och hur en produkt stöder inmatningspriset.

### <a name="apply-discounts-to-price-overrides"></a>Tillämpa rabatter på prisåsidosättningar

Inställningen **Tillämpa rabatter på prisåsidosättningar** avgör om rabatter kan tillämpas tillsammans med prisöverskridanden.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Fördelar rabatt för billigaste rabatter

För mix and match-rabatter som använder den "billigaste" beräkningstypen **Fördelar rabatt för billigaste rabatter** avgör om prissättningsmotorn fördelar rabatten över rader.

Om parametern ställs in på **Nej** används rabatten bara på de billigaste raderna. För en "köp 2 få 1 gratis" mixa och matcha-rabatt blir till exempel den billigaste artikeln gratis och de övriga två artiklarna finns kvar till full pris. I så fall får en kund som returnerar båda fullprisade artiklar ändå den tredje artikeln gratis. Det här scenariot kan orsaka en förlust för återförsäljaren.

Om parametern är inställd på **Ja**, fördelas rabatten av prissättningsmotorn på alla tillämpliga rader. Den här inställningen kan minska förlusten på returer.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Beräkna flerradspriser och rabatter manuellt

Inställningskontroller **Beräkna flerradspriser och rabatter manuellt** styr om prissättningsmotorn använder fördröjd pris- och rabattberäkning för kassaappen och callcenterkanalen. Om parametern är inställd på **Ja**, prissättningsmotorn beräknar inte omedelbart flerradrabatter (såsom kvantitetsrabatter, tröskelrabatter och mixa och matcha-rabatter) närhelst en försäljningsorder skapas eller redigeras i kassaapp eller kundtjänstkanal.

> [!NOTE]
> I Commerce version 10.0.30 och tidigare kontrollerar inställningen **Beräkna flerradspriser och rabatter manuellt** endast kundtjänstkanal. En separat inställning **Manuell beräkning av flera artikelrabatter** i funktionsprofilen styr prisberäkningsbeteendet i kassaappen. I Commerce version 10.0.31 konsolideras de två inställningarna till en inställning på företagsnivå.

### <a name="retention-period-in-days"></a>Kvarhållandeperiod i dagar

Inställningen **Kvarhållandeperiod i dagar** anger hur många dagar efter utgångsdatumet (om ett utgångsdatum är inställt) eller det avaktiverade datumet (om ett utgångsdatum inte är inställt) en rabatt ska tas bort systematiskt. Om parametern ställs in på **0** (noll) sker ingen automatisk radering.

> [!NOTE]
> I Commerce version 10.0.30 och tidigare kallas den här inställningen **Antal dagar efter vilka utgångna rabatter tas bort**.

### <a name="coupon-bar-code"></a>Kupongstreckkod

Inställningen **Kupongstreckkod** avgör vilken specifik streckkod som används för att generera streckkoder. Användarna kan välja en av de fördefinierade streckkoder som konfigureras på sidan för **streckkodsinställningar**. Mer information om streckkoder och streckkodsmasker finns i [Ställa in streckkoder](set-up-bar-codes.md) och [ställa in streckkodsmasker](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>Kupongkoden måste kopplas manuellt till returtransaktioner

Inställningen **Kupongkoden måste kopplas manuellt till returtransaktioner** är endast tillämplig på returtransaktioner som inget försäljningskvitto tillhandahålls för. Ställ in parametern till **Nej** om kupongkoder automatiskt ska tillämpas på transaktionen. Ställ in det till **Ja** om kupongkoder måste läggas till manuellt i transaktionen.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Använd försäljningsavtal inställda för organisationen

För B2B-order, om parametern **Använd försäljningsavtal inställda för organisationen** anges till **Ja** använder prissättningsmotorn de försäljningsavtal som är definierade för organisationen i användarens kundhierarki för att fastställa det avtalsbaserade priset. Om parametern har satts till **Nej**, eller om kundhierarkin inte är definierad, söker prissättningsmotorn efter försäljningsavtal som har definierats för användaren för att fastställa det kontraktsbaserade priset. Mer information om kundhierarkier för B2B-e-handel finns [i Hantera B2B-affärspartners med hjälp av kundhierarkier](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Inställningar för prissättning på kanalnivå

Med hjälp av följande inställningar kan organisationer styra prissättningsbeteendet i specifika försäljningskanaler.

### <a name="enable-order-price-control"></a>Aktivera orderpriskontroll

Parametern **Aktivera priskontroll för order** finns på snabbfliken **Allmänt** för sidan **kundtjänstkonfigurationen**. Inställningen bestämmer om prissättningsmotorn anger en begränsning för prisåsidosättningsåtgärden i kundtjänstkanal. Den fungerar tillsammans med inställningen **Tillåt prisjustering** på produktnivå.

Om orderpriskontroll är inaktiverad kan en kundtjänstanvändare göra prisändringar på försäljningsraderna i kundtjänstkanal, oavsett om motsvarande produkter tillåter prisjustering eller inte.

Om orderpriskontroll är aktiverad är det bara produkter där parametern **Tillåt prisjustering** anges till **Ja** tillåta prisöverskridanden i callcenter-kanalförsäljningsordrar och en orsakskod måste anges på motsvarande försäljningsrader. En kundtjänstanvändare kan endast ändra försäljningspriset upp till värdet **Kostnadspålägg i procent** som har definierats **Butik och handel \> Kanalinställning \> Kundtjänstinställning \> Åsidosätt behörigheter**. Om en åsidosättning av pris överstiger denna procentsats måste användaren skicka en begäran, som sedan bearbetas via ett fördefinierat handelsarbetsflöde för granskning och godkännande. För mer information om Handelsarbetsflöden, se [arbetsflödessystem, översikt](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Inställningar för prissättning på produktnivå

Följande inställningar framtvingar prissättningsregler på produktnivå och finns på sidan **Produktkonfiguration** för en organisation.

### <a name="allow-price-adjust"></a>Tillåt prisjustering

Om parametern **Tillåt prisjustering** är inställd på **Ja**, kan en prisåsidosättning tillämpas på produkten i försäljningsorder för kundtjänstkanal.

### <a name="key-in-price"></a>Ange pris

Inställningen **Nyckeln i pris** avgör om ett nyckelpris är obligatoriskt när en produkt läggs till en försäljningstransaktion i kassan. Det definierar även motsvarande prisvärdebegränsningar.

### <a name="zero-price-valid"></a>Nollpris giltigt

Inställningen **Nollpris giltigt** avgör om fördefinierade, system beräknade eller manuellt justerade försäljningspriser för en produkt kan vara 0 (noll). Ställ in parametern till **Ja** om ett pris på noll är tillåtet. Inställningen kan också anges på kategorinivå från produkthierarkin för Handel.

### <a name="prevent-all-discounts"></a>Förhindra alla rabatter

Genom att ställa in parametern **Förhindra alla rabatter** till **Ja**, förhindrar du att alla typer av rabatter (inklusive manuella rabatter) används på en produkt. Inställningen kan också anges på kategorinivå från produkthierarkin för Handel.

> [!NOTE]
> De här inställningarna begränsar inte hur prisåsidosättningsåtgärden eftersom åtgärden anger priset och behandlas inte som en rabatt.

### <a name="prevent-manual-discounts"></a>Förhindra manuella rabatter

Genom att ställa in parametern **Förhindra manuella rabatter** till **Ja**, förhindrar du att manuella transaktionsrabatter från att användas på en produkt. Alla andra rabatter kan fortfarande användas. Inställningen kan också anges på kategorinivå från produkthierarkin för Handel.

> [!NOTE]
> De här inställningarna begränsar inte hur prisåsidosättningsåtgärden eftersom åtgärden anger priset och behandlas inte som en rabatt.

### <a name="prevent-retail-discounts"></a>Förhindra butiksrabatter

Om parametern **Förhindra detaljhandelsrabatter** ställs in på **Ja** kan rabatterna **enkel**, **kvantitet**, **tröskel**, **mixa och matcha** och **leverans** inte tillämpas på en produkt. Alla andra rabatter (inklusive manuella rabatter) kan fortfarande användas.

### <a name="prevent-tender-based-discounts"></a>Förhindra anbudsbaserade rabatter

Om parametern **Förhindra anbudsbaserade rabatter** anges till **Ja**, kan en **anbudsbaserade** rabatt inte tillämpas på en produkt. Alla andra rabatter (inklusive manuella rabatter) kan fortfarande användas.

Återförsäljare väljer ofta att exkludera vissa produkter, t.ex. nya artiklar eller artiklar på begäran, från artikelbaserade rabatter (som enkla rabatter och mängdrabatter). Men de kanske fortfarande vill tillämpa anbudsbaserade rabatter om en kund betalar genom att använda det föredragna anbudet. För att uppnå detta resultat kan återförsäljare ställa in **Förhindra alla rabatter** och **Förhindra anbudsbaserade rabatter** till **Nej** och **Förhindra butiksrabatter** och **Förhindra manuella rabatter** till **Ja**.

## <a name="deprecated-or-removed-settings"></a>Inaktuell eller borttagna inställningar

Följande prisinställningar har tagits bort eller planeras för borttagning från Dynamics 365 Commerce.

| Inställning | Orsak till utfasning eller borttagning | Status för utfasning eller borttagning |
|---------|-----------------------------------|-------------------------------|
| Hantering av överlappande rabatter | Vi angav den här inställningen i Handelsparametrar för att styra hur prissättningsmotorn söker efter och fastställer vilken av de bästa rabattkombinationerna som ska användas. Det **bästa rabatt** alternativet tvingar fram alla möjliga rabattkombinationer under prissättningsberäkningen. Alternativet **Bäst prestanda** är ett optimerat alternativ som använder en heuristisk algoritm och marginalvärde rankningsmetod för att prioritera, utvärdera och bestämma den bästa kombinationen i tid. Alternativet **Balanserad beräkning** i kodbasen fungerar det här alternativet på samma sätt som **Bästa prestanda**. Därför är det i grund och botten ett duplicerat alternativ. För att förbättra prestandan har prissättningsmotorn uppdaterats så att den bara använder **bästa prestanda** som standardalternativ. Därför är inställningen inte längre tillämplig. | Avaktiveras i versionen 10.0.21 och kommer att tas bort i oktober 2022. |
| Tillåt prisjusteringar som höjer produktpriset | Vi tillhandahåller den här inställningen för att kontrollera om prisjusteringsfunktionen kan höja produktpriserna. Om parametern är avstängd kan organisationer använda prisjusteringsfunktionen endast för att ställa in en produkts enhetspris så att det är lägre än baspriset och handelsavtalets försäljningspris. Vi avaktar den här inställningen eftersom prisjusteringsfunktionen har uppdaterats för tvåvägsjusteringar (ökning eller minskning) ur rutan. | Avaktiveras i versionen 10.0.30 och kommer att tas bort i oktober 2023. |
| Aktivera prisrapport för butik | Vi hade den här inställningen för att kontrollera om **prisrapport** funktionen är tillgänglig för användning i butikskonfigurationssidan. Vi fasade ut den här inställningen eftersom butikskonfigurationssidan har uppdaterats så att den alltid tillhandahåller **Prisrapport** som standardfunktion. | Avaktiveras i versionen 10.0.31 och kommer att tas bort i oktober 2023. |
| Använd dagens datum för att beräkna priser | Prissättningsmotorn Dynamics 365 Supply Chain Management stöder prisberäkning baserat på begärt leveransdatum eller begärt mottagningsdatum, tillsammans med dagens datum. Prissättningsmotorn för Handel stöder endast prissättningsberäkningar baserade på dagens datum. För kunder som använder både Supply Chain Management och Commerce-funktioner tillhandahåller vi den här inställningen och rekommenderade att kunderna alltid ställer in den på **Ja** så att de två prissättningsmotorerna kan arbeta tillsammans. Vi avaktar den här inställningen eftersom den inte ändrar beräkningsbeteendet och är redundant. | Avaktiveras i versionen 10.0.31 och kommer att tas bort i oktober 2023. |
| Maxpris | Vi angav den här inställningen i funktionsprofilen för att styra om endast produkter som har ett försäljningspris under det angivna maximipriset kan säljas via kassan i specifika butiker. Vi utfasade den här inställningen på grund av låg funktionsanvändning. | Avaktiveras i versionen 10.0.31 och kommer att tas bort i oktober 2023. |
| Använd rabatter till enhetspris | Denna inställning var avsedd att kontrollera om priser och rabatter avrundas på prisnivån per enhet eller försäljningsradnivån under prissättningsberäkningen. Vi utfasade det eftersom det inte förbrukas någonstans i den aktuella kodbasen. | Avaktiveras i versionen 10.0.31 och kommer att tas bort i oktober 2023. |
| Manuell beräkning av flera artikelrabatter | Vi angav den här inställningen för att styra om prissättningsmotorn använder försenad prisberäkning för butikskanal. Om parametern är inställd på **Ja**, prissättningsmotorn beräknar inte omedelbart flerradrabatter (såsom kvantitetsrabatter, tröskelrabatter och mixa och matcha-rabatter) närhelst en försäljningsorder skapas eller redigeras i kassaapp. Vi valde att konsolidera den här inställningen med en liknande inställning i Handelsparametrar för att göra en kanalkontroll. | Avaktiveras i versionen 10.0.31 och kommer att tas bort i oktober 2023. |

En fullständig lista över borttagna eller avaktuella funktioner Dynamics 365 Commerce finns i [Borttagna eller inaktuella funktioner i Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
