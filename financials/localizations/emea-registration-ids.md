---
title: Registrerings-ID
description: "Det här avsnittet innehåller information om hur du ställer in och använder registrering ID: N."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>Registrerings-ID

Det här avsnittet innehåller information om hur du ställer in och använder registrering ID: N.

Ha olika och andra föreskrifter för att registrera registreringsnummer eller ID många länder och regioner. Det här avsnittet Översikt en över inställningarna och bearbetning av Registreringstyper stöds för parter i olika europeiska länder/regioner. Alla länder/regioner har sina krav för att stödja olika landsspecifika funktioner som rör registreringsnummer från annat tillstånd kontor. Exempel på registreringsnummer är social security number (SSN), tax identification-nummer (TIN) och Europeiska moms-ID (EU moms-ID). Funktionen ger en enhetlig ram för alla länder i alla regioner med hänsyn till vissa krav i vissa länder. I följande avsnitt beskrivs allmänna informationsflödet som används för att ställa in och bearbeta registrering ID: N.

## <a name="registration-type-creation"></a>Skapa en registrering
Innan du kan ange registrerings-ID måste du ställa in Registreringstyper för olika typer av registreringsnummer som varje part som ingår i. Gå till **Organisationsadministration**&gt;**globala adressboken**&gt;**Registreringstyper**&gt;**Registreringstyper** att skapa och hantera Registreringstyper för leverantörer, kunder, personal och juridiska personer i olika länder/regioner.

|Fält                 |beskrivning      |
|------------------------------|----------------------------|                                                                           
| Namn                | Namnet på registreringstypen. |                                                                           
| beskrivning         | Beskrivning av registreringstypen. |
| Land/region      | Den unika identifieraren för landet/regionen.|
| Skattemyndighet       | Skattemyndigheten som associeras med registreringstypen.|
| Begränsat till       | Typ av begränsning som gäller för momsregistreringstypen: ingen Person i organisationen.|
| Format              | Formatet för registreringstypen validering.|
| Kan uppdateras      | Anger om registreringsnumret för registreringstypen kan uppdateras när det har placerats.|
| Unik              | Anger om registreringsnumret för registreringstypen är unikt. |
| Primärt för land | Om en part som är kopplad till en eller fler adresser bland annat land och registrerings-ID är giltig för alla adresser måste du ange en adress som primär för landet. Du kan bara registrera ett ID som primär. Anger om registreringsnummer anges endast som primär adress land. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Tilldela en registrering i en registreringskategori
Registreringskategori är godkänd för särskilt land/region för skatt, tull och andra ändamål land/region registrering identifierare. Den här kategorin definierar valideringsregler av viss registrerings-ID (inklusive kontrollsiffror etc.) och registrerings-ID för inkludering i olika rapporter. Sidan **Organisationsadministration**&gt;**globala adressboken**&gt;**Registreringstyper**&gt;**Registreringskategorier** att tilldela registreringskategori stöds registreringstyp för ett visst land.

| Fält            | beskrivning|
|-----------------------|----------------|
| Registreringstyp     | Registrering särskilt ange land/region.|
| Begränsat till         | Typ av begränsning gäller för momsregistreringstypen: ingen Person i organisationen.|
| Registreringskategori | Identifieraren unika registreringar godkänts för modulen landet. En fullständig lista över stöds i AX7.1 kategorier är lägre än. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Ange registrering ID för globala adressboksposter
Den globala adressboken (GAB) i Microsoft Dynamics 365 för operationer innehåller konsoliderade adressinformation för kunder, leverantörer, kontakter, affärsrelationer och juridiska personer. Mer information finns i [översikt över Global adressbok bok](/dynamics365/operations/organization-administration/overview-global-address-book). Partposter som lagras i den globala adressboken kan innehålla en eller flera poster. Dessa adresser används för olika ändamål såsom fakturering, eller delleverans. Du kan ställa in registrering ID för adressinformation för kunder, leverantörer, personal och juridiska personer. Registrera part (juridisk person, leverantör, kund, anställd) som du vill ange register-ID och klicka på Sök **registrering ID** rör part juridisk person, leverantör, kund, arbetare att öppna formulär i **hantera adresser** sida. På den **skatt registreringen** klickar du på **Lägg**, och ange följande information om registrering-ID.

