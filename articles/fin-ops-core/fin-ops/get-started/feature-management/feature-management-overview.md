---
title: Översikt över funktionshantering
description: I det här avsnittet beskrivs funktionen funktionshantering och hur du kan använda den.
author: ChrisGarty
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 2164c07d1a179a0aa15611b742084d872f41bbfc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270823"
---
# <a name="feature-management-overview"></a>Översikt över funktionshantering

[!include [banner](../../includes/banner.md)]

Funktioner läggs till och uppdateras i alla versioner. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

## <a name="the-feature-management-workspace"></a>Använd arbetsytan funktionshantering.

Du kan öppna arbetsytan **funktionshantering** genom att välja lämplig panel på instrumentpanelen. En sida visas med en lista över funktioner för alla utgåvor som stöds av funktionshanteringsupplevelsen. Med tiden kommer Microsoft att förbättra funktionerna i funktionshantering så att de omfattar ytterligare funktioner som hjälper dig att hantera funktioner.

Funktionslistan inkluderar följande information:

- **Funktionens namn** – en beskrivning av funktionen som har lagts till.
- **Aktiverad status** – en symbol anger om en funktion har aktiverats (bockmarkering), inte aktiveras (tom), har tidsplanerats för att aktiveras (klocka) eller är obligatorisk aktiverad (lås) kräver uppmärksamhet innan du aktiverar den (varning) eller så kan den inte aktiveras (X). Inställningen som visas används för alla juridiska personer. Observera att även om en funktion har aktiverats, styrs den fortfarande av säkerhet. Funktionen är därför bara tillgänglig för användare som har åtkomst till den, baserat på deras säkerhetsroll. Det är också bara tillgängligt för juridiska personer som användaren har till gång till.
- **Aktivera datum** – det datum då funktionen aktiverades eller är tidsplanerad att aktiveras.
- **Funktionen tillagd** – det datum då funktionen lades till i din miljö. Detta datum anges automatiskt när du uppdaterar miljön under de månatliga versionscyklerna.
- **Modul** – den modul som påverkas av den nya funktionen.

När du väljer en funktion visas ytterligare information i informations fönstret till höger om funktionslistan. Längst upp i fönstret visas funktionsnamnet, det datum då funktionen lades till, den modul som påverkas av funktionen och länken **Läs mer**. Välj den här länken om du vill visa dokumentationen för funktionen. Om dokumentationen inte är tillgänglig kommer du till en tillfällig sida. Informationsfönstret innehåller också fältet **kommentarer** där du kan lägga till egna kommentarer om funktionen.

Arbetsytan **Funktionshantering** funktionshantering innehåller också flera flikar som var och en visar en lista med funktioner.

- **Ny** – denna flik visar alla funktioner som har lagts till sedan den senaste månadsuppdateringen. Om du har hoppat över några månatliga uppdateringar visas alla nya funktioner som har lagts till sedan senaste gången du uppdaterade på fliken. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner visas också på en sida högst upp på sidan.
- **Inte aktiverad** – på den här fliken visas alla funktioner som inte har aktiverats. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner som inte har aktiverats visas också på en sida högst upp på sidan.
- **Tidsplanerad** – denna flik visar alla funktioner som har tidsplanerats att aktiveras för framtida datum. De funktioner som har det tidigaste tidsplanerade datumet visas överst i listan. Det totala antalet tidsplaneringar av nya funktioner visas också på en sida högst upp på sidan.
- **Alla** – på den här fliken visas alla funktioner. De nyaste funktionerna visas högst upp i listan.

## <a name="turn-on-a-feature"></a>Aktivera en funktion

Om en funktion inte har aktiverats visas knappen **Aktivera nu** i informationsfönstret. Du kan använda den här knappen om du vill aktivera funktionen.

- Välj den funktion som du vill aktivera och välj sedan **aktivera nu** i informationsfönstret. Funktionen är aktiverad.

Vissa funktioner kan inte inaktiveras när du har aktiverat dem. Om funktionen som du försöker aktivera inte kan inaktiveras får du en varning. I det här läget kan du välja **Avbryt** om du vill avbryta åtgärden och lämna funktionen inaktiverad. Om du däremot väljer **aktivera** och aktiverar funktionen kommer du inte att kunna inaktivera den senare.

Vissa funktioner visar ett meddelande som ger ytterligare information innan du aktiverar dem. Dessa funktioner indikeras med en gul varningssymbol. Du bör läsa ytterligare information noggrant för att bättre förstå vad som kommer att hända när funktionen är aktiverad. Du kan dock fortfarande välja **aktivera** för att aktivera funktionen.

