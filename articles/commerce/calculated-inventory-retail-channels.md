---
title: Beräkna lagertillgänglighet för butikskanaler
description: I det här avsnittet beskrivs alternativen som kan användas för att visa lagerbehållningen för butiken och online-kanaler.
author: hhainesms
manager: annbe
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 68fa26daac055cd0fd72035683f05ed36052b3a3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995830"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Beräkna lagertillgänglighet för butikskanaler

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur ett företag kan använda Microsoft Dynamics 365 Commerce för att visa uppskattade tillgängliga produkter i online- och butikskanaler.

## <a name="accuracy-of-calculation"></a>Beräkningens noggrannhet

Commerce använder flera servrar och databaser för att garantera skalbarhet och prestanda. Därför är det viktigt att du förstår att de tillgängliga lagervärdet som tillhandahålls via kassaprogrammet (POS), API:er för lagertillgänglighet för näthandel och lagerbehållningssidorna i Commerce-administration kanske inte är 100 procent korrekt i realtid. Om transaktioner som skapas för produkter i online- eller butikskanalen ännu inte har synkroniserats till Commerce-administrationens server och databasen, kan lagerbehållningssidorna i Commerce-administration inte visa ett korrekt lager värde i realtid för dessa produkter. Om du har konfigurerat ditt företag så att användare i Commerce-administrationen eller andra integrerade program kan sälja, ta emot, returnera eller på annat sätt justera lagret från en butik eller på onlinenivå, kanske inte kassa- eller online-kanalen har all information som krävs för att visa ett korrekt lagerbehållningsvärde i realtid för artiklar.

I det här avsnittet beskrivs de processer för datasynkronisering som kan köras ofta för att begränsa fördröjningen av data mellan program eller kanaler. Det är dock viktigt att du förstår att all tillgänglig data som ges under användningsdagen betraktas som ett uppskattat värde. Därför, om du försöker jämföra den lagerbehållningsinformation som programmet ger med verklig fysisk inventering på hyllorna, eller om du försöker jämföra de behållningsvärden som visas i POS med de data som du hittar för samma lagerställe i I Commerce-administration kan värdena skilja sig. Denna skillnad förväntas under användningsdagen och bör inte betraktas som en utleverans. Om du vill granska data och se till att de värden som finns i API:er för lagertillgänglighet och Commerce-administration matchar de faktiska fysiska enheterna som finns i butiken eller lagerhyllorna, är det bäst att göra det efter att kanal åtgärderna har stoppad för dagen och alla transaktioner har synkroniserats korrekt mellan Commerce-administration och kanalen.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Använd API:er för lagersökning för begäran av lagertillgänglighet för näthandel

Du kan använda följande API:er för att visa lagertillgänglighet för en produkt när dina kunder handlar på en näthandelssajt.

- **GetEstimatedAvailability** – Använd den här API:n för att hämta lagertillgänglighet för artikeln i näthandelskanalens lager eller alla lagerställen som är kopplade till konfigurationen av uppfyllelsegruppen för näthandelskanalen. Detta API kan också användas för lagerställen i ett visst sökområde eller en viss radie, baserat på longitud- och latituddata.
- **GetEstimatedProductWarehouseAvailability** – Använd detta API för att begära lager för en artikel från ett visst lagerställe. Du kan till exempel använda det för att visa lagerdispositionen i scenarier som innefattar orderupphämtning.

> [!NOTE]
> Dessa API:er ersätter **GetProductAvailabilities** och **GetAvailableInventoryNearby** API:er i Dynamics 365 Retail version 10.0.7 och tidigare.

Båda API:er hämtar data från Commerce Server och tillhandahåller en uppskattning av lagerbehållningen för en viss kombination av produkt- eller produktvarianten och ett lagerställe. Även om andra API:er som är tillgängliga på Commerce Server kan gå direkt till Commerce-administration för att hämta behållning för produkter, rekommenderar vi inte att de används i en näthandelsmiljö på grund av potentiella prestandaproblem och relaterad påverkan som dessa frekventa förfrågningar kan ha på dina servrar för Commerce-administration. Vidare om lagerbehållningen beräknas genom Commerce Server, är beräkningen mer sannolikt att inkludera lager som såldes i de senaste näthandelstransaktionerna som ännu inte har synkroniserats med Commerce-administration. Även om det kanske inte finns någon information om dessa transaktioner i Commerce-administration har Commerce Server och kanaldatabasdata. Data kommer därför att bedömas i och kan ge en mer korrekt uppskattning av produktens tillgängliga lager.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Komma igång med beräknad lagertillgänglighet för näthandel

