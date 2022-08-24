---
title: Beräkna lagertillgänglighet för butikskanaler
description: I denna artikel beskrivs hur ett företag kan använda Microsoft Dynamics 365 Commerce för att visa uppskattade tillgängliga produkter i online- och butikskanaler.
author: hhainesms
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 8d656cc82472e0515f0f8a64ec21c6c674223ec6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279692"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Beräkna lagertillgänglighet för butikskanaler

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur ett företag kan använda Microsoft Dynamics 365 Commerce för att visa uppskattade tillgängliga produkter i online- och butikskanaler.

## <a name="accuracy-of-inventory-availability"></a>Exakthet för lagertillgänglighet

Commerce använder flera servrar och databaser för att garantera skalbarhet och prestanda. Därför är det viktigt att du förstår att de tillgängliga lagervärden som tillhandahålls via kassaprogrammet (POS), API:er för lagertillgänglighet för näthandel samt lagerbehållningssidorna i Commerce headquarters kanske inte är 100 procent korrekta i realtid. Om transaktioner som skapas för produkter i nät- eller butikskanalen ännu inte har synkroniserats med Commerce headquarters, kanske lagerbehållningssidorna i administrationen inte visar ett korrekt lager värde i realtid för dessa produkter. Om du har konfigurerat ditt företag så att användare i administrationen eller andra integrerade program kan sälja, ta emot, returnera eller på annat sätt justera lagret från en butik eller på ett nätlager, kanske inte kassa- eller nätkanalen har all information som krävs för att visa korrekta värden för artiklar i realtid.

Det är vitalt att du förstår att all tillgänglig data som ges under användningsdagen betraktas som ett uppskattat värde. Om du försöker jämföra den lagerbehållningsinformation som programmet ger med det verkliga fysiska lagret på hyllorna, eller om du försöker jämföra de behållningsvärden som visas i kassan med de faktiska data som du hittar för samma lagerställe i administration, kan värdena därför komma att skilja sig åt. Denna skillnad förväntas under användningsdagen och bör inte betraktas som en utleverans. Om du vill granska data och se till att de värden som finns i kassa, API:er och administration matchar de faktiska fysiska enheterna som finns i butiken eller på lagerhyllorna, är det bäst att göra detta efter att kanalåtgärderna har avslutats för dagen och alla transaktioner har synkroniserats korrekt mellan administration och kanaler.

## <a name="channel-side-inventory-calculation"></a>Lagerberäkning på kanalsidan

Lagerberäkningen på kanalsidan är en mekanism som tar den senast kända kanallagerdatan i Commerce headquarters som grund och därefter faktorer i ytterligare lagerändringar som inträffat på kanalsidan som inte inkluderats i denna grund för att beräkna en uppskattad lagerbehållning i närapå realtid. 

Följande lagerändringar beaktas för närvarande i lagerberäkningslogiken på kanalsidan:

- Lager som säljs via cash-and-carry-order i butik
- Lager som säljs via kundorder i butik eller nätkanal
- Lager som returnerats till butiken
- Lager som är uppfyllt (plocka, packa, skeppa) från butikslagerställe

Om du vill använda lagerberäkningen på kanalsidan måste du aktivera funktionen **Optimerad beräkning för produkttillgänglighet**.

Följ stegen nedan om din Commerce-miljö har version **10.0.8 till 10.0.11**.

1. I Commerce headquarters, gå till **Retail och Commerce** \> **Gemensamma Commerce-parametrar**.
1. På fliken **Lager** i fältet **Produkttillgänglighetsjobb** välj **Använd optimerad process för produkttillgänglighetsjobb**.

Följ stegen nedan om din Commerce-miljö har version **10.0.12 eller senare**.

1. I Commerce headquarters, gå till **Arbetsytor \> Funktionshantering** och aktivera funktionen **Optimerad beräkning för produkttillgänglighet**.
1. Om dina online- och butikskanaler använder samma lagerställen för uppfyllelse, måste du också aktivera funktionen **Utökad lagerberäkningslogik på kanalsidan för näthandel**. På så sätt kommer beräkningslogiken på kanalsidan att ta hänsyn till de icke bokförda transaktioner som har skapats i butikskanalen. (Dessa transaktioner kan vara hämtköpstransaktioner, kundorder och returer.)
1. Kör jobbet **1070** (**jakanlkonfiguration**).

