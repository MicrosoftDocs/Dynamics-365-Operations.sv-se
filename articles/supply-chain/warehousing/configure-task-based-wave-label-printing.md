---
title: Tidsplanera påfyllnadsetikett utskrift under påfyllnad
description: I denna artikel beskrivs hur du konfigurerar och använder funktionerna för uppgiftsbaserad utskrift av påfyllnadsetikett.
author: perlynne
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ac2bc4cce42bada43334b82301d716414cd6d654
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889469"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Tidsplanera påfyllnadsetikett utskrift under påfyllnad

[!include [banner](../../includes/banner.md)]

Använd *utskriftsfunktionen för påfyllnadsetiketter* som en del av din påfyllnadsprocess för att förbättra effektiviteten och låta systemet skapa påfyllnadsetiketter och arbeta i separata uppgifter.

Processen för konfiguration av påfyllnadsetikett utskrift är komplex och bygger på korrekt konfiguration och huvuddata. Det fungerar inte för att genereringen av påfyllnadsetikett poster ska misslyckas och när den gör det rullas hela påfyllnadsbearbetningen tillbaka. Med hjälp av den *uppgiftsbaserade utskriftsfunktionen* för påfyllnadsetiketter slipper du skapa om arbete och arbetsrader på nytt varje gång en påfyllnadsetikett skrivs ut på fel sätt.

När du använder *utskriftsfunktionen för påfyllnadsetiketter* som baseras på uppgifter skapar systemet först arbete och arbetsrader. Därefter skapas och skrivs påfyllnadsetiketter ut. Slutligen, om påfyllnadsetiketterna skapas korrekt, frisläpper det arbete och påfyllnad för plockning.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Aktivera funktionen för utskrift av påfyllnadsetiketter med uppgiftsbaserad påfyllnad i funktionshanteringen

För att kunna använda de funktioner som beskrivs i denna artikel måste de vara aktiverade för ditt system. Använda [utgiftshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) aktiverar du följande funktioner i ordning:

1. *Påfyllnadsetikettsutskrift* – Den här funktionen krävs för att aktivera påfyllnadsprocessmetoden för utskrift av påfyllnadsetikett.
1. *Arbetsspärr för hela organisationen* – Denna funktion krävs för både manuell och automatisk konfiguration av planerat arbete. (Från och med version 10.0.21 av Supply Chain Management är den här funktionen obligatorisk, varför den är aktiverad som standard och inte kan stängas av igen.)
1. *Uppgiftsbaserad påfyllnadsetikettsutskrift* – Den här funktionen behövs för att dela upp påfyllnadsetikettsutskrift i ett separat transaktionsintervall.

## <a name="manually-enable-the-new-wave-step-method"></a>Aktivera den nya påfyllnadsstegmetoden manuellt

Börja med att skapa den nya påfyllnadsstegmetoden och aktivera den för parallell asynkron uppgiftsbearbetning.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Klicka på **återskapa metod** i åtgärdsfönstret. Lägg märke till att *waveLabelPrinting* läggs till i listan över de påfyllnadsprocessmetoder som du kan använda i mallarna för påfyllnad.
1. Välj den post där fältet **Metodnamn** är inställt på *waveLabelPrinting* och välj sedan **Uppgiftskonfiguration** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Lagerställe** – Välj det lager du ska använda för att schemalägga bearbetning av arbete. (Om du använder demodata för testsyften kan du välja lagerställe *24*.)
    - **Maximalt antal batchuppgifter** – Ange ett maximalt antal batchuppgifter. I de flesta fall bör värdet vara från *8* till *16*. Vi rekommenderar dock att du hittar den optimala inställningen för dina scenarier.
    - **Batchgrupp för påfyllnadsbearbetning** – Välj en särskild batchgrupp för påfyllnadsbearbetning för att optimera bearbetning av batchkö.

Du kan nu uppdatera en befintlig påfyllnadsmall så att den använder påfyllnadsbearbetningsmetoden för *Utskrift av påfyllnadsetikett*. Du kan också skapa en ny påfyllnadsmall där den används.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Välj den påfyllnadsmall som ska uppdateras i listfönstret. (Om du använder demodata för testsyften kan du välja lagerställe *24 leveransstandard*.)
1. På snabbfliken **Metoder**, i kolumnen **Återstående metoder**, markerar du den rad där fältet **Namn** är inställt på *waveLabelPrinting*.
1. Välj **lägg till** (höger pilknapp) för att flytta vald rad till kolumnen **Valda metoder**.
1. I fältet **Kod för påfyllnadssteg** ange den kod för påfyllnadssteg som kommer att användas för att ansluta påfyllnadsmallen med en påfyllnadsetikettmall.

## <a name="set-wave-task-processing-threshold-data"></a>Ställ in tröskelvärdesdata för bearbetning av påfyllnadsuppgift

Första gången en påfyllnadsprocess körs med någon uppgiftsbaserad bearbetning skapar systemet standardtröskeldata för påfyllnadsuppgiftsbehandling Data används för att kontrollera när påfyllnadsbearbetningen kommer att köras asynkront och vara uppgiftsbaserad, vilket gör det möjligt att bearbeta och skapa påfyllnadsetiketter parallellt.

Standarddata använder inledningsvis ett tröskelvärde på *1* för minsta antal på arbets-ID (`MinimumWorkThresholdForLabelPrinting`). Därför, när systemet bearbetar en påfyllnad som har mer än ett arbets-ID, kommer den att använda uppgiftsbaserad bearbetning av påfyllnadsetiketter i en separat transaktion. Du kan infoga/uppdatera dessa data manuellt i `WHSWaveTaskProcessingThresholdParameters` registret i dina testmiljöer. Om du behöver ändra den här inställningen i en produktionsmiljö måste du kontakta Microsofts Support och begära uppdateringen.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Ändringar i påfyllnadsbearbetningslogiken när uppgiftsbaserad påfyllnadsetikettutskrift används

Om påfyllnadsetikettsbearbetningen överskrider tröskelvärdet för bearbetning av påfyllnadsuppgiften initieras uppgiftsbaserad bearbetning. I nästa påfyllnadsbearbetning som passar påfyllnadsmallen körs påfyllnadsetikettsutskriften i en fristående *ttsbegin*/*ttscommit* transaktion omedelbart efter att arbetet har skapats. Om arbets frisläppning (tas bort spärr) är konfigurerad på påfyllnadsmallen så att den körs automatiskt, sker det först när utskriften av påfyllnadsetiketten har slutförts.

Om påfyllnadsetikett genereringen misslyckas (om till exempel konverteringen av arbetskvantiteten till påfyllnadsetikettskvantiteten misslyckas och ett fel uppstår), misslyckas bara lämplig transaktion. Arbetet som tidigare skapades förblir låst. Gör på följande sätt om du vill korrigera fel och skriva ut påfyllnadsetiketterna.

1. Gå till **Warehouse management \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj relevant påfyllnad i rutnätet.
1. I Åtgärdsfönstret, på fliken **påfyllning**, i gruppen **skriv ut**, markerar du **påfyllnadsetiketter**.
1. Följ instruktionerna på skärmen om du vill skicka etiketter för utskrift.
1. I åtgärdsfönstret på fliken **Påfyllnad** i gruppen **Påfyllnad** välj **Frisläppa** för att manuellt frisläppa arbetet för den valda påfyllnaden.

## <a name="additional-resources"></a>Ytterligare resurser

- [Utskrift av påfyllnadsetikett](configure-wave-label-printing.md)
- [Tidsplanera att skapa arbete under påfyllnad](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
