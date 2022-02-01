---
title: Översikt över momsberäkning
description: Detta ämne innehåller information om skatteberäkningsfunktionens övergripande omfattning och funktioner.
author: wangchen
ms.date: 11/17/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b5f9f41bdadc76064aa9aee92e27e6b504baf461
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986026"
---
# <a name="tax-calculation-overview"></a>Översikt över momsberäkning

[!include [banner](../includes/banner.md)]

Skatteberäkningen är en hyperskalbar tjänst för flera innehavare som gör det möjligt för den globala skattemotorn (Global Tax Engine) att automatisera och förenkla bestämmandet och beräkningsprocessen för skatt. Skattemotorn är helt konfigurerbar. Elementen som kan konfigureras är inklusive, men inte begränsat till, den beskattningsbara datamodellen, skattekoden, tillämplighetsmatrisen för skatt och beräkningsformeln för skatt. Skattemotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.

Beräkningstjänsten för skatt går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.

> [!IMPORTANT]
> När du aktiverar tjänsten Momsberäkning kan vissa åtgärder på relaterade data utföras i ett annat datacenter än det datacenter som underhåller dina tjänstedata. Granska [Användarvillkoren](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) innan du aktiverar Momsberäkning. Din sekretess är viktig för oss. Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).

Momsberäkning är en mikrotjänstbaserad momsmotor som erbjuder exponentiell skalbarhet och kan hjälpa dig att utföra följande uppgifter:

- Automatiskt fastställa rätt momsgrupp, artikelskattegrupp och momskoder med hjälp av en förbättrad mekanism för bestämning.
- Stöd för flera momsregistreringsnummer i en och samma juridiska person, och automatiskt fastställande av korrekt momsregistreringsnummer för beskattningsbara transaktioner.
- Stöd för momsbestämning, beräkning, bokföring och kvittning för överföringsorder.
- Definiera konfigurerbara formler och villkor för momsberäkning för dina specifika affärsbehov.
- Dela lösningen för momsbestämning och beräkning mellan juridiska personer i syfte att spara underhållsarbete och undvika fel.
- Stöd för bestämning av kund- och leverantörsskattenummer.
- Bestämning av supportlistekoder.
- Stödparametrar för momsberäkning på skattemyndighetsnivå.

