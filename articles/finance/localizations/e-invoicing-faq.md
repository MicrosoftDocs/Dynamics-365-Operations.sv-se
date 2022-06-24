---
title: Vanliga frågeställningar om E-fakturering
description: I den här artikeln finns information om vanliga frågeställningar och svar angående e-fakturering.
author: gionoder
ms.date: 04/21/2021
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fbb43438a9da567460eb744afb64dae5274f04a9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904366"
---
# <a name="electronic-invoicing-faq"></a>Vanliga frågor och svar om elektronisk fakturering

[!include [banner](../includes/banner.md)]

I denna artikel finns svar på vanliga frågeställningar om tjänsten för e-fakturering. E-fakturering utökar den elektroniska fakturerings kapaciteten som finns i Dynamics 365 Finance, Dynamics 365 Supply Chain Management och Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Vad är viktigt med e-fakturering och varför ska det betydelse för min organisation?

Komplexiteten och risken i verksamheten fortsätter att se annorlunda ut när organisationerna ökar globalt och expanderar sina verksamhetsområden över hela regionen. Att upprätthålla efterlevnad och anpassa sig efter ofta ändrade regler är en allt större regelefterlevnad och är särskilt viktigt vid fakturering. Faktureringen har traditionellt varit dyrt och känsligt för fel eftersom företag är beroende av pappersdokument och manuellt viktiga processer.  

Organisationer har börjat förflytta sig från pappersfakturor för att minska kostnaden och snabba upp slutpunktsprocessen. Den offentliga staten förser sig med e-fakturering som en nyckelkomponent i skattedigitaliseringen. Genom att en organisation kräver att organisationer digitalt skickar skatteinformation i realtid till skattemyndigheterna, kan de offentliga myndigheterna minimera förfallna och manipulera, och minska belastningen. 

Världen växlar till papperslös dokumentbearbetning och utan att införa e-fakturering, kan kunderna riskera efterföljandeproblem, onödiga kostnader och ligger efter konkurrenterna. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Inte Finance, Supply Chain Management och Project Operations innehåller redan funktioner för e-fakturering? Vilket värde ger detta till mig som kund? 

E-fakturering utökar de elektroniska faktureringsfunktionerna i Finance, Supply Chain Management och Project Operations. Funktionen gör det också enklare att se till att de senaste elektroniska faktureringsstandarderna följs och ger praktiska erfarenheter av olika geologier inom elektronisk fakturabearbetning och utbyte. Den elektroniska faktureringen kan låsa upp en vektor med förmåner, till exempel: 

   - Snabbare och enklare antagande av lands-/regionspecifika krav.
   - Standardiserade implementeringar av lösningen för e-fakturering. 
   - Förbättrad spårningsbarhet för e-fakturabearbetning.  
   - Underhållet av ändringar av juridiska krav och lokal affärspraxis blir enklare. 
   - Förenklad förpackningslösning.
   - Skalningskapaciteter för en stor volym skickade dokument som leder till snabbare svängar.
   - Förmåga att dela lösningar med andra företag.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Har tjänsten för e-fakturering stöd för lokala installationer av Finance, Supply Chain Management och Project Operations? 

Den aktuella plattformsversionen tillåter inte användning av den lokala versionen och det finns inga planer på att stödja den i framtiden.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>Har tjänsten för e-fakturering ett gränssnitt som är kompatibelt med funktionen för automatisk leverantörsimport?