Vissa funktioner visar ett meddelande om att funktionen inte kan aktiveras förrän en åtgärd har vidtagits. Dessa funktioner indikeras med en röd X-symbol. Du måste vidta de åtgärder som beskrivs i beskrivningen innan funktionen är aktiverad. Om du till exempel inte kan använda en funktion förrän en konfigurationsnyckel har inaktiverats måste du först inaktivera konfigurationsnyckeln och sedan återgå till funktionshantering för att aktivera funktionen.

När funktionen är aktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Det här meddelandet anger att funktionen har aktiverats eller anger det framtida datum när funktionen är tidsplanerad att aktiveras. Det visas varje gång du väljer funktionen i funktionslistan.

Funktioner som är schemalagda att aktiveras i framtiden visas på fliken **Schemalagd**. En batchprocess aktiverar dem vid midnatt det angivna datumet, baserat på tidszonen som representeras av systemdatumet.

## <a name="reschedule-a-feature"></a>Tidsplanera om en funktion

Om en funktion har tidsplanerats att aktiverats i framtiden visas knappen **tidsplanera** i informationsfönstret. Du kan använda den här knappen om du vill ändra värdet **aktivera datum** till ett annat datum.

1. Välj en tidsplanerad funktion som du vill tidsplanera om och välj sedan **Tidsplanera** i informationsfönstret.
2. I dialogrutan som visas i fältet **aktivera datum** anger du det nya datum då funktionen ska aktiveras.
3. Välj **aktivera** om du vill tidsplanera om funktionen eller **inaktivera** om du vill avbryta schemat.

## <a name="turn-off-a-feature"></a>Inaktivera en funktion

Om en funktion redan har aktiverats visas knappen **Inaktivera** i informationsfönstret. Du kan använda den här knappen om du vill inaktivera funktionen. Knappen **inaktivera** är inte tillgänglig om funktionen inte kan inaktiveras när den har aktiverats.

- Välj den funktion som du vill stänga av och välj sedan **inaktivera** i informationsfönstret. Funktionen är inaktiverad och fältet **aktivera datum** avmarkeras.

När funktionen är inaktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Meddelandet anger att funktionen inte har aktiverats ännu. Det visas varje gång du väljer funktionen i funktionslistan. Funktioner som int hr aktiverats visas på fliken **Inte aktiverad**.

## <a name="features-that-must-be-turned-on"></a>Funktioner som måste aktiveras

Ibland levereras en kritisk funktion som måste aktiveras automatiskt när du gör en uppdatering. De här funktionerna aktiveras automatiskt på det datum som anges i fältet **aktivera datum**. För dessa funktioner visas ett meddelande under länken **Mer information** i informationsfönstret. Det här meddelandet anger att funktionen har aktiverats eller anger det framtida datum när funktionen kommer att aktiveras. Det visas varje gång du väljer funktionen i funktionslistan.

## <a name="enable-all-features"></a>Aktivera alla funktioner

Som standard är alla funktioner som läggs till i miljön inaktiverade. Du kan aktivera alla funktioner genom att välja knappen **Aktivera alla**. 

När du väljer **aktivera alla** visas ett alternativ där du behöver ange följande information:
- En lista över alla funktioner som kräver bekräftelse innan de kan aktiveras. Om du vill aktivera funktionerna i listan väljer du **Ja** för knappen **Aktivera funktioner som kräver bekräftelse**.
- En lista över alla funktioner som inte kan aktiveras visas. Dessa funktioner kommer inte att aktiveras.

Alla funktioner som kan aktiveras kommer att aktiveras. Om en funktion redan är schemalagd för att aktiveras i framtiden kommer schemat inte att ändras. 

## <a name="turn-on-all-features-automatically"></a>Aktivera alla funktioner automatiskt

Som standard är alla funktioner som läggs till i miljön inaktiverade, såvida de inte är obligatoriska funktioner. Om du vill aktivera alla nya funktioner automatiskt kan du dock ändra vad som händer när nya funktioner läggs till genom att använda listrutan under arbetsytans rubrik.

- Välj `Enable new features automatically` för att automatiskt aktivera alla nya funktioner när de läggs till i miljön.
- Välj `Do not enable new features automatically` för att standardinställa alla nya funktioner av när de läggs till i din miljö.


När du aktiverar alla funktioner automatiskt, kommer det att aktivera alla funktioner som skulle vara aktiverade när du klickar på knappen **aktivera alla**. Det kommer inte att aktivera funktioner som kräver bekräftelse eller funktioner som inte kan aktiveras förrän en åtgärd vidtas.

## <a name="check-for-updates"></a>Sök efter uppdateringar

