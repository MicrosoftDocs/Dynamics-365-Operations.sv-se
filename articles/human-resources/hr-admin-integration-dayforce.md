---
title: Konfigurera integrering med Dayforce
description: Detta ämne beskriver erforderliga konfigurationssteg för integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f92850a741f2a0d4d1c2636cbbdf21fe95f307df
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559471"
---
# <a name="configure-integration-with-dayforce"></a>Konfigurera integrering med Dayforce

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Integreringen mellan Microsoft Dynamics 365 Human Resources och Ceridian Dayforce är beroende av flera konfigurationssteg som beskrivs i det här avsnittet. Du måste konfigurera integreringen i både Personal och Dayforce innan du kan bearbeta en betalning.

När du använder tjänster som exempelvis Dayforce för att utföra betalningar måste du aktivera integrering i Personal. Integreringen kräver specifika data från Personal. Därför måste du kontrollera att data som är mappad till Dayforce konfigureras i Personal på ett sätt som stöder integreringen. Integreringen använder följande breda datakategorier:

- Personaldata
- Kompensationsdata
- Lönedata som till exempel lönecykler, betalningsperioder och inkomstkoder
- Medarbetardata

I detta ämne beskrivs vilka steg du måste följa för att aktivera integreringen. Här förklaras de datatyper och den konfigurationsinformation som krävs för integreringen.

## <a name="enable-the-integration"></a>Aktivera integreringen

Du måste aktivera integreringen i Personal och ange konfigurationsinformation för att ansluta till Dayforce. Om du vill att den redovisningstransaktion som framställs ska importeras till Microsoft Dynamics 365 Finance måste du också skapa ett lagringskonto för Microsoft Azure och ange anslutningssträngen för Azure-lagring i Finance.

Följ dessa steg om du vill aktivera integrering i Personal.

1. På sidan **Systemadministration** väljer du **Integreringskonfiguration**.
2. Ange slutpunkten för filöverföringsprotokollet (FTP) och den säkra FTP-sökvägen.
3. Ange användarnamn och lösenord för den användare som kommer att använda den säkra FTP-slutpunkten och mappsökvägen.
4. Testa anslutningen efter behov samt ange alternativet **Aktivera integrering av löner** som **Ja**.

När integreringen aktiveras skapas dataexportpaket och filer, och frekvensen anges. Du kan ändra frekvensen efter behov.

Mer information om Azure-lagringskonton och anslutningssträngar för Azure-lagring, se följande Azure-avsnitt:

