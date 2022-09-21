---
title: Initiera Commerce Scale Unit (moln)
description: I den här artikeln beskrivs hur du initierar Commerce Scale Unit (moln) i Microsoft Dynamics 365 Commerce.
author: jashanno
ms.date: 06/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: f9d21de3e498b293394835d5cf564899338b9c18
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474026"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Initiera Commerce Scale Unit (moln)

[!include[banner](../includes/banner.md)]

I den här artikeln beskrivs hur du initierar Commerce Scale Unit (moln) i Microsoft Dynamics 365 Commerce.

Om du använder en Nivå 2-sandbox eller produktionsmiljö som har appversion 8.1.2.x eller senare måste du initiera Commerce Scale Unit (moln) innan du kan använda butikskanalfunktioner antingen för kassaåtgärder (POS) eller för e-handelsverksamhet som använder Retail Server i molnet. Initialiseringen distribuerar en Commerce Scale Unit (moln).

> [!IMPORTANT]
> För att befintliga kunder ska kunna använda butikskanalsfunktionen i molnbaserade, för att säkerställa att supporten för din verksamhet fortsätter och avbryts, kräver vi att du uppdaterar butikskanalerna så att du använder Commerce Scale Unit. Nya miljöer som distribueras utan Commerce Scale Unit får inte längre kvalitets- och tjänsteuppdateringar för komponenter för butikskanaler som har en molnbaserad värd. Det krävs ingen åtgärd för kunder som bara använder Commerce Scale Unit (självvärdbaserad). Kontakta din Microsoft FastTrack Solution Architect om du behöver ett filnamnstillägg.

## <a name="prerequisites"></a>Förutsättningar

1. Distribuera en Nivå-2 eller produktionsmiljö som har version 8.1.2.x eller senare.
2. Du kan själv distribuera upp till 2 Commerce Scale Unit per miljö. Om du behöver fler än 2 Commerce Scale Unit per miljö i Microsoft Dynamics Lifecycle Services (LCS), skapa en supportförfrågan och ange **Begäran om ytterligare Commerce Scale Unit** och ange miljö-ID antal Commerce Scale Unit och önskade datacenterregioner. Begäran slutförs inom fem arbetsdagar. Om du inte kräver fler än 2 Commerce Scale Unit per miljö behöver du inte skapa en supportbegäran. 
3. Du måste ha behörigheten projektägare i Lifecycle Services innan du kan initiera Commerce Scale Unit.
4. Kontrollera att konfigurationsnycklarna för detaljhandelslicens är aktiverade i din miljö. För mer information, se [Rapport med licenskoder och konfigurationsnycklar](../sysadmin/license-codes-configuration-keys-report.md). Du måste ha följande nycklar aktiverad för att du ska kunna använda Commerce Scale Unit.

    - RetailBasic
    - RetaileCommerce – Om du tänker använda e-handel för Dynamics 365 Commerce.
    - RetailGiftCard – Om du tänker använda presentkort.
    - RetailInvent – Om du tänker använda lager.
    - RetailModernPos – Om du tänker använda kassan (POS).
    - RetailReplenishment – Om du planerar att använda påfyllning.
    - RetailScheduler
    - RetailStores – Om du tänker använda kassan.


## <a name="region-availability"></a>Regiontillgänglighet
Commerce Scale Unit är tillgängligt för distribution i följande regioner.

| Global plats | Region              | Tillgänglighet        | Kommentarer                  |
|-----------------|---------------------|---------------------|---------------------------|
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Östra USA             | Allmänt tillgängligt |  Inga kommentarer.                         |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Östra USA 2           | Allmänt tillgängligt |  Inga kommentarer.                          |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Norra centrala USA    | Begränsad kapacitet    |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Södra centrala USA    | Begränsad kapacitet    |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Centrala USA          | Allmänt tillgängligt |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Västra USA             | Allmänt tillgängligt |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Västra USA 2           | Allmänt tillgängligt |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Centrala Kanada      | Begränsad kapacitet    |  Inga kommentarer.                            |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | Östra Kanada         | Begränsad kapacitet    |   Inga kommentarer.                           |
| NORDAMERIKA, CENTRALAMERIKA OCH SYDAMERIKA        | USA, västra centrala     | Begränsad kapacitet    |   Inga kommentarer.                           |
| APAC            | Östra Australien      | Allmänt tillgängligt |   Inga kommentarer.                           |
| APAC            | Sydostasien      | Begränsad kapacitet | Inga distributioner tillåtna.    |
| APAC            | Östra Japan          | Allmänt tillgängligt |  Inga kommentarer.                            |
| APAC            | Västra Japan          | Allmänt tillgängligt |   Inga kommentarer.                           |
| APAC            | Sydöstra Australien | Allmänt tillgängligt |   Inga kommentarer.                           |
| APAC            | Östasien           | Begränsad kapacitet    |   Inga kommentarer.                           |
| APAC            | Indien, syd         | Begränsad kapacitet | Inga distributioner tillåtna.    |
| APAC            | Indien, centrala       | Begränsad kapacitet    | Kräver godkännandeprocess. |
| EMEA            | Västeuropa         | Allmänt tillgängligt    |  Inga kommentarer. |
| EMEA            | Nordeuropa        | Allmänt tillgängligt    |  Inga kommentarer. |
| EMEA            | Storbritannien, södra            | Allmänt tillgängligt |    Inga kommentarer.                          |
| EMEA            | Storbritannien, västra             | Allmänt tillgängligt |    Inga kommentarer.                          |
| UAE             | Förenade Arabemiraten, norra           | Begränsad kapacitet    | Kräver godkännandeprocess. |

