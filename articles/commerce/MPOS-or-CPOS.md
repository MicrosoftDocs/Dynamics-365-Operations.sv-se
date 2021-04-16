---
title: Välj mellan Modern POS (MPOS) och Cloud POS
description: Det här avsnittet beskriver viktiga skillnader mellan Modern POS och Cloud POS. Här beskrivs också olika faktorer som återförsäljare som implementerar Dynamics 365 Commerce bör överväga i syfte att hjälpa dem göra det bästa valet för just deras behov.
author: jblucher
ms.date: 10/13/2017
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
ms.openlocfilehash: 84ee7c82fa6aaa819798f4bc052b12b06a51c025
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796520"
---
# <a name="choose-between-modern-pos-mpos-and-cloud-pos"></a>Välj mellan Modern POS (MPOS) och Cloud POS

[!include [banner](includes/banner.md)]

Detta avsnitt ger implementerarna ytterligare bakgrund, tips och riktlinjer för de faktorer som bör de överväga när de distribuerar Dynamics 365 Commerce. Genom att granska och följa dessa riktlinjer som ett led i distributionsprocessen kan implementerare undvika problem som kan påverka användarnas tillfredsställelse eller prestanda.

## <a name="insights"></a>Insikter

Commerce innehåller en mängd olika alternativ för distribution och topologi. Återförsäljare kan därför välja de komponenter och den konfiguration som bäst passar deras affärsmässiga och tekniska behov. En aspekt av implementering som kräver ett noggrant övervägande är valet av plattform och formulärfaktor för butikskomponenten.

### <a name="pos-platform-and-form-factor-considerations"></a>Överväganden för butiksplattform och formulärfaktorer

Commerce har stöd för följande kassaalternativ:

- Modern POS (MPOS) för Microsoft Windows
- MPOS för Microsoft Windows Phone
- MPOS för Apple iPad eller Google Android-surfplatta
- Cloud POS (CPOS), som stöder webbläsarna Microsoft Edge, Internet Explorer, och Google Chrome

I samtliga fall delar samma lassan (MPOS och CPOS) samma grundläggande programkod. Detta är viktigt av följande skäl:

- Användargränssnittet (UI) är konsekvent, oavsett plattform eller formulärfaktor.
- De flesta funktionerna är desamma, oavsett plattform eller formulärfaktor. Det finns emellertid några viktiga skillnader. Dessa skillnader anges i det här avsnittet.
- I en butik kan kassavariationerna kombineras och köras samtidigt. För sina primära kassaapparater kan en återförsäljare exempelvis använda MPOS på datorer som kör Windows. Återförsäljaren kan emellertid komplettera dessa kassor med webbläsarbaserade terminaler eller mobila enheter.
- Anpassningar och utbyggnader kan enkelt användas på plattformar och formulärfaktorer. Eftersom den grundläggande programkoden delas kan de flesta anpassningar implementeras en gång i stället för flera gånger.

### <a name="mpos-vs-cpos"></a>MPOS kontra CPOS

Fastän MPOS och CPOS är i stort sett samma sak, finns det vissa viktiga skillnader som du behöver känna till.

#### <a name="mpos"></a>MPOS

MPOS på en Windows-, iOS- eller Android-enhet är ett program som paketeras, installeras och underhålls på enheten.

