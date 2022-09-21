---
title: Översikt över momsberäkning
description: Detta ämne innehåller information om momsberäkningsfunktionens övergripande omfattning och funktioner.
author: EricWangChen
ms.date: 09/08/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.search.form: TaxIntegrationTaxServiceParameters
ms.openlocfilehash: a193db82b2b079c1e10fbfb6bfde7aa43b18bc4a
ms.sourcegitcommit: dbb997f252377b8884674edd95e66caf8d817816
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2022
ms.locfileid: "9465177"
---
# <a name="tax-calculation-overview"></a>Översikt över momsberäkning

[!include [banner](../includes/banner.md)]

Skatteberäkningen är en hyperskalbar tjänst för flera innehavare som gör det möjligt för den globala skattemotorn (Global Tax Engine) att automatisera och förenkla bestämmandet och beräkningsprocessen för skatt. Skattemotorn är helt konfigurerbar. Elementen som kan konfigureras är inklusive, men inte begränsat till, den beskattningsbara datamodellen, skattekoden, tillämplighetsmatrisen för skatt och beräkningsformeln för skatt. Skattemotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.

Momsberäkning integreras med Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.

> [!IMPORTANT]
> När du aktiverar tjänsten Momsberäkning kan vissa åtgärder på relaterade data utföras i ett annat datacenter än det datacenter som underhåller dina tjänstedata. Granska [Användarvillkoren](https://go.microsoft.com/fwlink/?linkid=2156043) innan du aktiverar Momsberäkning. Din sekretess är viktig för oss. Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).

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

- Asien och stillahavsområdet
- Australien
- Brasilien
- Kanada
- Europa
- Frankrike
- Indien
- Japan
- Sydafrika
- Schweiz
- Förenade Arabemiraten
- Storbritannien
- USA

> [!NOTE]
> Momsberäkning har inte stöd för tidigare version av Dynamics 365, exempelvis Dynamics AX 2012, eller en lokal distribution av Dynamics 365.

## <a name="versions"></a>Versioner
Vi rekommenderar att du importerar och ställer in din momsberäkningskonfiguration med den version som matchar din version av Finance eller Supply Chain Management.

| Finance eller Supply Chain Management version | Skattekonfigurationsversion               |
| --------------- | --------------------------------------- |
| 10.0.30         | Momsberäkningskonfiguration 40.55.239 |
| 10.0.29         | Momsberäkningskonfiguration 40.55.236 |
| 10.0.28         | Momsberäkningskonfiguration 40.54.234 |
| 10.0.27         | Momsberäkningskonfiguration 40.54.234 |


## <a name="data-flow"></a>Dataflöde

Här finns en översikt över dataflödesprocessen för momsberäkning. 

1. Visa och importera modellkonfigurationer för beskattningsbara dokument och modellmappningskonfigurationer. Om du måste utöka konfigurationer för ett avancerat scenario, se [Lägg till datafält i momskonfigurationer](tax-service-add-data-fields-tax-configurations.md).
2. Skapa eller underhåll momsfunktioner i RCS. Du kan använda momsfunktioner när du vill hantera momssatser och tillämplighetsregler för moms.
3. När konfigurationen av momsfunktionen är klar publicerar du momskonfigurationerna och momsfunktionerna från RCS till den globala databasen.
4. I Finance väljer du vilken konfigurationsversion för momsfunktionen som ska användas för en specifik juridisk person.
5. Du hanterar transaktioner i Finance och Supply Chain Management precis som vanligt. När momsberäkning behövs samlar klienten in information från transaktionen – till exempel försäljningsorder eller inköpsorder – och paketerar informationen som nyttolast. En begäran skickas sedan för beräkning av momsen.
6. Momsberäkningsförfrågan tas emot från klienten och beräkningen slutförs. Momsresultatet returneras sedan till klienten.
7. Dynamics 365-klienten får momsresultatet och visar resultatet av momsberäkningen på en momssida.

## <a name="supported-transactions"></a>Transaktioner som stöds

Momsberäkning kan aktiveras av transaktioner. 

I följande tabell visas en lista över de transaktioner som stöds i motsvarande version.

| Version | Transaktioner |
|---------|--------------|
| 10.0.29 | Periodiska journaler |
| 10.0.28 | Leverantörsbetalningsjournal<br> Kundbetalningsjournal | 
| 10.0.26 | Allmänna journaler<br> Leverantörsfakturajournal |
| 10.0.23 | Fritextfaktura |
| 10.0.21| Försäljning<br><ul><li>Försäljningsoffert</li><li>Försäljningsorder</li><li>Bekräftelse</li><li>Plocklista</li><li>Följesedel</li><li>Försäljningsfaktura</li><li>Kreditfaktura</li><li>Returorder</li><li>Övriga avgifter för rubrik</li><li>Övriga avgifter för rad</li></ul>Inköp<br><ul><li>Inköpsorder</li><li>Bekräftelse</li><li>Inleveranslista</li><li>Produktinleverans</li><li>Inköpsfaktura</li><li>Övriga avgifter för rubrik</li><li>Övriga avgifter för rad</li><li>Kreditfaktura</li><li>Returorder</li><li>Inköpsrekvisition</li><li>Övriga avgifter för inköpsrekvisitionsrad</li><li>Anbudsförfrågan</li><li>Övriga avgifter för anbudsförfråganrubriken</li><li>Övriga avgifter för anbudsförfråganraden</li></ul>Lager<ul><li>Överföringsorder - leverera</li><li>Överföringsorder – ta emot</li></ul>|

## <a name="supported-countriesregions"></a>Länder/regioner som stöds

Momsberäkning kan köras med de lokaliseringsfunktioner som stöds. Följande tabell listar länderna/regionerna för en juridisk persons primära adress.

| Version | Land/region |
|---------|----------------|
| 10.0.26 | - Kina <br>- Tjeckien<br>- Spanien |
| 10.0.24 | Mexiko |
| 10.0.23 | - Thailand <br>- Japan <br>- Malaysia <br>- Singapore |
| 10.0.22 | - Australien<br>- Bahrain <br>- Kanada<br>- Egypten <br>- Hong Kong SAR <br>- Kuwait <br>- Nya Zeeland <br>- Oman <br>- Qatar <br>- Saudiarabien <br>- Sydafrika <br>- Förenade Arabemiraten |
| 10.0.21 | - Österrike <br>- Belgien <br>- Danmark <br>- Estland <br>- Finland <br>- Frankrike <br>- Tyskland <br>- Ungern <br>- Island <br>- Irland <br>- Italien <br>- Lettland <br>- Litauen <br>- Nederländerna <br>- Norge <br>- Polen <br>- Sverige <br>- Schweiz <br>- Storbritannien <br>- USA |

I alla länder eller regioner som inte är lokaliserade av Microsoft kan momsberäkning också aktiveras och köras med andra globala funktioner.

## <a name="related-resources"></a>Relaterade resurser

[Kom i gång med skattetjänst](./global-get-started-with-tax-calculation-service.md)

[Flera momsregistreringsnummer](./emea-multiple-vat-registration-numbers.md)

[Skattefunktionsstöd för överföringsorder](./tasks/tax-feature-support-for-transfer-order.md)

[Så här skapar du tillägg i skattetjänst](./tax-service-add-data-fields-tax-integration-by-extension.md)