Om din Commerce-miljö uppgraderades från en version som är tidigare än Commerce-version 10.0.8, efter att du har aktiverat funktionen **Optimerad beräkning för produkttillgänglighet** måste du också köra **Initiera schemaläggare för handel** för att funktionen ska aktiveras. Gå till **Retail och Commerce** \> **Administrationsinställning** \> **Schemaläggare för handel**.

Om du vill använda lagerberäkningen på kanalsidan måste först en periodisk ögonblicksbild av lagerdata från administrationen som skapats av jobbet **Produkttillgänglighet** skickas till kanaldatabaserna. Ögonblicksbilden representerar den information som administration har om lagertillgänglighet för en specifik kombination av en produkt eller produktvariant och ett lagerställe. Den inkluderar bara de lagertransaktioner som bearbetats och bokförts i administrationen vid tidpunkten för ögonblicksbilden, och den kanske inte är 100 procent korrekt i realtid på grund av den konstanta försäljningsbearbetningen som sker på distribuerade servrar.

- Om lagret såldes för en produkt i ett butikslager med hämtköp ("cash-and-carry") eller asynkron försäljning av kundorder i kassaprogrammet, finns det ingen omedelbar information om den relaterade lagerkvantiteten för försäljningen i administrationen. Administrationen kommer att ha information om lagret som säljs för dessa typer av butiksförsäljning först när P-jobbet överför den relaterade transaktionen från butikens kanaldatabas till administrationen och relaterade försäljningsorder skapas genom utdragsbokföring eller av indroppningsbaserad bokföring. När ordern skapas i administration skapas relaterade lagertransaktioner. 
- För näthandelskanalorder har administrationen information om lagertransaktionerna först när transaktionerna har skickats till administration via P-jobbet och synkroniseringen av ordern har slutförts.

Följ de här stegen om du vill ta en ögonblicksbild av lagret i Commerce headquarters.

1. Gå till **Retail och Commerce \> Retail och Commerce IT \> Produkter och lager \> Produkttillgänglighet**.
1. Välj **OK** för att köra jobbet **Produkttillgänglighet**. Du kan även tidsplanera det här jobbet så att det körs i en batch.

När jobbet **Produkttillgänglighet** har slutförts måste de data som samlats in skickas till kanalens databaser så att den senaste ögonblicksbilden för administration kan övervägas vid beräkningen av uppskattad lagerhållning på kanalsidan.

Om du vill synkronisera ögonblicksbilddata från administrationen till dina kanaldatabaser gör du på följande sätt:

1. Gå till **Retail and Commerce \> Retail and Commerce-IT \> Distributionsschema**.
1. Kör jobbet **1130** (**Produkttillgänglighet**) om du vill synkronisera den ögonblicksbilddata som jobbet **Produkttillgänglighet** har skapat från administrationen till kanaldatabaserna.

## <a name="inventory-availability-apis-for-e-commerce"></a>API:er för lagertillgänglighet i näthandel

Commerce innehåller följande API:er för näthandelsscenarier om du vill efterfråga lagertillgängligheten för en produkt:

- **GetEstimatedAvailability** – Använd detta API när du vill söka efter en produkt eller produktvariant i det nätkanallagerställe eller de lagerställen som är kopplade till nätkanalens uppfyllelsegrupp.
- **GetEstimatedProductWarehouseAvailability** – Använd detta API för att efterfråga lager för en produkt eller en produktvariant från ett visst lagerställe.

> [!NOTE]
> Dessa API:er ersätter API:erna **GetProductAvailabilities** och **GetAvailableInventoryNearby** i Commerce version 10.0.7 och tidigare.

