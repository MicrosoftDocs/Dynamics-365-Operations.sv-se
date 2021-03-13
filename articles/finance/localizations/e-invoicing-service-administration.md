---
title: Administreringskomponenter för tillägget Elektronisk fakturering
description: Detta ämne innehåller information om de komponenter som är relaterade till administrationen av tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104440"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Administreringskomponenter för tillägget Elektronisk fakturering

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Detta ämne innehåller information om de komponenter som är relaterade till administrationen av tillägget Elektronisk fakturering. Det ger också information om hur du konfigurerar tillägget Elektronisk fakturering.

## <a name="azure"></a>Azure

Använd Microsoft Azure för att skapa hemligheter för nyckelvalv och lagringsnyckel. Använd sedan hemligheterna i konfigurationen för tillägget Elektronisk fakturering.

## <a name="lifecycle-services"></a>Lifecycle Services

Använd Microsoft Dynamics Lifecycle Services (LCS) för att aktivera tillägget för mikrotjänster för ditt LCS-distributionsprojekt.

I LCS väljer du panelen **Hantering av funktionen för förhandsgranskning** och aktivera sedan funktionen **E-faktureringstjänst**.

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) är det gränssnitt som används för att konfigurerar tillägget Elektronisk fakturering. Resurser som t.ex. miljöer och funktioner för elektronisk fakturering skapas, underhålls och finns i RCS. När resurserna är klara publiceras de i tilläggstjänsten Elektronisk fakturering.

Mer information om RCS finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md)

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integrering med tillägget Elektronisk fakturering

Innan du kan använda RCS för att konfigurera elektroniska fakturor, måste du konfigurera RCS att det är tillåtet att kommunicera med tillägget Elektronisk fakturering. Du slutför den här konfigurationen på fliken **Tillägg för elektronisk fakturering** på sidan **Parametrar för elektronisk rapportering**.

#### <a name="service-endpoint"></a>Slutpunkt för tjänst

URL-adressen till tilläggslutpunkten för Elektronisk fakturering kan variera beroende på Azure-datacentrets geografiska område. I följande register visas tillgänglighet per region:

| Geografiskt område för Azure-datacenter | URL för tjänstslutpunkt                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Östra USA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| Västra USA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| Norra EU                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| Västra EU                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a>Sökande-ID

Program-ID:t är ID:t för tilläggsprogrammet Elektronisk fakturering. I detta fall är värdet fast: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

#### <a name="lcs-environment-id"></a>ID för LCS-miljö

ID:t för LCS-miljön är ID:t för ditt företags LCS-abonnemang.

### <a name="service-environments"></a>Tjänstmiljöer

Tjänstemiljöer är logiska partitioner som skapas för att stödja körning av elektroniska faktureringsfunktioner i tillägget Elektronisk fakturering. Säkerhetshemligheter, digitala certifikat och styrningen (dvs. åtkomstbehörigheter) måste konfigureras på servicemiljönivå.

Kunderna kan skapa så många servicemiljöer som de vill. Alla servicemiljöer som en kund skapar är oberoende av varandra.

Servicemiljöer måste skapas och underhållas i RCS. När tjänstemiljöerna är klara måste de publiceras i tillägget Elektronisk fakturering.

#### <a name="service-environment-status"></a>Status för tjänstemiljö

Tjänstemiljöer kan hanteras via status. Möjliga alternativ är:

- **Ej publicerad** – Miljön har skapats men ännu inte publicerats.
- **Publicerad** – Miljön har publicerats i tillägget Elektronisk fakturering.
- **Ändrat** – Attributen för en publicerad miljö har ändrats, men ändringarna har ännu inte publicerats.

#### <a name="customer-secrets"></a>Kundhemligheter

Tilläggstjänsten Elektronisk fakturering bär ansvar för lagringen av alla dina affärsdata i de Azure-resurser som företaget äger. Du måste skapa två huvudresurser för Azure om du vill säkerställa att tjänsten fungerar korrekt och att alla affärsdata som krävs för och genereras av tilläggstjänsten Elektronisk fakturering endast nås av tillägget.

- Ett Azure Storage-konto (Blob Storage) som lagrar elektroniska fakturor
- Ett Azure-nyckelvalv som lagrar certifikat, samt lagringskontots "uniform resource identifier (URI)"

> [!NOTE]
> Ett särskilt nyckelvalv och kundlagringskonto måste allokeras specifikt för att användas med tillägget Elektronisk fakturering.

Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Användare

Varje servicemiljö måste visa en lista över de användare som kan ansluta från Dynamics 365 Finance och Dynamics 365 Supply Chain Management i tillägget Elektronisk fakturering.

#### <a name="publication"></a>Publicering

Tjänstemiljöerna måste publiceras i tillägget Elektronisk fakturering innan de kan användas. Endast publicerade miljöer kan nås via Finance och Supply Chain Management. En tjänstemiljö måste dessutom publiceras innan några uppdateringar av dess attribut börjar gälla för den elektroniska faktureringstjänsten.

### <a name="connected-applications"></a>Anslutna program

Anslutna program är de instanser av Finance och Supply Chain Management som du kanske vill nå via RCS. Förutom program-URL:en och dess klientorganisation innehåller ett anslutet program även de autentiseringsuppgifter som gör att RCS kan ansluta till miljön.

Med hjälp av de anslutna programmen kan du konfigurera en del av den elektroniska faktureringsfunktionen i Finance och Supply Chain Management för att få hela den elektroniska faktureringsfunktionen att fungera.

## <a name="finance-and-supply-chain-management"></a>Finance och Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integrering med tillägget Elektronisk fakturering

Innan du kan använda Finance och Supply Chain Management för att utfärda elektroniska fakturor via tillägget Elektronisk fakturering, måste tillägget konfigureras att möjliggöra kommunikation med tjänsten.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Integreringsfunktioner för tillägget Elektronisk fakturering

Om du vill aktivera kommunikationen mellan Finance och Supply Chain Management och tillägget Elektronisk fakturering måste du aktivera funktionen **Integrering av tillägget Elektronisk fakturering** i arbetsytan **Funktionshantering**.

#### <a name="service-endpoint"></a>Slutpunkt för tjänst

Tjänsteslutpunkten är den URL där tillägget Elektronisk fakturering finns. Innan du kan utfärda elektroniska fakturor måste tjänsteslutpunkten konfigureras i Finance och Supply Chain Management i syfte att möjliggöra kommunikation med tjänsten.

Om du vill konfigurera tjänsteslutpunkten går du till **Organisationsadministration \> Inställningar \> Parameter för elektroniskt dokument** innan du i fliken **Överföringstjänster** och fältet **URL för tillägget Elektronisk fakturering** anger URL:en enligt beskrivet i tabellen i avsnittet **Tjänsteslutpunkt**.

#### <a name="environments"></a>Miljöer

Miljönamnet som anges i Finance och Supply Chain Management refererar till namnet på den miljö som skapas i RCS publiceras i tillägget Elektronisk fakturering.

Miljön måste konfigureras i fliken **Överföringstjänster** på sidan **Parameter för elektroniskt dokument** så att alla begäranden om att utfärda elektroniska fakturor innehåller den miljö där tillägget Elektronisk fakturering kan avgöra vilken funktion för elektronisk fakturering som ska bearbeta begäran.

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera elektroniska fakturor i RCS](e-invoicing-configuration-rcs.md)
- [Utfärda elektroniska fakturor i Finance and Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
