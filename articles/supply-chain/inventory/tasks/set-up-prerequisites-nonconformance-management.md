---
title: Ställ in förutsättningar för avvikelsehantering
description: Använd det här avsnittet för att aktivera avvikelsehanteringsprocesser.
author: perlynne
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80a7ae2249179c561d03f7b729ebb942ba856046
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961533"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Ställ in förutsättningar för avvikelsehantering

[!include [banner](../../includes/banner.md)]

Använd det här avsnittet för att aktivera avvikelsehanteringsprocesser. En avvikelse beskriver en procedur eller artikel med kvalitetsproblem, där beskrivningen innehåller problemets källa och typ. I proceduren används demonstrationsföretag USMF. Vanligtvis utförs den här proceduren av en Kvalitetschef.


## <a name="enable-quality-management-processes-within-the-company"></a>Aktivera kvalitetshanteringprocesser inom företaget
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning**.
2. Välj fliken **Kvalitetshantering**.
3. Välj **Ja** i fältet **Använd kvalitetshantering** när du vill aktivera kvalitetshanteringsprocesser för företaget.
4. Ange en siffra i den lokala valutan i fältet **Timtariff**. Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse. Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse och påverkar inte andra funktioner.  
5. Välj **Rapportinställningar** för att definiera kvalitetsrapportanmärkningstyperna som ska användas för olika slag av kvalitetshanteringsrapporter.

## <a name="enable-user-for-nonconformance-processing"></a>Gör det möjligt för användare att bearbeta avvikelsen.
1. I navigeringsfönstret, gå till **Moduler > Systemadministration > Användare > Användare**. 
2. Använd snabbfiltret för att hitta den användare som ska godkänna eller avvisa avvikelseposterna. Filtrera till exempel på fältet **Namn** med värdet `Ricardo`. För att bearbeta godkännandet av en avvikelse måste användaren som godkänner eller avvisar avvikelser ha ett "Namn"-värde tilldelat på sidan **Användare**. För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.  
3. Markera raden för önskad post.
4. Välj **Användaralternativ**.
5. Välj fliken **Inställningar**.
6. Välj **Ja** i fältet **Aktivera dokumenthantering**.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definiera diagnostyper för bearbetning av avvikelse
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Kvalitetshantering > Diagnostyper**. Använd sidan **Diagnostyper** för att definiera klassificeringen av diagnosåtgärder. En korrigering identifierar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, vem som ska genomföra den samt begärt och planerat slutförandedatum.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Diagnostik**.
4. I fältet **Beskrivning** anger du ett värde.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definiera kvalitetsavgifter för bearbetning av avvikelse
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Kvalitetshantering > Kvalitetsavgifter**. Använd sidan **Kvalitetsavgifter** för att definiera klassificeringen av avgifter som ska användas i åtgärder relaterade till avvikelser.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Kod för avgifter**.
4. I fältet **Beskrivning** anger du ett värde.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definiera operationer för bearbetning av avvikelse
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Kvalitetshantering > Åtgärder**. Använd sidan **Åtgärder** för att definiera klassificeringen av det arbete som kan utföras vid en godkänd avvikelse. När du relaterar en operation till en avvikelse kan du definiera detaljerad information om material, arbetstid och tillägg som krävs för att operationen ska kunna genomföras. Denna information utgör beräkningsgrunden när kostnaden för utförandet av operationen ska uppskattas.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Åtgärd**.
4. I fältet **Beskrivning** anger du ett värde.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definiera problemtyper för bearbetning av avvikelse
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Kvalitetshantering > Problemtyper**. Använd sidan **Problemtyper** för att definiera en klassificering av kvalitetsproblem som uppstår i de olika avvikelsetyperna. Avvikelsetyperna omfattar: **Internt**, **Kunde**, **Leverantör**, **Servicebegäran**, **Produktion** och **Produktion av samprodukt**. En enskild problemtyp kan kopplas till flera avvikelsetyper.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Problemtyp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj **Avvikelsetyper**. Använd sidan **Avvikelsetyper** för att auktorisera en problemtyp som ska användas för en eller flera avvikelsetyper. Exempelvis kan en problemtyp som har att göra med en defekt kod gälla för alla avvikelsetyper, medan en problemtyp för kundklagomål endast kan gälla för avvikelsetyperna kund och serviceförfrågan.  
6. Välj **Ny**.
7. Välj ett alternativ i fältet **Avvikelsetyp** för den nya raden.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definiera karantänzoner för bearbetning av avvikelse
1. I navigeringsfönstret gå till **Moduler > Lagerhantering > Inställningar > Kvalitetshantering > Karantänzoner**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Karantänzon**.
4. I fältet **Beskrivning** anger du ett värde.
5. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]