Innan du använder de två API:er som nämnts tidigare måste du aktivera funktionen **Optimerad beräkning för produkttillgänglighet** via arbetsytan **Funktionshantering** i Commerce Headquarters.

Innan API:erna kan beräkna den bästa uppskattningen av lagertillgänglighet för en artikel, måste en periodisk ögonblicksbild av lagertillgänglighet från Commerce-administration bearbetas och skickas till den kanaldatabas som näthandel Commerce Scale Unit använder. Ögonblicksbilden representerar den information som Commerce-administration har om lagertillgänglighet för en specifik kombination av en produkt- eller produktvarianten och ett lagerställe. Den kan omfatta lagerjusteringar eller rörelser som orsakas av lagerinleveranser, försändelser eller andra processer som utförs i Commerce-administration och som näthandelskanalen har information om endast på grund av synkroniseringsprocessen.

Den gonblicksbild för databas som jobbet **produkttillgänglighet** beräknar bara de lagertransaktioner som har bearbetats och bokförts i Commerce-administration vid den tidpunkt då ögonblicksbilden togs. Om lagret såldes för en produkt i ett butikslager med hämtköp eller asynkron försäljning av kundorder i kassaprogrammet, finns det inte omedelbar information om den relaterade lagerkvantiteten för försäljningen i Commerce-administration. Det kommer att ha information om lagret som säljs för dessa typer av butiksförsäljning först när P-jobbet överför den relaterade transaktionen från butikens kanaldatabas till Commerce-administration och den relaterade försäljningsordern skapas genom utdraget bokföring av bokföringsprocessen för indroppning. När ordern skapas i Commerce-administration skapas relaterade lagertransaktioner. För näthandelskanalorder har Commerce-administration information om lagertransaktionerna först när transaktionerna har skickats till Commerce-administration via P-projektet och synkroniseringen av ordern har slutförts. Därför är det viktigt att du inser att lagrets ögonblicksbildsvärde som finns i jobbet **produkttillgänglighets** inte är 100-procent korrekt i realtid på grund av den konstanta försäljningsprocessen som sker mellan distribuerade servrar.

Följ de här stegen om du vill ta en ögonblicksbild av lagret i Commerce-administration.

1. Gå till **Retail och Commerce \> Retail och Commerce IT \> Produkter och lager \> Produkttillgänglighet**.
1. Välj **OK** för att köra jobbet **Produkttillgänglighet**. Du kan även tidsplanera det här jobbet så att det körs i en batch.

När jobbet **produkttillgänglighet** har slutförts måste de data som fångades skickas till näthandelskanalens databaser, så att den senaste lagringsbilden för Commerce-administration kan övervägas vid beräkningen av uppskattad lagerhållning.

1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Kör jobbet **1130** (**produkttillgänglighet**) om du vill synkronisera data för ögonblicksbild **produkttillgänglighet** har skapats från Commerce-administration till kanaldatabaserna.

När lagertillgängligheten begärs från API **GetEstimatedAvailability** eller **GetEstimatedProductWarehouseAvailability** körs en beräkning för att försöka få bästa möjliga uppskattning av lagret för produkten. Beräkningen hänvisar till alla kundorder för näthandel som finns i kanaldatabasen, men den togs inte med i ögonblicksbilden av de data som 1130-jobbet tillhandahåller. Den här logiken utförs genom att den senast bearbetade lagertransaktionen spåras från Commerce-administration och jämförs med transaktionerna i kanaldatabasen. Den tillhandahåller en baslinje för beräkningslogiken för kanalsidan, så att de ytterligare lagerrörelser som inträffat för kundorder försäljningstransaktioner i näthandels kanaldatabas kan delas upp i det uppskattade lagervärdet som API:n kan.

Beräkningslogiken på kanalsidan returnerar ett uppskattat fysiskt tillgängligt värde och ett totalt tillgängligt värde för den begärda produkten och lagerstället. Värdena kan visas på din näthandelssajt om du vill det, eller så kan de användas för att utlösa annan affärslogik på din näthandelssajt. Du kan till exempel visa meddelandet "brist på lager" i stället för den faktiska behållningskvantiteten som har godkänt API.

