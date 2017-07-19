---
title: Hantera legotillverkningsarbete i produktionen
description: "Det här avsnittet beskriver hur verksamhet på entreprenad (legotillverkning) hanteras i Microsoft Dynamics 365 for Finance and Operations. Med andra ord förklaras hur produktionsåtgärder som tilldelats en resurs hanteras av en leverantör."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0e1368d3f637143fd47c3772c811257e8472cc74
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="manage-subcontracting-work-in-production"></a>Hantera legotillverkningsarbete i produktionen

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur verksamhet på entreprenad (legotillverkning) hanteras i Microsoft Dynamics 365 for Finance and Operations. Med andra ord förklaras hur produktionsåtgärder som tilldelats en resurs hanteras av en leverantör.

I [produktionsprocesser](production-process-overview.md) kan arbetet utföras av resurser som ägs eller förvaltas av leverantörer. Leverantörsresurser används vanligtvis för att jämna ut periodiskt överdriven efterfrågan som överskrider den tillgängliga kapaciteten hos ett företags egna resurser. Leverantören kan eventuellt också erbjuda särskilda [resurskunskaper](resource-capabilities.md)eller resurser till ett lägre pris.  

Beroende på de leverantörsresurser som används i produktionsprocessen har en viss [väg](routes-operations.md) ofta ytterligare logistiska behov, detta eftersom material och halvfabrikat först måste transporteras till leverantörens plats. Sedan måste resultatet för legotillverkningsverksamheten transporteras antingen till platsen som allokeras till nästa verksamhet eller ett lager för färdiga varor.  

När legotillverkningsverksamhet eller -åtgärder används, påverkar de alla verksamhetsfaser: från definitionen av de åtgärder som krävs för produktionen till kostnadsredovisning, prognoser, planering och schemaläggning och hanteringen av logistik för material, halvfabrikat och färdiga varor. Dessutom kräver dessa resurser egna processer för redovisning och kostnadskontroll.  

För interna resurser tilldelas som regel en fast kostnadstariff för en period. Däremot baseras kostnaden för resurser på entreprenad på inköpspriset för den tillhörande tjänsten. Tjänsten definieras som en annan produkt, och används för att underlätta anskaffnings- och inköpsprocesser för en viss legotillverkningsoperation.  

Det finns för närvarande inga uttryckliga begrepp för halvfabrikat i Microsoft Dynamics 365 for Finance and Operations. För produktionsorder som kräver mer än en åtgärd för att omvandla råmaterial till färdig vara, bokförs den färdiga varan åter i lager först i samband med den sista åtgärden. Halvfärdiga produkter som tidigare åtgärder framställer redovisas som pågående arbete (PIA), men varken bokförs eller spåras i lagret. Även om du kan dela flöden och strukturlistor i flera mindre enheter, ökar denna metod antalet varor, strukturlistor och flöden som måste hanteras.  

Det finns två metoder för att modellera legotillverkning för produktionsverksamheten. Dessa metoder skiljer sig åt genom hur legotillverkningsprocessen kan utformas, hur halvfabrikat representeras under processen, samt hur kostnadsstyrningen hanteras.

-   Legotillverkning av flödesoperationer i produktionsorder eller batchorder
    -   Tjänsteprodukten måste vara en produkt i lager och måste ingå i strukturlistan.
    -   Den här metoden stöder först in - först ut (FIFO) eller standardkostnad.
    -   Halvfabrikat representeras av tjänsteprodukten i samband med processen.
    -   Kostnadskontroll fördelar de kostnader som är kopplade till legotillverkningen till materiella kostnader.
-   Legotillverkning av produktionsflödesaktiviteter i ett resurssnålt produktionsflöde
    -   Tjänsten är en icke-lagerförd tjänsteprodukt, och ingår inte i strukturlistan.
    -   Den här metoden använder inköpsavtal som serviceavtal.
    -   Den här metoden använder kostnadskalkylering med automatisk lageravräkning.
    -   Metoden möjliggör sammanlagd och asynkron anskaffning. (Materialflödet är oberoende av inköpsprocessen.)
    -   Kostnadskontrollen fördelar legotillverkning i sitt eget kostnadsuppdelningsblock.

