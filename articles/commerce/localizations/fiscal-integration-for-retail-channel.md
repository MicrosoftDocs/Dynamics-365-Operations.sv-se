---
title: Översikt över räkenskapsintegration för handelskanaler
description: Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegration som är tillgängliga i Dynamics 365 Commerce.
author: josaw
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2019-1-16
ms.dyn365.ops.version: 10
ms.openlocfilehash: 155056eb3a2acd0d66e0ace8d5558929678cb8e3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798791"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>Översikt över räkenskapsintegration för handelskanaler

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduktion

Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegration som är tillgängliga i Dynamics 365 Commerce. Räkenskapsintegration omfattar integration med olika räkenskapsenheter och tjänster som underlättar för räkenskapsregistrering av försäljning i enlighet med lokala skattelagar som syftar till förhindrande av skattebedrägeri inom detaljhandel. Typiska scenarier som kan omfatta räkenskapsintegration är:

- Registrera en räkenskapsenhet som är ansluten till kassa (POS), till exempel en kvittoskrivare och skriva ut en kvittoskrivare för kunden.
- Skicka säkert information som är relaterad till försäljning och returer som slutförs i Retail POS till en extern webbtjänst som drivs av skattemyndigheten.
- Hjälpa till att garantera oföränderlighet av försäljningstransaktionsdata via digitala signaturer.