Om du vill använda beräkningstjänsten för moms ska du installera tillägget för momsberäkning från projektet i Microsoft Dynamics Lifecycle Services. Slutför sedan konfigurationen i [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) och aktivera funktionen Momsberäkning i Finance and Supply Chain Management. För mer information, se [Kom igång med skattetjänsten](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Tillgänglighet

Momsberäkning är vanligtvis tillgängligt i produktionsmiljöer för alla kunder i version 10.0.21.

Nya funktioner levereras även fortsättningsvis. Kontrollera den senaste versionsplanen ofta i syfte att ta reda på disponering och område för funktioner som stöds.

Skatteberäkningstjänsten distribueras på följande Azure-områden: Fler Azure-geologer kommer att läggas till baserat på kundernas behov.

- Asien och Stillahavsområdet
- Australien
- Kanada
- Europa
- Japan
- Storbritannien
- USA

> [!NOTE]
> Momsberäkning har inte stöd för tidigare version av Dynamics 365, exempelvis Dynamics AX 2012, eller en lokal distribution av Dynamics 365.

## <a name="versions"></a>Versioner
Vi rekommenderar att du importerar och ställer in din momsberäkningskonfiguration med den version som matchar din version av Finance eller Supply Chain Management.

| Finance eller Supply Chain Management version | Skattekonfigurationsversion               |
| --------------- | --------------------------------------- |
| 10.0.18         | Momskonfiguration - Europa 30.12.82     |
| 10.0.19         | Momsberäkningskonfiguration 36.38.193 |
| 10.0.20         | Momsberäkningskonfiguration 40.43.208 |
| 10.0.21         | Momsberäkningskonfiguration 40.48.215 |
| 10.0.22         | Momsberäkningskonfiguration 40.48.215 |
| 10.0.23         | Momsberäkningskonfiguration 40.50.221 |
| 10.0.24         | Momsberäkningskonfiguration 40.50.225 |


## <a name="data-flow"></a>Dataflöde

Här finns en översikt över dataflödesprocessen för momsberäkning. 

1. Visa och importera modellkonfigurationer för beskattningsbara dokument och modellmappningskonfigurationer. Om du måste utöka konfigurationer för ett avancerat scenario, se [Lägg till datafält i momskonfigurationer](tax-service-add-data-fields-tax-configurations.md).
2. Skapa eller underhåll momsfunktioner i RCS. Du kan använda momsfunktioner när du vill hantera momssatser och tillämplighetsregler för moms.
3. När konfigurationen av momsfunktionen är klar publicerar du momskonfigurationerna och momsfunktionerna från RCS till den globala databasen.
4. I Finance väljer du vilken konfigurationsversion för momsfunktionen som ska användas för en specifik juridisk person.
5. Du hanterar transaktioner i Finance och Supply Chain Management precis som vanligt. När momsberäkning behövs samlar klienten in information från transaktionen - till exempel försäljningsorder eller inköpsorder - och paketerar informationen som nyttolast. En begäran skickas sedan för beräkning av momsen.
6. Momsberäkningsförfrågan tas emot från klienten och beräkningen slutförs. Momsresultatet returneras sedan till klienten.
7. Dynamics 365-klienten får momsresultatet och visar resultatet av momsberäkningen på en momssida.

## <a name="supported-transactions"></a>Transaktioner som stöds

Momsberäkning kan aktiveras av transaktioner. 

Följande transaktioner stöds i version 10.0.21: 

- Försäljning

    - Försäljningsoffert
    - Försäljningsorder
    - Bekräftelse
    - Plocklista
    - Följesedel
    - Försäljningsfaktura
    - Kreditfaktura
    - Returorder
    - Övriga avgifter för rubrik
    - Övriga avgifter för rad

- Inköp

    - Inköpsorder
    - Bekräftelse
    - Inleveranslista
    - Produktinleverans
    - Inköpsfaktura
    - Övriga avgifter för rubrik
    - Övriga avgifter för rad
    - Kreditfaktura
    - Returorder
    - Inköpsrekvisition
    - Övriga avgifter för inköpsrekvisitionsrad
    - Anbudsförfrågan
    - Övriga avgifter för anbudsförfråganrubriken
    - Övriga avgifter för anbudsförfråganraden

- Lager

    - Överföringsorder - leverera
    - Överföringsorder - ta emot

Följande transaktioner stöds i version 10.0.23: 

- Fritextfaktura

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Momsberäkning kan aktiveras av juridisk person. 

Följande länder/regioner för en juridisk persons primära adress stöds i version 10.0.21:

- Österrike
- Belgien
- Danmark
- Estland
- Finland
- Frankrike
- Tyskland
- Ungern
- Island
- Italien
- Lettland
- Litauen
- Nederländerna
- Norge
- Polen
- Sverige
- Schweiz
- Storbritannien
- USA

Följande länder/regioner för en juridisk persons primära adress stöds i version 10.0.22:

- Australien
- Bahrain
- Kanada
- Egypten
- Hongkong SAR
- Kuwait
- Nya Zeeland
- Oman
- Qatar
- Saudiarabien
- Sydafrika
- Förenade Arabemiraten

Följande länder/regioner för en juridisk persons primära adress stöds i version 10.0.23:

- Thailand
- Japan
- Malaysia
- Singapore

Följande länder/regioner för en juridisk persons primära adress stöds i version 10.0.24:

- Mexiko

## <a name="related-resources"></a>Relaterade resurser

[Kom i gång med skattetjänst](./global-get-started-with-tax-calculation-service.md)

[Flera momsregistreringsnummer](./emea-multiple-vat-registration-numbers.md)

[Skattefunktionsstöd för överföringsorder](./tasks/tax-feature-support-for-transfer-order.md)

[Så här skapar du tillägg i skattetjänst](./tax-service-add-data-fields-tax-integration-by-extension.md)
