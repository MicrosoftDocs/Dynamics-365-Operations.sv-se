---
title: Dynamics 365 Talent till Dynamics 365 Finance-integrering av frågor och svar
description: Det här avsnittet beskriver vilken information som synkroniseras i en Talent och Finance-integrering.
author: andreabichsel
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-12-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5bb855e6dd7ff236b7bda9e59e12ed8cc8ab9bc9
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251025"
---
# <a name="dynamics-365-talent-to-dynamics-365-finance-integration-faq"></a>Dynamics 365 Talent till Dynamics 365 Finance-integrering av frågor och svar

[!include [banner](includes/banner.md)]

Det här avsnittet svarar på vanliga frågor om vilken information som synkroniseras när Dynamics 365 Talent är integrerad med Dynamics 365 Finance.

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Synkroniseras all data eller bara vissa datatabeller?

För Core HR synkroniseras en delmängd data. En lista över alla enheter finns i [integrering från Dynamics 365 Talent till Dynamics 365 Finance](talent-financeandoperations-integration.md).

För Attract och Onboard, är all data inbyggd i Common Data Service.

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Kan jag skapa en ny mappning utan att använda mallarna?

Mallar är startpunkten. Du kan skapa en egen mall, men det behövs alltid en mall när du skapar ett projekt för integration. Mer information om projekt, mallar och dataintegration (DI) finns i [integrera data i Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-talent-and-finance"></a>Kan jag mappa ekonomiska dimensioner för överföring mellan Talent och Finance?

Ekonomiska dimensioner finns inte för närvarande i Common Data Service och ingår därför inte i standardmallen. Mallen är planerad men det finns för närvarande ingen tidslinje när den släpps.

För data som finns i Finance men inte finns i Talent, länkar ihop de två systemen med hjälp av **konfigurerar länkar** i Talent. Mer information om hur du konfigurerar länkar mellan Talent och Finance finns i [Vad är nytt eller ändrat i Dynamics 365 Talent: Core HR (31 oktober 2018)](whats-new-talent-october-31.md).

![Mappa ekonomiska dimensioner](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>Ibland när jag importerar anställda blir de inaktiva arbetare i Finance. Varför?

Du får det här felet om medarbetaren inte har en aktiv informationspost i Talent. Du löser problemet genom att gå till **Personalhantering \> Medarbetare \> Anställningshistorik \> Datumhanterare** och kontrollera att det finns en aktiv informationspost för medarbetare.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Om jag väljer att endast mappa en delmängd av fält kommer ändringar som görs i ett icke-mappat fält utlösa en synkronisering?

Datasynkronisering efter körning av tidsplan. Integreringen kommer att hämta en post om ett fält i posten ändras oavsett om fältet är en del av integreringsmappningen.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Hur skickar jag endast aktiva ändringar av anställda och inte de avslutade posterna?

Med hjälp av "Avancerad fråga" kan du filtrera och omforma källdata innan du skickar den till destinationen.

![Avancerad fråga för aktiva medarbetare](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>Kan jag ange vilka fält som ska skickas till Finance för en viss enhet?

Fält kan läggas till eller tas bort från integrationsaktiviteten. Alla fält som existerar på entiteten Common Data Service fylls i från Core HR.
Ytterligare data kan fyllas i via PowerApps.

![Lägg till eller ta bort fält till och från från integrationsaktiviteten.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-talent-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Jag har ställt in integration som ett batchjobb, men Talent förlorade anslutningen till destinationssystemet. Hur kan jag skicka samma uppsättning ändringar till destinationssystemet

Inga särskilda inställningar krävs för undantagshantering. Dataintegration kommer automatiskt att fånga och rapportera fel som uppstår vid källan och målet och tillåter manuella försök. Det tillåter emellertid inte manuell datakorrigering. Om datauppdateringar krävs som ska ske antingen på källan eller destinationen.

## <a name="can-i-set-up-bi-directional-integration"></a>Kan jag ställa in dubbelriktad integrering?

Nej, integrering är för närvarande ensidig (Talent to Finance and Operations). Det finns en standardmall för att skicka data från Talent till Finance.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Kan jag tillåta postborttagning som en del av min integration?

Nej, dataintegration kommer inte att fånga borttagna poster för dataöverföring. Endast skapande av data och uppdateringar (UPSERT) ingår för närvarande.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Kan jag köra om felaktig körning? I så fall skickar den en fullständig fil eller bara ändringarna?

Den första körningen av dataintegration är alltid en fullständig körning. Efterföljande körningar baseras på ändringsspårning. När en felkörning utförs, extraherar den posterna i körningen och skickar ut de senaste ändringarna från Common Data Service.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>När jag sparar projektet visas felmeddelandet: ”projektet har mappningsfel”. Vad ska jag göra?

Kontrollera inställningarna för integrationsnycklarna, gör eventuella nödvändiga ändringar i inställningarna och uppdatera enheterna i projektet.

När du använder standardmallen importeras integrationsnycklar automatiskt. Det här problemet kan uppstå när nya uppgifter läggs till i den befintliga mallen.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Om jag har N antal juridiska personer där arbetstagarna har anställning måste jag skapa en mappning för var och en av dem?

Ja, för varje juridisk person i Finance behöver du ett separat integrationsprojekt i dataintegration.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Behöver jag överföra data som inte ingår i standardmallen som tillhandahålls av Microsoft. Kan jag göra det?

Ja, fält kan läggas till eller tas bort från den nuvarande mallen. Mallen kan ändras så att den inkluderar ytterligare data från andra Common Data Service-entiteter. Enheten måste ha Common Data Service inkluderad i mallen. 

## <a name="i-just-created-new-finance-and-talent-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Jag skapade precis nya miljöer för Finance och Talent och jag får felet ”datavärdet strider mot integritetsbegränsningar”. Varför?

Orsaker till felet kan vara:

- Dataöverföring resulterade i dubbla extraheringar av poster vid källan (Common Data Service).

- Dataöverföringen har null-värden för fält som behövs i Finance and Operations. Verifiera data på Common Data Service som uppfyller behovet av Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Om det finns exekveringsfel och anställningsidentifikationen inte synkroniserades, hur hittar jag det historikjobb som har misslyckad medarbetarpost?

dataintegrerare skapar flera projekt i Finance. Förhållandet mellan dataintegrerare-uppgiften och Finance-projektet är en till en.

Spåra tiden från tidigare dataintegrerare körningshistorik och letar upp index -1 projekt i Finance. Om aktivitetens nummer är 9 i dataintegrerare är index i Finance är 8.

1. Hämta uppgiftsindex från dataintegrerare (i det här exemplet ”9”).

![Hämta uppgiftsindex från dataintegrerare](media/CaptureTaskIndex.png)

2. Spåra körningstiden för projektet.

![Spåra körningstiden för projektet](media/CaptureTimeOfExecution.png)

3. I Finance identifierar du index -1. I detta exempel matchar projektet med suffixet ”8” och körningstiden för index ”0”-projekt matchar med körningstid i steg 2.

![Identifiera index.](media/IdentifyIndex.png)

## <a name="after-integrating-talent-and-finance-i-dont-see-my-talent-data-in-finance-what-do-i-do"></a>När du integrerar Talent och Finance ser jag inte mina Talent-data i Finance. Vad ska jag göra?

Integrering med Finance är en tvåstegsprocess. Kontrollera först att Talent-data är uppdaterade och finns tillgänglig i Common Data Service. Detta är en synkronisering nästan i realtid och kan kontrolleras i PowerApps genom att granska data i datatabellerna.

![Data i Common Data Service](media/DataInCDS.png)

Om data inte visas som förväntat i Common Data Service, kontrollerar du att enheten stöds i integrationen. Om du vill inkludera ytterligare information i Common Data Service krävs en ändring på Microsoft-sidan.

Om enheten stöds och data som finns på Common Data Service, verifiera att mappningen är korrekt i dataintegrerare. Om integratormappningen ser bra ut, verifiera att datahanteringsjobb har körts. Fel kan uppstå vid körning av batch-jobb. Mer information om hur du använder datahantering finns i [Datahantering](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>Adresser för mina medarbetare är felaktiga när jag har importerat dem till Finance. Vad ska jag göra?

Nummerserien för **plats-ID** använder samma mönster i både Talent och Finance. Nummerserien måste vara unika på båda sidor så att det inte finns några adresskollisioner när du integrerar data från Common Data Service till Finance and Operations.

Under implementering av Talent, verifiera att nummerserier inte är desamma i Talent och Finance. Verifiera att alla nummerserier inte är identiska där data kan behållas i båda systemen.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>När jag skapar min anslutning visas inte anslutningen i listrutan för anslutning. Vad ska jag göra?

Se till att du väljer Dynamics 365 Finance och Common Data Service när du skapar anslutningarna.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Vid synkronisering av anställningar får jag felet ”CompanyInfo_FK finns inte” eller ”värdet 12/31/2154 11:59:59 pm i fältet Slutdatum för anställning saknas i den relaterade tabellen Anställning. Vad ska jag göra?

Se till att du mappar till rätt juridiska personer. Synkronisering av juridisk person ingår inte i standardmallen, så det är normalt att varje juridisk person som finns i Talent och Common Data Service även finns i Finance.
Se också till att du väljer rätt juridiska personer för associerad anslutningsinställning.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>Efter installationen av mitt projekt verkar fältmappningen för Finance vara tom. Vad ska jag göra?

Uppdatera datatabellerna i Finance genom att gå till **datahantering \> ramverksparametrar \> entitetsinställningar \> uppdatera entitetslistan.** Detta tar några minuter att slutföra och sedan visas mappningarna. Problemet uppstår när nya projekt skapas.

![Saknad fältmappning](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Ytterligare resurser

- Dataintegrerare (DI): 

  - [Integrera data i Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator)

  - [dataintegrerare felhantering och felsökning](https://docs.microsoft.com/powerapps/administrator/data-integrator-error-management)

  - [Svara på DSR-förfrågningar för systemgenererade loggar i PowerApps, Microsoft Flow och Common Data Service](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Datahantering

  - [Datahantering](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)
