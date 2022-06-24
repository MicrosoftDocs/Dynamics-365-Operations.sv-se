---
title: Välja mellan Store Commerce och molnbaserad kassa
description: I denna artikel beskrivs viktiga skillnader mellan Store Commerce och Cloud POS, samt olika faktorer som återförsäljare som implementerar Dynamics 365 Commerce bör överväga i syfte att välja optimalt efter just deras behov.
author: jblucher
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 26f6e94b13b3058ac42c4c7b83dcf7179bae18e3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854016"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>Välja mellan Store Commerce och molnbaserad kassa

[!include [banner](includes/banner.md)]

I denna artikel beskrivs viktiga skillnader mellan Store Commerce och Cloud POS, samt olika faktorer som återförsäljare som implementerar Dynamics 365 Commerce bör överväga i syfte att välja optimalt efter just deras behov. Det ger implementerarna ytterligare bakgrund, tips och riktlinjer för de faktorer som bör de överväga när de distribuerar Dynamics 365 Commerce. Genom att granska och följa dessa riktlinjer som ett led i distributionsprocessen kan implementerare undvika problem som kan påverka användarnas tillfredsställelse eller prestanda.

## <a name="insights"></a>Insikter

Commerce innehåller en mängd olika alternativ för distribution och topologi. Återförsäljare kan därför välja de komponenter och den konfiguration som bäst passar deras affärsmässiga och tekniska behov. En aspekt av implementering som kräver ett noggrant övervägande är valet av plattform och formulärfaktor för butikskomponenten.

### <a name="pos-platform-and-form-factor-considerations"></a>Överväganden för butiksplattform och formulärfaktorer

Commerce har stöd för följande kassaalternativ:

- Store Commerce för Microsoft Windows
- Store Commerce för iOS och Android
- Cloud POS (CPOS), som stöder webbläsarna Microsoft Edge och Google Chrome
- Modern POS (MPOS) för Microsoft Windows (MPOS inaktiveras i oktober 2023.) 

I samtliga fall delar samma kassan (Store Commerce och CPOS) samma grundläggande programkod. Detta är viktigt av följande skäl:

- Användargränssnittet (UI) är konsekvent, oavsett plattform eller formulärfaktor.
- De flesta funktionerna är desamma, oavsett plattform eller formulärfaktor. Det finns emellertid några viktiga skillnader. Dessa skillnader anges i denna artikel.
- I varje butik kan kassavariationerna kombineras och köras samtidigt. För sina primära kassaapparater kan en återförsäljare exempelvis använda Store Commerce på datorer som kör Windows. Återförsäljaren kan emellertid komplettera dessa kassor med webbläsarbaserade terminaler eller mobila enheter.
- Anpassningar och utbyggnader kan enkelt användas på plattformar och formulärfaktorer. Eftersom den grundläggande programkoden delas kan de flesta anpassningar implementeras en gång i stället för flera gånger.

### <a name="store-commerce-vs-cpos"></a>Store Commerce jämfört med CPOS

Fastän Store Commerce och CPOS är i stort sett samma sak, finns det vissa viktiga skillnader som du behöver känna till.

#### <a name="store-commerce"></a>Store Commerce

Store Commerce är ett skrivbordsprogram som har installerats och ser beroende på en enhet.

