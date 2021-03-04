---
title: Registrerings-ID
description: Det här avsnittet innehåller information om hur du konfigurerar och använder registrerings-ID.
author: ShylaThompson
manager: AnnBe
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a0b978228e26ec70457a4bcb1c064070953909b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448158"
---
# <a name="registration-ids"></a>Registrerings-ID

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du konfigurerar och använder registrerings-ID.

Många länder och regioner har olika regler och krav för att registrera momsregistreringsnummer eller -ID. Det här avsnittet ger en översikt en över de inställningar och den bearbetning av stödda registreringstyper som krävs för parter i olika europeiska länder/regioner. Alla länder/regioner har sina krav för att stödja olika landsspecifika funktioner som berör registreringsnummer utfärdade av andra myndigheter. Exempel på registreringsnummer är socialförsäkringsnummer (social security number, SSN), skatteidentifieringsnummer (tax identification number, TIN) samt europeiskt moms-ID (EU moms-ID). Den här funktionen ger en enhetlig ram för alla länder i alla regioner med hänsyn till nationsspecifika krav i vissa europeiska länder. Följande avsnitt beskriver det generella flödet av information som används för att konfigurera och bearbeta registrerings-ID.

## <a name="registration-type-creation"></a>Skapa registreringstyp
Innan du kan ange ett registrerings-ID måste du ställa in momsregistreringstyper för de olika typer av registreringsnummer som varje part berörs av. Navigera till sidan **Organisationsadministration** &gt; **Global adressbok** &gt; **Registreringstyper** &gt; **Registreringstyper**  för att skapa och hantera registreringstyper för leverantörer, kunder, personal och juridiska personer i olika länder/regioner.

|Fält                 |beskrivning      |
|------------------------------|----------------------------|                                                                           
| Namn                | Namn på registreringstypen. |                                                                           
| beskrivning         | Beskrivningen av registreringstypen. |
| Land/region      | Unik identifierare för landet/regionen.|
| Skattemyndighet       | Den skattemyndighet som är associerad med registreringstypen.|
| Begränsat till       | Typ av begränsning som gäller för momsregistreringstypen: Ingen, Person, Organisation.|
| Format              | Valideringsformatet för momsregistreringstypen.|
| Kan uppdateras      | Anger om registreringsnumret för registreringstypen kan uppdateras efter det att den har angetts.|
| Unik              | Anger om registreringsnumret för registreringstypen är unikt. |
| Primärt för land | Om en part är associerad med en eller fler adresser i ett visst land och registrerings-ID är giltigt för alla adresser, måste du ange en adress som primär för landet. Du kan bara registrera ett ID som primärt. Anger om registreringsnummer kan anges endast som primär landsadress. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Tilldela en registreringstyp i en registreringskategori
Registreringskategori är registreringsidentifierare för land/region som har godkänts för användning i ett visst land/ en viss region i moms-, tull- och andra syften. Den här kategorin definierar valideringsregler för ett visst registrerings-ID (inklusive kontrollsiffror osv.) och registrerings-ID för inkludering i olika rapporter. Använd sidan **Organisationsadministration** &gt; **Global adressbok** &gt; **Registreringstyper** &gt; **Registreringskategorier** för att tilldela registreringstypen för ett visst land till en registreringskategori som stöds.

| Fält            | beskrivning|
|-----------------------|----------------|
| Registreringstyp     | Registreringstypen i ett visst land/en viss region.|
| Begränsat till         | Begränsningstypen gäller för momsregistreringstypen: Ingen, Person, Organisation.|
| Registreringskategori | Den unika registreringsidentifieraren som har godkänts för användning i landet. Den fullständiga listan med kategorier som stöds visas senare i det här avsnittet. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Ange registrerings-ID för globala adressboksposter

Den globala adressboken (GAB) innehåller konsoliderad adressinformation för kunder, leverantörer, kontakter, affärsrelationer och juridiska personer. Mer information finns i [Översikt över Global adressbok](../../fin-and-ops/organization-administration/overview-global-address-book.md). Partposterna som lagras i den globala adressboken kan innehålla en eller flera adressposter. Dessa adresser används för olika ändamål såsom fakturering, eller delleverans. Du kan ställa in registrerings-ID för adressinformation för kunder, leverantörer, personal och juridiska personer. Leta upp den partpost (juridisk person, leverantör, kund, anställd) som du vill ange register-ID för, klicka på **Registrerings-ID** på formulär som berör par, juridisk person, leverantör, kund eller arbetare för att öppna sidan **Hantera adresser**. På fliken **Momsregistrering** klickar du på **Lägg till** och anger följande information om registrerings-ID.


