---
title: 'Tillägg för elektronisk fakturering: översikt'
description: Det här avsnittet ger information om tillägget Elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 01/22/2021
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
ms.openlocfilehash: 2c35b810151349384f105d9ac1d93e1885031450
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104218"
---
# <a name="electronic-invoicing-add-on-overview"></a>Tillägg för elektronisk fakturering: översikt

[!include [banner](../includes/banner.md)]

Tillägg för elektronisk fakturering för Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management är en skalbar tjänst för flera innehavare som möjliggör konfigurerbar bearbetning av elektroniska fakturadokument och konfigurerbart dokumentutbyte. Bearbetnings- och integrationsreglerna är helt konfigurerbara och logiken körs utanför Finance och Supply Chain Management. Tjänsten är huvudsakligen riktad mot bearbetning av e-faktura i scenarier med företag till myndigheter, men den kan konfigureras för andra ändamål.

Med hjälp av tillägget Elektronisk fakturering kan du uppnå följande mål:

- Snabb och enkel antagande av lands-/regionspecifika krav
- Standardiserade implementeringar av lösningen för tillägg för elektronisk fakturering
- Förbättrad spårning av dokumenthistorik
- Kortare implementeringscykel
- Minskad total ägandekostnad (TCO)
- Lätt inställbara konfigurationer som inte kräver kodändringar
- Förenklad konfigurationsförpackning
- Inbyggd export, import och integration samt enkel utökning i bearbetning av dokument med e-fakturor
- Enkel återanvändning av samma inställningar för export, import och integration mellan företag

Om du vill använda tillägget elektronisk fakturering måste du installera det från ditt projekt i Microsoft Dynamics Lifecycle Services (LCS). Följ sedan inställningsproceduren för att aktivera integrationen med Finance eller Supply Chain Management. För mer information, se [Kom igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Tjänstetillgänglighet

För närvarande är tillägget Elektronisk fakturering tillgängligt för kunder via förhandsgranskningsprogrammet, och i nästa fas blir tjänsten allmänt tillgänglig. Eftersom funktioner som åtgärdar lands-/regionspecifika krav kan begränsas till olika faser av versionen, bör du alltid kontrollera den mest aktuella dokumentationen som belyser omfattningen och omfattningen av de lands-/regionspecifika lösningar som stöds.

Tillägg för elektronisk fakturering distribueras i följande Azure-geografiska områden:

- USA
- Europa

> [!NOTE]
> Tillägg för elektronisk fakturering stöder inte lokala distributioner.

## <a name="extended-configurability"></a>Utökade konfigureringsmöjligheter

Tillägg för elektronisk fakturering kan användas i situationer där du måste skapa och skicka ett elektroniskt dokument till de utsedda parterna. Den är särskilt utformad för att köra ett konfigurerbart flöde av bearbetningsåtgärder, baserat på mottagna data. De alternativ för konfigurering som är tillgängliga i Finance och Supply Chain Management är begränsade till transformering av dokument. Tjänsten utvidgar dessa alternativ genom att lägga till de konfigurerbara integreringarna som är tillgängliga i den. Dessutom har alla elektroniska fakturafunktioner som tidigare funnits, t.ex. Brazilian Nota fiscal eletrônica (NF-e), Mexican Comprobante Fiscal Digital por Internet (CFDI) eller andra funktioner för Västeuropeiska Universal Business Language (UBL)/Pan-European Public Procurement OnLine (PEPPOL) kommer att använda konfigurationer för export och import och för att möjliggöra integrationer med externa webbtjänster.

## <a name="feature-highlights"></a>Funktionens höjdpunkter

- Inbyggd integration med Finance och Supply Chain Management
- Konsekvent användarupplevelse för konfiguration och övervakning av e-fakturaprocessen för alla länder eller regioner
- Snabbare, enklare och billigare antagande av lösningar för tillägg för elektronisk fakturering i nya länder eller regioner
- Konfiguration av tjänsten via Regulatory Configuration Service (RCS) och inställningar för globaliseringsfunktionen
- Omvandling av affärsdata till flera e-fakturaformat (XML, JavaScript Object Notation \[JSON\], TXT och kommaavgränsade värden \[CSV\]) med hjälp av konfigurationer som har definierats i RCS:

    - Elektroniska rapportformat som är tillgängliga för länder eller regioner där omvandling av e-faktura inte är tillgänglig

- Konfigurerbar överföring av e-fakturor till externa webbtjänster, inklusive certifieringshantering genom digitala signaturer:

    - Inbyggd, lätt att utöka och konfigurerbar integration med ytterligare innehåll för flera länder

    > [!NOTE]
    > För närvarande stöds ett begränsat antal direktöverföringar. Mer information finns i avsnittet [Tjänstetillgänglighet](#availability) tidigare i det här avsnittet. Supporten kommer att utökas i framtiden.

- Hantering av svar från webbtjänster, inklusive hantering av konfigurerbara undantagsmeddelanden
- Stöd för elektroniska signaturer (till exempel genom användning av XMLDSig-signeringsalgoritmen)
- Batchbearbetning av e-faktura meddelanden

## <a name="architecture-and-data-flow"></a>Arkitektur och dataflöde

När tillägget Elektronisk fakturering installeras från LCS och de obligatoriska inställningarna har slutförts i alla program som krävs, upprättas en säker anslutning. Tjänsten finns för närvarande i datacenter i USA och i Europa. Därför kan det bero på att tjänstplatsen skiljer sig från platsen för den relaterade Finance eller Supply Chain Management-instansen. När du har slutfört inställningen av tillägget Elektronisk fakturering och aktiverat integrationen, skickas huvuddata och transaktionsdata som hör till ett visst dokument till tillägget Elektronisk fakturering när en elektronisk faktura skickas.

> [!NOTE]
> Om den elektroniska fakturan eller något annat dokument innehåller personuppgifter kontrollerar du att din användning av den här funktionen stämmer överens med allmän dataskyddsförordning (GDPR) och andra regler som rör överföring av personuppgifter.

### <a name="high-level-description-of-the-data-flow"></a>Beskrivning på hög nivå av dataflödet

1. Klienten skickar ett kanoniskt affärsdokument till tjänsten.
2. Med hjälp av den kontextinformation som tas emot från klienten väljer tjänsten det tillämpliga bearbetningsflödet.
3. Tjänsten kör bearbetningsåtgärderna. Dessa åtgärder kan inkludera att omvandla affärsdokumentet till en elektronisk faktura, använda en elektronisk signatur och skicka dokumentet till en extern webbtjänst.
4. Alla inlevererade och bearbetade dokument lagras i kundens Azure Blob-lagring.
5. Alla de innehavares hemligheter och certifikat som användes för bearbetningen lagras i kundens Azure Key Vault.
6. Tjänsten tillhandahåller information på begäran för klienten om bearbetningsstatus för det affärsdokument som har skickats.
7. Klienten får information om den slutförda bearbetningskörningen och gör all tillgänglig logginformation. Det gör också dokumentet som har skapats eller mottagits under flödesbearbetning tillgänglig.

Följande illustration visar hur data flödar till och från tillägg för elektronisk fakturering.

![Dataflöde för tillägget Elektronisk fakturering](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Sekretesspolicy
Om du aktiverar och använder tillägget Elektronisk fakturering kan det krävas att begränsade data skickas, vilket inkluderar organisationens momsregistrerings-ID. Detta kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor i fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser
- [Tjänsteadministration](e-invoicing-service-administration.md)
- [Konfigurera elektroniska fakturor i RCS](e-invoicing-configuration-rcs.md)
- [Utfärda elektroniska fakturor i Finance and Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]