Distributionskapaciteten i regioner med begränsad kapacitet är ytterst begränsad. Begäran om distribution utvärderas från fall till fall. Om du har ett tvingande affärsbehov av distribution i regioner med begränsad kapacitet kan du göra en supportbegäran och lägga till den i väntelistan. Kapacitetsbegränsade områden för närvarande tillåter för närvarande inte distribution av Commerce Scale Unit. 

![Mappning som visar regiontillgänglighet.](media/Commerce-Scale-Unit-Region-Availability.png "Mappning som visar regiontillgänglighet")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Initialisera Commerce Scale Unit i en ny miljödistribution

Se till att huvudkontoret är tillgängligt. Du måste registrera skalningsenheten med huvudkontoret under initieringsprocessen. Det rekommenderas inte att initiera en skalningsenhet när huvudkontoret är under service, eftersom den kan bli otillgänglig under serviceprocessen.

1. Kontrollera att huvudkontorsmiljön är tillgänglig och inte i [underhållsläge](../sysadmin/maintenance-mode.md).
2. I LCS, på sidan med miljödetaljer, välj **Miljöinformation \> Commerce**.
3. På sidan inställning av Commerce distribution, välj **Initiera**.
4. Välj vilken version av Commerce Scale Unit som ska initieras.
5. Välj en region att initiera Commerce Scale Unit i.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Konfigurera kanaler för att använda Commerce Scale Unit

När Commerce Scale Unit har distribuerats måste du se till att dina kanaler är konfigurerade att använda databasen för den. 

Konfigurera kanalerna så att de använder databasen Commerce Scale Unit genom att följa dessa steg.

1. I Commerce headquarters, gå till **Retail och Commerce \> Administrationsinställning \> Commerce-schemaläggare \> Kanaldatabas**.
1. Välj en kanaldatabas i den vänstra rutan.
1. På snabbfliken **Butikskanal**, välj **Lägg till** och välj sedan din återförsäljarkanal i listrutan.
1. Välj **Lägg till** och välj sedan din onlinekanal i listrutan. 

När du är klar, gå till **Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema** och köra jobbet 9999.

> [!NOTE] 
> Jobb 9999 synkroniserar alla nya produkter och kunder till Commerce Scale Unit. Den här processen kan ta en lång tid. Om kanalen måste vara tillgänglig bara för konfiguration av e-handel webbplatsskaparen kan du köra jobb 1070 istället för jobb 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Databasuppdatering och Commerce Scale Unit

Innan du börjar, se till att du är bekant med [Steg att slutföra efter en databasuppdatering för miljöer som använder Commerce-funktionalitet](../database/database-refresh.md).

Skalningsenhetens kanaldatabasposter (i formuläret Kanaldatabas) kan inte flyttas över miljöer som en del av databasuppdatering. Det beror på att posterna representerar miljöspecifik konfiguration.

Efter databasuppdatering kan du återskapa skalningsenhetens kanaldatabaspost genom att utfärda en ominstallation av din skalningsenhet i LCS. Alla användningar eller serviceoperationer i skalningsenheten försöker att registrera skalningsenhet med huvudkontoret, om registreringen identifieras som saknad.

Du kan distribuera om skalningsenheten utan att ändra några komponenter genom att välja att distribuera samma version som din skalningsenhet redan har. Det kan du göra i LCS genom att följa stegen nedan:

1. I LCS, på sidan med miljödetaljer, välj **Miljöinformation \> Retail**.
2. På sidan ställ in distribution väljer du den skalningsenhet du vill omdistribuera.
3. Välj på skalningsenhetens driftmeny **Uppdatera**.
4. På skjutreglaget, i listrutan för **Välj version**, välj alternativet **Ange en version**.
5. I textrutan under typen **Ange en version**, i versionen som visas för din skalningsenhet, visar bredvid etiketten **Aktuell version**.
6. Klicka på knappen **Uppdatera**.

Du behöver inte välja **Uppdateringstillägg** även om du har använt tillägg tidigare eftersom det senaste filnamnstillägget som tillämpas på skalningsenheten plockas automatiskt när du uppdaterar en skalningsenhet.

Om du har flera skalningsenheter måste du utföra operationen ovan för varje skalningsenhet. Om så önskas kan operationerna utföras parallellt.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Distribuera ytterligare Commerce Scale Unit (valfritt)

