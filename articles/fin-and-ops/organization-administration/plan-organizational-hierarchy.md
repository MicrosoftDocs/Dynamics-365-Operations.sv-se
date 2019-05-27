---
title: Planera en organisationshierarki
description: Innan du konfigurerar organisationer och organiationshierarkier, se till att du förstår hur du utformar din verksamhet på bästa sätt.
author: sericks007
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 633d85333a510cec9cee2721e6e2330a47b6c78c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545796"
---
# <a name="plan-your-organizational-hierarchy"></a>Planera en organisationshierarki

[!include [banner](../includes/banner.md)]

Innan du ställer in organisationer och organisationshierarkier i Microsoft Dynamics 365 for Finance and Operations måste du planera hur din verksamhet ska se ut. Organisationsmodellen har en avsevärd effekt på implementeringen av Finance and Operations och på affärsprocesser.

Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag. Därför är det viktigaste övervägandet, när du modellerar organisationer, strukturen på företaget. Vi rekommenderar att du definierar organisationsstrukturer som baseras på feedback från chefer och ledande befattningshavare från funktionella områden, till exempel ekonomi och redovisning, personal, drift, inköp, och försäljning och marknadsföring.

När du skapar planeringshierarkier för dimensionsuppsättningar, är det också viktigt att ta hänsyn till relationen mellan organisationshierarkin och ekonomiska dimensioner. Du kan ställa in flera organisationens hierarkier som representerar olika vyer av arbetet. Med ekonomiska dimensioner kan du skapa rapporter baserat på dessa vyer. Arbeta med din Microsoft Dynamics 365 for Finance and Operations-partner för att skapa hierarkier för både organisationens och lagstadgade rapporteringsbehov.

> [!NOTE]
> Även om du kan använda finansiella dimensioner för att framställa juridiska personer utan att skapa de juridiska personerna i Finance and Operations, så har finansiella dimensioner inte utformats i syfte att adressera verksamhetsrelaterade behov eller affärsbehov hos juridiska personer. Internredovisningsfunktionen i Finance and Operations har utformats att endast fokusera på de redovisningsposter som skapas av respektive transaktion.

> [!IMPORTANT]
> Du bör inte bestämma din organisationsmodell enbart med informationen i denna artikel som underlag. Den här dokumentationen är en guide. Du kan arbeta med din Finance and Operations Partner-partner för ytterligare vägledning. Din Finance and Operations-partner har erfarenhet från olika industrier och kundbaser.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Bestäm om interna organisationer ska modelleras som juridiska personer eller driftenheter

Du måste ha minst en juridisk person som representerar din verksamhet i Finance and Operations. En juridisk person kan ingå juridiska avtal och måste förbereda bokslut som visar dess resultat.

I Finance and Operations kan juridiska personer användas för transaktionsaffärer eller för konsolidering. Detta innebär att en juridisk person i Finance and Operations inte nödvändigtvis representerar en verklig enhet i verksamheten. Ett företag som medverkar i transaktioner kan till exempel äga dotterbolag som är juridiska personer. I det här scenariot krävs en juridisk person för transaktioner, och en virtuell juridisk person krävs för att konsolidera resultat och saldon från dotterbolagens juridiska personer.

Interna organisationer i din verksamhet, till exempel regionkontor, kan representeras som ytterligare juridiska personer, eller som driftenheter i den huvudsakliga juridiska personen. En driftenhet behöver inte vara en juridiskt definierad organisation. Driftenheter används för att kontrollera ekonomiska resurser och driftprocesser i verksamheten. Avdelningar och kostnadsställen är till exempel driftenheter.

Alla funktioner i Finance and Operations fungerar olika beroende på om organisationen är en juridisk person eller en driftenhet. Överväg noga nedanstående funktioner innan du fattar ditt beslut.

### <a name="master-data"></a>Huvuddata

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Vissa huvuddata, till exempel kunder, betalningsvillkor, skattemyndigheter och platsspecifika lagerorder, måste anges för varje juridisk person. Vissa huvuddata, till exempel användare, produkter och de flesta personalresursdata, delas mellan alla juridiska personer.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Huvuddata delas mellan driftenheter.

