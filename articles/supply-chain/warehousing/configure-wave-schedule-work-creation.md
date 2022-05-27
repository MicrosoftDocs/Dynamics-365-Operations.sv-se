---
title: Schemalägga arbetsskapande under cykel
description: Det här avsnittet beskriver hur du ställer in och använder metoden Schemalägga arbetsskapande under cykel.
author: Mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c955e7275c0bdc12dc206dde1d7e390f16270148
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691143"
---
# <a name="schedule-work-creation-during-wave"></a>Schemalägga arbetsskapande under cykel

[!include [banner](../../includes/banner.md)]

Använd funktionen *Schemalägga arbetsskapande* som en del av din påfyllnadsprocess för att öka påfyllnadsprocessens genomströmning genom att systemet skapar arbete med parallell bearbetning.

När funktionaliteten är aktiverad kommer planerat arbete automatiskt att få skapat, vilket systemet så småningom kommer att bearbeta för att skapa verkligt arbete. Om antalet påfyllnadsbelastningsrader når ett förutbestämt tröskelvärde kommer systemet att skapa verkligt arbete snabbare genom att tillämpa parallell, asynkron bearbetning.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Aktivera funktionerna för att skapa tidsplanerat arbete i funktionshanteringen

De funktioner som beskrivs i det här avsnittet måste vara inaktiverade för ditt system. Använda [utgiftshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) aktiverar du följande funktioner i följande ordning:

1. **Arbetsspärr för hela organisationen** – Krävs för både manuell och automatisk konfiguration av planerat arbete. (Från och med version 10.0.21 av Supply Chain Management är den här funktionen obligatorisk, varför den är aktiverad som standard och inte kan stängas av igen.)
1. **Schemalägga arbetsskapande** – Krävs för både manuell och automatisk konfiguration av planerat arbete.
1. **Organisationsomfattande påfyllnadsmetod "Schemalägg arbetet"** – Krävs för både manuell och automatisk konfiguration av planerat arbete. Du behöver inte den här funktionen om du bara vill använda manuell konfiguration.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Konfigurera tidsplanerat arbete automatiskt

Om du aktiverar funktionen *påfyllnadsmetoden Organisationsomfattande påfyllnadsmetod* följande automatiskt i systemet:

- Påfyllnadsmetoden *Skapa tidsplan för arbete* (`WHSScheduleWorkCreationWaveStepMethod`) läggs till och konfigureras att köra parallellt över alla juridiska enheter.
- Påfyllnadsmallar från alla juridiska personer som har typ av **Påfyllnadsmalltyp** anges till *Leverans* and **Mallstatus** anges till *Giltig* kommer att ersätta metoden *Skapa arbete* med *Schemalägga skapande av arbete*. Påfyllnadsmallar från juridiska personer där metoden *Skapa arbete* får repeteras kommer inte att ändras.
- Uppgiftskonfigurationer för metoden *Skapa arbetsschema* kommer att skapas för alla lager från alla juridiska enheter som har **Använd lagerstyrningsprocesser** aktiverad. Det innebär att metoden *Schemalägga skapande av arbete* körs parallellt som standard. Befintliga lagerställen som du ändrar **Använd lagerstyrningsprocesser** från *Nej* till *Ja* kommer som standard också att köra den här metoden parallellt.
- lla juridiska personer bearbetar påfyllnader i batchar och **Vänta på lås (ms)** anges till ett standardvärde på *60 000* ms om det tidigare har satts till *0* ms.
- Alla nya påfyllnadsmallar som du skapar kommer att ha metoden *Schemalägg skapande av arbete* i stället för metoden *Skapa arbete*.

De befintliga konfigurationerna av uppgift och påfyllnadsbehandling kommer också att behållas för alla juridiska enheter som redan är konfigurerade för att bearbeta påfyllnader i partier, och för alla lager som redan är konfigurerade för att använda konfigurationerna kommer också att sparas för alla juridiska enheter som redan är konfigurerade för att behandla påfyllnader i bacther och för alla lager som redan är konfigurerade för att använda metoden *Schemalägg skapande av arbete* parallellt.

Om det behövs kan du manuellt återställa någon eller alla inställningar som görs automatiskt när du aktiverar funktionen *Metoden för organisationsomfattande schemaläggning av skapande av arbete* genom att göra följande:

- För påfyllnadsmallar, gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**. Ersätt metoden *Schemalägga arbetsskapande* med *Skapa arbete*.
- För lagerparametrar, gå till **Warehouse management \> Inställningar \> Parametrar för lagerstyrning**. På fliken **Påfyllnadsbearbetning** använder du de prioriterade värdena för **Bearbeta påfyllnader i batch** och **Vänta på lås (ms)**.
- För påfyllnadsmetoder, gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**. Välj `WHSScheduleWorkCreationWaveStepMethod` och i åtgärdsfönstret, välj **Uppgiftskonfiguration**. Ändra eller radera antalet batchuppgifter och den tilldelade påfyllnadsgruppen för respektive lagerställe i listan efter behov.

