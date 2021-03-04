---
title: Arbetsbelastning för tillverknings körning för moln och kantskalningsenheter
description: I det här avsnittet beskrivs hur arbetsbelastningar för tillverkningskörning fungerar med moln och kantskalningsenheter.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 799c479c750fcaf296f3e2787fa38416af51963c
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516882"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Arbetsbelastning för tillverknings körning för moln och kantskalningsenheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Vissa företagsfunktioner stöds inte fullt ut i den allmänna förhandsgranskningen när enheter för belastningsenheter används.

I tillverkningskörning ger moln och kantskalningsenheter följande funktioner, även om kantenheterna inte är anslutna till navet:

- Maskinoperatörer och arbetsledare kan komma åt den operationella produktionsplanen.
- Maskinoperatörer kan hålla planen aktuell genom att köra separata jobb för bearbetning och processtillverkning.
- Arbetsledaren kan justera driftsplanen.
- Arbetare kan få åtkomst till tid och närvaro för in- och utstämpling i kanten, för att säkerställa korrekt löneberäkning för arbetare.

I det här avsnittet beskrivs hur arbetsbelastningar för tillverkningskörning fungerar med moln och kantskalningsenheter.

## <a name="the-manufacturing-lifecycle"></a>Tillverkningslivscykeln

Som visas i bilden nedan är tillverkningslivscykeln uppdelad i tre faser: *planera*, *utföra* och *slutföra*.

[![Tillverkningskörningsfaser när en enskild miljö används](media/mes-phases.png "Tillverkningskörningsfaser när en enskild miljö används")](media/mes-phases-large.png)

_Planeringsfasen_ omfattar produktdefinition, planering, skapande och tidsplanering av order och frisläppning. Frisläppningssteget visar över gången från _planeringsfasen_ till _körningsfasen_. När en tillverkningsorder frisläpps visas produktionsorderjobben på produktionsvåningen och är klara för körning.

När ett produktionsjobb markeras som slutfört flyttas det från _körningsfasen_ till _avslutningsfasen_. I _Avslutningsfasen_ går registreringar från *Körningsfasen* går igenom ett godkännandearbetsflöde där de beräknas, godkänns och överförs. Vid den tidpunkten slutförs tillverkningsordern. Underlaget för arbetarens lön genereras därför.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Dela körningsfasen i en separat arbetsbelastning

Som följande bild visar, när skalenheter används delas _körningsfasen_ ut som separat arbetsbelastning.

[![Produktionskörningsfaser när skalenheter används](media/mes-phases-workloads.png "Produktionskörningsfaser när skalenheter används")](media/mes-phases-workloads-large.png)

Modellen hämtas nu från en installation med enkel instans till en modell som baseras på navet och skalenheten. _Planeringsfasen_ och _avslutningsfasen_ körs som backoffice-operationer på navet och arbetsbelastningen för tillverkningskörning körs på skalenheterna. Data överförs asynkront mellan nav och skalenhet.

När en tillverknings order frisläpps på navet överförs alla data som krävs för att bearbeta produktions jobben till skalenheten. Dessa data omfattar produktionsorder, produktionsflöden, strukturlistor och produkter. Data som inte är relaterade till en tillverkningsorder (t.ex. indirekta aktiviteter, frånvarokoder och produktionsparametrar) överförs också från navet till skalenheten. Som regel kan data som kommer från navet och som överförs till skalenheten bara skapas eller uppdateras på navet. En ny frånvarokod eller indirekt aktivitet kan till exempel inte skapas i skalenheten&mdash;de kan bara användas för registrering. Registreringarna som görs på skalenheten under körningen överförs sedan till navet, där godkännande av tid och närvaro, lager och ekonomiska uppdateringar bearbetas.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Tillverkningskörningsuppgifter som kan köras på arbetsbelastningar

Följande uppgifter för tillverkningskörning kan förnärvarande köras på arbetsbelastningar när skalenheter används:

- Instämpling, inloggning, utstämpling och frånvaro
- Startjobb
- Bunta jobb
- Rapportförlopp
- Rapportera kassation
- Indirekt aktivitet
- Avbrott

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Arbeta med arbetsbelastningar för tillverkningskörning på navet

De processer som krävs för att köra arbetsbelastningar i tillverkningsprocessen körs automatiskt för att behålla navet och alla skalenheter synkroniserade efter behov. Om du däremot har problem kan du manuellt utlösa bearbetningen av råregistreringar som tas emot från arbetsbelastningar och/eller kontrollera bearbetningsloggen för registrering.

### <a name="manually-process-raw-registrations"></a>Bearbeta råregistreringar manuellt

Ett batchjobb i Supply Chain Management körs automatiskt för att bearbeta alla registreringar som har mottagits från arbetsbördan. Det här jobbet skapar de nödvändiga produktionsjournalerna och loggboksposter när en registrering bearbetas för ett slutfört jobb på arbetsbelastningen.

Även om jobbet vanligtvis körs automatiskt kan du när som helst köra det manuellt genom att logga in på navet och gå till **produktionskontrollen \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> behandla råregistreringar**.

### <a name="check-the-raw-registration-processing-log"></a>Kontrollera bearbetningsloggen för råregistreringar

Du kan granska bearbetningsloggen för registrering genom att logga in på navet och gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> bearbetningslogg för råregistrering**. På sidan **bearbetningslogg för råregistrering** visas en lista över bearbetade råregistreringar och status för varje registrering.

![Sidan bearbetningslogg för råregistreringar](media/mes-processing-log.png "Sidan bearbetningslogg för råregistreringar")

Du kan arbeta med valfri registrering i listan genom att markera den och sedan välja någon av följande knappar i åtgärdsfönstret:

- **Process** – bearbeta den valda registreringen manuellt. Den här åtgärden kan vara användbar om jobbet _Bearbeta råregistreringar_ inte körs eller om det misslyckas.
- **Avbryt** – Avbryt den valda registreringen.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Arbeta med arbetsbelastningar för tillverkningskörning på en skalenhet

De processer som krävs för att köra arbetsbelastningar i tillverkningsprocessen körs automatiskt för att behålla navet och alla skalenheter synkroniserade efter behov. Om du har problem kan du emellertid kontrollera historiken för order som har bearbetats på en skalenhet eller köra jobbet _tillverkningsnav till skalenhet meddelandeprocessor_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Visa historiken för tillverkningsjobb som har bearbetats på en skalenhet

För att granska historiken om tillverkningsjobb som har bearbetats på en skalenhet, logga in på skalenheten och gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> historiken för bearbetning av tillverkningsjobb**. Sidan **historik för bearbetning av tillverkningsjobb** visar bearbetningshistoriken för tillverkningsorder på skalenheten. Du kan arbeta med valfri produktionsorder i listan genom att markera den och sedan välja någon av följande knappar i åtgärdsfönstret:

- **Process** – bearbeta den valda produktionsorder manuellt.
- **Avbryt** – Avbryt den valda produktionsordern.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Tillverkningsnav till skalenhet meddelande processorjobb

Jobbet _Tillverkningsnav till skalenhet meddelande processorjobb_ bearbetar data från navet till skalenheten. Det här jobbet startas automatiskt när arbetsbelastning för tillverkningskörningen distribueras. Du kan dock köra den manuellt när som helst genom att gå till **tillverkningskontroll \> periodiska uppgifter \> hantering av backoffice-arbetsbelastning \> Tillverkningsnav till skalenhet meddelande processorjobb**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]