Nej. Det finns planer för det här gränssnittet men det finns ingen planerad tidslinje. När det har planerats kommer dessa datum att vara planerade i [frisläppningsplanerna](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Hur hanterar tjänsten för e-fakturering filbilagor i den elektroniska fakturan? Behövs en SharePoint-server när PDF-filer lagras i XML-filen?

Filerna som är kopplade till den elektroniska fakturan hanteras som inbäddade binära data i ett XML-element. En SharePoint server ett dokumenthanteringssystem som inte behövs för att PDF-filer ska sparas, men bilagan måste lagras i dokumenthanteringssystemet Finance, Supply Chain Management och Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>Är tjänsten för e-fakturering tillgänglig enligt regelverket för mitt land/min region?

Tjänsten för e-fakturering är en mikrotjänstplattform som kommer att bli globalt tillgänglig.

Microsoft planerar att publicera de elektroniska fakturaformaten och integrationerna för de länder som funktionellt lokaliseras av Microsoft. Mer information finns i [Tillgänglighet för elektroniska faktureringsfunktioner](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Om det elektroniska faktureringsformatet för ditt land/din region inte visas, är den plattform som förser scenariot med att stödja detta scenario i framtiden. Du kan fortfarande dra nytta av den konfigurationskapacitet som e-fakturering har och konfigurera det elektroniska faktureringsformatet själv, eller så kan du arbeta med en partner/ISV och konfigurera dem för din organisation.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Är Dynamics 365 för Regulatory Services en ny modul som Personal eller Project Operations som är kopplad till Finance eller Supply Chain Management? Finns det extra kostnader för det?

Dynamics 365 för Regulatory Services (RCS) är en molnbaserad tjänst för konfigurering av globaliseringsresurser. RCS är gratis för alla licensinnehavare för Finance, Supply Chain Management och Project Operations.

För registrering av RCS, gå till <https://marketing.configure.global.dynamics.com/>.

Mer information finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Behöver jag registrera mig för att få e-faktureringstjänsten, eller behöver jag bara aktivera den i funktionshanteringen?

Om du har en licens för Finance, Supply Chain Management och Project Operations, se [Komma igång med serviceadministration för tillägget för e-fakturering](e-invoicing-get-started-service-administration.md) för att registrera dig för e-fakturering.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Fungerar tjänsten för e-fakturering med virtuella nivå 1-maskiner? Vilken miljö krävs minimal?

Integrationen i e-faktureringstjänsten kräver minst en virtuell nivå 2-maskin som värd för Finance och Supply Chain Management. Mer information om miljöplanering finns i [miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>Har e-faktureringstjänsten ett testläge för att testa sändning av fakturor?

Detta kan uppnås genom konfiguration. Om du vill testa sändning av fakturor kan du ansluta till Finance eller Supply Chain Management från en UAT-miljö (användaracceptanstest) och skicka testfakturorna. E-fakturering stöder konfiguration av digitala testcertifikat och för e-fakturor som kräver digitalt godkännande har skattemyndigheten konfigurerat en URL från testwebbtjänsterna.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Finns det någon dokumentation om de medföljande landsspecifika elektroniska faktureringsfunktionerna?

Ja. Information om tillgängligheten för e-faktureringsfunktioner och de format dessa stöder finns i [Tillgänglighet för elektroniska faktureringsfunktioner](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>Tillåter den elektroniska faktureringstjänsten en juridisk person i Finance eller Supply Chain Management som är konfigurerad för ett visst land att använda funktioner för elektronisk fakturering från olika länder/regioner?

Ja. Funktionerna för elektronisk fakturering kan komma att förbrukas i syfte att bearbeta inskickade affärsdokument som är oberoende av landet för den juridiska personen, om följande gäller:

   - Affärsdokumentet som genereras använder lämplig dokumentmodellmappning.
   - Det finns en matchning mellan affärsdokumentet och tillämplighetsreglerna som konfigurerats i den elektroniska faktureringsfunktionen.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>Använder tjänsten för elektronisk fakturering samma konfigurations- och designupplevelse som den elektroniska rapporteringsmodulen i Ekonomi och Supply Chain Management? 

Ja. Samma designerverktyg som används i modulen Elektronisk rapportering (ER) i Ekonomi och Supply Chain Management används för att skapa och konfigurera datamodellmappning och filformatskonfigurationer. Dessa designerverktyg används även i Regulatory Configuration Services (RCS) för att skapa och konfigurera konfigurationer för datamodellmappning och filformat som används för konfiguration av e-faktureringsfunktioner.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>Kan tillämplighetsreglerna utökas och konfigureras så att de inte är knutna till någon specifik parameter, till exempel en juridisk person?

Ja. Tillämplighetsreglerna är helt konfigurerbara. Du kan lägga till eller ta bort satser, bygga logikfunktioner samt gruppera och ta bort satser. Mer information finns i [Tillämplighetsregler](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>Stöder den elektroniska faktureringstjänsten andra ER-formatkonfigurationer för att generera andra typer av dokument? Stöder den att man skickar dokumenten elektroniskt till kunder, till exempel en följesedel?

Du kan använda andra ER-formatkonfigurationer för att skapa önskade utdatafiler. ER-formatkonfigurationen måste emellertid härledas från samma ER-fakturamodellmappning som konfigureras i Finance eller Supply Chain Management för att generera affärsdokument. Att skicka utdatafilen direkt till kunden som en EDI-transaktion stöds inte vid leverans av elektronisk fakturering.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>Stöder den elektroniska faktureringstjänsten utbyte av elektroniska fakturor med kunder? Stöder den konfigurering av olika fakturaformat för samma faktura?

Kapaciteten att ta emot och importera elektroniska fakturor från leverantören planeras, men att automatiskt skicka elektroniska fakturor till kunder stöds för närvarande inte.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>Stöder den elektroniska faktureringstjänsten utbyte av EDI-meddelanden med andra företag?

Den elektroniska faktureringstjänstens fokus att utbyta elektroniska fakturameddelandetyper som styrs av regelefterlevnadskrav. Mottagning och import av elektroniska leverantörsfakturor planeras, men att skicka elektroniska fakturafiler till kunderna stöds i nuläget inte per automatik, med undantag för scenarier där det är ett regelverksmässigt krav att skicka elektroniska fakturor till kunderna.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>Stöder den elektroniska faktureringstjänsten import eller sammanslagning av anpassningar som gjorts i ER-formatkonfigurationerna från den äldre elektroniska faktureringsfunktionen?

Du kan återanvända ER-formatkonfigurationer i den elektroniska faktureringstjänsten. ER-formatkonfigurationen måste emellertid härledas från samma ER-fakturamodellmappning som funktionen för elektronisk faktura utformades att använda, och som konfigureras i Finance eller Supply Chain Management för att generera affärsdokumenten.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>Stöder den elektroniska faktureringstjänsten utfärdande av elektroniska fakturor från anpassade register? Hur skapar man i så fall ER-datamodellkonfigurationerna för de nya registren och entiteterna?

Ja. Det kräver dock att man anpassar fakturamodellmappningen och lägger till nödvändiga referenser till de kundanpassade registren, eller, beroende på komplexiteten, skapar en ny fakturamodellmappning.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>Har den elektroniska faktureringstjänsten stöd för olika webbtjänstslutpunkter?

Den elektroniska faktureringstjänsten stöder olika webbtjänstslutpunkter. Du kan använda konfigurerbar integrering med REST-webbtjänster eller ett antal landsspecifika parametriserade webbtjänstintegrationer. Olika slutpunkter kan konfigureras för samma webbtjänster och API:er med olika konfigurationsversioner. Mer information finns i avsnittet [Lista över parametrar per åtgärd](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>Är elektronisk fakturering integrerad med de olika fakturaoperatörernas API:er från de nordiska länderna, eller ska den hanteras från fall till fall?

Microsoft utökar kontinuerligt den funktionella täckningen för att tillhandahålla "out-of-the box"-integreringar med hjälp av elektroniska faktureringsfunktioner. Mer information om formaten och integreringarna som stöds finns i [Tillgänglighet för elektroniska faktureringsfunktioner](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Om du inte hittade svaren du letar efter kan du e-posta din fråga till produktutvecklingsteamet på <D365EInvoicePreview@microsoft.com>. Vi kontaktar dig eller ökar täckningen för de här vanliga frågeställningarna.