Funktioner läggs till i din miljö efter varje uppdatering. Du kan dock manuellt söka efter uppdateringar genom att klicka på knappen **Sök efter uppdateringar**. Alla funktioner som har lagts till i systemet efter att uppdateringen kommer att läggas till i listan över funktionerna. Till exempel, om en funktion i förhandsversion är aktiverad efter en frisläppning kan du söka efter uppdateringar och funktionen kommer att läggas till i din lista.

## <a name="assigning-roles"></a>Tilldela roller

Arbetsytan för **Funktionshantering** kan öppnas av systemadministratörer och även av användare som har tilldelats rollen Funktionshanterare eller Funktionsvisare. Dessa två roller skapades för att ge stöd till upplevelsen för funktionshantering. Användare med funktionshanterarens roll kan aktivera och inaktivera alla funktioner. De kan också uppdatera avsnittet **kommentarer** för funktionen. Användare med funktionsrollen kan endast visa arbetsytan **Funktionshantering**. De kan inte aktivera eller inaktivera funktioner.

Rollen Funktionshanterare och rollen Funktionsvisare åsidosätter inte den befintliga säkerhet som en användare har. De styr bara om användaren kan aktivera och inaktivera funktioner. De ger inte tillgång till själva funktionerna.

## <a name="features-that-use-configuration-keys"></a>Funktioner som använder konfigurationsnycklar

Om en funktion använder en konfigurationsnyckel men konfigurationsnyckeln inte är aktiverad visar arbetsytan **Funktionshantering** inte funktionen i listan över tillgängliga funktioner. När du har aktiverat konfigurationsnyckeln måste du uppdatera funktionslistan genom att använda menyalternativet **Kontrollera updatering**. Funktionen visas sedan i funktionslistan.

Om du inaktiverar konfigurationsnyckeln tas funktionen inte bort från funktionslistan.

## <a name="data-entities"></a>Datatabeller

Med hjälp av en dataenhet som kallas **funktionshantering** kan du exportera funktionshanteringsinställningarna från en miljö och sedan importera dem till en annan miljö. Den här enheten uppdaterar endast befintliga funktioner. Affärslogiken i entiteten garanterar också att samma regler som används på arbetsytan **funktionshantering** används när importen görs. Du kan till exempel inte åsidosätta en obligatorisk funktionsinställning genom att ta bort datumet under importen.

I följande exempel beskrivs vad som händer när du använder entiteten **funktionshantering** för att importera data.

- Om **du ändrar värdet i det aktiverade** fältet till **ja**, aktive ras funktionen, och fältet **aktiverings datum** sätts till aktuellt datum.
- Om du ändrar värdet **Aktiverad** till **Nej** eller lämnar fältet **EnableDate** tomt inaktiveras funktionen och fältet **Aktivera datum**. Du kan inte inaktivera en obligatorisk funktion eller en funktion som inte kan inaktiveras när den är aktiverad.
- Om du ändrar värdet i fältet **EnableDate** till ett framtida datum, tidsplaneras funktionen för det datumet.
- Om du ändrar värdet i fältet **Aktiverad** till **Ja** och ändrar värdet i fältet **EnableDate** till ett framtida datum tidsplaneras funktionen för det datumet. 
- Om du ändrar värdet i fältet **Aktiverad** till **Nej** och ändrar också värdet i fältet **EnableDate** till ett framtida datum tidsplaneras funktionen för det datumet.
- Om en funktion är aktiverad och du lägger till fältet **EnableDate** som är inställt på ett framtida datum, förblir funktionen aktiverad. Om du vill tidsplanera om funktionen måste du ändra fältet **aktiv** till **Nej**.

## <a name="feature-management-and-flighting"></a>Funktionshantering och flygning

Med funktionshantering kan du styra de funktioner som levereras i varje utgåva. Förhandsversioner låter Microsoft Teams frisläppa funktioner till ett begränsat antal kunder så att funktionerna kan testas och valideras utan att alla kunder påverkas. Funktionshanteringen styr inte förhandsversioner av funktioner.

## <a name="new-features-are-optional-for-12-months"></a>Nya funktioner är valfria i 12 månader