Båda API:er använder intern beräkningslogik på kanalsidan och returnerar uppskattad **fysiskt tillgänglig** kvantitet, **totalt tillgänglig** kvantitet, **måttenhet (UoM)** samt **lagernivå** för begärd produkt och lagerhållning. Returnerade värden kan visas på din näthandelssajt om du vill det, eller också kan de användas för att utlösa annan affärslogik på din näthandelssajt. Du kan till exempel förhindra inköp av produkter med lagernivån "ej i lager".

Även om andra API:er som är tillgängliga i Commerce kan gå direkt till administrationen för att hämta kvantiteten för produkter, rekommenderar vi inte att de används i en näthandelsmiljö på grund av potentiella prestandaproblem och den påverkan som dessa frekventa förfrågningar kan ha på dina administrationsservrar. Med hjälp av beräkningen på kanalsidan kan de två API:erna som nämns ovan ge en mer exakt uppskattning av en produkts tillgänglighet, detta genom att ta hänsyn till de transaktioner som skapats i de kanaler som administrationen ännu inte känner till.

Om du vill definiera hur produktkvantiteten ska returneras i API-utleveransen följer du dessa steg.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar**.
1. Välj fliken **Lager** – på snabbfliken **API:er för lagertillgänglighet för e-Commerce** konfigurerar du sedan värdet för inställningen **Kvantitet för API-utdata**.
1. Kör jobbet **1070** (**kanalkonfiguration**) för att synkronisera de senaste inställningarna med kanaler.

Inställningen **Kvantitet i API-utdata** innehåller tre alternativ:

- **Returlagerkvantitet** – Fysiskt tillgänglig och totalt tillgänglig kvantitet för en begärd produkt returneras i API-utdata.
- **Returlagerkvantitet som subtraherar lagerbuffert** – Den kvantitet som returneras i API-utdata justeras genom att lagerbuffertvärdet subtraheras. Mer information om lagerbufferten finns i [Konfigurera lagerbuffertar och lagernivåer](inventory-buffers-levels.md).
- **Ej returlagerkvantitet** – Endast lagernivån returneras i API-utdata. Mer information om lagerbuffertens nivåer finns i [Konfigurera lagerbuffertar och lagernivåer](inventory-buffers-levels.md).

Du kan använda API-parametern `QuantityUnitTypeValue` om du vill ange den enhetstyp i vilken du vill att API:erna ska returnera kvantiteterna. Denna parametern stöder alternativen **Lagerenhet** (standard), **Inköpsenhet** och **Försäljningsenhet**. Den returnerade kvantiteten avrundas till den definierade precisionen för motsvarande måttenhet (UOM) i administrationen.

I API:t **GetEstimatedAvailability** finns följande inmatningsparametrar som stöder olika frågescenarier:

- `DefaultWarehouseOnly` – Använd den här parametern när du vill söka i lager efter en produkt i näthandelskanalens standardlagerställe. 
- `FilterByChannelFulfillmentGroup` och `SearchArea` – Använd dessa två parametrar för att söka i lagret efter en produkt från alla upphämtningsställen inom ett specifikt sökområde, baserat på `longitude`, `latitude` och `radius`. 
- `FilterByChannelFulfillmentGroup` och `DeliveryModeTypeFilterValue` – Använd dessa två parametrar för att söka lagerstället för en produkt från specifika lagerställen som är kopplade till en onlinekanals uppfyllelsegrupp och är konfigurerade för att stödja vissa leveranssätt. Parametern `DeliveryModeTypeFilterValue` stöder alternativen **alla** (standardalternativ), **leverans** samt **upphämtning**. I ett scenario där en onlineorder kan uppfyllas från flera leveranslagerställen kan du till exempel använda dessa två parametrar för att fråga efter en produkts lagertillgänglighet i alla dessa leveranslagerställen. API:t i det här fallet returnerar produktens lagerbehållningskvantitet och lagernivå i varje leveranslagerställe, plus en aggregerad kvantitet och en aggregerad lagernivå från alla leveranslagerställen i frågesomfång.
 
