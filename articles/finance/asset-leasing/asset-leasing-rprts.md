---
title: Leasing av tillgångar – rapporter
description: I det här avsnittet beskrivs kortfattat de rapporter som är tillgängliga i Leasing av tillgångar.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7044378a66ed9ff952f4579d375d59576fe09294fc158c000ab28a93f4173421
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739417"
---
# <a name="asset-leasing-reports"></a>Leasing av tillgångar – rapporter

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs kortfattat de rapporter som är tillgängliga i Leasing av tillgångar. De flesta rapporter visas genom att slutföra de här stegen eller liknande steg. 

- Om du vill visa de flesta Leasing av tillgångar-rapporter går du till **Leasing av tillgångar > Förfrågningar och rapporter > Leasingrapporter** och väljer en rapport som ska visas. För de rapporter som kräver en annan urvalssökväg finns stegen för att öppna rapporten i rapportens beskrivning. 
- När du väljer en rapport som ska skrivas ut öppnas en parametersida där du kan filtrera den information som finns i rapporten. Ange filtervillkor och klicka sedan på **OK** för att generera rapporten. I den genererade rapporten visas information som ligger inom de filter du har angett.

## <a name="asset-movement"></a>Tillgångens rörelse
Rapporten om tillgångsrörelse fungerar som en uppdateringsrapport för saldona för tillgång med nyttjanderätt för varje leasing. I den här rapporten kan du visa tillgångstransaktioner för en leasing under en angiven period. Rapporten innehåller följande fält. 

|     Rapportfält                  |     Beskrivning                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Startdatum              |     Startdatumet för leasingens tidigaste version.                     |   
|     Leasingperiod                     |     Leasingperioden för leasingens tidigaste version.                            |
|     Korttidsleasing               |     Om leasingen klassificeras som en korttidsleasing visas den som **Ja**.         |
|     Lågvärdesleasing                |     Om leasingen klassificeras som en lågvärdesleasing visas den som **Ja**.          |
|     Initial tillgång med nyttjanderätt     |     Det ursprungliga värdet på tillgången med nyttjanderätt från den första redovisningsjournalposten.      |
|     Ingående saldo              |     Det bokförda nettovärdet för tillgång med nyttjanderätt per **Från-datum**.                         |
|     Periodavskrivningsutgift    |     Det antal avskrivningsutgifter som har utförts inom det datumintervall som har definierats för rapporten.        |
|     Ackumulerad avskrivning       |     Beloppet för ackumulerad avskrivning per **Från-datum**.                               |
|     Nedskrivning                     |     Det belopp som tillgången har skrivits av med inom det datumintervall som har definierats för rapporten.               |
|     Ändringar                  |     Justeringsbeloppet för tillgången med nyttjanderätt mellan datumparametrar.                            |
|     Bokfört nettovärde                 |     Det avslutande bokförda nettovärdet för tillgången med nyttjanderätt, som är nettot av ackumulerad avskrivning per **Till-datum**.    |

## <a name="differences-report"></a>Differensrapport
I rapporten Skillnader visas skillnaderna mellan information som har lästs in i ramverket för leasingimport och den information som för närvarande finns i systemet. På så sätt kan du jämföra vad som justerats, uppdaterats eller lagts till via ramverket för leasingimport.  

Värdena i rapporten varierar beroende på valt leasing. I rapporten visas endast de fält som skiljer sig från vad som finns i systemet och i mellanlagringstabellerna. Det gamla värdet är det som antingen finns i systemet eller som tidigare fanns i systemet, beroende på om importprocessen har körts eller inte. Det nya värdet visar värdet i den mellanlagringstabell som ersätter det gamla värdet.

## <a name="five-years-undiscounted-payment-forecast"></a>Fem års icke-diskonterad betalningsprognos
Rapporten Fem års icke-diskonterad betalningsprognos visar de beräknade icke-diskonterade leasingbetalningar som ska betalas under de kommande fem åren från det datum som anges i rapportparametrarna. Rapporten innehåller följande fält. 

|     Rapportfält         |     Beskrivning                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Leasingbeskrivning     |     Leasingbeskrivningen från leasinghuvudet.                                                      |
|     Leasing-ID              |     Det unika leasing-ID.                                                                              |
|     Räkenskapsbok                  |     Leasingboken som är associerad med bok-ID.                                                         |
|     Klassificering        |     Klassificeringen av leasingen.                                                                  |
|     Konteringsnivå         |     Skiktet som leasingen bokförs till.                                                         |
|     Valuta              |     Leasingens valuta.                                                                        |
|     Aktuella               |     Summan av alla de leasingsbetalningar som ska betalas inom de närmaste 12 månaderna från rapportdatumet.          |
|     13–24 månader          |     Summan av alla de leasingsbetalningar som ska betalas inom 13 till 24 månader från rapportdatumet.           |
|     25–36 månader          |     Summan av alla de leasingsbetalningar som ska betalas inom 25 till 36 månader från rapportdatumet.           |
|     37–48 månader          |     Summan av alla de leasingsbetalningar som ska betalas inom 37 till 48 månader från rapportdatumet.           |
|     49–60 månader          |     Summan av alla de leasingsbetalningar som ska betalas inom 49 till 60 månader från rapportdatumet.           |
|     Därefter            |     Summan av alla de leasingsbetalningar som ska betalas på eller efter 61 månader från rapportdatumet.              |