|Fält                |beskrivning                                                |
|---------------------|-----------------------------------------------------------|
| Registreringstyp   | Registreringstypen i valt land/vald region.     |
| Organisationsnummer | Registrerings-ID för parten.                                |
| beskrivning         | Beskrivningen av registreringsnumret.               |
| Avdelning             | Ytterligare information om registreringsnumret. |
| Utfärdande organ      | Den myndighet som utfärdade registreringsnumret.        |
| Utfärdat den         | Utfärdandedatum för registreringsnumret.              |
| Giltighet           | Giltighetsdatum för registreringsnumret.           |
| Utgång          | Utgångsdatumet för momsregistreringsnumret.          |

> [!NOTE]
> Momsbefrielsenumret för juridisk person, leverantör eller kund kan väljas från registrerings-ID relaterade till moms-ID och som angetts för parten.

## <a name="search-for-records-by-registration-id"></a>Söka efter poster efter registrerings-ID
Funktionen för att söka efter partposter utifrån ett registrerings-ID finns för formulär relaterade till part, juridisk person, leverantör, kund och arbetare. Klicka på **Söka registrerings-ID** för att öppna sidan **Sökvillkor för registrerings-ID**. Ange sökvillkor och klicka på **Sök**. De markerade posterna från den globala adressboken och associerade typer av partspost visas.

## <a name="supported-registration-categories"></a>Registreringskategorier som stöds
I följande tabell visas de registreringstyper som stöds. Om du är bekant med Microsoft Dynamics AX 2012-fält för registrerings-ID så mappar denna tabell även dessa fält till registreringskategorierna i Dynamics 365 Finance.

| Finance registreringskategori         |Land/region  | Term/fält för Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Moms-ID                                                        | Alla länder i den Europeiska unionen (EU)|  Momsfriskrivningsnummer (lagstiftande typ SKATTE-ID i AX 2012 R3)|
| Företags-ID (COID)                                          | Belgien, Tjeckien,Estland,Ungern,Lettland,Litauen,Polen,Schweiz | Företagsnummer (EnterpriseNumber) Registreringsnummer (RegNum\_W) Registreringsnummer (RegNum\_W) Registreringsnummer (RegNum\_W) Registreringsnummer (RegNum\_W) Företagskod (EnterpriseCode) Registreringsnummer (RegNum\_W) UID (Lagstiftande typ UID i AX 2012 R3) |
| Filial-ID                                                     | Belgien            | Filialnummer (BranchNumber)|
| Spisová značka (registreringsnummer, utfärdande organ, avsnitt) | Tjeckien     | Infällt nummer (CommercialRegisterInsetNumber) Förvaras i avsnittet Handelsregister (CommercialRegister) i handelsregistret (CommercialRegisterSection)|
| Tullkund-ID                                           | Finland | Kundnummer för tull (CustomsCustomerNumber\_FI)|
| INN                                                           | Ryska federationen| INN (lagstiftande typ INN i AX 2012 R3)|
| RRC                                                           | Ryska federationen| RRC (lagstiftande typ RRC i AX 2012 R3)|
| OKDP                                                          | Ryska federationen| OKDP (lagstiftande typ OKDP i AX 2012 R3)|
| OKPO                                                          | Ryska federationen| OKPO (lagstiftande typ OKPO i AX 2012 R3)|
| RCOAD                                                         | Ryska federationen| RCOAD (lagar typ RCOAD i AX 2012 R3)|
| OGRN                                                          | Ryska federationen| OGRN (lagstiftande typ OGRN i AX 2012 R3) |
| SNILS                                                         | Ryska federationen| SNILS (lagstiftande typ SNILS i AX 2012 R3)|
| CIFTS                                                         | Ryska federationen| CIFTS (lagstiftande typ CIFTS i AX 2012 R3)|
| Pass                                                      | Spanien             | Pass|
| Officiellt ID-dokument                              | Spanien             | Officiellt ID-dokument|
| Uppehållstillstånd                                         | Spanien             | Uppehållstillstånd|
| Annat ID-dokument                                 | Spanien             | Annat ID-dokument|
| Ingår inte i befolkningsräkningen                                                  | Spanien             | Inte tillgängligt i AX 2012 R3|


Mer information om bearbetning av registrerings-ID, inklusive erforderliga förutsättningar, se följande uppgiftsinspelningar för moms-ID i Lifecycle Services (LCS):

-   Skapa moms-ID
-   Registrering av moms-ID för leverantör
-    Partsökning via moms-ID






[!INCLUDE[footer-include](../../includes/footer-banner.md)]