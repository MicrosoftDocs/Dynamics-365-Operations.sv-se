---
title: e-fakturering – översikt
description: Detta ämne ger en översikt över e-fakturering i Microsoft Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 4ce5776216855fc664b9beba68036d41920ae602
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861308"
---
# <a name="electronic-invoicing-overview"></a>e-fakturering – översikt

[!include [banner](../includes/banner.md)]

E-fakturering för Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management är en ytterst skalbar tjänst för flera klientorganisationer som möjliggör konfigurerbar bearbetning av e-fakturor och konfigurerbart elektroniskt dokumentutbyte. Bearbetnings- och integrationsreglerna är helt konfigurerbara och logiken körs utanför Finance och Supply Chain Management. Tjänsten är framför allt avsedd för bearbetning av e-fakturadokument i scenarier mellan företag och myndigheter. Den kan emellertid även konfigureras för andra syften, till exempel scenarier mellan företag för olika typer av dokument.

Med hjälp av e-fakturering kan du uppnå följande mål:

- Snabb och enkel antagande av lands-/regionspecifika krav
- Standardiserade implementeringar av lösningen för e-fakturering
- Förbättrad spårning av dokumenthistorik
- Kortare implementeringscykel
- Minskad total ägandekostnad (TCO)
- Enkelt inställbara konfigurationer som inte kräver kodändringar
- Förenklad konfigurationsförpackning
- Inbyggd export, import och integrering, samt enkel utökning i bearbetningen av e-fakturor
- Enkel återanvändning av samma inställningar för export, import och integration mellan företag

## <a name="service-availability"></a>Tjänstetillgänglighet

E-faktureringsfunktionen är för närvarande tillgänglig för kunder inom Ekonomi och Supply Chain Management. Mer information finns i licensvillkoren för ditt program.

Eftersom funktioner som åtgärdar lands-/regionspecifika krav kan begränsas i olika faser av versionen, bör du alltid studera den mest aktuella dokumentationen som belyser omfattningen av de lands-/regionspecifika lösningar som stöds.

e-fakturering distribueras i följande Azure-geografiska områden:

- USA
- Europa
- Asien

> [!NOTE]
> e-fakturering stöder inte lokala distributioner.

## <a name="feature-highlights"></a>Funktionens höjdpunkter

- Medföljande integrering med Ekonomi och Supply Chain Management
- En konsekvent användarupplevelse för konfiguration och övervakning av e-fakturaprocessen för alla länder och regioner
- Snabbare, enklare och billigare antagande av lösningar för e-fakturering i nya länder eller regioner
- Konfiguration av tjänsten via inställningen av Regulatory Configuration Service (RCS) och globaliseringsinställningar
- Omvandling av affärsdata till flera e-fakturaformat (XML, JavaScript Object Notation \[JSON\], TXT och kommaavgränsade värden \[CSV\]) med hjälp av konfigurationer som har definierats i RCS:

    - Elektroniska rapportformat (ER) som är tillgängliga för länder och regioner där konfigurering av e-faktura inte är tillgänglig

- Konfigurerbar överföring av e-fakturor till externa webbtjänster, inklusive certifieringshantering genom digitala signaturer:

    - Inbyggd, lätt expanderbar samt konfigurerbar integrering med ytterligare innehåll för flera länder och regioner

- Hantering av svar från webbtjänster, inklusive konfigurerbar hantering av undantagsmeddelanden
- Stöd för elektroniska signaturer (till exempel elektroniska signaturer som använder signeringsalgoritmen XMLDSig)
- Kapaciteten att skicka dokument till e-postmeddelanden och lagra dem i SharePoint
- Batchbearbetning av e-faktura meddelanden
- Konfigurerbar transformering av inkommande dokument och bearbetning av dessa dokument i Ekonomi och Supply Chain Management
- Möjligheten att ta emot inkommande dokument från kanaler såsom e-post och SharePoint

## <a name="privacy-notice"></a>Sekretesspolicy

Om du vill aktivera och använda funktionen för e-faktura måste begränsade data eventuellt skickas. Dessa data inkluderar företagets momsregistrerings-ID. Dessa data kommer att överföras till tredjepartsinstanser som har tillstånd av skattemyndigheten att skicka e-fakturor i de fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. Data som importeras från dessa externa system till denna Dynamics 365-onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i lands-/regionspecifik funktionsdokumentation.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