När du har initierat Commerce Scale Unit kan du själv distribuera en andra skalningsenhet om din licens ger dig rätt att göra detta. Om du vill distribuera fler än två skalningsenheter måste du skapa en supportbegäran. Ange i supportbegäran hur många Commerce Scale Unit du vill ha, miljönamn och önskade regioner. Mer information om licensiering finns i [Licensguide för Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

För varje ytterligare Commerce Scale Unit som du distribuerar rekommenderar vi att du skapar en separat kanaldatabasgrupp genom att följa stegen nedan.

1. I Commerce-huvudkontoret, gå till **Retail och Commerce > Retail Headquarters > Inställning av Butik schemaläggare > Kanaldatabasgrupp**.
2. Skapa en ny kanaldatabasgrupp.
3. Gå till **Retail och Commerce > Retail Headquarters > Inställning av Butik schemaläggare > Kanaldatabas** och välj kanaldatabasen som motsvarar den nyskapade Commerce Scale Unit.
4. Välj **Redigera** och välj den nya kanaldatabasgruppen.
5. Välj **Spara**.
6. Välj **Kör fullständig datasynkronisering** för den valda kanaldatabasen.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Ytterligare beaktanden om du initierar Commerce-kanalkomponenter med molnbaserad värd i en befintlig miljö

Om du redan använder molnbaserade Commerce-kanalkomponenter i en miljö, hjälper initiering av Commerce Scale Unit att minska stilleståndstiden när dessa komponenter uppdateras. Ytterligare planering krävs innan Commerce Scale Unit initieras.

När du initierar din första Commerce Scale Unit i en miljö som använder molnbaserade Commerce-kanalkomponenter, kommer initieringsprocessen att migrera dina kanaler som är kopplade till de molnvärdbaserade kanalkomponenterna till den första skalningsenheten. Kanaler som är kopplade till butiksskalningsenheter påverkas inte.

Migreringsprocessen är genomskinlig för kanalerna. När initieringen av skalningsenheten har startat utförs följande operationer automatiskt:

1. En ny Commerce Scale Unit skapas och associeras med miljön.
2. Commerce Scale Unit kommer att registreras som en tillgänglig kanaldatabas i huvudkontoret.
3. Alla kanaler som mappas till **standard** kanaldatabasen i huvudkontoret uppdateras så att de mappar till den nya Commerce Scale Unit.
4. En Commerce Data Exchange (CDX) fullständig datasynkronisering genomförs för att få kanaldata till den nya vågenheten.

**Planering och testning för initialisering av Commerce Scale Unit** Som en allmän regel, när du initierar Commerce Scale Unit, måste du planera för ett fem timmars stilleståndsfönster för butiksverksamheten såväl som alla e-handelskanaler som använder Retail Server eller molnbaserad kassa.

1. Uppdatera databasen från din produktionsmiljö till en UAT-miljö. 
2. Initialisera Commerce Scale Unit i UAT sandbox-miljön. 
3. Observera den starttid som ska slutföras för Commerce Scale Unit. Detta kommer att förser dig med den tid denna operation tar i din produktionsmiljö, då butiksåtgärder och e-handelsoperationer inte kommer att vara tillgängliga.

Du måste utföra följande ytterligare steg innan du initierar Commerce Scale Unit.

- **Stäng alla kassaskift** – Efter migreringen kan kassaanvändare inte stänga några skift som var aktiva under migreringsprocessen.
- **Bekräfta att alla P-jobb har slutförts framgångsrikt** – Det rekommenderas att P-jobb för att synkronisera väntande transaktioner har slutförts innan CSU initieras.
- **Logga ut från alla kassaenheter** – Kassaåtgärder stöds inte under migrering.
- **Återkalla och annullera alla uppskjutna transaktioner i kassan** – Uppskjutna transaktioner sparas inte som en del av initieringen.

> [!IMPORTANT]
> Som en del av initialiseringen av Commerce Scale Unit går tidigare uppskjutna transaktioner förlorade och kan inte återkallas. 

Följande sker under initieringsperioden:

- Molnbaserade Commerce-kanaler fungerar inte om du inte aktiverar offline-funktion för kassa.
- Kassaenheter med offlinekapaciteten aktiverad har reducerade funktioner.
- Alla e-handelsklienter som är beroende av Retail Server kommer att avbrytas.
- Kanaler som finns på enheter för Commerce Scale Unit (självvärdbaserad) påverkas inte.
- Huvudkontorets funktioner påverkas inte.

Så här sker det som sker efter att initieringen är klar:

- Enhetens aktiveringsläge för alla aktiverade kassaenheter bevaras, vilket innebär att enheterna inte behöver återaktiveras.
- Fristående maskinvaruinstanser kommer att fortsätta fungera.
- Rapporterna på kassakanalen återställs och visar inga data från före initieringen.
- Visa journaloperationen kommer också att återställas och inga data visas före initieringen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