- **Windows** – MPOS-programmet för Windows all programkod och inbäddat Commerce Runtime (CRT). 
- **iOS/Android** – på dessa plattformar utgör programmet värd för CPOS-programkoden. Med andra ord aktiveras programkoden från CPOS-servern på Microsoft Azure eller från skalningsenhet för handel. Mer information finns i [Översikt av Commerce Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Eftersom CPOS körs i en webbläsare installeras inte programmet på enheten. I stället får webbläsaren åtkomst till programkoden från CPOS-servern. CPOS får därför inte direkt åtkomst till butiksmaskinvaran och kan heller inte arbeta offline.

### <a name="store-deployment-considerations"></a>Överväganden för butiksdistribution

Förutom en plattform och formulärfaktor måste detaljhandlare också välja ett distributionsalternativ för butiken. Följande tabell anger tillgängliga konfigurationer för respektive kassaalternativ.

| Kassaprogram         | Skalningsenhet för handel | Tillgänglig offline |
|-------------------------|---------------|-------------------|
| MPOS för Windows        | Moln eller RSSU | Ja               |
| MPOS för iOS eller Android | Moln eller RSSU | Nej                |
| Cloud POS               | Moln eller RSSU | Nej                |

#### <a name="commerce-scale-unit"></a>Skalningsenhet för handel

Skalningsenhet för handel är en komponent som är värd för CRT. CRT ger tillgång till alla affärslogit som POS använder, och den ger åtkomst till kanalens databas. När de arbetar online används skalningsenhet för handel av alla kassaklienter i butiken. Skalningsenhet för handel kan distribueras i molnet eller i butiken.

#### <a name="offline-mode"></a>Offlineläge

MPOS för Windows stöder offline-läge. I offline-läge kan POS fortsätta att bearbeta försäljning även om den kopplas bort från skalningsenhet för handel. Den kan sedan synkroniseras med kanaldatabasen när anslutningen har återställts. MPOS använder sin egen inbäddade instans av CRT, och använder tillfälligt sin egen lokala datakälla (SQL Server-databas som är offline). Mer information om offline-funktioner finns i [Offline-funktioner för kassa](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Överväganden för kassakringutrustning/-maskinvara

Återförsäljare måste också ta hänsyn till hur POS får åtkomst till enheter och kringutrustning som exempelvis skrivare, kassaapparater och betalningsterminaler. Endast MPOS för Windows stöder direkt kommunikation med dessa enheter. MPOS för Windows Phone iOS eller Android, samt molnbaserad kassa kräver en maskinvarustation för att komma åt dessa enheter. Maskinvarustationer kan tilldelas ett kassaregister eller delas av kassorna i en butik. Mer information om maskinvarustationer finns [Konfiguration och installation av Retail-maskinvarustationer](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Implementeringöverväganden

Tänk på följande när du planerar kassaimplementeringen i dina butiker:

- **Funktionella krav** – Kärnprocesser och kärnfunktioner är desamma, oavsett plattforms-, formulärfaktors- eller distributionstopologi. De flesta återförsäljare behöver därför inte betänka funktionella krav när de planerar implementeringen.
- **Anslutning** – Nätverkstillgänglighet (nätverk för wide area network \[WAN\] och lokalt nätverk \[LAN\]) är en viktig faktor som kräver ett noggrant övervägande. De förmåner som en molnbaserad lösning utan utrymmeskrav ger med avseende på kostnad och enkelhet försvinner om systemet inte är tillgängligt för verksamhetskritiska processer.

    Om inte anslutningen för en viss enhet är mycket pålitlig och flexibel, eller antalet driftstopp är acceptabel för återförsäljaren, rekommenderas ett av följande alternativ:

    - Använd MPOS i Windows och aktivera offline-läget.
    - Distribuera en lokal skalningsenhet för handel.

    Dessa alternativ inte är ömsesidigt uteslutande. För en maximalt pålitlig topologi kan återförsäljare distribuera en lokal RSSU i syfte att minska beroendet av en internetanslutning eller Azure-tillgänglighet, och kan också distribuera kassaapparater där offline-läget aktiveras om det uppstår problem med den lokala servern eller det lokala nätverket.

- **Maskinvaruenheter/kringutrustning** – En viktig aspekt av ett Retail POS-system är möjligheten att använda kassakringutrustning som exempelvis skrivare, kassaapparater och betalningsterminaler. Även om alla tillgängliga kassalaternativ kan använda kringutrustning är det bara MPOS för Windows som stöder dem direkt. En eller fler maskinvarustationer krävs för alla andra program. Även om den här metoden ger ökad flexibilitet, måste ytterligare komponenter distribueras, konfigureras och underhållas.
- **Systemkrav** – Systemkraven för kassatillämpningen varierar. Ta reda på den senaste informationen innan du gör ditt val. Eftersom CPOS körs i en webbläsare stöder det till exempel fler operativsystem. Mer information om systemkraven finns [Systemkrav för molnbaserad distribution](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Distribution och underhåll** – Distributions- och underhållskravens komplexitet kan variera beroende på program- och distributionsalternativ. För en CPOS-distribution med molnbaserad värd måste du exempelvis inte installera och uppdatera på alla enheter. Därför minskar denna metod komplexitet och kostnad avsevärt. Om du distribuerar MPOS på alla kassor, aktiverar offline-läget och dessutom distribuerar delade maskinvarustationer, kan du emellertid avsevärt öka antalet slutpunkter som måste hanteras.


[!INCLUDE[footer-include](../includes/footer-banner.md)]