---
title: Ställ in förutsättningar för avvikelsehantering
description: Använd den här proceduren för att aktivera avvikelsehanteringsprocesser.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a4062acc91e024e3a0a41c0b3cb35ff5ffe2a4a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554239"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Ställ in förutsättningar för avvikelsehantering

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd den här proceduren för att aktivera avvikelsehanteringsprocesser. En avvikelse beskriver en procedur eller artikel med kvalitetsproblem, där beskrivningen innehåller problemets källa och typ. I proceduren används demonstrationsföretag USMF. Vanligtvis utförs den här proceduren av en Kvalitetschef.


## <a name="enable-quality-management-processes-within-the-company"></a>Aktivera kvalitetshanteringprocesser inom företaget
1. Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.
2. Klicka på kvalitetshanteringfliken.
3. Välj Ja i fältet Använd kvalitetshantering.
    * Välj den här parametern om du vill aktivera kvalitetshanteringprocesser för företaget.  
4. Skriv ett nummer i fältet Timtariff.
    * Använd timlön för att ange lokal valuta i fältet Lokal valuta. Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse. Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse och påverkar inte andra funktioner.  
5. Klicka på Rapportinställning.
    * Denna sida låter dig definiera kvalitetsrapportanmärkningstyperna som ska användas för olika slag av kvalitetshanteringrapporter.  
6. Stäng sidan.
7. Stäng sidan.

## <a name="enable-user-for-nonconformance-processing"></a>Gör det möjligt för användare att bearbeta avvikelsen.
1. Gå till Systemadministration > Användare > Användare.
    * För att bearbeta godkännandet av en avvikelse måste användaren som godkänner eller avvisar avvikelser måste ha ett "namn"-värde tilldelat på användarsidan. För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.  
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel i fältet Namn med värdet "Ricardo".
    * Använd filtret för att hitta den användare som ska godkänna eller avvisa avvikelseposterna.  
3. Klicka på länken på den valda raden i listan.
    * För att bearbeta godkännandet av en avvikelse måste användaren som godkänner eller avvisar avvikelser måste ha ett "namn"-värde tilldelat på användarsidan.  
4. Klicka på Användaralternativ.
5. Klicka på fliken Inställningar.
6. Välj Ja i fältet Aktivera dokumenthantering.
    * För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.  
7. Stäng sidan.
8. Stäng sidan.
9. Stäng sidan.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definiera diagnostyper för bearbetning av avvikelse
1. Gå till Lagerhantering > Inställningar > Kvalitetshantering > Diagnostyper.
    * Använd sidan Diagnostyper för att definiera klassificeringen av diagnosåtgärder. En korrigering identifierar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, vem som ska genomföra den samt begärt och planerat slutförandedatum.  
2. Klicka på Ny.
3. Ange ett värde i fältet Diagnoser.
4. Ange ett värde i fältet Beskrivning.
5. Stäng sidan.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definiera kvalitetsavgifter för bearbetning av avvikelse
1. Gå till Lagerhantering > Inställningar > Kvalitetshantering > Kvalitetsavgifter.
    * Använd sidan Kvalitetsavgifter för att definiera klassificeringen av avgifter som ska användas i åtgärder relaterade till avvikelser.  
2. Klicka på Ny.
3. I fältet Kod för avgifter, skriv ett värde.
4. Ange ett värde i fältet Beskrivning.
5. Stäng sidan.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definiera operationer för bearbetning av avvikelse
1. Gå till Lagerhantering > Inställningar > Kvalitetshantering > Operationer.
    * Använd sidan Operationer för att definiera klassificeringen av det arbete som kan utföras vid en godkänd avvikelse. När du relaterar en operation till en avvikelse kan du definiera detaljerad information om material, arbetstid och tillägg som krävs för att operationen ska kunna genomföras. Denna information utgör beräkningsgrunden när kostnaden för utförandet av operationen ska uppskattas.  
2. Klicka på Ny.
3. Ange ett värde i fältet Operation.
4. Ange ett värde i fältet Beskrivning.
5. Stäng sidan.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definiera problemtyper för bearbetning av avvikelse
1. Gå till Lagerhantering > Inställningar > Kvalitetshantering > Problemtyper.
    * Använd sidan Problemtyper för att definiera en klassificering av kvalitetsproblem som uppstår i de olika avvikelsetyperna. Avvikelsetyperna omfattar: Internt, Kund, Leverantör, Servicebegäran, Produktion och Produktion av samprodukt. En enskild problemtyp kan kopplas till flera avvikelsetyper.  
2. Klicka på Ny.
3. Ange ett värde i fältet Problemtyp.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Avvikelsetyper.
    * Använd sidan Avvikelsetyper för att auktorisera en problemtyp som ska användas i en eller flera avvikelsetyper. Exempelvis kan en problemtyp som har att göra med en defekt kod gälla för alla avvikelsetyper, medan en problemtyp för kundklagomål endast kan gälla för avvikelsetyperna kund och serviceförfrågan.  
6. Klicka på Ny.
7. Markera vald rad i listan.
8. Välj ett alternativ i fältet Typ av avvikelse.
9. Stäng sidan.
10. Stäng sidan.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definiera karantänzoner för bearbetning av avvikelse
1. Gå till Lagerhantering > Inställningar > Kvalitetshantering > Karantänzoner.
2. Klicka på Ny.
3. Skriv ett värde i fältet Karantänzon.
4. Ange ett värde i fältet Beskrivning.
5. Stäng sidan.

