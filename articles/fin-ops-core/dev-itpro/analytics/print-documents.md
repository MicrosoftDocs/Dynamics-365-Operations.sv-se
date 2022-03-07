---
title: Dokumentetutskrift – översikt
description: Du kan skriva ut dokument genom att använda en lokal skrivare eller en nätverksansluten enhet. Den här artikeln innehåller en översikt över hur dokument skrivs ut.
author: RichdiMSFT
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.custom:
- "69161"
- intro-internal
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b9105ef39e411ac33043f1941d4e1dd32b758e5
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984918"
---
# <a name="document-printing-overview"></a>Dokumentetutskrift – översikt

[!include [banner](../includes/banner.md)]

Du kan skriva ut dokument genom att använda en lokal skrivare eller en nätverksansluten enhet. Den här artikeln innehåller en översikt över hur dokument skrivs ut.

## <a name="printing-overview"></a>Översikt över utskrift

Appen tillhandahåller integrerade tjänster och klientprogram som gör det enklare att skapa, lagra och distribuera dokument som stöder affärsaktiviteten. Du kan skriva ut dokument genom att använda en lokal skrivare eller en nätverksansluten enhet. Dessutom kan du exportera sidor och rapporter direkt från klienten, som PDF-filer eller Microsoft Office-dokument. Slutligen gör den distribuerade arbetsbelastningen att du kan skriva ut affärsdokument direkt från en mobil enhet med hjälp av nätverksresurser. Även om utskriftsbehov varierar måste alla branscher vanligtvis skapa papperskopior av affärsdokument med appen. Skriva ut dokument på nätverksenheter från värdprogram ger en unik uppsättning utmaningar. Nedan följer några exempel:

- Skrivardrivrutiner kanske inte kan användas på användarens enhet.
- Användarens enhet kanske inte är ansluten till företagets nätverk.

Genom att använda en särskild värd och följa några enkla steg kan systemadministratörer konfigurera distributioner så att användarna kan skriva ut direkt från företagsprogram på nätverksenheter.

### <a name="application-printing-scenarios"></a>Scenarier för programutskrift 

I följande tabell beskrivs de tre primära utskriftsscenarierna.

| Scenario                        | Mål                                                      | Lösning |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. Skriva ut vad du ser        | Skriv ut vad som visas i webbläsaren.             | En ”utskriftsvänlig” version av webbsidan skapas för webbläsaren. |
| 2. Interaktiv utskrift         | Skriva ut ett precisionsdokument på en lokalt ansluten enhet. | Du kan exportera en PDF-version av rapporten och överföra den till webbläsaren. |
| 3. Utskrift på en nätverksenhet | Skicka ett precisionsdokument till en skrivare i domänen.     | Ett precisionsdokument skickas till ett klientprogram som körs på en server som har en värd i kundens domän. |

Eftersom lösningen varierar beroende på scenariet, innehåller appar inbyggda tjänster och verktygsuppsättningar som hjälper användarna att uppnå sina mål:

- **Scenario 1** stöds av webbläsarens återgivning av HTML5-klienten.
- **Scenario 2** använder klientprogram och Microsoft 365-tjänster.
- **Scenario 3** kräver stöd från klientprogram och från tjänster som finns i Microsoft Azure.

Förutom den plattform som distribueras på Azure-abonnemanget ger Finance and Operations-.program kunderna en integrerad, första part Azure-program som kan användas för att enkelt använda domänhanterade enheter för att skriva ut dokument.

## <a name="service-overview"></a>Översikt över tjänsten
När dokument som har skapats av värdprogram som väntar på att skrivas ut på en nätverksansluten enhet, förvaras de i Azure blobblagring. [Installera dokumentflödesagenten för att aktivera nätverksutskrift](install-document-routing-agent.md) använder Azure-autentisering för att upprätta en säker kanal till Azure-tjänsterna.

**Körningssekvens**

1. Rapporten skapas av Microsoft SQL Server Reporting Services (SSRS) och lagras i Azure blobblagring. Kopplade skrivarinställningar sparas tillsammans med dokumentet.
2. Dokumentflödesagenten frågar Azure Service Bus-kön efter aktiva jobb.
3. Dokumentet hämtas av dokumentflödesagenten och överförs till nätverksskrivaren.

Den klientbaserade lösningen låter kunder hantera omfattningen av deras skrivarbehov. Kunder som har aktiverat utskrifter av stora volymer kan installera många dokumentflödesagenter för att öka antalet samtidiga utskriftsoperationer. Alternativt kräver vissa kunder mycket få dokumentflödesagenter för att hantera deras förväntade utskriftsbehov.

### <a name="service-components-for-network-printing"></a>Tjänstkomponenter för nätverksutskrift

Diagrammet nedan visar de grundläggande komponenterna som hjälper till att stödja nätverksutskriftoperationer.

[![tjänstekomponenter-för-nätverksutskrift\_2016.](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

Observera att en skrivare kan registreras med flera dokumentflödesagenter. För att lösa skrivarens egenskaper använder värdtjänsten nätverkssökvägen som unikt identifierar alla nätverksskrivare. Därför visas den som ett alternativ i listan över skrivare som är tillgänglig i appar även om en skrivare är registrerad med flera klienter.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]