## <a name="subcontracting-of-route-operations"></a>Legotillverkning av flödesåtgärder.
Om du vill använda legotillverkning av flödesoperationer för produktions- eller batchorder, måste den tjänsteprodukt som används för anskaffning av tjänsten definieras som en produkt av typen **Tjänst**. Dessutom måste den ha en artikelmodellgrupp som har alternativet **Produkt i lager** under **Lagerpolicy** inställt på **Ja**. Det här alternativet anger om en produkt redovisas som lager på produktinleverans (**Produkt i lager** = **Ja**), eller om produkten kostnadsförs i en resultaträkning (**Produkt i lager** = **Nr**). Trots att detta kanske verkar vara motsatser, så baseras det hela på det faktum att endast produkter med denna policy skapar lagertransaktioner som kan användas inom kostnadskontroll för att beräkna planerade kostnader och fastställa de faktiska kostnaderna när en tillverkningsorder är färdig.  

Tjänsten måste läggas till i strukturlistan för att beaktas i samband med beräkning av planering och kostnader. Strukturlisteraden måste vara av typen **Leverantör** och tilldelas till den flödesverksamhet som tilldelats tjänsten. Denna flödesoperation måste ha en kostnadsredovisningsresurs och ett resursbehov som pekar på en resurs av typen **Leverantör** som kopplar verksamheten och relaterad tjänst till motsvarande leverantörskonto.  

När den här konfigurationen används, skapas en inköpsorder för den relaterade tjänsten baserat på uppskattningen av en produktionsorder. Inköpsordern för tjänsten används som ankare för legotillverkningen. Legotillverkning kan hanteras via listsidan **Legotillverkning** i tillverkningskontrollen. Legotillverkningen används för att leverera råmaterial och, i slutändan, ett halvfabrikat att skickas till leverantören som förberedelse för verksamheten. Den används också för att ta emot den resulterande produkten av legotillverkningsverksamheten i artikelinförsel, där tjänsteprodukten används för att identifiera när halvfabrikatet anländer. När inköpsorderraden tas emot, uppdateras produktionsverksamheten som slutförd.  

En produktionsorder kan ha många åtgärder, och varje åtgärd kan tilldelas en annan leverantör. Därför kan komplett tillverkningsorder utlösa flera olika inköpsorder.

