---
title: Schemalägga arbetsskapande under cykel
description: Det här avsnittet beskriver hur du ställer in och använder metoden Schemalägga arbetsskapande under cykel.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078308"
---
# <a name="schedule-work-creation-during-wave"></a>Schemalägga arbetsskapande under cykel

[!include [banner](../includes/banner.md)]

Använd funktionen *Schemalägga arbetsskapande* som en del av din påfyllnadsprocess för att öka påfyllnadsprocessens genomströmning genom att systemet skapar arbete med parallell bearbetning.

När funktionaliteten är aktiverad kommer planerat arbete automatiskt att få skapat, vilket systemet så småningom kommer att bearbeta för att skapa verkligt arbete. Om antalet påfyllnadsbelastningsrader når ett förutbestämt tröskelvärde kommer systemet att skapa verkligt arbete snabbare genom att tillämpa parallell, asynkron bearbetning.

## <a name="enable-the-schedule-work-creation-feature"></a>Aktivera funktionen Schemalägga arbetsskapande

### <a name="enable-the-feature-in-feature-management"></a>Aktivera nya funktioner i funktionshantering

Innan du kan använda funktionen *Schemalägga arbetsskapande* den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Schemalägga arbetsskapande*

> [!NOTE]
> Funktionen *Arbetsspärr för hela organisationen* måste vara aktiverad innan du kan aktivera *Schemalägga arbetsskapande*.

### <a name="manually-enable-batch-processing-of-waves"></a>Aktivera batchbearbetning av påfyllnad manuellt

För att dra nytta av en parallell asynkron metod för att skapa lagerarbete, måste din påfyllnadsprocess köras i batch. Så här ställer du in det:

1. Gå till  **Lagerstyrning\>Inställningar\>Parametrar för lagerstyrning**.

1. På sidan **Allmänt**, ange **Behandla påfyllnader i batch** till *Ja*. Eventuellt kan du också välja en dedikerad **Batchgrupp för påfyllnadsbearbetning** för att förhindra att din batch-kö bearbetning körs samtidigt som andra processer.

1. Ange **Vänta på lås (ms) tid**, som gäller när systemet bearbetar flera påfyllningar samtidigt. För de flesta större påfyllningsprocesser rekommenderar vi ett värde på *60000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Aktivera metoden nytt påfyllnadssteg manuellt för befintliga påfyllnadsmallar

Börja med att skapa den nya påfyllnadsstegmetoden och aktivera den för parallell asynkron uppgiftsbearbetning.

1. Gå till  **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.

1. Välj  **återskapa metoder** och observera att *WHSScheduleWorkCreationWaveStepMethod* har lagts till i listan över metoder för påfyllnadsprocess kan du använda i påfyllnadsmallar för leverans.

1. Välj posten med **metodnamnet** *WHSScheduleWorkCreationWaveStepMethod* och välj **Konfiguration av uppgift**.

1. Välj om du vill lägga till en ny rad i rutnätet **Ny** i åtgärdsfönstret och använd följande inställningar:

    - **Lagerställe** - Välj det lager du ska använda för att schemalägga bearbetning av arbete.

    - **Maximalt antal batchuppgifter** - Ange ett maximalt antal batchuppgifter. I de flesta fall bör detta värde vara i intervallet från 8-16, men vi rekommenderar att du experimenterar med den optimala inställningen baserat på dina scenarier.

    - **Batchgrupp för påfyllnadsbearbetning** - Välj en särskild batchgrupp för påfyllnadsbearbetning för att optimera bearbetning av batchkö.

Nu är du redo att uppdatera en befintlig påfyllnadsmall (eller skapa en ny) för att använda metoden för påfyllnadsbearbetning *Schemalägga arbetsskapande*.

1. Gå till  **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.

1. I åtgärdsfönstret väljer du **Redigera**.

1. I listfönstret väljer du den påfyllnadsmall som du vill uppdatera (om du testar med demodata kan du använda *standardvärdet för leverans 24*).

1. Expandera snabbflikarna **Metoder** och markera raden med hjälp av **Namn** *Schemalägga arbetsskapande* i rutnätet **Resterande metoder**.

1. Markera pilen som pekar på kolumnen **Markerade metoder** om du vill flytta den markerade raden till den kolumnen. (Du kan bara ha en vald metod åt gången som använder endera *WHSScheduleWorkCreationWaveStepMethod* eller *createWork*, så den befintliga raden med **metodnamn** *createWork* flyttas automatiskt till rutnätet **Resterande metoder**.)

## <a name="set-wave-task-processing-threshold-data"></a>Ställ in tröskelvärdesdata för bearbetning av påfyllnadsuppgift

Systemet skapar tröskeldata för standardaktivitetsbearbetning första gången en påfyllnadsprocess körs med hjälp av uppgiftsbaserad bearbetning. Data används för att kontrollera när påfyllnadsbearbetningen kommer att köras asynkront och vara uppgiftsbaserad, vilket gör det möjligt att bearbeta och skapa arbete parallellt.

Standarddata använder inledningsvis ett tröskelvärde på 15 för minsta antal belastningsrader (MINIMUMLINESLOADLINES). Det innebär att när systemet bearbetar en våg med mer än 15 belastningsrader kommer den att använda asynkron uppgiftsbearbetning. Du kan manuellt infoga/uppdatera dessa data i tabellen **WHSWaveTaskProcessingThresholdParameters** i testmiljöerna, men om du behöver ändra den här inställningen i en produktionsmiljö måste du kontakta Microsoft Support och begära uppdateringen.

## <a name="work-with-the-feature"></a>Arbeta med funktionen

När funktionen *Schemalägga arbetsskapande* är aktiverad kommer påfyllnadsbehandling att skapa planerat arbete, som så småningom kommer att användas av den nya arbetsskapande processen. När arbetet skapas spärras arbetet med funktionen *Arbetsspärr för hela organisationen*.

Flödesschemat nedan visar hur planerat arbete skapas under påfyllnadsbearbetning.

![Skapa tidsplan för arbete](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Planerat arbete

Sidan **Information om planerat arbete** (**Lagerstyrning \> Arbete \> Information om planerat arbete**) visar information om det planerade arbetet som ursprungligen skapas under påfyllnadsbehandling. Följande värden för **Processtatus** finns:

- **Köad** - Det planerade arbetet väntar på att användas för att skapa arbete.
- **Slutfört** - Det planerade arbetet har använts för att skapa arbete.
- **Misslyckat** - påfyllnadsbearbetningen har misslyckats. Observera att det planerade arbetet kan vara i **misslyckat** läge med eller utan relaterat faktiskt arbete. När den faktiska processen för att skapa arbete misslyckas, kvarstår det faktiska arbetet med status *Annullerat*.

### <a name="batch-job-for-the-work-creation-process"></a>Batchjobb för att skapa arbete

Om du vill visa batchjobben för påfyllnadsbearbetning, välj **batchjobb** i åtgärdsfönstret på sidan **Alla påfyllnader**.

Här kan du visa alla batchuppgiftsdetaljer för varje batchjobb-ID.