## <a name="gaap-cash-flows-report"></a>Rapporten GAAP-kassaflöden
Rapporten med GAAP-upplysningar uppfyller USA:s GAAP-upplysningskrav som anges i 842-20-50-4(g)(1). Om du vill visa rapporten går du till **Leasing av tillgångar > Förfrågningar och rapporter > Upplysningar > GAAP-kassaflöden**. 

|     Rapportfält                                 |     Beskrivning                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Från-datum <br> Till-datum                        |     Definierar ett datumintervall som används för att begränsa den information som ingår i rapporten.      |
|     Juridisk person                                  |     Den juridiska person som är knuten till leasingavtalet.                                      |
|     Leasingtyp                                    |     Klassificeringen av leasingen som antingen finansiell eller operationell.           |
|     Leasing-ID                                      |     Det unika leasing-ID.                                                      |
|     Leasingbeskrivning                             |     Leasingbeskrivningen från leasinghuvudet.                              |
|     Leasingbok                                    |     Leasingboken som raden refererar till.                        |
|     Konteringsnivå                                 |     Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål.                          |
|     Leasinggrupp                                   |     Den grupp som leasingen är knutet till.                                     |
|     Valuta                                      |     Förkortningen för den transaktionsvaluta som används. Alla rapporter kommer att konvertera transaktionsvalutan till rapporteringsvalutan.                      |
|     Finansiell leasing – operativa kassaflöden         |     Summan av det totala antalet bokförda variabla betalningar och de totala räntebetalningarna som bokförts från amorteringsplanen mellan datumparametrarna.        |
|     Finansiell leasing – finansiella kassaflöden           |     Summan av de totala huvudbetalningarna från amorteringsplanen mellan datumparametrarna.       |
|     Operationell leasing – operativa kassaflöden       |     Summan av alla bokförda leasingbetalningar och bokförda variabla betalningar mellan datumparametrarna.            |

## <a name="lease-balances-forecast"></a>Prognos för leasingbalans
I prognosen för leasingsaldon visas en lista med information direkt från planen för amortering av leasingskuld och avskrivningsplanen för tillgången. Rapporten visar prognostiserade belopp för förväntad leasingskuld och tillgångar med nyttjanderätt under en tidsperiod, inklusive alla förväntade utgifter för dessa leasingar. Rapporten innehåller följande fält.

|     Rapportfält                 |     Beskrivning                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Ingående saldo             |     Startsaldot i leasingen amorteringsplan för perioden som innehåller rapportens startdatum.            |
|     Första redovisningstillfälle           |     Om startdatumet för leasingavtalet ligger inom det datumintervall som har definierats för rapporten visas skuldkontots värde för den första redovisningsjournalposten.      |
|     Betalningar                      |     Summan av leasingbetalningar som ligger inom det datumintervall som har definierats för rapporten.                               |
|     Intresse                      |     Summan av de räntekostnader för leasingen som ligger inom det datumintervall som har definierats för rapporten.                    |
|     Utgående balans                |     Skuldsaldot för leasingen per **Till-datum**.                                                             |
|     Kortfristig skuld          |     Det kortfristiga skuldbeloppet i leasingavtalets amorteringsplan per **Till-datum**.                           |
|     Långfristig skuld           |     Det långfristiga skuldbeloppet i leasingavtalets amorteringsplan per **Till-datum**.                            |
|     Ingående bokfört nettovärde      |     "Ingående bokfört nettovärde" i leasingens avskrivningsplan för tillgångar för perioden som innehåller rapportens startdatum      |
|     Första redovisningstillfälle           |     Om startdatumet för leasingavtalet ligger mellan rapportens datumparametrar visas tillgångskontots värde för den första redovisningsjournalposten.            |
|     Avskrivningsutgift          |     Summan av de avskrivningskostnader för leasingen som ligger inom det datumintervall som har definierats för rapporten.                  |
|     Utgående balans                |     Tillgångssaldot för leasingen per **Till-datum**.                                                              |
|     Justering av eget kapital             |     Startsaldot minus startvärdet i första bokförda nettovärdet.                                                             |

## <a name="lease-commencements-report"></a>Rapport över leasingars start
I rapporten över leasingars start visas alla leasingar som har påbörjats inom ett angivet datum intervall, inklusive den ursprungliga skulden och de aktuella saldona för tillgångar med nyttjanderätt. Rapporten innehåller följande fält. 

|     Rapportfält                 |     Beskrivning                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Startdatum             |     Datum för den första redovisningsjournalposten som bokfördes för den aktuella leasingversionen.         |
|     Belopp för inledande leasingskuld      |     Skuldbeloppet från den första redovisningsjournalposten.                                  |
|     Startbelopp för tillgång          |     Tillgångsbeloppet från den första redovisningsjournalposten.                                      |