Inköpsruta, butiksväljare, önskelista, kundvagn och kundvagnsikon för Commerce förbrukar de API:er och parametrar som omnämns ovan i syfte att visa meddelanden om lagernivåer på hela näthandelssajten. ommerce-webbplatsbyggaren innehåller olika lagerinställningar som styr marknadsföring och inköp. Mer information om [Använd lagerinställningar](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Sökning efter kassalager med beräkning på kanalsidan

I Commerce version 10.0.9 och tidigare använde funktionen **Lagersökning** i kassan (POS) ett serviceanrop i realtid i syfte att hämta lagerinformation för vald produkt för såväl användarens aktuella butik och alla andra eventuella butiker som har konfigurerats för uppfyllelsegruppen som ett led i kanalfigurationen för butiken. I Commerce version 10.0.10 och senare kan du stänga av tjänsteanrop till administrationen i realtid och istället använda beräkningar på kanalsidan på Commerce-servern för att bestämma vilken lagerbehållning som är fysiskt tillgänglig för butiken och alla andra platser som har definierats i uppfyllelsegruppen. Denna kanalberäknade lagerkonfiguration är också användbar för platser där Internet-anslutningen är otillförlitlig, detta eftersom du inte behöver vara online för att hämta lagersökningar från administrationen.

När kanalsidans beräkning är korrekt konfigurerad och hanterad kan den ge en mer tillförlitlig uppskattning av den aktuella butiksinventeringen, detta eftersom den använder de transaktionsdata som finns i Commerce-kanaldatabasen men som administrationen kanske ännu inte har information om. Om du till exempel använder det befintliga serviceanropet i realtid för lagersökningar i kassan (POS) har administrationen antagligen ingen information om hämtköpförsäljning som har utförts för en produkt. Det lagerbehållningsvärde som administrationen returnerar för den produkten kommer därför troligen att överskrida butikens faktiska lagerbehållning med en enhet. Om du däremot använder beräkning på kanalsidan kan hämtköpförsäljning delas upp i beräkningen och dras av från behållningsvärdet som visas. Även om de värden som används vid beräkningen av både kanalsidan och servicesamtalet i realtid är enbart uppskattningar av lagerbehållning, är värdet som beräkningen på kanalsidan ger mycket mer exakt för den aktuella butiken.

Om du vill konfigurera funktionen **Lagersökning** i Commerce headquarters i syfte att använda beräkningslogiken på kanalsidan och stänga av serviceanrop i realtid måste du först aktivera funktionen **Optimerad beräkning för produkttillgänglighet** via arbetsytan **Funktionshantering** i Commerce headquarters och sedan följa dessa steg.

1. Gå till **Retail and Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**.
1. Välj en funktionsprofil.
1. På snabbfliken **Funktioner**, i avsnittet **Beräkning av lagertillgänglighet**, ändrar du värdet för **Beräkningsvärde för lagertillgänglighet** från **Realtidstjänst** till **Kanal**. Alla funktionsprofiler använder som standard servicesamtal i realtid. Du måste ändra värdet i det här fältet om du vill använda beräkningslogik på kanalsidan. Alla butiker som är kopplade till den valda funktionsprofilen påverkas av den här ändringen.

Du måste sedan synkronisera ändringarna till kanalen genom distributionsschemaprocessen i administrationen genom att utföra följande steg:

1. Gå till **Retail and Commerce \> Retail and Commerce-IT \> Distributionsschema**.
1. Kör jobbet **1070** (**jakanlkonfiguration**).

När konfigurationen är klar använder den information som finns om fysiskt tillgängligt lager inte längre ett samtal i realtid när en användare i kassaprogrammet använder åtgärden **lagersökning** (standard- och matrisvyer). I stället beräknas data om fysiskt tillgängligt lager för den aktuella butiken och alla butiker i uppfyllelsegruppen, baserat på den senaste kända ögonblicksbilden som levererades till kanaldatabasen från Commerce headquarters. Värdet för ögonblicksbilden kan finjusteras ytterligare av kanalberäkningen för att justera det fysiskt tillgängliga värdet, baserat på ytterligare försäljnings- eller returtransaktioner för den valda produkten i kanaldatabasen som inte inkluderades i de senaste synkroniserad ögonblicksbilden från 1130-jobbet. Om kanaldatabasen inte innehåller transaktionsdata för något av lagren eller butikerna i uppfyllelsegruppen, innehåller den inga ytterligare transaktioner som kan beaktas vid en omberäkning av värdet. Därför är den bästa uppskattningen av lagerbehållning som kan visas för dessa lagerställen eller butiker, data från den senaste ögonblicksbilden av Commerce headquarters.

Skärmen **Orderuppfyllelse** i POS utnyttjar också beräkningen av kanalsidan för att visa inventering för objekt när en rad för orderuppfyllning är vald och en användare visar panelen **Detaljer** för lagerbehållning för den valda artikeln..

## <a name="optimize-your-inventory-data"></a>Optimera dina lagerdata

För att säkerställa bästa möjliga uppskattning av lagret är det viktigt att du använder följande Commerce-batchjobb och kör dem ofta:

- **P-Jobb** – p-jobbet finns på sidan **distributionsplaner** och bör köras ofta. Det här jobbet ger näthandelsorder, asynkrona kundorder som skapats av POS och hämtköporder som skapas från kanaldatabaser till Commerce headquarters, så att de kan bearbetas ytterligare. Innan dessa data synkroniseras från kanalen till Commerce headquarters har inte Commerce headquarters någon information om lagerjusteringar till produkter i de lagerställen som kommer från dessa transaktioner.
- **Synkronisera order** – i det här jobbet bearbetas råa transaktionsdata i Commerce headquarters som P-jobbet innehåller och omvandlar näthandel och asynkrona kundordertransaktioner till försäljningsorder i Commerce headquarters. Inga lagertransaktioner skapas förrän jobbet bearbetas och försäljningsorder skapas. Lagerbehållningen i Commerce headquarters kan därför inte ta hänsyn till transaktionerna.
- **Beräkna transaktionsutdrag i batch** – för hämtköpstransaktioner som skapas i butiken, säkerkonfigurerardroppningsbaserad bokföringsprocess att lagret som är relaterat till försäljningen uppdateras effektivt. För att få effektiv bearbetning av lagertransaktioner för hämtköpsorder måste du konfigurera systemet för att använda [indroppningsbaserad bokföring](./trickle-feed.md).
- **Bokför transaktionsutdrag i batch** – det här jobbet krävs även för indroppningsbaserad bokföring. Den följer jobbet **Beräkna transaktionsutdrag i batch**. Det här jobbet bokför de beräknade utdragen, så att försäljningsorder för hämtköpförsäljningen skapas i Commerce headquarters och i Commerce headquarters på ett mer exakt sätt återspeglar butikens lager.
- **Produkttillgänglighet** – det här jobbet skapar ögonblicksbilden av lagret från Commerce headquarters.
- **1130 (Produkttillgänglighet)** – det här jobbet finns på sidan **distributionsplaner** och bör köras omedelbart efter jobbet **produkttillgänglighet**. Det här jobbet transporterar data för lagerögonblicksbilden från Commerce headquarters till kanaldatabaserna.

> [!NOTE]
> - Det bästa är att köra jobben **Produkttillgänglighet** och **1130** varje timme, samt att schemalägga P-jobb, synkronisera order och "in-droppa" (trickle feed) bokföringsrelaterade jobb med samma eller högre frekvens.
> - När beräkningar för lagertillgänglighet på kanalsidan används för att skapa en begäran om lagertillgänglighet med hjälp av API:er för e-Commerce eller kassalagerlogik på kanalsidan, kommer beräkningen av prestandaskäl att använda en cache i syfte att avgöra huruvida tillräckligt med tid har passerat för att det ska vara berättigat att köra beräkningslogiken på nytt. Standardcache är inställd på 60 sekunder. Du har till exempel aktiverat en beräkning på kanalsidan för butiken och visat lagerbehållningen för en produkt på sidan **lagersökning**. Om en enhet av produkten sedan säljs kommer sidan **lagersökning** inte att visa det reducerade lagret förrän cachen har rensats. När användarna har bokfört transaktioner i POS ska de vänta 60 sekunder innan de kontrollerar att lagerbehållningen har reducerats.

Om ditt affärsscenario kräver en mindre cachetid kan du kontakta din produktsupportrepresentant för att få hjälp.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
