---
title: Översikt över räkenskapsintegrering för Commerce-kanaler
description: Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegrering som är tillgängliga i Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 00c68155088ff2aabbe2fe0c4f431b665aebcd0a
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462533"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Översikt över räkenskapsintegrering för Commerce-kanaler

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegrering som är tillgängliga i Dynamics 365 Commerce. 

Räkenskapsintegrering omfattar integrering med olika räkenskapsenheter och tjänster som underlättar för räkenskapsregistrering av försäljning i enlighet med lokala skattelagar som syftar till förhindrande av skattebedrägeri inom detaljhandel. Typiska scenarier som kan omfatta räkenskapsintegrering är:

- Registrera en räkenskapsenhet som är ansluten till kassa (POS), till exempel en kvittoskrivare och skriva ut en kvittoskrivare för kunden.
- Skicka säkert information som är relaterad till försäljning och returer som slutförs i Retail POS till en extern webbtjänst som drivs av skattemyndigheten.
- Hjälp till att garantera oföränderlighet för försäljningstransaktionsdata genom digitala signaturer.

Räkenskapsintegreringen är ett ramverk som utgör en gemensam lösning för ytterligare utveckling och anpassning av integrering mellan Retail POS och räkenskapsenheter och tjänster. Funktionen innehåller också exempel på räkenskapsintegrering som stöder grundläggande scenarier för vissa länder eller regioner, och som arbetar med specifika räkenskapsenheter och tjänster. Exempel på räkenskapsintegrering består av flera tillägg av Commerce-komponenter och ingår i programutvecklingskit (SDK). Mer information om exemplen på räkenskapsintegrering finns i [Exempel på räkenskapsintegrering i Commerce SDK](#fiscal-integration-samples-in-the-commerce-sdk). Information om hur du installerar och använder Commerce SDK finns i [Arkitektur i utvecklingspaket (SDK) för programutveckling](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Stöd för andra scenarier som inte stöds av exempel på räkenskapsintegrering, för att integrera Retail POS med andra räkenskapsprodukter eller tjänster och täcka kraven i andra länder eller regioner, måste du utöka ett befintligt exempel på räkenskapsintegrering eller skapa ett nytt prov med ett befintligt prov som exempel.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Process för räkenskapsregistrering och exempel på räkenskapsintegrering och tjänster

En process för räkenskapsregistrering i Retail POS kan bestå av ett eller flera steg. Varje steg omfattar räkenskapsregistrering av specifika transaktioner och händelser i en räkenskapsenhet eller tjänst. Följande komponenter ingår i räkenskapsregistrering i en räkenskapsenhet eller tjänst:

- **Räkenskapsdokumentleverantör** – Den här komponenten serialiserar transaktionshändelsen/data i det format som också används i samband med räkenskapsårets analyserar svaren från räkenskapsenhet eller tjänst och lagrar svaren i kanaldatabasen. Tillägget definierar även specifika transaktioner och händelser som ska registreras.
- **Räkenskapskoppling** – denna komponent initierar kommunikationen med räkenskapsenheten eller tjänsten, skickar begärande och kommandon direkt till räkenskapsenheten eller tjänsten baserat på transaktionshändelse/data som extraheras från skattedokument och tar emot svar från räkenskapsenheten eller tjänsten

Ett exempel på räkenskapsintegrering kan innehålla Commerce Runtime (CRT), Hardware station och kassatillägg för en finansiell dokumentleverantör och en finansiell anslutning. Den innehåller även följande komponentkonfigurationer:

- **Konfiguration av leverantör av skattedokument** – den här konfigurationen definierar en utmatningsmetod och ett format för skattedokument. Den innehåller även en datamappning för skatter och betalsätt som gör data från Retail POS kompatibel med de värden som ska fördefinieras i räkenskapsenhetens eller tjänst inbyggda programvara.
- **Konfiguration av räkenskapskopplare** – definierar den fysiska kommunikationen med räkenskapsenheten eller tjänsten.

En process för räkenskapsregistrering för en viss kassaapparat definieras av en motsvarande inställning i kassans funktionsprofil. Mer information om hur du konfigurerar processen för räkenskapsregistrering, laddar upp konfiguration av leverantör av skattedokument och räkenskapskopplare och ändra konfigurationsparametrar finns i [skapa en process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Om du behöver enheter för icke-skattemässiga åtgärder, till exempel sökning i produktkatalog, kundsökning eller skapande av transaktionsutkast, kan du välja dessa som register med skatteprocessrestriktioner. Mer information finns i [Ställa in register med skatteregistreringsrestriktioner](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

Följande typiska flöde för räkenskapsregistrering startar med en händelse i kassan (t.ex. slutförande av en försäljningstransaktion) och implementerar en fördefinierad sekvens med steg som omfattar andra Commerce-komponenter (till exempel CRT och maskinvarustationen ).

1. Kassan begär ett skattedokument från ramverket för räkenskapsintegrering (FIF).
1. FIF avgör om händelsen kräver räkenskapsregistrering.
1. Baserat på processen för räkenskapsregistrering identifierar FIF en skattekoppling och motsvarande leverantör av skattedokument för räkenskapsregistreringen.
1. FIF kör providern av skattedokument som genererar skattedokument (till exempel ett XML-dokument) som motsvarar transaktionen eller händelse.
1. FIF returnerar det genererade skattedokumentet till kassan.
1. Kassan begär att FIF ska skicka skattedokumentet till räkenskapsenheten eller tjänsten.
1. FIF kör räkenskapskopplingen som bearbetar skattedokumentet och skickar den till räkenskapsenheten eller tjänsten.
1. FIF returnerar räkenskapssvaret (d.v.s. svaret från räkenskapsenheten eller tjänsten) till kassan.
1. Kassan analyserar skattesvaret för att avgöra om skatteregistreringen lyckades. Kassan kräver att FIF ska hantera eventuella fel. 
1. Kassan begär att FIF-processen ska bearbetas och räkenskapssvaret sparas.
1. Leverantören för skattedokument bearbetar räkenskapssvaret. Under den här bearbetningen hämtar räkenskapsdokumentprovidern svaret och hämtar utökade data från den.
1. FIF sparar svaret och de utökade data till kanaldatabasen.
1. Vid behov skriver kassan ut ett kvitto via en vanlig kvittoskrivare som är kopplad till Maskinvarustation. Inleveransen kan innehålla obligatoriska data från räkenskapssvaret.
 
I följande exempel visas ett flöde för räkenskapsregistreringskörning för vanliga räkenskapsenheter eller tjänster.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>Skatteregistrering utförs via en enhet som är ansluten till maskinvarustationen

Den här konfigurationen används när en fysisk räkenskapsenhet, till exempel en kvittoskrivare, är ansluten till maskinvarustationen. Den gäller även när kommunikationen med en räkenskapsenhet eller tjänst sker via programvara som är installerad på maskinvarustation. I det här fallet finns providern av skattedokument på och CRT, kvittoskrivaren finns på maskinvarustationen.

![Skatteregistrering utförs via en enhet som är ansluten till maskinvarustationen.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>Skatteregistrering utförs via en extern tjänst

Denna konfiguration används när räkenskapsregistreringen utförs via en extern tjänst, t.ex. en webbtjänst som skattemyndigheten förser med. II det här fallet finns både providern av skattedokument och skatteanslutningen på CRT.

![Skatteregistrering utförs via en extern tjänst.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>Skatteregistreringen görs internt i CRT

Den här konfigurationen används när det inte krävs någon extern räkenskapsenhet eller tjänst för skatteregistrering. Den används till exempel när skatteregistrering görs genom digital signering av försäljningstransaktioner. II det här fallet finns både providern av skattedokument och skatteanslutningen på CRT.

![Skatteregistreringen görs internt i CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>Skatteregistrering utförs via en enhet eller tjänst i det lokala nätverket

Denna konfiguration används när en fysisk skatteanordning eller skattetjänst finns i butikens lokala nätverk och tillhandahåller ett HTTPS-approgrammeringsgränssnitt (API). I det här fallet finns providern av skattedokument på och CRT, kvittoskrivaren finns i kassan.

![Skatteregistrering utförs via en enhet eller tjänst i det lokala nätverket.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Felhantering

Ramverket för räkenskapsintegrering ger följande alternativ för att hantera misslyckanden under räkenskapsregistreringen:

- **Försök igen** – Operatörer kan använda det här alternativet när felet kan lösas snabbt och räkenskapsregistreringen kan köras igen. Det här alternativet kan till exempel användas när räkenskapsenheten inte är ansluten, kvittoskrivaren har slut på papper eller så finns det ett papper har fastnat i kvittoskrivaren.
- **Avbryt** – inställningen låter operatörer senarelägga räkenskapsregistreringen av den aktuella transaktionen eller händelsen om det uppstår ett fel. När registreringen senareläggs kan operatören fortsätta att arbeta med POS kan utföra alla åtgärder som räkenskapsregistrering inte är obligatoriskt för När en händelse som kräver räkenskapsregistrering sker i POS (till exempel en ny transaktion öppnas), kommer dialogrutan för felhantering automatisk att visas för att meddela operatören att föregående transaktion inte registrerades korrekt och att ge alternativ för felhantering.
- **Hoppa över** – operatörer kan använda det här alternativet när räkenskapsregistreringen kan utelämnas, under vissa förhållanden och vanliga operationer kan fortsätta i POS. Det här alternativet kan exempelvis användas när en försäljningstransaktion som räkenskapsregistreringen misslyckades för kan registreras i en speciell pappersjournal.
- **Markera som registrerad** – operatörer kan använda detta alternativ när transaktionen faktiskt registrerades i räkenskapsenhet (exempelvis ett skattekvitto skrevs ut), men ett fel uppstod vid räkenskapssvaret sparades i kanaldatabasen.
- **Senarelägg** – Operatörer kan använda det här alternativet när transaktionen inte registreras eftersom registreringstjänsten inte var tillgänglig. 

> [!NOTE]
> Alternativen **Hoppa över**, **Markera som registrerad** och **Senarelägg** som registrerad måste vara aktiverade på processen för räkenskapsregistrering innan de används. Dessutom måste motsvarande behörigheter tilldelas operatörer.

Alternativen **Hoppa över**, **Markera som registrerad** och **Senarelägg** tillåter informationskoder att samla in viss information om felet, till exempel orsaken till felet eller en justering för att hoppa över räkenskapsregistreringen eller märka transaktionen som registrerad. Mer information om hur du ställer in parametrar för felhantering finns i [ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Valfri skatteregistrering

Räkenskapsregistrering kan vara obligatorisk för vissa åtgärder och valfri för andra. Exempelvis kan räkenskapsregistrering av vanlig försäljning och returer kan vara obligatorisk men räkenskapsregistrering av åtgärder som är relaterade till kundinsättningar kan vara valfria. I detta fall blockerar misslyckande att slutföra räkenskapsregistreringen av en försäljning ytterligare försäljning, men misslyckande att slutföra räkenskapsregistreringen av en kundinsättning bör inte blockera ytterligare försäljning. Om du vill skilja mellan obligatoriska och frivilliga åtgärder, rekommenderas det att du hanterar dem via olika dokumentleverantörer och att du ställer in separata steg i räkenskapsregistreringsprocessen för leverantörerna. Parametern **Fortsätt vid fel** ska aktiveras för varje steg som hör till valfri räkenskapsregistrering. Mer information om hur du ställer in parametrar för felhantering finns i [ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Manuellt köra räkenskapsregistrering igen

Om räkenskapsregistrering av transaktioner eller händelser har skjutits upp efter ett fel (till exempel om operatören valde **Avbryt** i dialogrutan för felhantering), kan du manuellt köra räkenskapsregistreringen genom att åberopa en motsvarande åtgärd. För mer information, se [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="postpone-option"></a>Senarelägg alternativ

Med alternativet **Senarelägg** kan du fortsätta räkenskapsregistreringsprocessen om det aktuella steget misslyckas. Det kan användas när det finns ett alternativ för säkerhetskopiering av skatteregistrering.

### <a name="fiscal-registration-health-check"></a>Hälsokontroll av räkenskapsregistrering

Hälsokontrollproceduren för räkenskapsregistreringar kontrollerar tillgängligheten för räkenskapsenheten eller tjänsten när specifika händelser inträffar. Om räkenskapsregistreringen för tillfället inte kan slutföras meddelas operatorn i förväg.

POS kör hälsokontrollen när följande händelser inträffar:

- En ny transaktion öppnas.
- En uppskjuten transaktion återkallas.
- En försäljnings- eller returtransaktion slutförs.

Om hälsokontrollen misslyckas visar POS dialogrutan för hälsokontroll. Den här dialogrutan innehåller följande knappar:

- **OK** – med den här knappen kan operatorn ignorera ett hälsokontrollfel och fortsätta att utföra åtgärden. Operatörer kan välja den här knappen om behörigheten **Tillåt hoppa över hälsofel** är aktiverad för dem.
- **Avbryt** – om operatören väljer denna knapp, avbryter POS den senaste åtgärden (till exempel en artikel läggs inte till en ny transaktion).

> [!NOTE]
> Hälsokontrollen körs endast om den aktuella åtgärden kräver räkenskapsregistrering och om parametern **Fortsätt vid fel** inaktiveras för det aktuella steget av räkenskapsregistreringsprocessen. Mer information finns i [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Lagra räkenskapssvar i räkenskapstransaktion

Vid räkenskapsregistrering av transaktioner eller händelser lyckas, skapas en räkenskapstransaktion i kanaldatabasen och kopplas till den ursprungliga transaktionen eller händelsen. På samma sätt om alternativet **Hoppa över** eller **Markera som registrerad** väljs för en misslyckad räkenskapsregistrering, lagras informationen i en räkenskapstransaktion. En räkenskapstransaktion innehåller räkenskapssvar för räkenskapsenheten eller tjänsten. Om processen för räkenskapsregistrering består av flera steg, skapas en räkenskapstransaktion för varje steg i processen som resulterade i en lyckad eller misslyckad registrering.

Räkenskapstransaktioner överförs till Administration av *P-jobb* tillsammans med transaktioner. På snabbfliken **räkenskapstransaktioner** på sidan **transaktioner** kan du visa de räkenskapstransaktioner som är kopplade till transaktioner.

En räkenskapstransaktion innehåller följande information:

- Information om processen för räkenskapsregistrering (process, kopplingsgrupp, koppling och så vidare). Serienumret för räkenskapsenheten sparas också i fältet **registreringsnummer** om informationen ingår i räkenskapssvaret.
- Status för räkenskapsregistreringen: **slutförd** för att registreringen har lyckats, **överhoppad** om operatören har valt alternativet **Hoppa över** för en misslyckad registrering eller, **Markerad som registrerad** om operatören har valt alternativet **Markerad som registrerad** eller **senarelagd** om operatören valde alternativet **Senarelägga**.
- Informationskodtransaktioner som är relaterade till den valda skattetransaktionen. Visa informationskodtransaktionerna, på snabbfliken **räkenskapstransaktioner** väljer du en räkenskapstransaktion som har statusen **överhoppad** eller **markeras som registrerats** eller **senarelagd** och väljer sedan **informationskodtransaktioner**.

Genom att välja **Utökade data** kan du även visa egenskaperna för räkenskapstransaktionen. Listan över egenskaper som kan visas är specifik för den funktion för räkenskapsregistrering som genererat räkenskapstransaktionen. Du kan till exempel visa digital signatur, serienummer, certifikatets tumavtryck och andra skattetransaktionsegenskaper för den digitala signeringsfunktionen för Frankrike.

## <a name="fiscal-texts-for-discounts"></a>Räkenskapstexter för rabatter

Vissa länder eller regioner har särskilda önskemål om ytterligare texter som måste skrivas ut på skattekvitton när olika sorters rabatter tillämpas. Räkenskapsintegrering kan du ställa in en särskild text för en rabatt som skrivs ut efter en rabattrad på en kvittoskrivare. För manuella rabatter kan du konfigurera en räkenskapstext för den informationskod som anges som **produktrabatt**-informationskod i funktionsprofil för kassa. För mer information om hur man sätter upp räkenskapstexter för rabatter, se [skriva in räkenskapstexter för rabatter](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Skriva ut skatterapporter X och Z

Funktionen räkenskapsintegrering stöder generering av rapporter vid dagens slut som är specifika för integrerad räkenskapsenhet eller tjänst:

- Nya knappar som kör motsvarande operationer ska läggas till kassaskärmlayout. Mer information finns i [skapa skatterapporter X/Z från POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- I exemplet på räkenskapsintegrering bör dessa transaktioner anpassas till motsvarande verksamhet i räkenskapsenheten.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Exempel på räkenskapsintegrering i Commercer SDK

Följande exempel på räkenskapsintegrering är för tillfället tillgängliga i Commerce SDK:

- [Exempel på integrering av kvittoskrivare för Italien](./emea-ita-fpi-sample.md)
- [Exempel på integrering av kvittoskrivare för Polen](./emea-pol-fpi-sample.md)
- [Exempel på skatteregistreringstjänsten för Österrike](./emea-aut-fi-sample.md)
- [Exempel på skatteregistreringstjänsten för Tjeckien](./emea-cze-fi-sample.md)
- [Exempel på integrering av kontrollenhet för Sverige](./emea-swe-fi-sample.md)
- [Exempel på skatteregistreringstjänsten för Tyskland](./emea-deu-fi-sample.md)
- [Exempel på integrering av kvittoskrivare för Ryssland](./rus-fpi-sample.md)

Följande skatteintegreringsfunktion har också implementerats med hjälp av ramverket för skatteintegrering, men är tillgängligt vid leverans och ingår inte i Commerce SDK:

- [Skatteregistrering för Brasilien](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Digital signatur i Frankrike](./emea-fra-cash-registers.md)

Följande funktion för räkenskapsintegrering finns också i Commerce SDK, men för närvarande utnyttjar den inte i ramverket för räkenskapsintegrering. Migrering av den här funktionen till ramverket för räkenskapsintegrering planeras för senare uppdateringar.

- [Digital signatur för Norge](./emea-nor-cash-registers.md)

Följande äldre funktioner för räkenskapsintegrering som är tillgängliga i Commerce SDK använder inte ramverket för räkenskapsintegrering och kommer att göras inaktuella i senare uppdateringar:

- [Exempel på integrering av kontrollenhet för Sverige (äldre)](./retail-sdk-control-unit-sample.md)
- [Digital signatur i Frankrike (äldre)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