Den beräkningslogik som används för API:er för näthandelskanaler för uppskattat lagervärde kan endast utvärdera lager baserat på kundorder som har skapats i kanaldatabasen, men som ännu inte har synkroniserats och bokförts i Commerce-administration. Om din kanaldatabas också innehåller transaktionsdata för hämtköpförsäljning för butiksspecifika lager, bearbetas inte hämtköpförsäljningen i kanalsidans näthandelsberäkning för dessa lagerställen.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Konfigurera sökåtgärder för lager i kassakanalen

I Retail version 10.0.9 och tidigare använder åtgärden **Lagersökning** från POS ett servicesamtal i realtid till Commerce-administration för att få lagerinformation för den valda produkten, både för användarens aktuella butik och alla andra butiker som konfigurerats för uppfyllelsegrupp som en del av kanalkonfigurationen för butiken. I Commerce version 10.0.10 och senare kan du inaktivera servicesamtal i realtid till Commerce-administration. Istället kan du använda beräkning på kanalsidan på Commerce Server för att fastställa vilken lagerbehållning som är fysiskt tillgänglig för butiken och andra platser som har definierats i uppfyllelsegruppen. Denna kanalberäknade lagerkonfiguration är också användbar för platser där Internet-anslutningen är otillförlitlig, eftersom du inte behöver vara online för att hämta lagersökningar från Commerce-administration.

När kanalsidans beräkning är korrekt konfigurerad och hanterad kan den ge en mer tillförlitlig uppskattning av den aktuella butiksinventeringen, eftersom den använder de transaktionsdata som finns i Commerce-kanaldatabasen, men det kan hända att Commerce-administration ännu inte ha information om. Om du till exempel använder det befintliga servicesamtalet i realtid för lagersökningar i POS, har Commerce-administration antagligen ingen information om hämtköpförsäljning som har utförts för en produkt. Det lagerbehållningsvärde som återkommer för den produkten kommer därför att överskrida butikens faktiska lagerbehållning med en enhet. Om du däremot använder beräkning på kanalsidan kan hämtköpförsäljning delas upp i beräkningen och dras av från behållningsvärdet som visas. Även om de värden som används vid beräkningen av både kanalsidan och servicesamtalet i realtid är enbart uppskattningar av lagerbehållning, är värdet som beräkningen på kanalsidan ger mycket mer exakt för den aktuella butiken.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Komma igång med beräknad lagertillgänglighet för kassa på kanalsida

Om du vill använda beräkningslogiken på kanalsidan och inaktivera serviceanrop i realtid för lagersökningar från kassaprogrammet (POS) måste du först aktivera funktionen **Optimerad beräkning för produkttillgänglighet** via arbetsytan **Funktionshantering** i Commerce Headquarters. Förutom att aktivera funktionen måste du utföra ändringar i **Funktionsprofilen**.

Följ dessa steg för att ändra **Funktionsprofilen**:

1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**.
1. Välj en funktionsprofil.
1. På snabbfliken **funktioner** i avsnittet **Beräkning av lagertillgänglighet**, ändra värdet för fältet **Läget beräkning av lagertillgänglighet** från **Realtidstjänst** till **Kanal**. Alla funktionsprofiler använder som standard servicesamtal i realtid. Därför måste du ändra värdet i det här fältet om du vill använda beräkningslogik på kanalsidan. Alla butiker som är kopplade till den valda funktionsprofilen påverkas av den här ändringen.

Du måste sedan synkronisera ändringarna till kanalen genom distributionsschemaprocessen genom att utföra följande steg:

1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. Kör jobbet **1070** (**jakanlkonfiguration**).

När konfigurationen är klar använder den information som finns om fysiskt tillgängligt lager inte längre ett samtal i realtid när en användare i kassaprogrammet använder operationen **lagersökning** (standard- och matrisvyer). I stället beräknas data om fysiskt tillgängligt lager för den aktuella butiken och alla butiker i uppfyllelsegruppen, baserat på den senaste kända ögonblicksbilden som levererades till kanaldatabasen från Commerce-administration. Värdet för ögonblicksbilden kan finjusteras ytterligare av kanalberäkningen för att justera det fysiskt tillgängliga värdet, baserat på ytterligare försäljnings- eller returtransaktioner för den valda produkten i kanaldatabasen som inte inkluderades i de senaste synkroniserad ögonblicksbilden från 1130-jobbet. Om kanaldatabasen inte innehåller transaktionsdata för något av lagren eller butikerna i uppfyllelsegruppen, innehåller den inga ytterligare transaktioner som kan beaktas vid en omberäkning av värdet. Därför är den bästa uppskattningen av lagerbehållning som kan visas för dessa lagerställen eller butiker, data från den senaste ögonblicksbilden av Commerce-administration.

