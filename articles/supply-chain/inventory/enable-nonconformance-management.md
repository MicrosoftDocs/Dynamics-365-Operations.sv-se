---
title: Avvikelsehantering
description: "Det här avsnittet ger en beskrivning av grundläggande inställningar som krävs för att använda avvikelser. Ytterligare inställningar krävs om du vill använda kvalitetsorder."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: ba518bc1b2e0811d07ed2811e8e1da4812d02899
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="nonconformance-management"></a>Avvikelsehantering

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en beskrivning av grundläggande inställningar som krävs för att använda avvikelser. Ytterligare inställningar krävs om du vill använda kvalitetsorder.

Gör så här om du vill aktivera avvikelsehantering:

1.  Definiera parametrarna för hantering av lager och lagerstyrning som används till avvikelser:
    -   Välj alternativet **Ja** för **Använd kvalitetshantering**.
    -   Ange timlön i den lokala valutan i fältet **Timtariff**. Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse. Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse. De påverkar inte andra funktioner.
    -   Använd fliken **Kvalitetshantering** på sidan **Rapportinställningar** för att definiera den dokumenttyp som ska skrivas ut. Du kan skriva ut en avvikelserapport, en avvikelseetikett eller en korrigeringsrapport. Du kan definiera mer än en post för utskrift av olika dokumenttyper på en rapport, eller för utskrift av interna eller externa noteringar. Det kan vara praktiskt att använda sidan **Dokumenttyp** för att definiera en unik dokumenttyp för avvikelser och en unik dokumenttyp för korrigeringar. Du kan till exempel ange anteckningar om avvikelser genom att använda den unika dokumenttypen för avvikelser. I det här fallet identifierar du den unika dokumenttypen i rapportalternativen.
    -   Aktivera nummerserier för referenser för avvikelser och korrigeringar.

2.  Gör det möjligt för användare att godkänna avvikelser. Använd fältet **Namn** på sidan **Användare** för att tilldela en medarbetare till varje användare som måste godkänna en avvikelse. Systemet använder medarbetarna som ändrar status för en avvikelse för att följa avvikelsehistoriken. Användarna kan inte godkänna en avvikelse, om de inte har tilldelats en medarbetaridentifierare.
3.  Definiera vilka problemtyper som avvikelser ska kunna tilldelas. Använd sidan **Problemtyper** för att definiera en klassificering av kvalitetsproblem som uppstår i de olika avvikelsetyperna. Du kan ställa in följande avvikelsetyper: **Internt**, **Kund**, **Leverantör**, **Servicebegäran**, **Produktion** och **Produktion av samprodukt**. Använd sidan **Avvikelsetyper** för att auktorisera en problemtyp som ska användas i en eller flera avvikelsetyper. Exempelvis kan en problemtyp som har att göra med en defektkod gälla för alla avvikelsetyper, medan en problemtyp som gäller kundklagomål bara kan gälla avvikelsetyperna **Kund** och **Serviceförfrågan**.
4.  Definiera de karantänzoner som ska utgöra riktlinjer för hanteringen av defekt material. Använd sidan **Karantänzoner** för att definiera vilka zoner som kan tilldelas en avvikelse. På den utskrivna avvikelsetaggen anges den tilldelade karantänzonen samt information om användning för att ge vägledning om hur defekt material kan hanteras. Zonerna kan överensstämma med lagerplatser eller verksamhetsresurser.
5.  Definiera de diagnostyper som ska tilldelas till korrigeringar. Använd sidan **Diagnostyper** för att definiera klassificeringen av diagnosåtgärder. En korrigering specificerar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, och vem som ska genomföra åtgärden. Även det begärda slutförandedatumet och det planerade slutförandedatumet anges.
6.  Definiera de relaterade operationer som ska tilldelas till avvikelser. Använd sidan **Åtgärder** för att definiera klassificeringen av det arbete som kan utföras vid en godkänd avvikelse. När en relaterad operation tilldelas till en avvikelse kan du definiera detaljerad information om material, arbetstid och tillägg som krävs för att operationen ska kunna genomföras. Den här informationen används för att beräkna en uppskattad kostnad för operationen. Den detaljerade informationen och de uppskattade kostnaderna anges i referenssyfte. Relaterade kvalitetsoperationer skiljer sig från de operationer som kan definieras för ett produktionsflöde.


<a name="see-also"></a>Se även
--------

[Skapa och bearbeta en avvikelse (uppgiftsguide)](tasks/create-process-non-conformance.md)

[Kvalitetshanteringsprocesser](quality-management-processes.md)

[Ställ in förutsättningar för avvikelsehantering (uppgiftsguide)](tasks/set-up-prerequisites-nonconformance-management.md)