## <a name="manually-configure-scheduled-work-creation"></a>Konfigurera tidsplanerat arbete manuellt

Om du inte har aktiverat funktionen [*Organisationsomfattande påfyllnadsmetod "Schemalägga arbetsskapande"*](#Auto-enable-schedule-work-creation) kan du använda procedurerna i det här avsnittet för att manuellt konfigurera schemalagda arbetstillfällen efter behov.

### <a name="manually-enable-batch-processing-of-waves"></a>Aktivera batchbearbetning av påfyllnad manuellt

För att dra nytta av en parallell asynkron metod för att skapa lagerarbete, måste din påfyllnadsprocess köras i batch. Så här ställer du in det:

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. På sidan **Allmänt**, ange **Behandla påfyllnader i batch** till *Ja*. Eventuellt kan du också välja en dedikerad **Batchgrupp för påfyllnadsbearbetning** för att förhindra att din batch-kö bearbetning körs samtidigt som andra processer.
1. Ange **Vänta på lås (ms) tid**, som gäller när systemet bearbetar flera påfyllningar samtidigt. För de flesta större påfyllningsprocesser rekommenderar vi ett värde på *60000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Aktivera metoden nytt påfyllnadssteg manuellt för befintliga påfyllnadsmallar

Börja med att skapa den nya påfyllnadsstegmetoden och aktivera den för parallell asynkron uppgiftsbearbetning.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Välj **återskapa metoder** och observera att *WHSScheduleWorkCreationWaveStepMethod* har lagts till i listan över metoder för påfyllnadsprocess kan du använda i påfyllnadsmallar för leverans.
1. Välj posten med **metodnamnet** *WHSScheduleWorkCreationWaveStepMethod* och välj **Konfiguration av uppgift**.
1. Välj om du vill lägga till en ny rad i rutnätet **Ny** i åtgärdsfönstret och använd följande inställningar:

    - **Lagerställe** – Välj det lager du ska använda för att schemalägga bearbetning av arbete.
    - **Maximalt antal batchuppgifter** – Ange ett maximalt antal batchuppgifter. I de flesta fall bör detta värde vara i intervallet från 8-16, men vi rekommenderar att du experimenterar med den optimala inställningen baserat på dina scenarier.
    - **Batchgrupp för påfyllnadsbearbetning** – Välj en särskild batchgrupp för påfyllnadsbearbetning för att optimera bearbetning av batchkö.

Nu är du redo att uppdatera en befintlig påfyllnadsmall (eller skapa en ny) för att använda metoden för påfyllnadsbearbetning *Schemalägga arbetsskapande*.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I listfönstret väljer du den påfyllnadsmall som du vill uppdatera (om du testar med demodata kan du använda *standardvärdet för leverans 24*).
1. Expandera snabbflikarna **Metoder** och markera raden med hjälp av **Namn** *Schemalägga arbetsskapande* i rutnätet **Resterande metoder**.
1. Markera pilen som pekar på kolumnen **Markerade metoder** om du vill flytta den markerade raden till den kolumnen. (Du kan bara ha en vald metod åt gången som använder endera `WHSScheduleWorkCreationWaveStepMethod` eller `createWork`, så den befintliga raden med **Metodnamn** `createWork` flyttas automatiskt till rutnätet **Resterande metoder**.)

## <a name="set-wave-task-processing-threshold-data"></a>Ställ in tröskelvärdesdata för bearbetning av påfyllnadsuppgift

Systemet skapar tröskeldata för standardaktivitetsbearbetning första gången en påfyllnadsprocess körs med hjälp av uppgiftsbaserad bearbetning. Data används för att kontrollera när påfyllnadsbearbetningen kommer att köras asynkront och vara uppgiftsbaserad, vilket gör det möjligt att bearbeta och skapa arbete parallellt.

Standarddata använder inledningsvis ett tröskelvärde på 15 för minsta antal belastningsrader (`MINIMUMWAVELOADLINES`). Det innebär att när systemet bearbetar en våg med mer än 15 belastningsrader kommer den att använda asynkron uppgiftsbearbetning. Du kan infoga/uppdatera dessa data manuellt i `WHSWaveTaskProcessingThresholdParameters` registret i dina testmiljöer. Om du behöver ändra den här inställningen i en produktionsmiljö måste du kontakta Microsofts Support och begära uppdateringen.

## <a name="work-with-the-scheduled-work-creation"></a>Arbeta med det planerade arbetet som skapas

Mer information om hur du arbetar med att skapa planerat arbete finns i [Skapa och bearbeta påfyllnad ](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
