---
title: Administrationskomponenter för Elektronisk fakturering
description: Detta ämne innehåller information om de komponenter som är relaterade till administrationen av Elektronisk fakturering.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6582a0a9eda19fe69ead853ea5d79d763afcb8a468717fde84a32146fd0f79af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721736"
---
# <a name="electronic-invoicing-administration-components"></a>Administrationskomponenter för Elektronisk fakturering

[!include [banner](../includes/banner.md)]


Detta ämne innehåller information om de komponenter som är relaterade till administrationen av Elektronisk fakturering. Det ger också information om hur du konfigurerar Elektronisk fakturering.

## <a name="azure"></a>Azure

Använd Microsoft Azure för att skapa hemligheter för nyckelvalv och lagringsnyckel. Använd sedan hemligheterna i konfigurationen för Elektronisk fakturering.

## <a name="lifecycle-services"></a>Lifecycle Services

Använd Microsoft Dynamics Lifecycle Services (LCS) för att aktivera för mikrotjänster för ditt LCS-distributionsprojekt.

> [!NOTE]
> Installationen av ett mikrotjänst i LCS kräver minst en virtuell dator för nivå 2. Mer information om miljöplanering finns i [miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) är det gränssnitt som används för att konfigurerar Elektronisk fakturering. Resurser som t.ex. miljöer och funktioner för elektronisk fakturering skapas, underhålls och finns i RCS. När resurserna är klara publiceras de i tjänsten Elektronisk fakturering.

För registrering av RCS, se [Regulatory services](https://marketing.configure.global.dynamics.com/).

Mer information om RCS finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md)

### <a name="integration-with-electronic-invoicing"></a>Integrering med Elektronisk fakturering 

Innan du kan använda RCS för att konfigurera elektroniska fakturor, måste du konfigurera RCS att det är tillåtet att kommunicera med Elektronisk fakturering. Du slutför den här konfigurationen på fliken **Elektronisk fakturering** på sidan **Parametrar för elektronisk rapportering**.

#### <a name="service-endpoint"></a>Slutpunkt för tjänst

Elektronisk fakturering är tillgänglig i flera Azure-geografiska datacenterområden. I följande register visas tillgänglighet per region.

| Geografiskt område för Azure-datacenter |
|----------------------------|
| USA              |
| Europa                     |
| Storbritannien             |
| Asien                       |

### <a name="service-environments"></a>Tjänstmiljöer

Tjänstemiljöer är logiska partitioner som skapas för att stödja körning av elektroniska faktureringsfunktioner i Elektronisk fakturering. Säkerhetshemligheter, digitala certifikat och styrningen (dvs. åtkomstbehörigheter) måste konfigureras på servicemiljönivå.

Kunderna kan skapa så många servicemiljöer som de vill. Alla servicemiljöer som en kund skapar är oberoende av varandra.

Servicemiljöer måste skapas och underhållas i RCS. När tjänstemiljöerna är klara måste de publiceras i Elektronisk fakturering.

#### <a name="service-environment-status"></a>Status för tjänstemiljö

Tjänstemiljöer kan hanteras via status. Möjliga alternativ är:

- **Ej publicerad** – Miljön har skapats men ännu inte publicerats.
- **Publicerad** – Miljön har publicerats i Elektronisk fakturering.
- **Ändrat** – Attributen för en publicerad miljö har ändrats, men ändringarna har ännu inte publicerats.

#### <a name="customer-secrets"></a>Kundhemligheter

Tjänsten Elektronisk fakturering bär ansvar för lagringen av alla dina affärsdata i de Azure-resurser som företaget äger. Du måste skapa två huvudresurser för Azure om du vill säkerställa att tjänsten fungerar korrekt och att alla affärsdata som behövs för och genereras av tjänsten elektronisk fakturering endast används av tillägget.