Räkenskapsintegreringen är ett ramverk som utgör en gemensam lösning för ytterligare utveckling och anpassning av integration mellan Retail POS och räkenskapsenheter och tjänster. Funktionen innehåller också exempel på räkenskapsintegration som stöder grundläggande scenarier för vissa länder eller regioner, och som arbetar med specifika räkenskapsenheter och tjänster. Exempel på räkenskapsintegration består av flera tillägg av Commerce-komponenter och ingår i programutvecklingskit (SDK). Mer information om exempel på räkenskapsintegration finns i [Exempel på räkenskapsintegration i Retail SDK](#fiscal-integration-samples-in-the-retail-sdk). Information om hur du installerar och använder Retail SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Stöd för andra scenarier som inte stöds av exempel på räkenskapsintegration, för att integrera Retail POS med andra räkenskapsprodukter eller tjänster och täcka kraven i andra länder eller regioner, måste du utöka ett befintligt exempel på räkenskapsintegration eller skapa ett nytt prov med ett befintligt prov som exempel.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices"></a>Process för räkenskapsregistrering och exempel på räkenskapsintegration för räkenskapsenheter

En process för räkenskapsregistrering i Retail POS kan bestå av ett eller flera steg. Varje steg omfattar räkenskapsregistrering av specifika transaktioner och händelser i en räkenskapsenhet eller tjänst. Följande komponenter ingår i räkenskapsregistrering i en räkenskapsenhet som är ansluten till en maskinvarustation:

- **Tillägget Commerce Runtime (CRT)** – den här komponenten serialiserar transaktionshändelsen/data i det format som också används i samband med räkenskapsårets analyserar svaren från räkenskapsenhet och lagrar svaren i kanaldatabasen. Tillägget definierar även specifika transaktioner och händelser som ska registreras. Den här komponenten kalla ofta en *leverantör av skattedokument*.
- **Tillägg för maskinvarustation** – denna komponent initierar kommunikationen med räkenskapsenheten, skickar begärande och kommandon direkt till räkenskapsenheten baserat på transaktionshändelse/data som extraheras från skattedokument och tar emot svar från räkenskapsenheten. Den här komponenten kalla ofta en *räkenskapskoppling*.

Ett exempel på räkenskapsintegration för räkenskapsenheter innehåller respektive tillägg för CRT och maskinvarustation för en leverantör av skattedokument och en räkenskapskoppling Den innehåller även följande komponentkonfigurationer:

- **Konfiguration av leverantör av skattedokument** – den här konfigurationen definierar en utmatningsmetod och ett format för skattedokument. Den innehåller även en datamappning för skatter och betalsätt som gör data från Retail POS kompatibel med de värden som ska fördefinieras i räkenskapsenhetens inbyggda programvara.
- **Konfiguration av räkenskapskopplare** – definierar den fysiska kommunikationen med räkenskapsenheten.

En process för räkenskapsregistrering för ett visst kassaregister definieras av en motsvarande inställning i kassans funktionsprofil. Mer information om hur du konfigurerar processen för räkenskapsregistrering, laddar upp konfiguration av leverantör av skattedokument och räkenskapskopplare och ändra deras parametrar finns i [skapa en process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

I följande exempel visas en typisk flöde för räkenskapsregistreringskörning för räkenskapsenheter. Flödet börjar med en händelse i POS (exempelvis slutförandet av en försäljningstransaktion) och implementerar följande sekvens med steg:

1. POS begär ett skattedokumentet från CRT.
2. CRT avgör om händelsen kräver räkenskapsregistrering.
3. Baserat på processen för räkenskapsregistrering identifierar CRT en skattekoppling och motsvarande leverantör av skattedokument för räkenskapsregistreringen.
4. CRT kör leverantören av skattedokument som genererar skattedokument (till exempel ett XML-dokument) som motsvarar transaktionen eller händelse.
5. POS skickar skattedokumentet som CRT förbereder till en maskinvarustation.
6. Maskinvarustationen kör räkenskapskopplingen som bearbetar skattedokumentet och vidarebefordrar informationen till räkenskapsenheten eller tjänsten.
7. POS analyserar svaret från räkenskapsenheten eller tjänsten för att avgöra om räkenskapsregistreringen har lyckats.
8. CRT sparar svaret i kanaldatabasen.

![Lösningsschema](media/emea-fiscal-integration-solution.png "Lösningsschema")

## <a name="error-handling"></a>Felhantering

Ramverket för räkenskapsintegration ger följande alternativ för att hantera misslyckanden under räkenskapsregistreringen:

- **Försök igen** – Operatörer kan använda det här alternativet när felet kan lösas snabbt och räkenskapsregistreringen kan köras igen. Det här alternativet kan till exempel användas när räkenskapsenheten inte är ansluten, kvittoskrivaren har slut på papper eller så finns det ett papper har fastnat i kvittoskrivaren.
- **Avbryt** – inställningen låter operatörer senarelägga räkenskapsregistreringen av den aktuella transaktionen eller händelsen om det uppstår ett fel. När registreringen senareläggs kan operatören fortsätta att arbeta med POS kan utföra alla åtgärder som räkenskapsregistrering inte är obligatoriskt för När en händelse som kräver räkenskapsregistrering sker i POS (till exempel en ny transaktion öppnas), kommer dialogrutan för felhantering automatisk att visas för att meddela operatören att föregående transaktion inte registrerades korrekt och att ge alternativ för felhantering.
- **Hoppa över** – operatörer kan använda det här alternativet när räkenskapsregistreringen kan utelämnas, under vissa förhållanden och vanliga operationer kan fortsätta i POS. Det här alternativet kan exempelvis användas när en försäljningstransaktion som räkenskapsregistreringen misslyckades för kan registreras i en speciell pappersjournal.
- **Markera som registrerad** – operatörer kan använda detta alternativ när transaktionen faktiskt registrerades i räkenskapsenhet (exempelvis ett skattekvitto skrevs ut), men ett fel uppstod vid räkenskapssvaret sparades i kanaldatabasen.

> [!NOTE]
> Alternativen **Hoppa över** och **Markera som registrerad** måste vara aktiverade på processen för räkenskapsregistrering innan de används. Dessutom måste motsvarande behörigheter tilldelas operatörer.

Alternativen **Hoppa över** och **Markera som registrerade** tillåter informationskoder att samla in viss information om felet, till exempel orsaken till felet eller en justering för att hoppa över räkenskapsregistreringen eller märka transaktionen som registrerad. Mer information om hur du ställer in parametrar för felhantering finns i [ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Valfri skatteregistrering

Räkenskapsregistrering kan vara obligatorisk för vissa åtgärder och valfri för andra. Exempelvis kan räkenskapsregistrering av vanlig försäljning och returer kan vara obligatorisk men räkenskapsregistrering av åtgärder som är relaterade till kundinsättningar kan vara valfria. I detta fall blockerar misslyckande att slutföra räkenskapsregistreringen av en försäljning ytterligare försäljning, men misslyckande att slutföra räkenskapsregistreringen av en kundinsättning bör inte blockera ytterligare försäljning. Om du vill skilja mellan obligatoriska och frivilliga åtgärder, rekommenderas det att du hanterar dem via olika dokumentleverantörer och att du ställer in separata steg i räkenskapsregistreringsprocessen för leverantörerna. Parametern **Fortsätt vid fel** ska aktiveras för varje steg som hör till valfri räkenskapsregistrering. Mer information om hur du ställer in parametrar för felhantering finns i [ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-running-fiscal-registration"></a>Manuellt köra räkenskapsregistrering

Om räkenskapsregistrering av transaktioner eller händelser har skjutits upp efter ett fel (till exempel om operatören valde **Avbryt** i dialogrutan för felhantering), kan du manuellt köra räkenskapsregistreringen genom att åberopa en motsvarande åtgärd. För mer information, se [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

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
- Status för räkenskapsregistreringen: **slutförd** för att registreringen har lyckats, **överhoppad** om operatören har valt alternativet **hoppa över** för en misslyckad registrering eller **markera som registrerad** om operatören har valt alternativ **Markera som registrerad**.
- Informationskodtransaktioner som är relaterade till den valda skattetransaktionen. Visa informationskodtransaktionerna, på snabbfliken **räkenskapstransaktioner** väljer du en räkenskapstransaktion som har statusen **överhoppad** eller **markeras som registrerats** och väljer sedan **informationskodtransaktioner**.

## <a name="fiscal-texts-for-discounts"></a>Räkenskapstexter för rabatter

Vissa länder eller regioner har särskilda önskemål om ytterligare texter som måste skrivas ut på skattekvitton när olika sorters rabatter tillämpas. Räkenskapsintegration kan du ställa in en särskild text för en rabatt som skrivs ut efter en rabattrad på en kvittoskrivare. För manuella rabatter kan du konfigurera en räkenskapstext för den informationskod som anges som **produktrabatt**-informationskod i funktionsprofil för kassa. För mer information om hur man sätter upp räkenskapstexter för rabatter, se [skriva in räkenskapstexter för rabatter](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Skriva ut skatterapporter X och Z

Funktionen räkenskapsintegration stöder generering av rapporter vid dagens slut som är specifika för integrerad räkenskapsenhet eller tjänst:

- Nya knappar som kör motsvarande operationer ska läggas till kassaskärmlayout. Mer information finns i [skapa skatterapporter X/Z från POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- I exemplet på räkenskapsintegration bör dessa transaktioner anpassas till motsvarande verksamhet i räkenskapsenheten.

## <a name="fiscal-integration-samples-in-the-retail-sdk"></a>Exempel på räkenskapsintegration i Retail SDK

Följande exempel på räkenskapsintegration är tillgängliga i Retail SDK:

- [Exempel på integrering av kvittoskrivare för Italien](emea-ita-fpi-sample.md)
- [Exempel på integrering av kvittoskrivare för Polen](emea-pol-fpi-sample.md)
- [Exempel på skatteregistreringstjänsten för Österrike](emea-aut-fi-sample.md)
- [Exempel på skatteregistreringstjänsten för Tjeckien](emea-cze-fi-sample.md)
- [Exempel på integration av kontrollenhet för Sverige](./emea-swe-fi-sample.md)
- [Exempel på skatteregistreringstjänsten för Tyskland](./emea-deu-fi-sample.md)

Följande funktioner för räkenskapsintegration finns också i Retail SDK men för närvarande utnyttjar inte i ramverket för räkenskapsintegration. Migrering av den här funktionen till ramverket för räkenskapsintegration planeras för senare uppdateringar.


- [Digital signatur i Frankrike](emea-fra-cash-registers.md)
- [Digital signatur för Norge](emea-nor-cash-registers.md)

Följande tidigare funktioner för räkenskapsintegrering som är tillgängliga i Retail SDK använder inte ramverket för räkenskapsintegration och kommer att föråldras i senare uppdateringar:

- [Exempel på integration av kontrollenhet för Sverige (äldre)](./retail-sdk-control-unit-sample.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]