---
title: Ställ in kanaler för kundtjänst
description: Denna artikel innehåller information om hur du bearbetar order till kundtjänst med Dynamics 365 Commerce.
author: josaw1
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c6d21385d956534c799af5b9e20a54c9970da368
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854881"
---
# <a name="set-up-call-center-channels"></a>Ställa in kundtjänstkanaler

[!include [banner](includes/banner.md)]

Ett företag kan definiera flera kundtjänstkanaler i Dynamics 365 Commerce. Kundtjänstkanaler konfigureras i **Butik och handel** \> **Kanaler** \> **Kundtjänst** \> **Alla kundtjänster**, och de är specifika för en juridisk person.

När en ny kundtjänstkanal skapas tilldelas systematiskt ett driftenhetsnummer. Eftersom kundtjänst skapas som driftenheter, kan användare koppla kundtjänstkanalen till olika handelsfunktioner, t.ex. sortiment, kataloger och specifika leveranssätt.

Ett standardlagerställe kan konfigureras på kundtjänstkanalen. Sedan när försäljningsordern skapas i den kanalen anges standardlagerstället automatiskt på försäljningsorderns rubrik, såvida inget annat lagerställe har definierats på den kund som har valts för försäljningsordern. I det fallet anges kundens lager som standard.

Användarna måste kopplas till en kundtjänstkanal för att kunna använda funktionerna för kundtjänst. Alla försäljningsorder som skapas av en användare kopplas automatiskt till användarens kundtjänstkanal. En användare kan för närvarande inte kopplas till flera kundtjänstkanaler samtidigt.

En e-postmeddelandeprofil kan också konfigureras på kundtjänstkanalen. Profilen definierar de e-postmallar som används när e-postmeddelanden skickas till kunder som gör beställningar via kundtjänstkanalen. E-postutlösare kan konfigureras mot systemhändelser, till exempel att skicka beställningen eller orderförsändelse.

Innan försäljning kan behandlas korrekt via en kundtjänstkanal måste korrekta [betalsätt](/dynamics365/unified-operations/retail/work-with-payments) och leveranssätt definieras för kanalen.

Du kan definiera andra standardvärden som är relaterade till de ekonomiska dimensioner som ska kopplas till order som skapas med den kanalen på nivån för kundtjänstkanalen.

## <a name="options-for-order-processing-behavior"></a>Alternativ för orderhanteringsbeteende

Tre inställningar av en kundtjänst i har en betydande inverkan på funktionerna som är tillgängliga för försäljningsorder som skapas mot den kundtjänst: **aktivera slutförande av order**, **aktivera direkt försäljning**, och **aktivera orderpriskontroll**.

### <a name="enable-order-completion"></a>Aktivera slutförande av order

Inställningen **aktiverar slutförande av order** på kundtjänstkanalen har större påverkan på orderhanteringsflödet för försäljningsorder som har angetts för den kanalen. När den här inställningen aktiveras måste alla försäljningsorder genomgå en uppsättning valideringsregler innan den kan bekräftas. Du kan köra dessa regler genom att välja knappen **Slutför** som har lagts till i åtgärdsfönstret på sidan för försäljningsorder. Alla försäljningsorder som skapas när inställningen **aktivera slutförande av order** är aktiv måste genomgå orderslutförandeprocessen. Den här processen tvingar insamling av betalning och betalningsvalideringslogik. Utöver tvingad betalning kan orderinskickningsprocesse utlösa [bedrägericheckar](/dynamics365/unified-operations/retail/set-up-fraud-alerts) som konfigureras i systemet. Order som misslyckas att betalas eller bedrägerivalideringar spärras och kan inte frisläppas till ytterligare behandling (t.ex. plockning eller transport) tills du har löst problemet som orsakade spärrningen.

När inställningen **aktivera slutförande av order** har aktiverats för kundtjänstkanalen, om artikelrader registreras på en försäljningsorder och kanalanvändaren försöker stänga eller navigera bort från försäljningsorderformuläret utan att först välja **slutförd**, tvingar systemet orderslutföringsprocessen genom att öppna sidan för sammanfattning av försäljningsorder och som kräver att användaren skickar ordern. Om ordern inte kan skickas korrekt tillsammans med betalning, kan användaren använda [orderspärrar](/dynamics365/unified-operations/retail/work-with-order-holds) för att spärra ordern. Om användaren vill annullera ordern måste han eller hon korrekt annullera den med hjälp av Avbryt eller Ta bort, beroende på vilken funktion som användarens säkerhets tillåter.

Om inställningen **aktivera slutförande av order** är aktiv för kundtjänstkanalen kommer fältet **betalningsstatus** att spåras på ordern. Systemet beräknar **betalningsstatus** när försäljningsordern skickas. Endast order som har godkänd betalningsstatusen kan flytta genom systemet för ytterligare bearbetningssteg, t.ex. att plocka och leverera ordern. Om en betalning är avvisad kommer flaggan **bearbeta inte** att aktiveras för detaljerad orderstatus, detta sätter ordern i avvaktan tills du har löst betalningsproblemet.