- Ett Azure Storage-konto (Blob Storage) som lagrar elektroniska fakturor
- Ett Azure-nyckelvalv som lagrar certifikat samt lagringskontots "uniform resource identifier (URI)"


Ett särskilt nyckelvalv och kundlagringskonto måste allokeras specifikt för att användas med Elektronisk fakturering. Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

Om du vill övervaka dina nyckelvalv och ta emot notifieringar konfigurerar du Azure Monitor för nyckelvalv. Genom att aktivera nyckelvalvsloggning kan du övervaka hur, när och av vem dina nyckelvalv ska användas. Mer information finns i [Övervakning och notifiering för Azure-nyckelvalv](/azure/key-vault/general/alert) och [Så här aktiverar du nyckelvalvsloggning](/azure/key-vault/general/howto-logging?tabs=azure-cli).

Det rekommenderas att regelbundet ändra hemligheterna. Mer information finns i [Hemlighetsdokumentationen](/azure/key-vault/secrets/).

#### <a name="users"></a>Användare

Varje servicemiljö måste visa en lista över de användare som kan ansluta från Dynamics 365 Finance och Dynamics 365 Supply Chain Management i Elektronisk fakturering.

#### <a name="publication"></a>Publicering

Tjänstemiljöerna måste publiceras i Elektronisk fakturering innan de kan användas. Endast publicerade miljöer kan nås via Finance och Supply Chain Management. En tjänstemiljö måste dessutom publiceras innan några uppdateringar av dess attribut börjar gälla för den elektroniska faktureringstjänsten.

### <a name="connected-applications"></a>Anslutna program

Anslutna program är de instanser av Finance och Supply Chain Management som du kanske vill nå via RCS. Förutom program-URL:en och dess klientorganisation innehåller ett anslutet program även de autentiseringsuppgifter som gör att RCS kan ansluta till miljön.

Med hjälp av de anslutna programmen kan du konfigurera en del av den elektroniska faktureringsfunktionen i Finance och Supply Chain Management för att få hela den elektroniska faktureringsfunktionen att fungera.

## <a name="finance-and-supply-chain-management"></a>Finance och Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integrering med Elektronisk fakturering

Innan du kan använda Finance och Supply Chain Management för att utfärda elektroniska fakturor via Elektronisk fakturering, måste tillägget konfigureras att möjliggöra kommunikation med tjänsten.

#### <a name="electronic-invoicing-integration-feature"></a>Integreringsfunktioner för Elektronisk fakturering

Om du vill aktivera kommunikationen mellan Finance och Supply Chain Management och Elektronisk fakturering måste du aktivera funktionen **Integrering av Elektronisk fakturering** i arbetsytan **Funktionshantering**.

#### <a name="service-endpoint"></a>Slutpunkt för tjänst

Tjänsteslutpunkten är den URL där Elektronisk fakturering finns. Innan du kan utfärda elektroniska fakturor måste tjänsteslutpunkten konfigureras i Finance och Supply Chain Management i syfte att möjliggöra kommunikation med tjänsten.

Om du vill konfigurera tjänsteslutpunkten går du till **Organisationsadministration \> Inställningar \> Parameter för elektroniskt dokument** innan du i fliken **Överföringstjänster** och fältet **URL för Elektronisk fakturering** anger URL:en enligt beskrivet i tabellen i avsnittet **Tjänsteslutpunkt**.

#### <a name="environments"></a>Miljöer

Miljönamnet som anges i Finance och Supply Chain Management refererar till namnet på den miljö som skapas i RCS publiceras i Elektronisk fakturering.

Miljön måste konfigureras i fliken **Överföringstjänster** på sidan **Parameter för elektroniskt dokument** så att alla begäranden om att utfärda elektroniska fakturor innehåller den miljö där Elektronisk fakturering kan avgöra vilken funktion för elektronisk fakturering som ska bearbeta begäran.

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera elektroniska fakturor i RCS](e-invoicing-configuration-rcs.md)
- [Utfärda elektroniska fakturor i Finance and Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