- **Windows** – Store Commerce för Windows-app innehåller hela appkoden Commerce Runtime (CRT) och Hardware Station (HWS).
- **iOS/Android** – på dessa plattformar utgör programmet värd för CPOS-programkoden. Med andra ord aktiveras programkoden från CPOS-servern som värdbaseras på Commerce Scale Unit. Mer information finns i [Översikt av Commerce Scale Unit](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>CPOS

Eftersom CPOS körs i en webbläsare installeras inte programmet på enheten. I stället får webbläsaren åtkomst till programkoden från CPOS-servern. CPOS får därför inte direkt åtkomst till butiksmaskinvaran och kan heller inte arbeta offline.

### <a name="store-deployment-considerations"></a>Överväganden för butiksdistribution

Förutom en plattform och formulärfaktor måste detaljhandlare också välja ett distributionsalternativ för butiken. Följande tabell anger tillgängliga konfigurationer för respektive kassaalternativ.

| Kassaprogram            | Commerce Scale Unit | Tillgänglig offline | Lokalt HWS-stöd |
|----------------------------|---------------------|-------------------|-------------------|
| Store Commerce för Windows | Moln eller RSSU       | Ja               | Ja               |
| Store Commerce för Android | Moln eller RSSU       | Nej                | Ja               |
| Store Commerce för iOS     | Moln eller RSSU       | Nej                | Nej                |
| Cloud POS                  | Moln eller RSSU       | Nej                | Nej                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

Skalningsenhet för handel är en komponent som är värd för CRT. CRT ger tillgång till alla affärslogit som POS använder, och den ger åtkomst till kanalens databas. När de arbetar online används skalningsenhet för handel av alla kassaklienter i butiken. Skalningsenhet för handel kan distribueras i molnet eller i butiken.

#### <a name="offline-mode"></a>Offlineläge

Store Commerce för Windows stödjer offlineläge. I offline-läge kan POS fortsätta att bearbeta försäljning även om den kopplas bort från skalningsenhet för handel. Den kan sedan synkroniseras med kanaldatabasen när anslutningen har återställts. Store Commerce använder sin egen inbäddade instans av CRT, och använder tillfälligt sin egen lokala datakälla (SQL Server-databas som är offline). Mer information om offline-funktioner finns i [Offline-funktioner för kassa](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>Överväganden för kassakringutrustning/-maskinvara

Återförsäljare måste också ta hänsyn till hur POS får åtkomst till enheter och kringutrustning som exempelvis skrivare, kassaapparater och betalningsterminaler. Maskinvarustationer kan tilldelas ett kassaregister eller delas av kassorna i en butik.

| Kassaprogram            | Lokal HWS OPOS | Nätverkskringutrustning | Delat HWS-stöd |
|----------------------------|----------------|---------------------|--------------------|
| Store Commerce för Windows | Ja            | Ja                 | Ja                |
| Store Commerce för Android | Nej             | Ja                 | Ja                |
| Store Commerce för iOS     | Nej             | Nej                  | Ja                |
| Cloud POS                  | Nej             | Nej                  | Ja                |

Mer information om maskinvarustationer finns [Konfiguration och installation av Retail-maskinvarustationer](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>Implementeringöverväganden

Tänk på följande när du planerar kassaimplementeringen i dina butiker:

- **Funktionella krav** – Kärnprocesser och kärnfunktioner är desamma, oavsett plattforms-, formulärfaktors- eller distributionstopologi. De flesta återförsäljare behöver därför inte betänka funktionella krav när de planerar implementeringen.
- **Anslutning** – Nätverkstillgänglighet (nätverk för wide area network \[WAN\] och lokalt nätverk \[LAN\]) är en viktig faktor som kräver ett noggrant övervägande. De förmåner som en molnbaserad lösning utan utrymmeskrav ger med avseende på kostnad och enkelhet försvinner om systemet inte är tillgängligt för verksamhetskritiska processer.

    Om inte anslutningen för en viss enhet är mycket pålitlig och flexibel, eller antalet driftstopp är acceptabel för återförsäljaren, rekommenderas ett av följande alternativ:

    - Använd Store Commerce i Windows och aktivera offline-läget.
    - Distribuera en lokal skalningsenhet för handel.

    Dessa alternativ inte är ömsesidigt uteslutande. För en maximalt pålitlig topologi kan återförsäljare distribuera en lokal RSSU i syfte att minska beroendet av en internetanslutning eller Azure-tillgänglighet, och kan också distribuera kassaapparater där offline-läget aktiveras om det uppstår problem med den lokala servern eller det lokala nätverket.

- **Maskinvaruenheter/kringutrustning** – En viktig aspekt av ett Retail POS-system är möjligheten att använda kassakringutrustning som exempelvis skrivare, kassaapparater och betalningsterminaler. Även om alla tillgängliga kassalaternativ kan använda kringutrustning är det bara Store Commerce för Windows som stöder dem direkt. En eller fler maskinvarustationer krävs för alla andra program. Även om den här metoden ger ökad flexibilitet, måste ytterligare komponenter distribueras, konfigureras och underhållas.
- **Systemkrav** – Systemkraven för kassatillämpningen varierar. Ta reda på den senaste informationen innan du gör ditt val. Eftersom CPOS körs i en webbläsare stöder det till exempel fler operativsystem. Mer information om systemkraven finns [Systemkrav för molnbaserad distribution](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **Distribution och underhåll** – Distributions- och underhållskravens komplexitet kan variera beroende på program- och distributionsalternativ. För en CPOS-distribution med molnbaserad värd måste du exempelvis inte installera och uppdatera på alla enheter. Därför minskar denna metod komplexitet och kostnad avsevärt. Om du distribuerar Store Commerce på alla kassor, aktiverar offline-läget och dessutom distribuerar delade maskinvarustationer, kan du emellertid avsevärt öka antalet slutpunkter som måste hanteras.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