Skärmen **Orderuppfyllelse** i POS utnyttjar också beräkningen av kanalsidan för att visa inventering för objekt när en rad för orderuppfyllning är vald och en användare visar panelen **Detaljer** för lagerbehållning för den valda artikeln..

## <a name="optimize-your-inventory-data"></a>Optimera dina lagerdata

För att säkerställa bästa möjliga uppskattning av lagret är det viktigt att du använder följande Commerce-batchjobb och kör dem ofta:

- **P-Jobb** – p-jobbet finns på sidan **distributionsplaner** och bör köras ofta. Det här jobbet ger näthandelsorder, asynkrona kundorder som skapats av POS och hämtköporder som skapas från kanaldatabaser till Commerce-administration, så att de kan bearbetas ytterligare. Innan dessa data synkroniseras från kanalen till Commerce-administration har inte Commerce-administration någon information om lagerjusteringar till produkter i de lagerställen som kommer från dessa transaktioner.
- **Synkronisera order** – i det här jobbet bearbetas råa transaktionsdata i Commerce-administration som P-jobbet innehåller och omvandlar näthandel och asynkrona kundordertransaktioner till försäljningsorder i Commerce-administration. Inga lagertransaktioner skapas förrän jobbet bearbetas och försäljningsorder skapas. Lagerbehållningen i Commerce-administration kan därför inte ta hänsyn till transaktionerna.
- **Beräkna transaktionsutdrag i batch** – för hämtköpstransaktioner som skapas i butiken, säkerställer indroppningsbaserad bokföringsprocess att lagret som är relaterat till försäljningen uppdateras effektivt. För att få effektiv bearbetning av lagertransaktioner för hämtköpsorder måste du konfigurera systemet för att använda [indroppningsbaserad bokföring](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Bokför transaktionsutdrag i batch** – det här jobbet krävs även för indroppningsbaserad bokföring. Den följer jobbet **Beräkna transaktionsutdrag i batch**. Det här jobbet bokför de beräknade utdragen, så att försäljningsorder för hämtköpförsäljningen skapas i Commerce-administration och i Commerce-administration på ett mer exakt sätt återspeglar butikens lager.
- **Produkttillgänglighet** – det här jobbet skapar ögonblicksbilden av lagret från Commerce-administration.
- **1130 (Produkttillgänglighet)** – det här jobbet finns på sidan **distributionsplaner** och bör köras omedelbart efter jobbet **produkttillgänglighet**. Det här jobbet transporterar data för lagerögonblicksbilden från Commerce-administration till kanaldatabaserna.

Vi rekommenderar att du inte kör dessa batchjobb för ofta (med några minuters intervall). Att köra ofta överbelastar Commerce-administration (HQ) och kan påverka prestanda negativt. I allmänhet är det bra att köra produkttillgänglighet och 1130 jobb per timme och att tidsplanera P-jobb, synkronisera order och indroppningsbaserade jobb med samma eller högre frekvens.

> [!NOTE]
> Av prestandaskäl används beräkningen av lagerdispositionen för lagertillgänglighetsberäkningar för att göra en begäran om lagertillgänglighet att använda näthandels API: n eller den nya lagerlogiken för kassakanaler, beräkningen använder cache som fastställer om det har gått tillräckligt med tid för att motivera körning av beräkningslogiken igen. Standardcache är inställd på 60 sekunder. Du har till exempel aktiverat en beräkning på kanalsidan för butiken och visat lagerbehållningen för en produkt på sidan **lagersökning**. Om en enhet av produkten sedan säljs kommer sidan **lagersökning** inte att visa det reducerade lagret förrän cachen har rensats. När användarna har bokfört transaktioner i POS ska de vänta 60 sekunder innan de kontrollerar att lagerbehållningen har reducerats.

Om det krävs en mindre cachetid för affärsscenariot kan du kontakta produktsupporten för att få hjälp.


[!INCLUDE[footer-include](../includes/footer-banner.md)]