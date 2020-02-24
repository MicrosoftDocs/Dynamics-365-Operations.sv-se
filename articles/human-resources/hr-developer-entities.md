---
title: Common Data Service-entiteter
description: Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010647"
---
# <a name="common-data-service-entities"></a>Common Data Service-entiteter

Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.

Mer information om Common Data Service, se [Vad är Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Följande personalentiteter är tillgängliga i Common Data Service.

## <a name="benefit-entities"></a>Förmånsentiteter

**Frekvens i förmånsberäkning**

| **Fält**        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------|---------------|--------------|----------------|
| Beskrivning       | Text          |              | X              |
| Frekvenskontroll | Alternativuppsättning    | X            | X              |
| Är oåterkallelig      | Två alternativ   |              | X              |
| Namn              | Text          | X            | X              |


**Tariff för förmånsberäkning**

| **Fält**  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------|---------------|--------------|----------------|
| Beskrivning | Text          |              | X              |
| Namn        | Text          | X            | X              |
| TierType    | Alternativuppsättning    | X            | X              |


**Uppgift om tariff för förmånsberäkning**

| **Fält**                             | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|----------------------------------------|----------------|--------------|----------------|
| Uppgiftsnummer för tariff för förmånsberäkning | Text           | X            | X              |
| Beräkningstariff-ID                    | Slå upp         | X            | X              |
| Lönetilläggsmetod                    | Alternativuppsättning     | X            | X              |
| Giltighet                              | Endast datum      | X            | X              |
| Arbetsgivarbidrag                  | Decimalnummer |              | X              |
| Förfallotid                             | Endast datum      | X            | X              |
| WorkerDeduction                        | Decimalnummer |              | X              |


**Förmånstyp**

| **Fält**           | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------|---------------|--------------|----------------|
| ConcurrentEnrollment | Alternativuppsättning    |              | X              |
| Beskrivning          | Text          |              | X              |
| Namn                 | Text          | X            | X              |
| PayrollCategory      | Alternativuppsättning    |              | X              |


**Förmånsplan**

| **Fält**                               | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|------------------------------------------|----------------|--------------|----------------|
| Gränsmetod för restbelopp                      | Alternativuppsättning     |              | X              |
| Förmånstyp                             | Slå upp         | X            | X              |
| Begränsningsmetod för lönetillägg                | Alternativuppsättning     |              | X              |
| Lönetilläggsmetod                      | Alternativuppsättning     |              | X              |
| Valuta                                 | Slå upp         |              | X              |
| Avdragsprioritet                       | Heltal   |              | X              |
| Gränsbelopp för standardtillägg        | Valuta       |              | X              |
| Standardtilläggsbelopp (bas) | Valuta       |              | X              |
| Gränsperiod för standardtillägg        | Alternativuppsättning     |              | X              |
| Gränsbelopp för standardavdrag           | Valuta       |              | X              |
| Standardavdragsbelopp (bas)    | Valuta       |              | X              |
| Gränsperiod för standardavdrag           | Alternativuppsättning     |              | X              |
| Beskrivning                              | Text           |              | X              |
| Valutakurs                            | Decimalnummer |              | X              |
| Är ytterligare en lönekörning                | Två alternativ    |              | X              |
| Är rapporterbar enligt Affordable Care Act        | Två alternativ    |              | X              |
| Genereras av restbelopp                      | Två alternativ    |              | X              |
| Är bruttolön                              | Två alternativ    |              | X              |
| Är primär                               | Två alternativ    |              | X              |
| Namn                                     | Text           | X            | X              |
| Effekt på lön                           | Alternativuppsättning     |              | X              |
| Pensioneringstyp                          | Alternativuppsättning     |              | X              |


**Entiteten anställning**

| **Fält**                     | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|--------------------------------|----------------|--------------|----------------|
| Justerat startdatum för arbetare     | Datum och tid  |              | X              |
| Företag                        | Slå upp         | X            | X              |
| Enhetsbelopp för arbetsgivarens varsel | Decimalnummer |              | X              |
| Enhet för arbetsgivarens varsel        | Alternativuppsättning     |              | X              |
| Slutdatum för anställning            | Datum och tid  |              | X              |
| Anställningsnummer              | Text           | X            | X              |
| Startdatum för anställning          | Datum och tid  |              | X              |
| Senaste arbetsdag              | Datum och tid  |              | X              |
| Övergångsdatum                | Datum och tid  |              | X              |
| Giltig från                     | Datum och tid  | X            | X              |
| Giltig till                       | Datum och tid  |              | X              |
| Arbetare                         | Slå upp         | X            | X              |
| Arbetarens uppsägningsbelopp           | Decimalnummer |              | X              |
| Arbetarens startdatum             | Datum och tid  |              | X              |
| Typ av arbetare                    | Alternativuppsättning     | X            | X              |
| Enhet för arbetarens varsel          | Alternativuppsättning     |              | X              |

## <a name="worker-entities"></a>Entiteter för arbetare

**Etniskt ursprung**

| **Fält**         | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|--------------------|---------------|--------------|----------------|
| Beskrivning        | Text          |              | X              |
| Etniskt ursprungsnamn | Text          | X            | X              |


**Språk**

| **Fält**    | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|---------------|---------------|--------------|----------------|
| Beskrivning   | Text          |              | X              |
| Namn på språk | Text          | X            | X              |


**Veteranstatus**

| **Fält**           | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------|---------------|--------------|----------------|
| Beskrivning          | Text          |              | X              |
| Är skyddad veteran | Två alternativ    |              | X              |
| Namn på språk        | Text          | X            | X              |


**Arbetare**

| **Fält**                | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|---------------------------|---------------|--------------|----------------|
| Födelsedatum                 | Endast datum     |              | X              |
| Beskrivning               | Text          |              | X              |
| E-postadress 1           | E-postadress         |              | X              |
| E-postadress 2           | E-postadress         |              | X              |
| Facebook-identitet         | Text          |              | X              |
| Förnamn                | Text          |              | X              |
| Fullständigt namn                 | Text          |              | X              |
| Kön                    | Alternativuppsättning    |              | X              |
| Generering                | Text          |              | X              |
| Är kontakt via e-post tillåten  | Två alternativ   |              | X              |
| Är kontakt via telefon tillåten  | Två alternativ   |              | X              |
| Efternamn                 | Text          |              | X              |
| LinkedIn-identitet         | Text          |              | X              |
| VD                   | Slå upp        |              | X              |
| Mellannamn               | Text          |              | X              |
| Mobiltelefon              | Telefon         |              | X              |
| Office Graph-ID   | Text          |              | X              |
| Primär e-postadress     | E-postadress         |              | X              |
| Primär telefon         | Telefon         |              | X              |
| Yrke                | Text          |              | X              |
| Sociala nätverk 1          | Alternativuppsättning    |              | X              |
| Sociala nätverk 2          | Alternativuppsättning    |              | X              |
| ID för socialt nätverk 1 | Text          |              | X              |
| ID för socialt nätverk 2 | Text          |              | X              |
| Källa                    | Alternativuppsättning    | X            | X              |
| Status                    | Alternativuppsättning    | X            | X              |
| Telefon 1               | Telefon         |              | X              |
| Telefon 2               | Telefon         |              | X              |
| Telefon 3               | Telefon         |              | X              |
| Twitter-identitet          | Text          |              | X              |
| Användare                      | Slå upp        |              | X              |
| Webbplatsens URL               | URL           |              | X              |
| Arbetarnummer             | Text          | X            | X              |
| Typ av arbetare               | Alternativuppsättning    | X            | X              |
| Yomi förnamn           | Text          |              | X              |
| Yomi fullständigt namn            | Text          |              | X              |
| Yomi efternamn            | Text          |              | X              |
| Yomi mellannamn          | Text          |              | X              |


**Arbetarens adress**

| **Fält**           | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|----------------------|----------------|--------------|----------------|
| Adressnummer       | Text           | X            | X              |
| Adresstyp         | Alternativuppsättning     | X            | X              |
| Ort                 | Text           |              | X              |
| Land eller region    | Text           |              | X              |
| Län               | Text           |              | X              |
| Fax                  | Telefon          |              | X              |
| Är prioriterad         | Två alternativ    |              | X              |
| Breddgrad             | Decimalnummer |              | X              |
| Rad 1               | Text           |              | X              |
| Rad 2               | Text           |              | X              |
| Rad 3               | Text           |              | X              |
| Longitud            | Decimalnummer |              | X              |
| Postnummer          | Text           |              | X              |
| Postbox      | Text           |              | X              |
| Leveransmetodkod | Heltal   |              | X              |
| Delstat eller region    | Text           |              | X              |
| Telefon 1          | Telefon          |              | X              |
| Telefon 2          | Telefon          |              | X              |
| Telefon 3          | Telefon          |              | X              |
| UPS-zon             | Text           |              | X              |
| UTC-förskjutning           | Heltal   |              | X              |
| Arbetare               | Slå upp         | X            | X              |


**Arbetarens personuppgift**

| Fält                             | Datatyp    | Obligatoriskt | Sökbart |
|------------------------------------|--------------|----------|------------|
| Födelseort                         | Text         |          | X          |
| Födelseland eller region            | Alternativuppsättning   |          | X          |
| Födelsedatum                          | Endast datum    |          | X          |
| Hemland eller region      | Alternativuppsättning   |          | X          |
| Avliden den                      | Endast datum    |          | X          |
| Inaktiverat verifieringsdatum för veteran | Endast datum    |          | X          |
| Utbildning                          | Text         |          | X          |
| Etniskt ursprung                     | Slå upp       |          | X          |
| ExpatriateEndDate                  | Endast datum    |          | X          |
| ExpatriateStartDate                | Endast datum    |          | X          |
| Faderns födelseland eller region     | Alternativuppsättning   |          | X          |
| Kön                             | Alternativuppsättning   |          | X          |
| Är inaktiverat                        | Två alternativ  |          | X          |
| Är veteran med funktionshinder                | Två alternativ  |          | X          |
| Gäller regler för utlandstjänst    | Två alternativ  |          | X          |
| Är heltidsstudent               | Två alternativ  |          | X          |
| Civilstånd                     | Alternativuppsättning   |          | X          |
| Slutdatum för militärtjänstgöring          | Endast datum    |          | X          |
| Startdatum för militärtjänstgöring        | Endast datum    |          | X          |
| Moderns födelseland eller region     | Alternativuppsättning   |          | X          |
| Medborgarskap, land eller region      | Alternativuppsättning   |          | X          |
| Modersmål                    | Slå upp       |          | X          |
| Antal beroenden               | Heltal |          |            |
| Veteranstatus                     | Slå upp       |          | X          |
| Arbetare                             | Slå upp       | X        | X          |
| Arbetarens personnummer      | Text         | X        | X          |


**Bankkonto för arbetare**

| **Fält**                 | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------------|---------------|--------------|----------------|
| Kontoinnehavare             | Text          |              | X              |
| Kontoidentifiering     | Text          |              | X              |
| Adressbeskrivning        | Text          |              | X              |
| Bankkontotyp          | Alternativuppsättning    |              | X              |
| Bankplatskod         | Text          |              | X              |
| Namn på filial                | Text          |              | X              |
| Filialnummer              | Text          |              | X              |
| Ort                       | Text          |              | X              |
| Land eller region          | Text          |              | X              |
| Län                     | Text          |              | X              |
| Beskrivning                | Text          |              | X              |
| Namn på distrikt              | Text          |              | X              |
| E-postadress                      | Text          |              | X              |
| Anknytning                  | Text          |              | X              |
| Fax                        | Text          |              | X              |
| IBAN                       | Text          |              | X              |
| Rad 1                     | Text          |              | X              |
| Rad 2                     | Text          |              | X              |
| Rad 3                     | Text          |              | X              |
| Mobiltelefon               | Text          |              | X              |
| Namn på person             | Text          |              | X              |
| Postnummer                | Text          |              | X              |
| Postbox            | Text          |              |                |
| Organisationsnummer             | Text          |              | X              |
| Typ av clearingnummer        | Alternativuppsättning    |              | X              |
| Delstat eller region          | Text          |              | X              |
| SWIFT-kod                 | Text          |              | X              |
| Telefon                  | Text          |              | X              |
| Telexnr               | Text          |              | X              |
| Webbplatsens URL                | Text          |              | X              |
| Arbetare                     | Slå upp        | X            | X              |
| Bankkontonummer för arbetare | Text          |              | X              |
| Bankkontonummer för arbetare | Text          | X            | X              |

**Fast arbetarkompensation**

| Fält                                | Datatyp      | Obligatoriskt | Sökbart |
|---------------------------------------|----------------|----------|------------|
| Företag                               | Slå upp         | X        | X          |
| Kompensationstyp                     | Alternativuppsättning     |          | X          |
| Valuta                              | Slå upp         |          | X          |
| Gäller från                        | Endast datum      |          | X          |
| Händelse                                 | Slå upp         | X        | X          |
| Valutakurs                         | Decimalnummer |          | X          |
| Utgångsdatum                       | Endast datum      |          | X          |
| Radnummer                           | Decimalnummer |          | X          |
| Lönefrekvens                         | Slå upp         | X        | X          |
| Lönesats                              | Valuta       |          | X          |
| Lönesats (bas)                       | Valuta       |          | X          |
| Plan                                  | Slå upp         | X        | X          |
| Befattning                              | Slå upp         | X        | X          |
| Processtyp                          | Alternativuppsättning     | X        | X          |
| Inställningsrad för referenspunkt            | Slå upp         |          | X          |
| Arbetare                                | Slå upp         | X        | X          |
| Fast arbetarkompensationsnummer      | Text           | X        | X          |

**Arbetsidentifieringsnummer**

| Fält                 | Datatyp   | Obligatoriskt | Sökbart |
|------------------------|-------------|----------|------------|
| Beskrivning            | Text        |          | X          |
| Inmatningstyp             | Text        |          | X          |
| Utgångsdatum        | Endast datum   |          | X          |
| ID-nummer  | Text        | X        | X          |
| ID-typ    | Slå upp      | X        | X          |
| Är primär             | Två alternativ |          | X          |
| Utfärdandedatum             | Endast datum   |          | X          |
| Utfärdande organ         | Slå upp      | X        | X          |
| Arbetare                 | Slå upp      | X        | X          |


## <a name="position-entities"></a>Befattningsenheter

**Jobbefattning**

| **Fält**               | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|--------------------------|----------------|--------------|----------------|
| Aktivering               | Datum och tid  |              | X              |
| Tillgänglig för tilldelning | Datum och tid  |              | X              |
| Avdelning               | Slå upp         |              | X              |
| Beskrivning              | Text           |              | X              |
| Heltidslön     | Decimalnummer |              | X              |
| Befattning                      | Slå upp         | X            | X              |
| Jobbefattningsnummer      | Text           | X            | X              |
| Överordnad Jobbefattning      | Slå upp         |              | X              |
| Befattningstyp            | Slå upp         |              | X              |
| Pension               | Datum och tid  |              | X              |
| Rubrik                    | Alternativuppsättning     |              | X              |
| Giltig från               | Datum och tid  | X            | X              |
| Giltig till                 | Datum och tid  |              | X              |


**Befattningstyp**

| **Fält**         | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|--------------------|---------------|--------------|----------------|
| Klassificering     | Alternativuppsättning    |              | X              |
| Beskrivning        | Text          |              | X              |
| Befattningstypens namn | Text          | X            | X              |


**Befattningstilldelning för arbetare**

| **Fält**                        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------------------------|---------------|--------------|----------------|
| Jobbefattning                      | Slå upp        | X            | X              |
| Befattningstilldelningsnummer för arbetare | Text          | X            | X              |
| Giltig från                        | Text          | X            | X              |
| Giltig till                          |               |              | X              |
| Arbetare                            |               | X            | X              |

## <a name="job-entities"></a>Jobbenheter

**Jobb**

| **Fält**                   | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|------------------------------|----------------|--------------|----------------|
| Tillåt obegränsade befattningar    | Två alternativ    |              | X              |
| Heltidslön | Decimalnummer |              | X              |
| Beskrivning                  | Text           |              | X              |
| Jobbeskrivning              | Text           |              | X              |
| Jobbfunktion                 | Slå upp         |              | X              |
| Jobbtyp                     | Slå upp         |              | X              |
| Maximalt antal befattningar  | Heltal   |              | X              |
| Namn                         | Text           | X            | X              |
| Rubrik                        | Alternativuppsättning     |              | X              |
| Giltig från                   | Datum och tid  | X            | X              |
| Giltig till                     | Datum och tid  |              | X              |


**Jobbfunktion**

| **Fält**        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------|---------------|--------------|----------------|
| Beskrivning       | Text          | X            | X              |
| Jobbfunktionsnamn | Text          | X            | X              |


**Jobbtyp**

| **Fält**    | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|---------------|---------------|--------------|----------------|
| Beskrivning   | Text          | X            | X              |
| Befrielsestatus | Alternativuppsättning    | X            | X              |
| Jobbtypnamn | Text          | X            | X              |

## <a name="leave-and-absence-entities"></a>Enheter för tjänstledighet och frånvaro

**Anmälan om tjänstledighet**

| **Fält**            | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------------|---------------|--------------|----------------|
| Underlag för periodiseringsdatum    | Endast datum     | X            | X              |
| Startdatum för periodiseringsperiod    | Endast datum     | X            | X              |
| Anpassat datum           | Endast datum     | X            | X              |
| Är periodisering uppskjuten  | Två alternativ   |              | X              |
| LeaveEnrollmentNumber | Text          | X            | X              |
| Tjänstledighetsplan            | Slå upp        | X            | X              |
| Startdatum            | Endast datum     | X            | X              |
| Grundnivå            | Alternativuppsättning    | X            | X              |
| Arbetare                | Slå upp        | X            | X              |


**Banktransaktion för tjänstledighet**

| **Fält**                    | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|-------------------------------|----------------|--------------|----------------|
| Tid                        | Decimalnummer | X            | X              |
| Företag                       | Slå upp         | X            | X              |
| Banktransaktionsnummer för tjänstledighet | Text           | X            | X              |
| Tjänstledighetsplan                    | Slå upp         |              | X              |
| Tjänstledighetstyp                    | Slå upp         | X            | X              |
| Transaktionsdatum              | Endast datum      | X            | X              |
| Transaktionsnummer            | Decimalnummer | X            | X              |
| Transaktionstyp              | Alternativuppsättning     | X            | X              |
| Arbetare                        | Slå upp         | X            | X              |


**Tjänstledighetsplan**

| **Fält**        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------|---------------|--------------|----------------|
| Periodiseringsfrekvens | Alternativuppsättning    | X            | X              |
| Företag           | Slå upp        | X            | X              |
| Beskrivning       | Text          |              | X              |
| Tjänstledighetstyp        | Slå upp        | X            | X              |
| Namn              | Text          | X            | X              |
| Startdatum        | Endast datum     | X            | X              |


**Begäran om tjänstledighet**

| **Fält**           | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------|---------------|--------------|----------------|
| Kommentar              | Text          | X            | X              |
| Företag              | Slå upp        | X            | X              |
| Nummer på begäran om tjänstledighet | Text          |              | X              |
| Datum för förfrågan         | Datum och tid | X            | X              |
| Status               | Alternativuppsättning    | X            | X              |
| Arbetare               | Slå upp        | X            | X              |


**Information om begäran om tjänstledighet**

| **Fält**                  | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|-----------------------------|----------------|--------------|----------------|
| Tid                      | Decimalnummer | X            | X              |
| Tjänstledighetens slutdatum                  | Datum och tid  | X            | X              |
| Begäran om tjänstledighet               | Slå upp         | X            | X              |
| Informationsnummer för begäran om tjänstledighet | Text           | X            | X              |
| Tjänstledighetstyp                  | Slå upp         | X            | X              |


**Tjänstledighetstyp**

| **Fält**      | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------|---------------|--------------|----------------|
| Företag         | Slå upp        | X            | X              |
| Beskrivning     | Text          |              | X              |
| Inkomstkod    | Slå upp        |              | X              |
| Namn på tjänstledighetstyp | Text          | X            | X              |


**Arbetskalender**

| **Fält**  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------|---------------|--------------|----------------|
| Företag     | Slå upp        | X            | X              |
| Beskrivning | Text          |              | X              |
| Namn        | Text          | X            | X              |


**Arbetsdagar i kalendern**

| **Fält**               | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|--------------------------|---------------|--------------|----------------|
| Kalenderdatum            | Endast datum     | X            | X              |
| Företag                  | Slå upp        |              | X              |
| Status                   | Text          |              | X              |
| Arbetskalender            | Slå upp        | X            | X              |
| Nummer för arbetsdag i kalendern | Text          | X            | X              |


**Helgdag i arbetskalender**

| **Fält**  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------|---------------|--------------|----------------|
| Namn        | Text          |              | X              |
| Beskrivning | Text          | X            | X              |


**Rad för helgdag i arbetskalender**

| **Fält**                        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------------------------|---------------|--------------|----------------|
| Datum för helgdag                      | Endast datum     | X            | X              |
| Namn                              | Text          |              | X              |
| Helgdag i arbetskalender             | Slå upp        | X            | X              |
| Radnummer för helgdag i arbetskalender | Text          | X            | X              |


**Tidsintervall till arbetskalendern**

| **Fält**                         | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|------------------------------------|---------------|--------------|----------------|
| Företag                            | Slå upp        |              | X              |
| Sluttid                           | Heltal  |              | X              |
| Starttid                         | Heltal  |              | X              |
| Arbetskalender                      | Slå upp        | X            | X              |
| Arbetsdagar i kalendern                  | Slå upp        | X            | X              |
| Tidsintervallnummer till arbetskalendern | Text          | X            | X              |

## <a name="organization-entities"></a>Organisationsenheter

**Företag**

| **Fält**   | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|--------------|---------------|--------------|----------------|
| Företagskod | Text          | X            | X              |
| Namn         | Text          | X            | X              |


**Avdelning**

| **Fält**        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------|---------------|--------------|----------------|
| Avdelningsnummer | Text          | X            | X              |
| Beskrivning       | Text          |              | X              |
| Namn              | Text          | X            | X              |
| Överordnad avdelning | Slå upp        |              | X              |


**Valuta**

| **Fält**         | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|--------------------|----------------|--------------|----------------|
| Valutakod      | Text           | X            | X              |
| Valutanamn      | Text           | X            | X              |
| Valutaprecision | Heltal   | X            | X              |
| Valutasymbol    | Text           | X            | X              |
| Enhetsbild       | Bild          |              |                |
| Valutakurs      | Decimalnummer | X            | X              |
| Organisation       | Slå upp         | X            | X              |
| Status             | Alternativuppsättning     |              | X              |

## <a name="payroll-entities"></a>Löneenheter

**Lönecykel**

| **Fält**  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------|---------------|--------------|----------------|
| Beskrivning | Text          | X            | X              |
| Frekvens   | Alternativuppsättning    | X            | X              |
| Namn        | Text          | X            | X              |


**Löneperiod**

| **Fält**           | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------|---------------|--------------|----------------|
| Standardbetalningsdatum | Endast datum     |              | X              |
| Beskrivning          | Text          |              | X              |
| Lönecykel            | Visa          | X            | X              |
| Betalningsperiodnummer    | Text          | X            | X              |
| Slutdatum för period      | Endast datum     | X            | X              |
| Startdatum för period    | Endast datum     | X            | X              |
| Status               | Alternativuppsättning    |              | X              |


**Inkomstkod för lön**

| **Fält**              | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------------|---------------|--------------|----------------|
| Beskrivning             | Text          | X            | X              |
| Inkludera i betalningstyp | Alternativuppsättning    | X            | X              |
| Är produktiv           | Två alternativ   | X            | X              |
| Namn                    | Text          |              | X              |
| Kvantitetsenhet           | Alternativuppsättning    |              | X              |
| Spåra FMLA-timmar        | Två alternativ   |              | X              |


**Skatteregion**

| **Fält**        | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------|---------------|--------------|----------------|
| Ort              | Text          |              | X              |
| Land eller region | Text          |              | X              |
| Län            | Text          |              | X              |
| Namn              | Text          | X            | X              |
| Delstat eller region | Text          |              | X              |


**Löneperiod med frekvens i förmånsberäkning**

| **Fält**                                      | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-------------------------------------------------|---------------|--------------|----------------|
| Frekvens i förmånsberäkning                   | Slå upp        | X            | X              |
| Löneperiodnummer med frekvens i förmånsberäkning | Text          | X            | X              |
| Löneperiod                                      | Slå upp        | X            | X              |


**Bankkontoutbetalningar**

| **Fält**                       | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|----------------------------------|----------------|--------------|----------------|
| Tid                           | Valuta       |              | X              |
| Belopp (bas)                    | Valuta       |              | X              |
| Bankkonto                     | Slå upp         | X            | X              |
| Nummer för bankkontoutbetalningar | Text           | X            | X              |
| Företag                          | Slå upp         | X            | X              |
| Valuta                         | Slå upp         |              | X              |
| Valutakurs                    | Decimalnummer |              | X              |
| Är påminnelse                     | Två alternativ    |              | X              |
| Prioritet                         | Heltal   |              | X              |

**Utfärdande organ personidentifiering**

| **Fält**           | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|----------------------|---------------|--------------|----------------|
| Adressbeskrivning  | Text          |              | X              |
| Adressrad 1       | Text          |              | X              |
| Adressrad 2       | Text          |              | X              |
| Adressrad 3       | Text          |              | X              |
| Ort                 | Text          |              | X              |
| Land eller region    | Alternativuppsättning    |              | X              |
| Län               | Text          |              | X              |
| Beskrivning          | Text          |              | X              |
| E-postadress                | Text          |              | X              |
| Anknytning            | Text          |              | X              |
| Fax                  | Text          |              | X              |
| Utfärdande organets namn  | Text          | X            | X              |
| Mobiltelefon         | Text          |              | X              |
| Sida                 | Text          |              | X              |
| Postnummer          | Text          |              | X              |
| Postbox      | Text          |              | X              |
| SMS                  | Text          |              | X              |
| Delstat eller region    | Text          |              | X              |
| Telefon            | Text          |              | X              |
| Telex                | Text          |              | X              |
| Webbplatsens URL          | Text          |              | X              |

**Arbetsidentifieringstyp**

| **Fält**                        | **Datatyp**  | **Obligatoriskt** | **Sökbart** |
|-----------------------------------|----------------|--------------|----------------|
| Tillåtna värden                    | Alternativuppsättning     |              | X              |
| Land eller region                 | Text           |              | X              |
| Beskrivning                       | Text           |              | X              |
| Fast längd                      | Heltal   |              | X              |
| ID-nummerformat      | Text           |              | X              |
| Typ                              | Alternativuppsättning     |              | X              |
| Arbetsidentifieringstyp | Text           | X            | X              |

## <a name="fixed-compensation-entities"></a>Enheter för fast kompensation

**Fast kompensationsplan**

| **Fält**                  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------------------|---------------|--------------|----------------|
| Företag                     | Slå upp        | X            | X              |
| Kompensationsrutnät           | Slå upp        |              | X              |
| Valuta                    | Slå upp        | X            | X              |
| Beskrivning                 | Text          | X            | X              |
| Gäller från              | Endast datum     | X            | X              |
| Utgångsdatum             | Endast datum     | X            | X              |
| Anställningsregel                   | Alternativuppsättning    | X            | X              |
| Namn                        | Text          | X            | X              |
| Tolerans utanför intervallet      | Alternativuppsättning    | X            | X              |
| Lönefrekvens               | Slå upp        | X            | X              |
| Rekommendation tillåts      | Två alternativ   | X            | X              |
| Radinställning för referenspunkt  | Slå upp        |              | X              |
| Typ                        | Alternativuppsättning    | X            | X              |

**Kompensationsrutnät**

| **Fält**                  | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------------------|---------------|--------------|----------------|
| Företag                     | Slå upp        | X            | X              |
| Valuta                    | Slå upp        |              | X              |
| Beskrivning                 | Text          | X            | X              |
| Gäller från              | Endast datum     |              | X              |
| Utgångsdatum             | Endast datum     |              | X              |
| Namn                        | Text          | X            | X              |
| Referenspunktsinställning       | Slå upp        | X            | X              |
| Typ                        | Alternativuppsättning    | X            | X              |

**Kompensationsnivå**

| **Fält**      | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------|---------------|--------------|----------------|
| Beskrivning     | Text          |              | X              |
| Namn            | Text          | X            | X              |
| Typ            | Alternativuppsättning     | X            | X              |

**Lönefrekvens för kompensation**

| **Fält**                  | **Datatyp**   | **Obligatoriskt** | **Sökbart** |
|-----------------------------|-----------------|--------------|----------------|
| Årskonverteringsfaktor    | Decimalnummer  |              | X              |
| Företag                     | Slå upp          | X            | X              |
| Beskrivning                 | Text            |              | X              |
| Timkonverteringsfaktor    | Decimalnummer  |              | X              |
| Månadskonverteringsfaktor   | Decimalnummer  |              | X              |
| Namn                        | Text            | X            | X              |
| Period                      | Alternativuppsättning      |              | X              |
| Veckokonverteringsfaktor    | Alternativuppsättning      |              | X              |


**Kompensationsreferenspunkt**

| **Fält**          | **Datatyp**   | **Obligatoriskt** | **Sökbart** |
|---------------------|-----------------|--------------|----------------|
| Företag             | Slå upp          | X            | X              |
| Kompensationstyp   | Alternativuppsättning      | X            | X              |
| Beskrivning         | Text            | X            | X              |
| Namn                | Text            | X            | X              |

**Ställ in kompensationsreferenspunkt**

| **Fält**            | **Datatyp**   | **Obligatoriskt** | **Sökbart** |
|-----------------------|-----------------|--------------|----------------|
| Företag               | Slå upp          | X            | X              |
| Beskrivning           | Text            | X            | X              |
| Radnummer           | Decimalnummer  | X            | X              |
| Namn                  | Text            | X            | X              |
| Referenspunktsinställning | Slå upp          | X            | X              |

**Kompensationsregion**

| **Fält**      | **Datatyp** | **Obligatoriskt** | **Sökbart** |
|-----------------|---------------|--------------|----------------|
| Beskrivning     | Text          | X            | X              |
| Namn            | Text          | X            | X              |

**Kompensationsstruktur**

| **Fält**                    | **Datatyp**   | **Obligatoriskt** | **Sökbart** |
|-------------------------------|---------------  |--------------|----------------|
| Tid                        | Valuta        |              | X              |
| Basbelopp                   | Valuta        |              | X              |
| Företag                       | Slå upp          | X            | X              |
| Nummer för kompensationsstruktur | Text            | X            | X              |
| Valuta                      | Slå upp          |              | X              |
| Valutakurs                 | Decimalnummer  |              | X              |
| Rutnät                          | Slå upp          | X            | X              |
| Nivå                         | Slå upp          | X            | X              |
| Referenspunkt               | Slå upp          | X            | X              |
| Radinställning för referenspunkt    | Slå upp          | X            | X              |

**Händelse för fast kompensation**

| **Fält**            | **Datatyp**   | **Obligatoriskt** | **Sökbart** |
|-----------------------|-----------------|--------------|----------------|
| Företag               | Slå upp          | X            | X              |
| Beskrivning           | Text            | X            | X              |
| Händelsetyp            | Alternativuppsättning      | X            | X              |
| Är aktiv             | Två alternativ     | X            |                |
| Namn                  | Text            | X            | X              |

## <a name="entity-relationship-models"></a>Modeller för enhetsrelation

### <a name="worker"></a>Arbetare
![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Jobb och jobbefattning
![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Fördelar
![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensation
![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Lämna
![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Arbetskalender
![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)