- [Om Azure-lagringskonton](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Konfigurera anslutningssträngar för Azure-lagring](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>Teknisk information när löneintegrering har aktiverats

Att slå på löneintegrering har två primära effekter:

- Ett dataexportprojekt med namnet "Löneintegreringexport" skapas. Det här projektet innehåller de entiteter och fält som krävs för löneintegrering. För att undersöka projekt, gå till **Systemadministration**, välj **Datahantering** och öppna dataprojekt från lista över projekt.
- Det här batchjobbet kör dataexportprojektet, krypterar det resulterande datapaketet och överför datapaketfilen till den SFTP-slutpunkt som konfigurerats på skärmen **integreringskonfiguration**.

> [!NOTE]
> Det datapaket som överförs till SFTP-slutpunkten krypteras med en nyckel som är unik för paketet. Nyckeln finns i ett Azure Key Vault som bara kan nås av Ceridian. Det går inte att dekryptera och undersöka innehållet i datapaketet. Om du behöver undersöka innehållet i datapaketet, måste du exportera dataprojektet "Löneintegreringexport" manuellt, hämta det och sedan öppna det. Manuell export använder inte kryptering eller överföring av paketet.

## <a name="configure-your-data"></a>Konfigurera dina data 

Du måste konfigurera personaldata för att bearbeta löner i Personal. Du måste ställa in organisationsinformation, t.ex. jobb och befattningar samt förmåner och kompensationsinformation. Denna information utgör den anställnings-, lön- och avdragsinformationen som krävs för att generera lön för medarbetare.

### <a name="human-resource-data"></a>Personaldata

#### <a name="benefits"></a>Förmåner 

Personal tillhandahåller verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och kompensationsplaner för medarbetare som en organisation erbjuder eller bearbetar för sin personal.

När du skapar förmåner, kom då ihåg följande data och konfigurationer som används i Dayforce.

##### <a name="benefit-plans"></a>Förmånsplaner

- Plan (obligatoriskt)
- Typ (obligatoriskt)
- Effekt på lön (obligatoriskt)
- Återvinn restbetalningar
- Avdragsmetod
- Avdragsprioritet
- Gränsperiod
- Begränsa belopp

##### <a name="benefits"></a>Förmåner

- Plan (obligatoriskt)
- Typ (obligatoriskt)
- Tillval (obligatoriskt)
- Förmåns-ID (obligatoriskt)
- Frekvens
- Bas
- Belopp eller tariff
- Inkomstkod

##### <a name="supported-frequencies"></a>Frekvenser som stöds 

- Varje vecka
- Varannan vecka
- Var fjortonde dag
- Månatlig

##### <a name="supported-bases"></a>Databaser som stöds 

- Fast belopp
- Procent av inkomst
- Produktiva timmar

Dayforce skapar följande avdrag baserat på den löneeffekt som definieras i förmånsplanen.

| Val i Personal        | Resultat i Dayforce                            |
|----------------------------|-----------------------------------------------|
| Ingen                       | Inget avdrag skapas.                      |
| Endast avdrag             | Löneavdrag för en medarbetare skapas.             |
| Endast lönetillägg          | Löneavdrag för en arbetsgivare skapas.             |
| Avdrag och tillägg | Avdrag för medarbetare och arbetsgivare skapas. |

Mer information om hur du definierar och hanterar ett förmånsprogram finns i följande avsnitt:

- [Utveckla ett förmånsprogram för medarbetare](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Skapa en ny förmån](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Definiera förmånsberättiganderegler och policyer](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Registrera och ta bort förmåner för medarbetare](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Kompensation 

Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar. En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner. Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner.

Dayforce använder kompensationsinformation för att beräkna en medarbetares tim- eller årliga betalning. Fasta kompensationsplaner och lönekonverteringar är obligatoriska. Medarbetarna måste vara anslutna till en fast kompensationsplan.

Mer information om att kompensationsplaner finns i följande avsnitt:

- [Skapa planer för fast kompensation](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Skapa planer för variabel kompensation](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Utveckla struktur och planer för lön/kompensation](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Bearbeta kompensation](/dynamics365/unified-operations/talent/process-compensation)
- [Definiera kompensationsprocessen och beräkna resultat](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Registrera en medarbetare i en fast kompensationsplan](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Registrera en medarbetare i en variabel kompensationsplan](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Jobb 

Ett jobb är den samling uppgifter och ansvarsområden som avkrävs en person som utför ett jobb. Mer information finns i följande avsnitt:

- [Installera komponenter för ett jobb](/dynamics365/unified-operations/talent/create-job)
- [Definiera nya jobb](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Befattningar

En befattning är ett exempel på ett enskilt jobb. Befattningen "Försäljningschef (öst)" är exempelvis en av de befattningar som associeras med jobbet "Försäljningschef." En befattning finns på en avdelning. Endast en enda medarbetare kan vara associerad med respektive befattning.

Tänk på följande uppgifter och konfigurationsinformation när du ställer in befattningar:

- Befattning (obligatoriskt)
- Beskrivning (obligatoriskt)
- Jobb (obligatoriskt)
- Avdelning (obligatoriskt)
- Befattningstyp (obligatoriskt)
- Heltidslön
- Ordinarie timmar per år (obligatoriskt)
- Betalas av den juridiska personen (obligatoriskt)
- Lönecykel (obligatoriskt)
- Standardekonomisk dimension – kostnadsställe (obligatoriskt)
- Medarbetartilldelning – medarbetare, tilldelningsstart, tilldelningsslut, orsakskod

Om flera befattningar på samma avdelning är associerade med samma jobb konsolideras de till en enda befattning i Dayforce.

Mer information finns i följande avsnitt:

- [Organisera arbetsstyrkan med avdelningar, jobb och befattningar](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Ställ in befattningar](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Avdelningar

En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust.

Mer information finns i följande avsnitt:

- [Skapa en avdelning och associera den med avdelningshierarkin](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Definiera nya avdelningar](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Lönecykler och löneperioder

En lönecykel avgör hur ofta lönelistan körs, samt vilka specifika dagar som medarbetarna får betalt. En lönecykel kan exempelvis vara månadsvis och medarbetarna få sin lön den sista dagen i månaden. Alternativt kan en lönecykel vara veckovis och medarbetarna få sin lön på tisdagen efter betalningsperiodens utgång. Lönecykler tilldelas befattningar i syfte att styra när medarbetare på dessa befattningar får sin lön.

När du har skapat lönecykler kan du generera betalningsperioder för respektive cykel. Varje betalningsperiod innehåller ett standardbetalningsdatum som baseras på den information du anger. Du kan emellertid ändra standarddatumet för betalning i en löneperiod i syfte att tillåta undantag, till exempel när betalningsdatumet infaller på en allmän helgdag.

Följande information används i Dayforce:

- Lönecykel (obligatoriskt)
- Lönecykelfrekvens (obligatoriskt)
- Periodens startdatum (första löneperiod obligatorisk)
- Standarddatum för betalning (första löneperiod obligatorisk)

Denna information är integrerad i Dayforce som lönegrupper och delas upp efter land eller region för respektive lönecykel. Minst en löneperiod måste genereras före integrering. Dayforce genererar gruppkalendrar för lön och betalningsdatum utifrån startdatumet för den första löneperioden och det standarddatum för betalning som anges i Personal.

#### <a name="earning-codes"></a>Inkomstkoder

Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter. Koderna har olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav, och gross up-kapacitet.

Följande information används i Dayforce:

- Inkomstkod (obligatoriskt)
- beskrivning
- Enhet
- Produktiv

### <a name="worker-data"></a>Medarbetardata

Poster för de olika typer av medarbetare som du har är viktiga för dina personal- och lönesystem. Den information du anger kan användas för att spåra medarbetare och personuppgifter.

För medarbetare kan du behålla följande information:

- **Grundläggande** – Grundläggande information om en medarbetare, till exempel kontaktinformation, demografisk information, identifikationsinformation, familjeinformation, status för militärtjänst, exilstatusinformation samt personliga och nödkontakter.
- **Anställning** – Information om en medarbetares anställning, exempelvis företags- eller organisationstillhörighet, befattningstilldelning, start- och slutdatum, jobbtillgänglighet, anställningsvillkor, pension, semester- samt omplaceringsinformation.
- **Tjänstledighet och frånvaro** – Information om en medarbetares frånvaro, exempelvis jobbkalendrar, frånvarotransaktioner samt frånvaroinställningar.
- **Ersättning och lön** – Information om en medarbetares ersättningsplaner och löneinformation, exempelvis plananmälan, utmärkelser, resultat, provision, skatteinformation, pensionering samt löneavdrag.

När du anger medarbetarinformation, kom då ihåg följande uppgifter och konfigurationer som används i Dayforce.

#### <a name="general-information"></a>Allmän information

- Anställningsnummer (obligatoriskt)
- Förnamn (obligatoriskt)
- Efternamn (obligatoriskt)
- Mellannamn
- Datum för tjänsteålder
- Känt som

#### <a name="personal-information"></a>Personlig information

- Civilstånd (obligatoriskt)
- Födelsedatum (obligatoriskt)
- Könstillhörighet (obligatoriskt)
- Person med funktionsnedsättningar
- Medborgarskap, land, region (endast för Mexiko)

#### <a name="address-information"></a>Adressinformation

- Primär adress (obligatoriskt)
- Land/region (obligatoriskt)
- Postnummer (obligatoriskt)
- Nummer (obligatoriskt) (endast för Mexiko)
- Byggnadskomplement (endast för Mexiko)
- Stad (obligatoriskt)
- Delstat (obligatoriskt)
- Region (obligatoriskt)

#### <a name="contact-information"></a>Kontaktinformation 

- Primär adress (obligatoriskt)
- Kontaktnummer (obligatoriskt)
- Anknytning

#### <a name="payroll-information-and-earning-codes"></a>Löneinformation och inkomstkoder

Medarbetare kan tilldelas en viss inkomst till en viss betalningsfrekvens och ha en prioriterad betalningsmetod. Följande fält används i Dayforce för att garantera att dessa prioriteringar och inställningar används.

##### <a name="earning-codes"></a>Inkomstkoder

- Befattning (obligatoriskt)
- Inkomstkod (obligatoriskt)
- Frekvens (obligatoriskt)
- Belopp (obligatoriskt)

##### <a name="payroll-information"></a>Löneinformation

- Betalningsmetod
- Ekonomisk region (obligatoriskt)
- ID för anställningsförmåner
- Nationellt ID-nummer (obligatoriskt)
- Militärtjänstgöring, nummer
- Skiftes-ID (obligatoriskt)
- Skattenummer (obligatoriskt)
- Fack-ID (obligatoriskt)
- Arbetsdags-ID (obligatoriskt)
- Arbetstillståndsnummer

> [!NOTE]
> För betalsättet stöder Mexiko **Kontant**, **Check** (företagets fysiska check), samt **Elektronisk betalning**. Om betalsättet np anges används **Check** som standard.

#### <a name="employment-details"></a>Anställningsinformation

Detaljerad anställningshistorik används som viktig information i syfte att hämta en medarbetares anställnings-, uppsägnings- och återanställningsstatus i Dayforce. Dayforce stöder endast en aktiv anställningspost åt gången.

- Startdatum för anställning (obligatoriskt)
- Slutdatum för anställning
- Startdatum
- Justerat startdatum
- Uppsägningsdatum (obligatoriskt vid uppsägning)
- Uppsägningsorsak (obligatoriskt vid uppsägning)

Medarbetarens viktiga datum beräknas med hjälp av följande information.

| Personal                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Senaste anställningsdatum | Anställningsstart för aktuell, icke-uppsagd post för anställningshistorik                                 |
| Uppsägningsdatum      | Uppsägningsdatum för aktuell, icke-uppsagd post för anställningshistorik                                 |
| Startdatum            | Justerat startdatum, startdatum eller anställningsstart för aktuell, inaktiv post för anställningshistorik |
| Ursprungligt anställningsdatum    | Anställningsstart för tidigaste anställningshistorikpost                                               |

#### <a name="compensation"></a>Kompensation

En fast kompensationsplan måste kopplas till varje medarbetares primära befattning under hela anställningsperioden. Perioden inleds det datum då medarbetaren anställts (eller på anställningens startdatum) och fortsätter till och med uppsägningen.

- Giltighetsdatum (obligatoriskt)
- Utgångsdatum
- Lönesats (obligatoriskt)
- Lönesatskonverteringar (obligatoriskt)
- Årlig motsvarighet (obligatoriskt)
- Motsvarighet per timme (obligatoriskt)

Om en timanställd har flera befattningar importeras den fasta kompensationen för den primära befattningen till Dayforce som bastariff/-lön för medarbetaren. För icke-primära befattningar sparas timtariffen i motsvarande befattning i Dayforce.

Om en fast anställd tjänsteman har flera befattningar hämtas den ackumulerade timtariffen och årslönen för samtliga aktiva befattningar och används som bastariff/-lön för medarbetarnivån.

#### <a name="identification-numbers"></a>Identifieringsnummer

##### <a name="social-security-identifier"></a>Socialförsäkrings-identifierare 

Alla medarbetare måste ha en primär identifierare. Denna identifierare måste vara av identifieringstypen **SSN**. I Dayforce hämtas den automatiskt som den socialförsäkringsidentifierare för anställd som krävs för anställning.

- Primär adress (obligatoriskt)
- Identifieringstyp = "SSN"
- Utfärdat den
- Utgångsdatum

Medarbetare kan deklarera flera ID-nummer med ID-typen **SSN**. Endast posten som är markerad som **Primär** integreras emellertid i Dayforce, oavsett om numret är aktivt eller har upphört att gälla.

#### <a name="bank-accounts-and-disbursements"></a>Bankkonton och utbetalningar

Giltig bankkontoinformation måste anges för varje medarbetare som väljer att få sin lön via bankkontoöverföringar.

| Personal                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Bankkontonummer (obligatoriskt) |                                                                                                             |
| SWIFT-kod (obligatoriskt)          | Fältet **Bank-ID** används när löner bearbetas i Mexiko.                                                             |
| Filialnummer (obligatoriskt)       |                                                                                                             |
| Bankkontotyp (obligatoriskt)   | Fältet **Kontotyp** används när löner bearbetas i Mexiko. Värden som stöds inkluderar **Check** och **Lönelista**. |

> [!NOTE]
> Medarbetare som väljer att få lön via bankkontoöverföring måste ange en länk till ett restkonto tillhörande en juridisk person med primär adress i Mexiko och som är associerad med ett giltigt bankkonto från en mexikansk bank. Alla övriga restkonton ignoreras.

#### <a name="address-information"></a>Adressinformation

Alla medarbetare måste ha en primär plats. Den här platsen används i Dayforce i syfte att fastställa medarbetarens primära hemort i skattesyfte.

- Primär adress (obligatoriskt)
- Land/region (obligatoriskt)
- Postnummer (obligatoriskt)
- Gata (obligatoriskt)
- Nummer (obligatoriskt)
- Byggnadskomplement
- Stad (obligatoriskt)
- Delstat (obligatoriskt)
- Region (obligatoriskt)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Konfigurera dina data för att generera lön i USA och Kanada

Om du genererar lön för medarbetare i USA och Kanada måste följande element konfigureras:

- Avdelningar är obligatoriska vid befattningarna:
- Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.

> [!NOTE] 
> Du kan konfigurera Personal att kräva att befattningar anger en avdelning. Gör detta genom att gå till **delade befattningar i Personal > befattningar > kräver avdelningar för befattningar**. Vi rekommenderar att den här inställningen tillämpas för integrering.

### <a name="job-types"></a>Jobbtyper

Jobbtyper används för att gruppera liknande jobb i kategorier. Jobbtyper krävs för att bearbeta lön i USA och Kanada. Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning. Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.

Följande jobbtyper och beskrivningar krävs.

| Jobbtyp   | beskrivning |
|------------|-------------|
| Varje timme     | Varje timme      |
| Fast lön   | Fast lön    |

### <a name="position-types"></a>Befattningstyper 

Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat. Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.

Följande befattningstyper och beskrivningar krävs.

| Befattningstyp   | beskrivning        |
|-----------------|--------------------|
| Heltid       | Heltidsanställd |
| Deltid       | Deltidsanställd |

### <a name="reason-codes"></a>Orsakskoder

Orsakskoder innehåller information om statusen för en medarbetare. Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.

Följande orsakskoder och -beskrivningar krävs.

| Orsakskod    | beskrivning      | Tillämpliga scenarier |
|----------------|------------------|----------------------|
| EGEN UPPSÄGNING    | Egen uppsägning      | Säg upp medarbetare     |
| UPPSÄGNING    | Uppsägning      | Säg upp medarbetare     |
| PENSION     | Pension       | Säg upp medarbetare     |
| ÖVRIGT          | Andra orsaker    | Säg upp medarbetare     |
| DÖDSFALL          | Dödsfall            | Säg upp medarbetare     |
| TJÄNSTLEDIGHET | Tjänstledighet | Säg upp medarbetare     |
| KONTRAKTSLUT    | Kontraktslut  | Säg upp medarbetare     |
| LÖNEÄNDRING   | Löneändring | Kompensation         |

### <a name="marital-status"></a>Civilstånd

Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.

Följande tabell visar hur civilståndsvärden mappas till Dayforce.

| Personal                 | Dayforce             |
|------------------------|----------------------|
| Gift                | Gift              |
| Ett                 | Ett               |
| Änka/Änkeman                | Änka/Änkeman              |
| Skild               | Frånskild             |
| Registrerat partnerskap | Samboförhållande |
| Inga                   | Inga                 |
| Sambo             | Sambo           |

### <a name="gender"></a>Kön

Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.

Följande tabell visar hur könsbeteckningar mappas till Dayforce.

| Personal       | Dayforce        |
|--------------|-----------------|
| Man         | Man            |
| Kvinna       | Kvinna          |
| Icke-specifik | *Stöds ej* |

### <a name="earning-codes"></a>Inkomstkoder

Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter. Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet. Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.

#### <a name="supported-frequencies"></a>Frekvenser som stöds

- Allt
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH – 1N2N3N4OFMTH
- 2N3N4N5OFMth – 2N3N4N5OFMth
- 1OFQTR – 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR – 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR – NOVNDECOFYEAR

### <a name="addresses"></a>Adresser

Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen. Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.

| Personal          | Dayforce              |
|-----------------|-----------------------|
| Land/region  | Landskod          |
| Postnummer | Postnummer           |
| Stat           | Delstatskod            |
| Ort            | Ort                  |
| Län          | Region (kommun) |
| Gata          | Adressrad 1        |

### <a name="tax-regions"></a>Skatteregioner

Skatteregioner används för att bestämma vilken skattesats som ska användas vid lönegenerering. Skatteregioner mappas till Dayforce som platsadresser. Förvald skatteregion måste associeras med medarbetarens aktiva befattning. 

- Skatteregion (obligatoriskt)
- Land/region (obligatoriskt)
- Delstat (obligatoriskt)
- Län 
- Stad (obligatoriskt)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Konfigurera dina data för att generera lön i Mexiko

Om du genererar lön för medarbetare i Mexiko måste följande element konfigureras:

- Avdelningar är obligatoriska vid befattningarna:
- Kostnadsställen måste ställas in som ekonomiska dimensioner och måste vara det första elementet i standardsträngen för ekonomisk dimension.

### <a name="job-types"></a>Jobbtyper

Jobbtyper används för att gruppera liknande jobb i kategorier. Jobbtyper krävs för att bearbeta löner i Mexiko. Några exempel på jobbtyper är heltid och deltid, eller fast lön och timpenning. Jobbtyper mappas till Dayforce som lönetyper som anger huruvida en anställd arbetar per timme eller har fast lön.

Följande jobbtyper och beskrivningar krävs.

| Jobbtyp   | beskrivning |
|------------|-------------|
| Varje timme     | MX Varje timme   |
| Fast lön   | MX Fast lön |

### <a name="position-types"></a>Befattningstyper 

Du kan använda befattningstyper för att beskriva huruvida befattningen är på heltid, deltid eller annat. Befattningstyper mappas till Dayforce som löneklasser som anger huruvida en anställd arbetar heltid eller deltid.

Följande befattningstyper och beskrivningar krävs.

| Befattningstyp   | beskrivning        |
|-----------------|--------------------|
| Heltid       | Heltidsanställd |
| Deltid       | Deltidsanställd |

### <a name="reason-codes"></a>Orsakskoder

Orsakskoder innehåller information om statusen för en medarbetare. Orsakskoder mappas till Dayforce som statusanledningar som anger orsaken till ändringar i en medarbetares befattning eller anställningsstatus.

Följande orsakskoder och -beskrivningar krävs.

| Orsakskod            | beskrivning                    | Tillämpliga scenarier |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Avgick före första lön | Säg upp medarbetare     |
| EGEN UPPSÄGNING            | Egen uppsägning                    | Säg upp medarbetare     |
| PENSION                | Pension                        | Säg upp medarbetare     |
| UPPSÄGNING            | Uppsägning                    | Säg upp medarbetare     |
| PENSION             | Pension                     | Säg upp medarbetare     |
| FRÅNVARANDE               | Frånvarande                       | Säg upp medarbetare     |
| ÖVRIGT                  | Andra orsaker                  | Säg upp medarbetare     |
| AVSLUT                | Verksamheten nedlagd               | Säg upp medarbetare     |
| DÖDSFALL                  | Dödsfall                          | Säg upp medarbetare     |
| TJÄNSTLEDIGHET         | Tjänstledighet               | Säg upp medarbetare     |
| KONTRAKTSLUT            | Kontraktslut                | Säg upp medarbetare     |
| LÖNEÄNDRING           | Löneändring               | Kompensation         |

### <a name="terms-of-employment"></a>Anställningsvillkor

Anställningsvillkor används för att skapa kategorier av anställningsvillkor. Villkoren mappas till Dayforce som indikatorvärden för anställning.

Följande anställningsvillkor samt beskrivningar krävs.

| Anställningsvillkor   | beskrivning |
|-----------------------|-------------|
| Vanligt               | Vanligt     |
| Direkt                | Direkt      |
| Praktik            | Praktik  |
| Permanent             | Permanent   |

### <a name="marital-status"></a>Civilstånd

Civilståndsvärden mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.

Följande tabell visar hur civilståndsvärden mappas till Dayforce.

| Personal                 | Dayforce                  |
|------------------------|---------------------------|
| Gift                | Gift                   |
| Ett                 | Ett                    |
| Änka/Änkeman                | Änka/Änkeman                   |
| Skild               | Frånskild                  |
| Registrerat partnerskap | Samboförhållande      |
| Inga                   | *Stöds inte i Mexiko* |
| Sambo             | *Stöds inte i Mexiko* |

### <a name="gender"></a>Kön

Könsbeteckningar mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.

Följande tabell visar hur könsbeteckningar mappas till Dayforce.

| Personal       | Dayforce                  |
|--------------|---------------------------|
| Man         | Man                      |
| Kvinna       | Kvinna                    |
| Icke-specifik | *Stöds inte i Mexiko* |

### <a name="payment-method"></a>Betalningsmetod

Betalsätt ger medarbetare och företag ett sätt att beskriva hur medarbetaren ska betalas. Betalsätt mappas till Dayforce och översätts på lämpligt sätt till giltiga värden i samband med integrering.

Följande tabell visar hur betalsätt mappas till Dayforce.

| Personal             | Dayforce                  |
|--------------------|---------------------------|
| Kontant               | Kontant                      |
| Elektronisk betalning | Överför                  |
| Check              | Check                    |
| Bankutdrag         | *Stöds inte i Mexiko* |
| Annat              | *Stöds inte i Mexiko* |

### <a name="bank-account-type"></a>Bankkontotyp

Bankkontotyper används för elektroniska betalningar till medarbetare. Bankkontotyper mappas till Dayforce som kontoinformation för överföringar. Bankkontotyper översätts på lämpligt till giltiga värden i samband med integrering.

| Personal            | Dayforce                  |
|-------------------|---------------------------|
| Checkkonto  | Checkkonto           |
| Lönekonto   | Lönekonto            |
| Sparkonto   | *Stöds inte i Mexiko* |
| BankGirot-konto | *Stöds inte i Mexiko* |
| PlusGirot-konto | *Stöds inte i Mexiko* |

### <a name="earning-codes"></a>Inkomstkoder

Inkomstkoder identifierar individuellt alla typer av arbetstagarintäkter. Koderna omfattar flera olika parametrar som rör inkomster, till exempel redovisningsbestämmelser, skattelagar, rapporteringskrav och gross up-kapacitet. Om en frekvens som inte stöds används tillämpas frekvensen **Varje lön** som standard för beräkningen.

#### <a name="supported-frequencies"></a>Frekvenser som stöds

- Allt
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH – 1N2N3N4OFMTH
- 2N3N4N5OFMth – 2N3N4N5OFMth
- 1OFQTR – 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR – 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR – NOVNDECOFYEAR

### <a name="addresses"></a>Adresser

Identifiering av specifika lands-/region-, delstats- och region(kommun)-koder kräver särskilda format som Dayforce och leverantörer i respektive land/region kan känna igen. Även om formatet för städer är flexibelt måste varje stad associeras med en delstat.

| Personal              | Dayforce              |
|---------------------|-----------------------|
| Land/region      | Landskod          |
| Postnummer     | Postnummer           |
| Stat               | Delstatskod            |
| Ort                | Ort                  |
| Län              | Region (kommun) |
| Gata              | Adressrad 1        |
| Gatunummer       | Adressrad 2        |
| Byggnadskomplement | Adressrad 5        |

### <a name="passport-number"></a>Passnummer

Medarbetare kan deklarera passinformation. Denna information bär ID-typen **Pass** och integreras i Dayforce som en del av medarbetarens Mexikospecifika information.

- Identifieringstyp = "Pass"
- Utfärdat den
- Utgångsdatum

Medarbetare kan deklarera flera ID-nummer med ID-typen **Pass**. Endast den aktuella passposten integreras emellertid i Dayforce. Om alla passposter har upphört att gälla kommer det pass som är utfärdat senast att integreras i Dayforce.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
