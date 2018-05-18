---
title: "Inställningskrav för produktion"
description: "Det här avsnittet innehåller information om inställningar som måste göras innan du kan arbeta med produktionsstyrningen."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47fe11168ad2ddea2a7033eda8d8bd8220efea32
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="production-setup-requirements"></a>Inställningskrav för produktion

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om inställningar som måste göras innan du kan arbeta med produktionsstyrningen. 

Produktionskontroll integreras med funktioner i andra moduler. Detta gör att du kan ändra tillverkningsorder och se till att de uppdateras automatiskt i alla andra relaterade processer och beräkningar i systemet. Konfigurationsprocedurerna i det här avsnittet visas i den ordning som du ska utföra dem.

## <a name="required-baseline-setup-in-other-modules"></a>Baslinjeinställningar som krävs i andra moduler
En del information måste ställas in i andra moduler för att du ska kunna arbeta med produktionsmodulen. Den här konfigurationen omfattar följande uppgifter:

-   Ställa in allmän företagsinformation.
-   Ställ in redovisningsmodulen.
-   Definiera artikelgrupper.
-   Ställ in redovisningskonton för artikelgrupper.
-   Ställ in lagerartikelregistret i Lagerhantering.
-   Skapa strukturlistor och strukturlisteversioner i Lagerhantering.

## <a name="required-calendar-and-resource-setup"></a>Kalender- och resursinställningar som krävs
Innan du använder Produktionskontroll öppnar du Organisationsadministration och skapar och definierar kalendern och verksamhetsresurserna i följande ordning:

1.  **Arbetstidsmallar** – Ställ in arbetstidsmallar för att definiera de tidsperioder som är tillgängliga för produktionsplanering.
2.  **Kalendrar** – Ställ in arbetstidskalendrar för att definiera vilka dagar under året som är tillgängliga för produktionsplanering.
3.  **Resursgrupper** – Ställ in resursgrupper för att gruppera verksamhetsresurserna så att du kan få en översikt över ledig kapacitet när du kör planeringen. Det är inte nödvändigt att ställa in resursgrupper innan du ställer in verksamhetsresurser. Men vi rekommenderar att du förstår hur du grupperar resurser när du ställer in Produktionskontroll.
4.  **Resurser** – Ställ in verksamhetsresurser för att definiera de resurser som används för att genomföra produktionsprocessen och planera för kapacitet.

## <a name="required-production-parameters-setup"></a>Inställningar av produktionsparametrar som krävs
**Produktionskontrollparametrar** – Ställ in grundläggande produktionsparametrar för att definiera hur systemet hanterar och bearbetar tillverkningsorder. Definiera hur produktionsorder skapas, uppskattas, planeras och förbrukas. Du kan också ange vilken typ av återrapportering du vill använda och hur kostnadsredovisning ska utföras.

## <a name="required-journal-name-identification"></a>Journalnamns-ID krävs
**Produktionsjournalnamn** – Ange de produktionsjournalnamn som används för att registrera och bokföra transaktioner.

## <a name="setup-if-you-use-operations"></a>Inställningar om du använder operationer
Operationer motsvarar de specifika aktiviteter som genomförs för att producera den färdiga produkten. **Obs!** Du måste veta vilka typer av aktiviteter som behövs för att producera artikeln, och aktiviteternas ordning och prioritet. Du måste också veta vilka resurser som är inblandade, och hur många.

1.  **Åtgärder** – Ställ in åtgärder som motsvarar de uppgifter som måste genomföras för att producera den färdiga artikeln.
2.  **Relationer** – Ställ in operationsrelationer för att skapa detaljerade egenskaper. Definiera åtgärdsrelationer genom att klicka på **Relationer** på sidan **Operationer** .

## <a name="setup-if-you-use-routes"></a>Inställningar om du använder flöden
Om du arbetar med flöden måste operationerna definieras för varje produktionsflöde som du ställer in. Flödet motsvarar den väg som artikeln följer från operation till operation, från början till slutet av produktionsprocessen.

1.  **Kostnadskategorier** – Ställ in kostnadskategorier för att definiera kostnaden per timme för angivna processer och inställningstider.
2.  **Kostnadsgrupper** – Ställ in kostnadsgrupper för att skapa och underhålla olika typer av kostnadsredovisning.
3.  **Flödesgrupper** – Ställ in flödesgrupper för att definiera parametrar som gäller för grupper med flöden. Du måste ställa in flödesgrupper innan du skapar produktionsflöden.
4.  **Flöden** – Ställ in produktionsflöden och definiera standardinställningar för att styra planering, kostnadsredovisning och priser för flödesoperationer, samt att kontrollera förloppsrapporter.
5.  **Flöden** – Ställ in flödesversioner för att möjliggöra artikelvariationer under produktionen.

## <a name="optional-advanced-settings"></a>Valfria avancerade inställningar
1.  **Produktionsgrupper** – Ställ in produktionsgrupper för att skapa relationer mellan tillverkningsordern och redovisningskonton. Redovisningskontona används för att bokföra eller gruppera order för rapportering.
2.  **Produktionspooler** – Skapa produktionspooler för att gruppera produktionsorder så att du kan bearbeta brådskande produktionsorder, eller för att ta bort eller bokföra grupper med order.
3.  **Egenskaper** – Definiera egenskaper för att skapa särskilda attribut som du kan tilldela till resurser för att styra ordningen för produktioner. De här attributen är kopplade till arbetstidsmallen.