### <a name="module-parameters"></a>Modulparametrar

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Parametrarna för moduler som parametrar för Kundreskontra, parametrar för Leverantörsreskontra och parametrar för Kassa- och bankhantering, måste anges per juridisk person. Eftersom modulinställningen för juridiska personer är separat kan varje dotterbolag uppfylla lokala lagstadgade krav och affärsmetoder. Till exempel kan en juridisk person inom professionella tjänster och en juridisk person inom tillverkning ha olika modulparametrar, även om de rapporterar till samma moderbolag.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Modulparametrar delas mellan driftenheter.

### <a name="data-security"></a>Datasäkerhet

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

De flesta data säkras automatiskt av företags-ID. Ett företags-ID är en unik identifierare för de data som är associerade med en juridisk person. Ett företag kan kopplas till bara en juridisk person, och en juridisk person kan kopplas till ett företag. Användare kan bara få åtkomst till data för de företag som de har tillgång till. Du behöver inte anpassa Finance and Operations för att skydda dina data med företags-ID.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Data kan skyddas av driftenheten genom att skapa anpassade datasäkerhetspolicyer. Datasäkerhetspolicyer används för att begränsa åtkomst till data. Anta att en användare har behörighet att skapa inköpsorder bara i en viss driftenhet, till exempel. Datasäkerhetspolicyer kan skapas för att förhindra att användaren får åtkomst till inköpsorderdata från en annan driftenhet. Transaktionsvolymen och antalet säkerhetpolicyer kan påverka prestandan. Kom ihåg prestanda när du utformar säkerhetpolicyer.

### <a name="ledgers"></a>Redovisningar

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

För varje juridisk person krävs det en redovisning som innehåller en kontoplan, en redovisningsvaluta, en rapportvaluta och en räkenskapskalender. En balansräkning endast kan skapas för en juridisk person. Huvudkonton, dimensioner, kontostrukturer, kontoplaner och kontoregler kan användas av mer än en juridisk person.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

En driftenhet kan inte ha sin egen redovisningsinformation. Om dina interna organisationer inte kräver unika redovisningar, kan du utforma den som driftenheter. Redovisningsinformation ställs in för den överordnade juridiska personen i hierarkin. Inkomstutdrag kan skapas för driftenheter inom en juridisk person eller för den överordnade juridiska personen.

### <a name="fiscal-calendars"></a>Räkenskapskalendrar

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Varje juridisk person har en egen räkenskapskalender. Om dina interna organisationer använder olika räkenskapsår och räkenskapskalendrar måste du utforma organisationerna som juridiska personer.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Driftenheter måste ha samma räkenskapskalender. Om dina interna organisationer kan använda samma räkenskapsår och av räkenskapskalendrar, kan du utforma organisationerna som driftenheter.

### <a name="consolidation"></a>Konsolidering

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Du måste konsolidera de finansiella resultaten för regionkontor till ett enda konsoliderat företag för att förbereda bokslut.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Konsolidering krävs inte eftersom data redan är delade mellan driftenheter.

### <a name="centralized-payments"></a>Centraliserade betalningar

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Centraliserade betalningar måste ställas in så att fakturor för alla underordnade juridiska personer kan betalas till eller från en enskild överordnad juridisk person.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Centraliserade betalningar krävs inte eftersom alla fakturor registreras i en enda juridisk person.

### <a name="intercompany-transactions"></a>Koncerninterna transaktioner

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Koncerninterna försäljningsorder, inköpsorder, betalningar eller inleveranser kan tillämpas på varandra. Du måste inte att använda journalverifikationer. Du kan visa koncerninterna transaktioner på underredovisningsnivå (Kundreskontra, Leverantörsreskontra). I följande exempel visas hur koncerninterna transaktioner hanteras.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exempel 1: Huvudkontoret erbjuder tjänster till regionala kontor och måste debitera kostnaden för dessa tjänster till de regionala kontoren

Om du utformar det regionala kontoret som en juridisk person har du följande alternativ:

- Huvudkontoret skapar en redovisningstransaktion i syfte att korsfakturera regionkontoret för utgiften. Transaktionerna föråldras inte.
- Huvudkontoret skickar en inköpsorder för tjänsten till regionkontoret. En försäljningsorder skapas automatiskt i den juridiska personen för regionkontoret med koncerninterna redovisningstransaktioner.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exempel 2: Huvudkontoret köper in och betalar för tjänster som levereras till ett regionkontor

Om du utformar det regionala kontoret som en juridisk person har du följande alternativ:

