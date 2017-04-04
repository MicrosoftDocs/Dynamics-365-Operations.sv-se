---
title: Hantera legotillverkning arbete i produktion
description: "Det här avsnittet beskrivs hur operationerna hanteras i Microsoft Dynamics 365 för operationer. Med andra ord förklarar hur produktionsåtgärder som tilldelats en resurs som hanteras av en leverantör."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Hantera legotillverkning arbete i produktion

Det här avsnittet beskrivs hur operationerna hanteras i Microsoft Dynamics 365 för operationer. Med andra ord förklarar hur produktionsåtgärder som tilldelats en resurs som hanteras av en leverantör.

I [produktionsprocesser](production-process-overview.md), arbetet kan bli gjort av resurser, som ägs eller förvaltas av leverantörer. Resurser för leverantören används vanligtvis på periodiska överflödiga efterfrågan som är fastställd i den tillgängliga kapaciteten hos ett företag egna resurser. Leverantören kan också kunna erbjuda särskilda [resurskunskaper](resource-capabilities.md)eller resurser till ett lägre pris.  

Beroende på leverantören resurserna som används i produktionsprocessen, en [väg](routes-operations.md) ofta har behov av ytterligare logistiska eftersom material och halvfabrikat först måste transporteras till leverantörens webbplats. Sedan transporteras resultatet i legotillverkningsoperationen till platsen som allokeras till nästa operation eller ett lager av färdiga varor.  

När den legotillverkning åtgärder eller aktiviteter används påverkar de alla faser av transaktioner, från definitionen av de åtgärder som krävs för produktion, kostnadsredovisning, prognoser, planering och schemaläggning i hanteringen av logistik för material, halvfabrikat och färdiga varor. Dessutom kräver dessa resurser egna processer för redovisning och kostnadskontroll.  

För interna resurser tilldelas fasta kostnadstariffen normalt för en period. Däremot kan utifrån den legotillverkning resurskostnader inköpspriset för tjänsterna. Tjänsten definieras som en annan produkt och används för att skapa upphandling och köpa processer för en viss legotillverkningsoperationen.  

Det finns för närvarande inga uttryckliga begreppet halvfabrikat i Microsoft Dynamics 365 för operationer. Den färdiga varan bokförs för en produktionsorder som kräver mer än en åtgärd för att omvandla råmaterial till färdig artikel till lagret bara i den sista operationen. Halvfärdiga produkter som tidigare åtgärder ge redovisas i arbete (PIA) men inte bokföras eller spårats i lagret. Även om du kan dela flöden och strukturlistor strukturlistorna i flera mindre enheter, ökar antalet varor, strukturlistor och flöden som måste hanteras den här metoden.  

Det finns två metoder för modellering legotillverkning av produktionsoperationerna. Dessa metoder skiljer sig åt på det sättet att den legotillverkning processen kan utformas, halvfabrikat representeras i processen och hur kostnadsstyrning hanteras.

-   Legotillverkning av flödesoperationer i produktionsorder eller batchorder
    -   Tjänsten produkten måste vara produkt i lager och det måste vara en del av Strukturlistan.
    -   Den här metoden stöder först in, först ut (FIFO) eller standardkostnad.
    -   Halvfabrikat representeras av tjänstprodukter i processen.
    -   Kostnadskontroll fördelar kostnader som är kopplade till den legotillverkning till materiella kostnader.
-   Legotillverkning av produktionsflödesaktiviteter i lean-produktionsflöde
    -   Tjänsten är en icke-lagerförd tjänstprodukter och det är inte en del av Strukturlistan.
    -   Den här metoden används inköpsavtal serviceavtal.
    -   Den här metoden används bakåtavräkning.
    -   På så vis kan aggregerade och asynkrona upphandling. (Materialflödet är oberoende av inköpsprocessen.)
    -   Kostnadskontroll allokerar legotillverkning i sin egen analys kostnad-block.