## <a name="lease-modification-report"></a>Leasingändringsrapport
I leasingändringsrapporten visas alla leasingar som har ändrats inom ett angivet datum intervall. Rapporten visar även den användare som justerade leasingen och det totala justerade skuldbeloppet. Rapporten innehåller följande fält. 

|     Rapportfält                 |     Beskrivning           |
|---------------------------------  |-------------------------  |
|     Justerades av                   |     Användarnamnet på den person som ändrade leasingen.                                |
|     Justeringsdatum               |     Datumet då justeringsjournalposten bokfördes.                        |
|     Modifieringar                   |     Beloppet för justeringsjournalposter som bokförts på leasingens skuldkonto mellan datumparametrarna. Krediterna visas som positiva, medan debet blir negativ.       |
|     Vinst (förlust) belopp            |     Beloppet för justeringsjournalposter som bokförts på leasingens vinst/förlustkonto mellan datumparametrarna. Krediterna visas som positiva, medan debet blir negativ.       |
|     Balanserade vinstmedel             |     Beloppet för justeringsjournalposter som bokförts på leasingens konto med balanserad vinst mellan datumparametrarna.      |
|     Slutbalans för leasingen      |     Det resulterande skuldsaldot per leasingens justeringsdatum.           |

## <a name="lease-movement-report"></a>Leasingrörelserapport
Rapporten om leasingrörelse fungerar som en uppdateringsrapport för leasingskuldkontona för varje leasing. I den här rapporten kan du visa skuldtransaktioner för en leasing under en angiven period.

|     Rapportfält             |     Beskrivning                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Startdatum         |     Startdatumet för leasingens tidigaste version.    |
|     Leasingperiod                |     Leasingperioden för leasingens tidigaste version.           |
|     Resterande betalningar        |     Det antal betalningar som ännu inte har bokförts för leasingen.                       |
|     Ingående saldo         |     Summan av alla transaktioner som påverkar det leasingens skuld som inträffade före rapportens startdatum.             |
|     Första redovisningstillfälle       |     Beloppet för den första redovisningstransaktionen för leasingen som bokfördes inom det datumintervall som definierats för rapporten.     |
|     Betalningar                  |     Summan av de betalningstransaktionerna för leasingen som har bokförts inom det datumintervall som har definierats för rapporten. Värdena i den här kolumnen visas som negativa belopp eftersom betalningarna minskar leasingens skuldsaldo.  |
|     Intresse                  |     Summan av de upplupna räntor som har bokförts för leasingen inom det datumintervall som har definierats för rapporten.            |
|     Modifieringar               |     Summan av leasingens bokförda justeringstransaktioner som ligger inom det datumintervall som har definierats för rapporten.                               |
|     Utgående balans            |     Saldot för leasingens alla skuldtransaktioner som har bokförts per rapportens **Till-datum**.                  |

## <a name="lease-transactions-report"></a>Leasingtransaktionsrapport
Vid begäran om leasingtransaktioner visas alla journalposter som har genererats av Leasing av tillgångar. Varje journalpost är kopplad till det bok-ID som den kom från. På så sätt kan du enkelt associera journalposten till motsvarande leasing. Begäran om leasingtransaktioner fungerar på ett sätt som liknar sidan **Verifikationstransaktioner** i redovisningen.

## <a name="weighted-average-discount-rate-report"></a>Rapport med viktat genomsnittligt diskonto
Rapport med viktat genomsnittligt diskonto uppfyller USA:s GAAP-upplysningskrav som anges i ASC 842-20-50-4(g)(4) för ett viktat genomsnittligt diskonto. Om du vill visa rapporten går du till **Leasing av tillgångar > Förfrågningar och rapporter > Upplysningar > Viktat genomsnittligt diskonto**. Rapporten innehåller följande fält. 

|     Rapportfält                     |     Beskrivning                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     Från och med (datum)                        |     I den här rapporten ingår alla leasingar som har påbörjats på eller före datumparametern **Från och med**. Den här rapporten bör köras från och med den sista dagen i den period som ska rapporteras.      |
|     Juridisk person                      |     Den juridiska person som är knuten till leasingavtalet.                           |
|     Leasing-ID                          |     Det unika leasing-ID.                                                  |
|     Leasingbeskrivning                 |     Leasingbeskrivningen från leasinghuvudet.                          |
|     Räkenskapsbok                              |     Den specifika boktypen för den visade leasingen.                                                                                                                                            |
|     Bokföringsskikt                     |     Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål.      |
|     Leasinggrupp                       |     Den grupp som leasingen är hör till.                                 |
|     Diskontoränta                     |     Den kurs som används för att diskontera leasingbetalningar.                             |
|     Valuta                          |     Förkortningen för den transaktionsvaluta som används. Alla rapporter kommer att konvertera transaktionsvalutan till rapporteringsvalutan.  |
|     Resterande leasingbetalningar          |     Det totala beloppet med obetalda leasingbetalningar från betalningsplanen som återstår från **Från och med**-datumet.            |
|     Återstående vägda betalningar       |     De leasingbetalningar som återstår multiplicerat med den diskontoränta som används.   |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