- Faktura och betalning följer huvudkontorets regelverk. Huvudkontoret kan skapa en post i redovisningsjournalen för att debitera regionkontoret för utgiften. Transaktionerna föråldras inte.
- Faktura och betalning följer huvudkontorets regelverk. Huvudkontoret kan skapa en koncernintern redovisningstransaktion.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Koncerninterna transaktioner mellan driftenheter stöds bara genom journalverifikationer. En driftenhet inte kan skicka eller ta emot en inköpsorder, försäljningsorder eller faktura från en annan driftenhet i samma juridiska person. Du kan inte visa koncerninterna transaktioner på underredovisningsnivå (Kundreskontra, Leverantörsreskontra). I följande exempel visas hur koncerninterna transaktioner hanteras.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exempel 1: Huvudkontoret erbjuder tjänster till regionala kontor och måste debitera kostnaden för dessa tjänster till de regionala kontoren

Om du utformar regionkontoret som en driftenhet anger huvudkontoren en utgiftstransaktion och kodar den till regionkontoret.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exempel 2: Huvudkontoret köper in och betalar för tjänster som levereras till ett regionkontor

Om du utformar regionkontoret som en driftenhet, följer fakturan och betalningen de reglerade kraven för huvudkontor. Fakturan kan kodifieras till regionkontoret. Använd en balanserande ekonomisk dimension i resultaträkningen för att rapportera kostnader för regionkontoret.

### <a name="local-tax-requirements"></a>Lokala skattekrav

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

En juridisk person omfattas av gällande skattelagstiftning i det land eller den region där den juridiska personen är registrerad. En juridisk person som är registrerad i Danmark lyder till exempel under danska momslagar och regler. I Finance and Operations kan en juridisk person endast tillhöra ett land/region. Landet/regionen, som du valt för den primära adressen för juridiska personen, kontrollerar lands-/regionspecifika funktioner som är tillgängliga för den juridiska personen. Om till exempel den primära adressen för den juridiska personen är i Danmark, blir funktioner som är relaterade till danska momslagar och regler tillgängliga. Om ditt företag finns i olika länder/regioner, och kräver olika lokala momsalternativ, måste du därför registrera organisationerna som separata juridiska personer.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Driftenheter använder landssammanhanget för den överordnade juridiska personen. Driftenheter i samma juridiska personen kan inte ha olika lands-/regionspecifika behov. Om dina organisationer är i samma land/region och använder samma momsalternativ, kan du ställa in dem som driftenheter.

### <a name="statutory-reporting-for-a-countryregion"></a>Lagstadgad rapportering för ett land/region

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