## <a name="subcontracting-of-route-operations"></a>Legotillverkning av flödesoperationer
Om du vill använda legotillverkning av flödesoperationer för produktions- eller batchorder tjänstprodukter som används för anskaffning av tjänsten måste definieras som en produkt av den **Service** typ. Dessutom kan det finnas en artikelmodellgrupp som har den **produkt i lager** alternativet **lagrets principen** in på **Ja**. Det här alternativet anger om en produkt börjar tillämpas, redovisas som lager på produktinleverans (**produkt i lager** = **Ja**), eller om produkten resultaträkningen för ett konto för vinst och förlust (**produkt i lager** = **nr**). Trots detta kanske verkar vara motsatt är baserad på att produkter som har den här principen skapar lagertransaktioner som kan användas i kostnadskontroll för att beräkna planerade kostnader och fastställa de faktiska kostnaderna när en tillverkningsorder är färdig.  

Tjänsten måste läggas till Strukturlistan ska anses vara i beräkningen av planering och kostnad. Strukturlisteraden måste vara av den **leverantör** typ och tilldelas flödesoperationen som tilldelats tjänsten. Denna flödesoperation måste ha ett kostnadsredovisningsresurs och resursbehov som pekar på en resurs av den **leverantör** som ansluter operationen och tjänsterna till motsvarande leverantörskontot.  

När den här konfigurationen används skapas en inköpsorder för den relaterade tjänst, utifrån uppskattningen av en produktionsorder. Inköpsorder för tjänsten används som ankare för de legotillverkning.. Legotillverkning kan hanteras via den **arbete legotillverkning** listsida i tillverkningskontrollen. Legotillverkning för råmaterial och slutligen halvfärdig produkt att skickas till leverantören som förberedelse för operationen. Den används också ta emot produkten i legotillverkningsoperationen i artikelinförsel, där produkten service används för att identifiera anländer halvfärdig produkt. När du har fått inköpsorderraden uppdateras produktionsoperationen som slutförd.  

En produktionsorder kan ha många åtgärder och varje operation kan tilldelas en annan leverantör. Därför kan kan en slutpunkt till slutpunkt tillverkningsorder utlösa flera inköpsorder.