## <a name="subcontracting-of-production-flow-activities"></a>Legotillverkning av produktionsflödesaktiviteter
Lösningsmodellen [lean manufacturing](lean-manufacturing-overview.md)modellerar legotillverkning som en tjänst relaterad till ett [produktionsflöde](http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (avsnitt i uppgiftsguide). Därför kallas den här typen av legotillverkning också för [verksamhetsbaserad legotillverkning.](activity-based-subcontracting.md) En särskild kostnadsgruppstyp kallad **Direktutkontraktering** har införts, och legotillverkningstjänsterna är inte längre en del av strukturlistan (BOM) för de färdiga produkterna. När du använder lean manufacturing definieras all verksamhet av kanbans som kan vara relaterade till en eller flera produktionsflödesaktiviteter. Denna förklaring låter hittills precis som en förklaring för tillverkningsorder. Medan produktionsorder alltid måste avslutas med en färdig produkt, kan du emellertid skapa kanbans för att förse en halvfärdig produkt. Du behöver inte introducera en ny produkt eller strukturlistenivå.  

Eftersom kanban-regler kan vara mycket dynamiska, kan du utforma du olika leveransvarianter för samma produkt i ett produktionsflöde. När du använder resurssnål legotillverkning sker en strikt uppdelning av materialflödet och det ekonomiska flödet. Hela materialflödet representeras av kanban-aktiviteter. Inköpsorder för de tjänsteprodukterna och leveransbokföringarna av dessa tjänster kan utföras automatiskt, baserat på statusen för kanban-jobb i produktionsflödet. Kanban-jobb kan påbörjas och slutföras innan inköpsorderna skapas. Legotillverkningsdokument (inköpsorder och inköpsleveransen av tjänsten) kan aggregeras efter period och tjänst. Därför kan antalet inköpsdokument och rader hållas nere, till och med i mycket repetitiva åtgärder där leverantörer ger legotillverkningstjänster i ett enstycksflöde.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modellera legotillverkning i ett produktionsflöde

I ett [resurssnålt produktionsflöde](lean-manufacturing-modeling-lean-organization.md) kan en processaktivitet definieras som legotillverkning när den tilldelas en arbetsgrupp (resursgrupp) med en enda leverantörsresurs. När en arbetsgrupp tilldelas legotillverkning måste relaterade processaktiviteter kopplas till en aktiv inköpsavtalsrad som innehåller serviceartikeln och priset för tjänsten. Serviceavtalet för aktiviteten definierar också beräkningsförhållandet mellan produktkvantiteten för kanban-jobbet och resulterande tjänstekvantiteten. Du kan välja om tjänstekvantiteten ska beräknas baserat på antalet jobb, god produktkvantitet som rapporteras på jobben eller den totala produktkvantiteten (denna totala kvantitet innehåller kasserade produkter).  

Överföringsaktiviteter kan också definieras som legotillverkning. Denna definition sker implicit när du väljer den ansvariga parten för leverans i fältet för överföringsaktivitet. När du väljer **Speditör** eller **Mottagare** betraktas aktiviteten som legotillverkning om motsvarande käll- eller mållagerställe är ett lagerställe som hanteras av leverantören. När du väljer **Transportföretag** blir aktiviteten alltid legotillverkning. Precis som processaktiviteter med legotillverkning måste en överföringsaktivitet med legotillverkning kopplas till ett serviceavtal innan produktionsflödet kan aktiveras.

### <a name="backflush-costing"></a>Kostnadskalkylering med automatisk lageravräkning

Kostnadsredovisningen för legotillverkning är helt integrerad i kostnadsredovisningen för lean manufacturing-lösningen (kostnadskalkylering med automatisk lageravräkning). När du bokför inköpsorderkvittot för tjänsten, eller i samband med fakturering, tilldelas kostnaden för tjänsten till produktionsflödet. För kostnadskalkylering med automatisk lageravräkning beräknas avvikelsen för legotillverkningstjänster genom avräkning av legotillverkningsblocket av standardkostnaden för mottagna varor mot de faktiskt mottagna och fakturerade tjänstekvantiteterna.

## <a name="material-supply-for-subcontracted-operations"></a>Materialleverans för legotillverkningen
Halvfabrikat och andra relaterade material måste överföras till den plats där arbetet ska utföras fysiskt. När du använder legotillverkningsåtgärder och -verksamheter är denna överföring ofta relaterad till ytterligare transporter till leverantörsdrivna platser. Genom att tilldela material i strukturlistan till legotillverkningen deklarerar du att materialet måste mellanlagras på resursgruppens inleveransplats för den tilldelade resursen. Huvudplanering eller lean-lagerpåfyllnaden tillhandahåller sedan materialet till den platsen.  

För att modellera lagret som finns hos en leverantör är branschens bästa praxis att definiera ett lagerställe som hanteras av leverantören. Du kan enkelt definiera ett lagerställe som leverantören hanterar genom att skapa ett nytt lagerställe och tilldela leverantörskontot. Om du vill dokumentera att material måste överföras till leverantören innan en åtgärd kan utföras, ska du tilldela det leverantörshanterade lagret till lagret hos den resursgrupp som innehar resursen.  

Du kan använda flera strategier för att fylla på material på det här lagerstället:

-   Överföringsorder
-   Överför journaler
-   Uttags-kanbans
-   Direktinköp till leverantörens plats

Halvfabrikat utgör undantagen till regeln. Om du vill överföra halvfabrikat begränsas du till följande alternativ:

-   För produktions- och batchorder kan halvfärdiga produkter bara överföras logiskt med hjälp av plocklistejournalen från listsidan **Legotillverkning**. Den här journalen skapar ett följesedelsdokument som kan användas för att överföra halvfärdiga material och råmaterial till leverantören.
-   För legotillverkning i produktionsflöden dokumenteras överföringen av halvfärdiga produkter genom mottagande av uttags- eller produktionskanbans på leverantörsplatsen. Du kan avsluta en produktions-kanban med en ytterligare överföringsaktivitet för att modellera en explicit överföringsaktivitet.

**Obs!** Ett produktionsflöde för en enskild produktionsorder kan inte korsa flera platser. Denna regel gäller även legotillverkningen. Därför måste de lagerställen som representerar leverantörshanterade materialplatser definieras på samma plats som de interna resurser som används i flödet. Även om produktionsflöden kan passera flera platser, kan de inte transportera halvfärdiga produkter från en plats till en annan, detta eftersom åtgärden innebär en förändring av kostnadskontexten.  

Vanligtvis tilldelas utleveranslagerställe och platsen för en resursgrupp inom legotillverkning direkt till lagret och platsen för nästa verksamhetssteg i produktionsflödet/annat flöde. Den här inställningen hjälper till att minska mängden jobbrapportering som uppstår, eller antalet ytterligare överföringar som måste utformas.




