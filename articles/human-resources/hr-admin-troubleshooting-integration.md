---
title: Vanliga frågeställningar integration med Finance
description: Det här artikel beskriver vilken information som synkroniseras i en Personal- och Finance-integrering.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4f57e995dfcc04de8384d15f238c45290b3c3cbd
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067629"
---
# <a name="integration-with-finance-faq"></a>Vanliga frågeställningar integrering med Finance


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Den här artikeln svarar på vanliga frågeställningar om vilken information som synkroniseras när Dynamics 365 Human Resources är integrerad med Dynamics 365 Finance.

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>Kan jag redigera Dynamics 365 Talent-programanvändaren i Power Apps?

Nej Om du redigerar Personal-programanvändaren kan det hända att integreringen mellan Personal och Dataverse misslyckas. I följande tabell visas standardinställningarna för Talang-programanvändaren.

| Fullständigt namn | Sökande-ID | Azure AD Objekt-ID | Sökande-ID URI |
| --- | --- | --- | --- |
| Dynamics 365 för Talang | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![Standardinställningar för Talent-programanvändare.](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Synkroniseras all data eller bara vissa datatabeller?

E delmängd data synkroniseras. En lista över alla enheter finns i [Integrering med Dynamics 365 Finance](hr-admin-integration-finance.md).

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>Varför visas inga data synkroniserade till Dataverse?

Som standard är Dataverse-integreringen inaktiverad i nya miljöer som inte innehåller de tillhandahållna demodata. Som standard är den aktiverad i nya miljöer där demodata ingår och datasynkroniseringen börjar när miljön etableras. När din miljö är redo att synkronisera data kan du aktivera integreringen. Mer information finns i avsnittet [Konfigurera Dataverse-integrering](hr-admin-integration-common-data-service.md).

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Kan jag skapa en ny mappning utan att använda mallarna?

Mallar är startpunkten. Du kan skapa en egen mall, men det behövs alltid en mall när du skapar ett projekt för integrering. Mer information om projekt, mallar och dataintegrering (DI) finns i [integrera data i Microsoft Dataverse](/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>Kan jag mappa ekonomiska dimensioner för överföring mellan Personal och Finance?

Ekonomiska dimensioner finns inte för närvarande i Dataverse och ingår därför inte i standardmallen. Mallen är planerad men det finns för närvarande ingen tidslinje när den släpps.

För data som finns i Finance men inte finns i Personal, länkar ihop de två systemen med hjälp av **konfigurerar länkar** i Personal.

![Mappa ekonomiska dimensioner.](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>Ibland när jag importerar anställda blir de inaktiva medarbetare i Finance. Varför?

Du får det här felet om medarbetaren inte har en aktiv informationspost i Personal. Du löser problemet genom att gå till **Personalhantering \> Medarbetare \> Anställningshistorik \> Datumhanterare** och kontrollera att det finns en aktiv informationspost för medarbetare.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Om jag väljer att endast mappa en delmängd av fält kommer ändringar som görs i ett icke-mappat fält utlösa en synkronisering?

Datasynkronisering efter körning av tidsplan. Integreringen kommer att hämta en post om ett fält i posten ändras oavsett om fältet är en del av integreringsmappningen.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Hur skickar jag endast aktiva ändringar av anställda och inte de avslutade posterna?

Med hjälp av "Avancerad fråga" kan du filtrera och omforma källdata innan du skickar den till destinationen.

![Avancerad fråga för aktiva medarbetare.](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>Kan jag ange vilka fält som ska skickas till Finance för en viss enhet?

Fält kan läggas till eller tas bort från integreringsaktiviteten. Samtliga datafält i Dataverse-registret kommer inte att fyllas i från Personal.
Ytterligare data kan fyllas i via Power Apps.

![Lägg till eller ta bort fält till och från en integreringsaktivitet.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Jag har ställt in integrering som ett batchjobb, men Personal förlorade anslutningen till destinationssystemet. Hur kan jag skicka samma uppsättning ändringar till destinationssystemet

Inga särskilda inställningar krävs för undantagshantering. Dataintegrering kommer automatiskt att fånga och rapportera fel som uppstår vid källan och målet och tillåter manuella försök. Det tillåter emellertid inte manuell datakorrigering. Om datauppdateringar krävs som ska ske antingen på källan eller destinationen.

## <a name="can-i-set-up-bi-directional-integration"></a>Kan jag ställa in dubbelriktad integrering?

Nej, integrering är för närvarande ensidig (Personal till Ekonomi och drift). Det finns en standardmall för att skicka data från Personal till Finance.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Kan jag tillåta postborttagning som en del av min integrering?

Nej, dataintegrering kommer inte att fånga borttagna poster för dataöverföring. Endast skapande av data och uppdateringar (UPSERT) ingår för närvarande.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Kan jag köra om felaktig körning? I så fall skickar den en fullständig fil eller bara ändringarna?

Den första körningen av dataintegrering är alltid en fullständig körning. Efterföljande körningar baseras på ändringsspårning. När en felkörning utförs, extraherar den posterna i körningen och skickar ut de senaste ändringarna från Dataverse.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>När jag sparar projektet visas felmeddelandet: ”projektet har mappningsfel”. Vad ska jag göra?

Kontrollera inställningarna för integreringsnycklarna, gör eventuella nödvändiga ändringar i inställningarna och uppdatera enheterna i projektet.

När du använder standardmallen importeras integreringsnycklar automatiskt. Det här problemet kan uppstå när nya uppgifter läggs till i den befintliga mallen.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Om jag har N antal juridiska personer där arbetstagarna har anställning måste jag skapa en mappning för var och en av dem?

Ja, för varje juridisk person i Finance behöver du ett separat integreringsprojekt i dataintegrering.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Behöver jag överföra data som inte ingår i standardmallen som tillhandahålls av Microsoft. Kan jag göra det?

Ja, fält kan läggas till eller tas bort från den nuvarande mallen. Mallen kan ändras så att den inkluderar ytterligare data från andra Dataverse-register. Enheten måste ha Dataverse inkluderad i mallen. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Jag skapade precis nya miljöer för Finance och Personal och jag får felet ”datavärdet strider mot integritetsbegränsningar”. Varför?

Orsaker till felet kan vara:

- Dataöverföring resulterade i dubbla extraheringar av poster vid källan (Dataverse).

- Dataöverföringen har null-värden för fält som behövs i Ekonomi och drift. Verifiera data på Dataverse som uppfyller behovet av Ekonomi och drift.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Om det finns exekveringsfel och anställningsidentifikationen inte synkroniserades, hur hittar jag det historikjobb som har misslyckad medarbetarpost?

dataintegrerare skapar flera projekt i Finance. Förhållandet mellan dataintegrerare-uppgiften och Finance-projektet är en till en.

Spåra tiden från tidigare dataintegrerare körningshistorik och letar upp index -1 projekt i Finance. Om aktivitetens nummer är 9 i dataintegrerare är index i Finance är 8.

1. Hämta uppgiftsindex från dataintegrerare (i det här exemplet ”9”).

    ![Hämta uppgiftsindex från dataintegrerare.](media/CaptureTaskIndex.png)

2. Spåra körningstiden för projektet.

    ![Spåra körningstid för projekt.](media/CaptureTimeOfExecution.png)

3. I Finance identifierar du index -1. I detta exempel matchar projektet med suffixet ”8” och körningstiden för index ”0”-projekt matchar med körningstid i steg 2.

    ![Identifiera index.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>När du har integrerat Personal och Finance visas inte mina Personal uppgifter i Finance. Vad ska jag göra?

Integrering med Finance är en tvåstegsprocess. Kontrollera först att Personal-data är uppdaterade och finns tillgänglig i Dataverse. Detta är en synkronisering nästan i realtid och kan verifieras i Power Apps genom att granska datan i dataregistren.

![Data i Dataverse.](media/DataInCDS.png)

Om data inte visas som förväntat i Dataverse, kontrollerar du att enheten stöds i integreringen. Om du vill inkludera ytterligare information i Dataverse krävs en ändring på Microsoft-sidan.

Om enheten stöds och data som finns på Dataverse, verifiera att mappningen är korrekt i dataintegrerare. Om integratormappningen ser bra ut, verifiera att datahanteringsjobb har körts. Fel kan uppstå vid körning av batch-jobb. Mer information om hur du använder datahantering finns i [Datahantering](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>Adresser för mina medarbetare är felaktiga när jag har importerat dem till Finance. Vad ska jag göra?

Nummerserien för **plats-ID** använder samma mönster i både Personal och Finance. Nummerserien måste vara unik på båda sidor så att det inte finns några adresskrockar när du integrerar data från Dataverse till Ekonomi och drift.

Under implementering av Personal, verifiera att nummerserier inte är desamma i Personal and Finance. Verifiera att alla nummerserier inte är identiska där data kan behållas i båda systemen.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>När jag skapar min anslutning visas inte anslutningen i listrutan för anslutning. Vad ska jag göra?

Se till att du väljer Dynamics 365 Finance och Dataverse när du skapar anslutningarna.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Vid synkronisering av anställningar får jag felet ”CompanyInfo_FK finns inte” eller ”värdet 12/31/2154 11:59:59 pm i fältet Slutdatum för anställning saknas i den relaterade tabellen Anställning. Vad ska jag göra?

Se till att du mappar till rätt juridiska personer. Synkronisering av juridisk person ingår inte i standardmallen, så det är normalt att varje juridisk person som finns i Personal och Dataverse även finns i Finance. Se också till att du väljer rätt juridiska personer för associerad anslutningsinställning.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>Efter installationen av mitt projekt verkar fältmappningen för Finance vara tom. Vad ska jag göra?

Uppdatera datatabellerna i Finance genom att gå till **datahantering \> ramverksparametrar \> entitetsinställningar \> uppdatera entitetslistan.** Detta tar några minuter att slutföra och sedan visas mappningarna. Problemet uppstår när nya projekt skapas.

![Fältmappning saknas.](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Ytterligare resurser

- Dataintegrerare (DI): 

  - [Integrera data i Microsoft Dataverse](/powerapps/administrator/data-integrator)

  - [dataintegrerare felhantering och felsökning](/powerapps/administrator/data-integrator-error-management)

  - [Svara på DSR-förfrågningar för systemgenererade loggar i Power Apps, Microsoft Power Automate och Dataverse](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Datahantering

  - [Datahantering](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