I länder/regioner som stöds av Finance and Operations kan de flesta lagstadgade rapporter skapas. Information om vilka rapporter som är tillgängliga för varje land/region finns i [Microsoft Dynamics Localization Portal](https://mbs.microsoft.com/customersource/global/ax/support/support-news/GFMLocalizationPortalMC) for Finance and Operations. (En CustomerSource-logo ett obligatoriskt fält.)

> [!NOTE]
> Ett bokföringslager i redovisningen i Finance and Operations gör att du kan justera poster i ett moderbolag som använder en annan redovisningsstandard än dotterbolaget. För ett företag som använder allmänt accepterad boföringspraxis i Storbritannien (UK GAAP) kan du göra justeringar i bokföringsskiktet, till exempel. Dessa poster kan konsolideras i ett moderbolag som använder allmänt accepterade redovisningsprinciper (GAAP) i USA. Justeringsposterna påverkar inte UK GAAP-rapporteringen.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Lagstadgade rapporter måste skapas med hjälp av ett annat program. Du måste du se till att data samlas in i Finance and Operations för att stödja kraven för varje driftenhet, där de skiljer sig från kraven för huvudkontoret.

### <a name="currency"></a>Valuta

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Om dina organisationer måste använda olika funktionella valutor måste du utforma organisationerna som juridiska personer. Funktionella valutor ställs in per juridisk person. Du kan dock ange transaktioner i flera valutor.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Om dina organisationer kan använda en enda funktionell valuta, kan du utforma organisationerna som driftenheter. Driftenheter måste ha samma funktionella valuta. Du kan dock ange transaktioner och skapa rapporter i flera valutor.

### <a name="year-end-closing"></a>Årsbokslut

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Om lagar och redovisningsprinciper är olika mellan de länder/regioner där dina organisationer finns kan du behöva olika årsbokslutsprocedurer per organisation. Detta innebär att du måste utforma organisationer som juridiska personer. Varje juridisk person har egna årsbokslutsprocedurer.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Om lagar och redovisningsprinciper är samma mellan de länder/regioner där dina organisationer finns kan du använda en och samma uppsättning med årsbokslutsprocedurer. Detta innebär att du kan utforma organisationer som driftenheter. Alla driftenheter måste använda samma årsbokslutsprocedur.

### <a name="number-sequences"></a>Nummerserier

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Nummerserier för alla referenser kan konfigureras per juridisk person. Vissa nummerserier kan delas.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Nummerserier för alla referenser kan konfigureras per driftenhet. Vissa nummerserier kan delas.

### <a name="products"></a>Produkter

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Produktdefinitioner delas och de måste frisläppas till enskilda juridiska personer innan de kan inkluderas i transaktioner. Varje juridisk person har en egen uppsättning frisläppta produkter som kan inkluderas i transaktionsdokument. Om dina interna organisationer måste använda andra uppsättningar av produkter, måste du utforma organisationerna som juridiska personer.

> [!NOTE]
> Även om produktdefinitioner delas kan du ange olika försäljnings-, inköps - och lagerparametrar för artikeln på varje lagerplats i varje juridisk person där en produkt har frisläppts.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Alla driftenheter delar samma uppsättning produkter. Om dina interna organisationer kan dela samma uppsättning av produkter, kan du utforma organisationerna som driftenheter.

### <a name="inquiry-and-reporting"></a>Förfrågning och rapportering

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Om organisationen modelleras som en juridisk person

Du måste manuellt ändra företag för att ange transaktioner och utföra förfrågningar i flera juridiska personer. På grund av gränser för datasäkerhet kan konsoliderad förfrågning och rapportering vara resurs- och tidskrävande.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Om organisationen modelleras som en driftenhet

Du behöver inte byta företag för att komma åt data från flera driftenheter. Konsoliderad förfrågning och rapportering och enskild regional förfrågning är enklare och snabbare.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Metoder för att utforma organisationer och hierarkier

Tänk på följande när du implementerar en organisationshierarki:

- Skapa en avdelning för modellering av skärningspunkten mellan en juridisk person och en affärsenhet. Du kan sedan rulla upp data från en avdelning till en juridisk person för lagstadgad rapportering och från en avdelning till en affärsenhet för intern rapportering. Avdelningar kan fungera som resultatenheter. Om du använder avdelningar, behöver du inte använda juridiska personer och affärsenheter som dimensioner i kontostrukturen. Du kan bara använda avdelningar som en dimension. Du måste dock använda både kostnadsställen och avdelningar som dimensioner i kontostrukturen om kostnadsställen bara används som kostnadsackumulatorer och avdelningar används för intäktsredovisning.
- Modellera flera hierarkier för driftenheter om du har komplexa krav för att rapportera vinst och förlust.
- I en enskild juridisk person ska du inte skapa flera hierarkier för samma hierarkisyfte.
- Skapa inte en hierarki för varje syfte. Vanligtvis kan du skapa en hierarki för flera syften. En hierarki med driftenheter kan till exempel tilldelas till alla policyrelaterade syften.
- Skapa balanserade hierarkier. I en hierarki definieras alla noder som är på samma avstånd från rotnoden som en nivå. I en balanserad hierarki kan endast en typ av driftenhet inträffa vid varje nivå, och avståndet från rotnoden till varje nivå är konsekvent. Om det finns mellanstadier mellan en avdelning och en juridisk person eller en affärsenhet, kan platshållareorganisationer krävas för att skapa en allsidig hierarki.
- Modellera inte en separat hierarki med driftenheter om strukturen för juridiska personer också är din driftstruktur. En blandad hierarki med juridiska personer och driftenheter kan uppfylla båda syftena.
- Innan du utformar stora omstruktureringsscenarier använder du hierarkins giltighetsdatum för att utföra en följdanalys och ett valideringstest.
- Använd utkastläge för att ändra en hierarki innan du publicerar en ny version i en produktionsmiljö.
- Begränsa antalet personer som har behörighet att lägga till eller ta bort organisationer från en hierarki i en produktionsmiljö. Ett lägre antal minskar risken för kostsamma misstag och behovet av korrigeringar.
