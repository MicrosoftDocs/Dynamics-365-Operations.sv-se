---
title: Vanliga frågor om Elektronisk fakturering
description: I det här avsnittet finns information om vanliga frågor och svar angående elektronisk fakturering.
author: gionoder
ms.date: 03/17/2021
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 41cddcdad5043ec314a94dda67f4f2e9de406cac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840182"
---
# <a name="electronic-invoicing-faq"></a>Vanliga frågor om Elektronisk fakturering

[!include [banner](../includes/banner.md)]

I det här avsnittet finns svar på vanliga frågor om elektronisk fakturering. Elektronisk fakturering utökar den elektroniska fakturerings kapaciteten som finns i Dynamics 365 Finance, Dynamics 365 Supply Chain Management och Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Vad är viktigt med elektronisk fakturering och varför ska det betydelse för min organisation?

Komplexiteten och risken i verksamheten fortsätter att se annorlunda ut när organisationerna ökar globalt och expanderar sina verksamhetsområden över hela regionen. Att upprätthålla efterlevnad och anpassa sig efter ofta ändrade regler är en allt större regelefterlevnad och är särskilt viktigt vid fakturering. Faktureringen har traditionellt varit dyrt och känsligt för fel eftersom företag är beroende av pappersdokument och manuellt viktiga processer.  

Organisationer har börjat förflytta sig från pappersfakturor för att minska kostnaden och snabba upp slutpunktsprocessen. Den offentliga staten förser sig med elektronisk fakturering som en nyckelkomponent i momsdigitaliseringen. Genom att en organisation kräver att organisationer digitalt skickar momsinformation i realtid till skattemyndigheterna, kan de offentliga myndigheterna minimera förfallna och manipulera, och minska belastningen. 

Världen växlar till papperslös dokumentbearbetning och utan att införa elektronisk fakturering, kan kunderna riskera efterföljandeproblem, onödiga kostnader och ligger efter konkurrenterna. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Inte Finance, Supply Chain Management och Project Operations innehåller redan funktioner för elektronisk fakturering? Vilket värde ger detta till mig som kund? 

Elektronisk fakturering utökar den elektroniska fakturerings kapaciteten i Finance, Supply Chain Management och Project Operations. Funktionen gör det också enklare att se till att de senaste elektroniska faktureringsstandarderna följs och ger praktiska erfarenheter av olika geologier inom elektronisk fakturabearbetning och utbyte. Den elektroniska faktureringen kan låsa upp en vektor med förmåner, till exempel: 

   - Snabbare och enklare antagande av lands-/regionspecifika krav.
   - Standardiserade implementeringar av lösningen för elektronisk fakturering. 
   - Förbättrad spårningsbarhet för e-fakturabearbetning.  
   - Underhållet av ändringar av juridiska krav och lokal affärspraxis blir enklare. 
   - Förenklad förpackningslösning.
   - Skalningskapaciteter för en stor volym skickade dokument som leder till snabbare svängar.
   - Förmåga att dela lösningar med andra företag.

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Har elektronisk fakturering stöd för installationer av Finance, Supply Chain Management och Project Operations? 

Den aktuella plattformsversionen tillåter inte användning av den lokala versionen och det finns inga planer på att stödja den i framtiden.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>Har elektroniskt faktureringsgränssnitt med funktionen för leverantörsimport?

Nej. Det finns planer för det här gränssnittet men det finns ingen planerad tidslinje. När det har planerats kommer dessa datum att vara planerade i [frisläppningsplanerna](https://docs.microsoft.com/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Hur hanterar elektronisk fakturering filbilagor i den elektroniska fakturan? Behövs en SharePoint-server när PDF-filer lagras i XML-filen?

Filerna som är kopplade till den elektroniska fakturan hanteras som inbäddade binära data i ett XML-element. En SharePoint server ett dokumenthanteringssystem som inte behövs för att PDF-filer ska sparas, men bilagan måste lagras i dokumenthanteringssystemet Finance, Supply Chain Management och Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>Är elektronisk fakturering tillgänglig enligt reglerna för mitt land/min region?

Elektronisk fakturering är en mikrotjänstplattform som är global tillgänglig.

Microsoft planerar att publicera de elektroniska fakturaformaten och integrationerna för de länder som funktionellt lokaliseras av Microsoft. Mer information finns i [Tillgänglighet för elektroniska faktureringsfunktioner](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Om det elektroniska faktureringsformatet för ditt land/din region inte visas, är den plattform som förser scenariot med att stödja detta scenario i framtiden. Du kan fortfarande dra nytta av den konfigurationskapacitet som elektronisk fakturering har och konfigurera det elektroniska faktureringsformatet själv, eller så kan du arbeta med en partner/ISV och konfigurera dem för din organisation.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Är Dynamics 365 för Regulatory Services en ny modul som Personal eller Project Operations som är kopplad till Finance eller Supply Chain Management? Finns det extra kostnader för det?

Dynamics 365 för Regulatory Services (RCS) är en molnbaserad tjänst för konfigurering av globaliseringsresurser. RCS är gratis för alla licensinnehavare för Finance, Supply Chain Management och Project Operations.

För registrering av RCS, gå till <https://marketing.configure.global.dynamics.com/>.

Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Behöver jag registrera mig för att få elektronisk fakturering eller bara aktivera den i funktionshantering?

Om du har en licens för Finance, Supply Chain Management och Project Operations, se [Komma igång med serviceadministration för tillägget för elektronisk fakturering](e-invoicing-get-started-service-administration.md) för att registrera dig för elektronisk fakturering.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Fungerar elektronisk fakturering med virtuella nivå 1-maskiner? Vilken miljö krävs minimal?

Integrationen i elektronisk fakturering kräver minst en virtuell nivå 2-maskin som är värd för Finance och Supply Chain Management. Mer information om miljöplanering finns i [miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>Har elektronisk fakturering ett testläge för att testa sändning av fakturor?

Detta kan uppnås genom konfiguration. Om du vill testa sändning av fakturor kan du ansluta till Finance eller Supply Chain Management från en UAT-miljö (användaracceptanstest) och skicka testfakturorna. Elektronisk fakturering stöder konfiguration av digitala testcertifikat och för e-fakturor som kräver digitalt godkännande har skattemyndigheten konfigurerat en URL från testwebbtjänsterna.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Finns det någon dokumentation om de landsspecifika elektroniska faktureringsfunktionerna utanför rutan?

Ja. Information om tillgängligheten på funktioner för elektronisk fakturering och de format de stöder finns i [Tillgänglighet för elektroniska faktureringsfunktioner](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Om du inte hittade svaren du letar efter kan du e-posta din fråga till produktutvecklingsteamet på <D365EInvoicePreview@microsoft.com>. Vi kontaktar dig eller ökar täckningen för de här vanliga frågorna.