När en ny icke-kritisk funktion installeras, är den valfri under en 12-månaders period. Detta gör att du och din organisations tid planerar framåt för att kunna utsätta en funktion och låta den testas mot dina dagliga operationer. Mer information i [Frågor och svar om tjänstuppdateringar för en version](../one-version.md#what-about-new-features).

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Använda funktionshantering för att aktivera ISV-funktioner eller anpassade funktioner

Funktionshantering är för närvarande inte tillgängligt för funktioner från oberoende programvaruleverantörer (ISV) och anpassade funktioner. Microsoft lägger dock till fler funktioner för att förbättra funktionshanteringen. När dessa förbättringar har genomförts gör Microsoft funktionshantering tillgängligt för alla funktioner och innehåller instruktioner för hur du uppdaterar funktionerna.

## <a name="frequently-asked-questions-faq"></a>Vanliga frågor

### <a name="when-are-features-added-removed-or-changed"></a>När är funktioner tillagda, borttagna eller ändrade? 
Funktionerna läggs till, tas bort och ändras genom kodändringar. Miljöer måste uppdateras för att de ska få ändringarna.

### <a name="does-a-feature-become-mandatory-automatically"></a>Blir en funktion automatiskt obligatorisk? 
Nej, en funktion som blir obligatorisk är inte en automatisk åtgärd. Produktgrupperna måste göra en kodändring.

### <a name="when-do-features-become-mandatory"></a>När ska funktioner vara obligatoriska? 
Policyn är att alla nya funktioner kommer att ingå i en 12-månaders period och inte kräver någon ändringshantering förrän funktionen aktiveras. Produktgrupperna kan välja om en funktion ska vara obligatorisk efter att perioden har upphört. 

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Varför finns det inget specifikt "obligatoriskt aktiverat datum"? 
Tidpunkten för uppdateringsfrisläppning är variabel, tidsinställning för miljön är variabel och kunderna kan välja att hoppa över vissa uppdateringar. Därför är det svårt att fastställa särskilda datum. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>Var är dokumentationen till de funktioner som görs obligatoriska? 
Denna dokumentation kommer från varje Dynamics 365-appteam. Ofta nämns dessa funktioner i [uppdateringar av klientfunktionstillstånd](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) eller [borttagna eller inaktuella funktioner](../../../dev-itpro/migration-upgrade/deprecated-features.md). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Finns det ett produkt- eller signalmeddelande om att en funktion ska vara obligatorisk aktiverad? 
En meddelandefunktion som är relaterad till att utföra en funktion som är obligatorisk finns inte idag.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Kan funktionerna någonsin aktiveras utan att kunden vet om det? 
Ja, om funktioner inte har en funktionell effekt kan de aktiveras som standard.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>Vad är funktionsflygning och hur fungerar det med funktionshantering? 
Funktionsflygningar är i realtid på/av-brytare som Microsoft kontrollerar. De är åtskilda från kundkontrollen som ingår i funktionshantering. 
- Privata förhandsgranskningsfunktioner visas inte i funktionshantering förrän de har bearbetats. I produktionen måste kunden komma överens om att bli en del av ett specialprogram för att kunna genomföras.
- Funktioner för offentlig förhandsgranskning (allmänt tillgängliga) visas i funktionshantering om de inte är tillgängliga. Att utföra en flygning av en funktion betraktas som en sista utvägsalternativ för produktgrupper om det finns ett kritiskt problem och vanligtvis är en per kund-operation.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Kan funktionerna någonsin inte vara tillgängliga utan att kunden vet om det? 
Ja, om en funktion påverkar en miljö som inte har någon funktionell effekt kan de aktiveras som standard.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>Hur kan funktionsaktivering kontrolleras i kod?
Använd metoden **isFeatureEnabled** i klassen **FeatureStateProvider** och skicka den till en förekomst av funktionsklassen. Exempel: 

```xpp
if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))
```

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>Hur kan funktionsaktivering kontrolleras i metadata?
Egenskapen **FeatureClass** kan användas för att ange att vissa metadata är kopplade till en funktion. Klass namnet som används för funktionen ska användas, t.ex. **BatchContentionPreventionFeature**. Dessa metadata visas bara i den funktionen. Egenskapen **FeatureClass** är tillgänglig på menyer, menyalternativ, uppräkningsvärden och tabell/visningsfält.

### <a name="what-is-a-feature-class"></a>Vad är en funktionsklass?
Funktioner i funktionshantering definieras som *funktionsklasser*. En funktionsklass **implementerar IFeatureMetadata** och använder attributet funktionsklass för att identifiera sig själv för arbetsytan funktionshantering. Det finns många exempel på tillgängliga funktionsklasser som kan kontrolleras för aktivering i kod med hjälp av API **FeatureStateProvider** och i metadata med egenskapen **FeatureClass**. Exempel: 

```xpp
[ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
```

### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>Vad är IFeatureLifecycle implementerad av vissa funktionsklasser?
IFeatureLifecycle är en Microsoft-intern mekanism för att indikera livscykelfasen för funktionen. Funktioner kan vara:
- `PrivatePreview` – en förhandsversion måste vara synlig.
- `PublicPreview` – visas som standard men med en varning om att funktionen är i förhandsversion.
- `Released`- Helt släppt.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