## <a name="subcontracting-of-production-flow-activities"></a>Legotillverkning av produktionsflödesaktiviteter
Den [lean manufacturing](lean-manufacturing-overview.md)lösning modeller legotillverkning arbetet som en tjänst som hör till en aktivitet med en [produktionsflöde](http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (avsnittet guide). Därför den här typen av den legotillverkning kallas också för [verksamhetsbaserade legotillverkning.](activity-based-subcontracting.md) En speciell kostnadstyp grupp, **direktutkontraktering**, har införts och de legotillverkning tjänsterna inte ingår i Strukturen på de färdiga varorna. När du använder lean manufacturing definieras all verksamhet som av kanban som kan vara relaterad till en eller flera produktionsflödesaktiviteter. Denna förklaring låter hittills, precis som en förklaring av tillverkningsorder. Medan produktionsorder måste avslutas alltid med en färdig produkt, kan du skapa kanbans till leveransorder halvfärdig produkt. Du behöver en ny produkt och strukturlistenivå.  

Eftersom kanban-regler kan vara mycket dynamisk kan utforma du olika varianter för samma produkt på ett produktionsflöde. När du använder resurssnål åtskilda legotillverkning, material flödet och ekonomiska flöde strikt. Alla materialflödet representeras av kanban-aktiviteter. Inköpsorder för tjänstprodukter och bokföringarna mottagandet av dessa tjänster kan utföras automatiskt, baserat på status för kanban-jobb i produktionsflödet. Kanban-jobb kan påbörjas och avslutas innan inköpsorderna som skapas. Legotillverkningsdokument (inköpsorder och inleveransen av tjänsten) kan aggregeras och period. Därför kan antal inköpsdokument och rader hållas liten, även i mycket repetitiva åtgärder där leverantörer ger legotillverkningstjänster i ett enstaka stycke flöde.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modellering legotillverkning i ett produktionsflöde

I en [lean-produktionsflöde](lean-manufacturing-modeling-lean-organization.md), en processaktivitet definieras som den legotillverkning när tilldelas en arbetsgrupp (resursgrupp) med en enda leverantör resursen. När en arbetsgrupp gäller legotillverkning måste relaterade processaktiviteter kopplas till en aktiv inköpsavtalsraden som innehåller serviceartikeln och priset för tjänsten. Serviceavtalet för aktiviteten även definierar förhållandet mellan produktkvantitet för kanban-jobbet och resulterande tjänstekvantiteten beräkningen. Du kan välja om tjänstekvantiteten beräknas baserat på antalet jobb, god produktkvantitet som rapporteras på jobben eller den totala produktkvantitet (totala antalet innehåller kasserade produkter).  

Överföringsaktiviteter kan också definieras som den legotillverkning. Denna definition sker implicit när du väljer den ansvariga parten för leverans i fältet för överföring. När du väljer **speditören** eller **mottagaren**, om motsvarande källan eller målet lagerstället är ett lagerställe som hanteras av leverantören anses aktiviteten legotillverkning. När du väljer **transportföretagets**, aktiviteten alltid legotillverkning. Legotillverkning processaktiviteter som en legotillverkning överföringsaktivitet måste kopplas till ett serviceavtal innan det går att aktivera produktionsflödet.

### <a name="backflush-costing"></a>Kostnadskalkylering med automatisk lageravräkning

Kostnadsredovisning av legotillverkning integreras fullständigt kostnadsredovisning för lean manufacturing lösningen (bakåtavräkning). När du bokför ordern inleveransen av tjänsten eller faktureras tilldelas anskaffningskostnaden för tjänsten produktionsflödet. För bakåtavräkning beräknas avvikelsen för legotillverkningstjänster genom avräkning av det legotillverkning textblocket standardkostnaden för mottagna varorna mot de faktiska servicen inlevererad och fakturerad.

## <a name="material-supply-for-subcontracted-operations"></a>Materialleverans för den legotillverkning.
Halvfabrikat och andra relaterade material måste överföras till den plats där arbetet ska utföras fysiskt. När du använder operationerna och aktiviteter relaterade överföringen ofta för ytterligare transporter till en webbplats som drivs av leverantörer. Genom att tilldela material i Strukturlistan ska legotillverkningsoperationen kan du ange att materialet måste mellanlagras i resursgruppen för den fördelade resursen inleveransplats. Huvudplanering eller sedan resurssnål påfyllnad bestämmelser material till önskad plats.  

För att modellera lagret som finns hos en leverantör är det bäst i branschen att definiera ett lagerställe som hanteras av leverantören. Du kan definiera ett lagerställe som leverantören hanteras enkelt genom att skapa ett nytt lagerställe och tilldela leverantörskontot. Om du vill dokumentera materialet ska överföras till leverantören innan en åtgärd kan utföras, ska du dela ut inleveranslagret för resursgruppen som innehåller resursen leverantör hanteras lagret.  

Du kan använda flera strategier för att fylla på material på det här lagerstället:

-   Överföringsorder
-   Överför journaler
-   Uttag kanbans
-   Inköp till leverantör

Halvfärdiga produkter är undantag till regeln. Om du vill överföra halvfärdiga produkter är begränsat till följande alternativ:

-   För produktions- och batchorder halvfärdiga produkter kan bara överföras logiskt med hjälp av plocklistejournalen från den **arbete legotillverkning** listsida. Den här journalen skapas en följesedel dokument som kan användas för att överföra halvfärdiga och råmaterial till leverantören.
-   Överföringen av halvfabrikat dokumenteras genom mottagande av uttag eller produktion kanbans där leverantören för den legotillverkning i produktionsflöden. Du kan avsluta en produktions-kanban med en ytterligare överföringsaktivitet för att modellera ett explicit överföringsaktivitet.

**Anmärkning:** ett produktionsflöde för en enskild produktionsorder kan inte korsa flera siter. Denna regel gäller även legotillverkning. Därför lagerställena som representerar leverantören hanteras materialet platser måste definieras på samma plats som de interna resurser som används i flödet. Även om produktionsflöden kan passera platser, kan inte de transport halvfabrikat från en plats till en annan, eftersom åtgärden innebär en förändring av kostnaden kontext.  

Vanligtvis tilldelas Utleveranslagerställe och platsen för den legotillverkning resursgrupp direkt lagret och plats för operationen i flödet flödes- eller nästa steg. Den här inställningen bidrar till att minska mängden jobbet rapportering som uppstår eller antal ytterligare överföringarna som måste utformas.