Dessutom om inställningen **aktivera slutförande av order** är aktiv när användare skapar försäljningsorder och arbetar i läget för registrering av radartikel kommer fältet **källa** att vara tillgängligt på den huvudsakliga försäljningsorderrubriken. Fältet **källa** används för att hämta en [katalogkällkod](/dynamics365/unified-operations/retail/call-center-catalogs) i ett försäljningsscenario med direkt marknadsföring. Den här koden kan sedan ge särskilda priser och kampanjer.

Även om inställningen **aktiverar slutförande av order** är inaktiverad, kan användare fortfarande tillämpa en källkod till en försäljningsorder. Men de måste öppna rubriken för försäljningsorderinformation för åtkomst till fältet **källa**. Med andra ord krävs vissa ytterligare klick. Samma sak gäller för funktioner som slutför transport och expedierade order. Dessa funktioner är tillgängliga för alla order som har skapats i till en kundtjänst. Men när inställningen **aktivera slutförande av order** aktiveras kan användare visa konfigurationen av funktionerna i försäljningsrubriken medan de finns i radpostvyn. De behöver inte gå ner till rubrikinformationen för försäljningsorder för att hitta lämpliga inställningar och fält.

> [!NOTE]
> När funktionen **Flerkanals orderbetalningar för Commerce** är aktiverad kommer knappen callcenter **Aktivera slutförande av order** kommer att döljas i huvudkontoret på snabbfliken **Allmänt** för din kanal på **Retail och Commerce \> Kanaler \> Callcenter**.

### <a name="enable-direct-selling"></a>Aktivera direkt försäljning

Om inställningen **aktivera direkt försäljning** är aktiv för kundtjänstkanalen kan användarna utnyttja funktionerna i Commerce för merförsäljning och korsförsäljning. I det här fallet visas popup-fönster under orderregistreringen som föreslår andra produkter som användaren av kundtjänst kan erbjuda kunden. Produkterna som föreslås baseras på produkten som precis beställdes i försäljningsorderraden. För närvarande kan merförsäljning och korsförsäljning konfigureras på artikelnivå på produkter eller kataloger. Om inställning **aktivera direkt försäljning** är inaktiverad för kundtjänstkanalen visas inte popup-fönster under orderregistreringen, även om en giltig merförsäljning och korsförsäljning har definierats för en artikel som beställts.

När inställningen **aktivera direkt försäljning** är aktiv, aktiveras även skript och funktioner för bilder för försäljningsorderns startsida. I det här fallet finns en informationspanel på höger sida under orderregistreringen. Här kan du visa skript relaterade till den allmänna orderregistrerinsprocessen, katalogkällkod som kopplades eller skript som rör artiklarna som beställs. Dessutom kan bildpaneler visa en produktbild för artiklarna som beställs, om en bild har definierats för artikeln i inställningarna för produkten.

### <a name="enable-order-price-control"></a>Aktivera orderpriskontroll

När inställningen **Aktivera orderpriskontroll** är aktiv, kan endast behöriga användare ändra försäljningspriset för en artikel under orderregistreringen. Ändringarna måste ligga inom angivna toleranser. Användare som inte har rätt behörighet måste ansöka om en prisförändring i stället. Begäran bearbetas sedan igenom systemarbetsflöden för granskning och godkännande.

## <a name="channel-users"></a>Kanalanvändare

När du definierar kundstjänstkanal måste du koppla användare till kundstjänstkanalen. I annat fall kan inte till en kundstjänstkanal användas i systemet. När användare loggar in Commerce och registrerar försäljningsorder eller returorder på en sida relaterad till orderregistrering, valideras användaridentitet mot konfigurationen av kundstjänstkanal. Om en användare kopplas till en specifik kundtjänstkanal, ärver den användaren egenskaper och standardvärden för kanalen.

Som standard är flaggan **Försäljning** i rubriken på försäljningsordern aktiverad för alla order som kundtjänstanvändaren skapar. Dessa order kan sedan utnyttja systemets handelspecifika pris- och kampanjegenskaper.


Användare som inte är kopplade till en kundtjänstkanal använder funktioner för standardorderkvantitet i Microsoft Microsoft Dynamics 365 Finance. Order som användarna anger via försäljningsorderformuläret identifieras inte systematiskt som handelsorder. Dessutom är dessa order som dessa användare anger kanske inte föremål för några orderbearbetningsregler, prissättningslogik eller andra ordervalideringar som kan definieras i konfigurationen för kundtjänstkanalen eller kundtjänstsystemparametrar.

När du är klar med att konfigurera kundtjänstkanalen och definiera kanalanvändare, för att garantera önskad systemfunktion, se till att alla nödvändiga kundtjänstparametrar definieras i **butik och handel** \> **kanalinställningar** \> **kundtjänstinställningar** \> **kundtjänstparametrar**. Se till att relaterade nummerserier definieras också.

> [!NOTE]
> Om du använder kundtjänstfunktionen måste konfigurationsnyckeln **Flera leveransadresser** till aktiveras. Den här konfigurationsnyckeln finns i den konfigurationsnyckel för **handel** under **Systemadministration**\> **Konfiguration** \> **Licenskonfiguration**. Detta krävs på grund av kundtjänstfunktione som utför olika valideringar baserat på leveransadressen som konfigurerats på försäljningsorderradnivå. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