|Fält                |beskrivning                                                |
|---------------------|-----------------------------------------------------------|
| Registreringstyp   | Registreringstyp det valda land/regionen.     |
| Organisationsnummer | Part registrering-ID.                                |
| beskrivning         | Beskrivning av registreringsnummer.               |
| Avdelning             | Ytterligare information om registreringsnummer. |
| Utfärdande organ      | Utfärdaren registreringsnummer.        |
| Utfärdat den         | Utfärdat den för registreringsnummer.              |
| Giltighet           | Registreringsnumret giltighetsdatum.           |
| Utgång          | Utgångsdatum för registreringsnummer.          |

> [!NOTE]
> Momsregistreringsnumret för den juridiska personen, leverantör, kund kan väljas från registrering skatten ID relaterade till moms-ID och angett partens.

## <a name="search-for-records-by-registration-id"></a>Söka efter poster av registrerings-ID.
Sök efter partposter utifrån ett registrerings-ID finns i formulär som är relaterade till part juridisk person, leverantör, kund och arbetare. Klicka på **registrerings-ID för sökning** att öppna den **sökvillkor registrerings-ID** sida. Ange sökvillkor och klicka på **söka efter**. De markerade posterna från den globala adressboken och associerade typer av ickepartspost visas.

## <a name="supported-registration-categories"></a>Stöds Registreringskategorier
I följande tabell visas Momsregistreringstyperna som stöds i Dynamics 365 för operationer. Om du är bekant med Microsoft Dynamics AX 2012-fält för registrering ID motsvarar i den här tabellen även fälten Dynamics 365 operationer för registrering.

| Dynamics 365 för registrering av operationer         |Land/region  | Termen Dynamics AX 2012/fält|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Moms-ID                                                        | Alla länder i den Europeiska unionen (EU)|  Momsregistreringsnummer (lagar typ SKATTE-ID i AX2012 R3)|
| Företags-ID (COID)                                          | Belgien, Tjeckien Estland Ungern Lettland Litauen Polen Schweiz | Registreringsnummer för Enterprise nummer (EnterpriseNumber) (RegNum\_W) registreringsnummer (RegNum\_W) registreringsnummer (RegNum\_W) registreringsnummer (RegNum\_W) registreringsnummer för Enterprise-kod (EnterpriseCode) (RegNum\_W) UID (lagar typ UID i AX2012 R3) |
| Filial-ID                                                     | Belgien            | Bankkontorets nummer (BranchNumber)|
| Spisová značka (registreringsnummer kreditkortsföretag avsnittet) | Tjeckien     | Nummerserie (CommercialRegisterInsetNumber) Kept indrag i handelsled register (CommercialRegister) delen av handelsregister (CommercialRegisterSection)|
| Tullkund-ID                                           | Finland | Tullens kundnummer (CustomsCustomerNumber\_FI)|
| INN                                                           | Ryska federationen| INN (lagar typ INN i AX2012 R3)|
| RRC                                                           | Ryska federationen| RRC (lagar typ RRC i AX2012 R3)|
| OKDP                                                          | Ryska federationen| OKDP (lagar typ OKDP i AX2012 R3)|
| OKPO                                                          | Ryska federationen| OKPO (lagar typ OKPO i AX2012 R3)|
| RCOAD                                                         | Ryska federationen| RCOAD (lagar typ RCOAD i AX2012 R3)|
| OGRN                                                          | Ryska federationen| OGRN (lagar typ OGRN i AX2012 R3) |
| SNILS                                                         | Ryska federationen| SNILS (lagar typ SNILS i AX2012 R3)|
| CIFTS                                                         | Ryska federationen| CIFTS (lagar typ CIFTS i AX2012 R3)|

Mer information om registrering ID bearbetning, inklusive komponenterna, se följande uppgift inspelningar för Momsregistreringsnummer Lifecycle Services (LCS):

-   Skapa moms-ID
-   Registrering av moms-ID för leverantör
-    Partsökning via moms-ID



