---
title: Inventory Visibility-tips
description: Denna artikel innehåller några tips som du bör ta hänsyn till när du konfigurerar och använder tillägget Lagersynlighet.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306098"
---
# <a name="inventory-visibility-tips"></a>Tips för Lagersynlighet

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller några tips som du bör ta hänsyn till när du konfigurerar och använder tillägget Lagersynlighet.

- Tillägget Lagersynlighet stöder för närvarande endast Microsoft Dataverse miljöer som har skapats med hjälp av Microsoft Dynamics Lifecycle Services (LCS). Om din Dataverse-miljö har skapats på något annat sätt (till exempel genom att använda administratörscentret för Power Apps), och om den är länkad till din Dynamics 365 Supply Chain Management-miljö, måste du först kontakta produktteamet för Lagersynlighet om du vill åtgärda mappningsproblemet. Du kan kontakta teamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). Teamet hjälper dig att känna till när din miljö är klar för installation av Lagersynlighet.
- Om du har fler än en LCS-miljö kan du skapa olika Azure Active Directory (Azure AD) program för varje miljö. Om du använder samma program-ID och klientorganisations-ID för att installera tillägget Lagersynligt för olika miljöer, uppstår ett tokenproblem för äldre miljöer. Det är bara den sista instansen av tillägget Lagersynligt som installerades som kommer att vara giltig.
- Lagerhantering stöds för närvarande inte för miljöer med molnbaserad värd. Den stöds bara för nivå 2+-miljöer.
- Application Programming Interface (API) stöder för närvarande frågor upp till 100 enskilda artiklar efter `ProductID` värde. Flera `SiteID` och `LocationID` värden kan också anges i varje fråga. Maxgränsen definieras som `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- Bulk-API:t kan returnera maximalt 512 poster för varje begäran.
- Datakällan `fno` är reserverad för Supply Chain Management. Om tillägget Lagerhantering är integrerat i en Supply Chain Management-miljö leveranskedjan rekommenderar vi att du inte tar bort konfigurationer som är relaterade till `fno` i [datakällan](inventory-visibility-configuration.md#data-source-configuration).
- Lagersynlighet kan inte ändra data för `fno` datakällan. Dataflödet är enväg, vilket innebär att alla kvantitetsändringar för `fno` datakällan måste komma från din Supply Chain Management-miljö. Därför kan du inte använda API:t för att skicka begäran om behållningsändring eller reservation för `fno` datakällan.
- Om du lägger till en eller flera nya mått i din Supply Chain Management-miljö, bör du också lägga till dem i Lagerhantering. Alla kvantitetsändringar för nya mått måste dock komma från din Supply Chain Management-miljö.
- För närvarande består [partitionskonfigurationen](inventory-visibility-configuration.md#partition-configuration) partitionskonfigurationen av två grunddimensioner (`SiteId` och `LocationId`) som anger hur data distribueras. Åtgärder under samma partition kan leverera högre prestanda till lägre kostnad. Lösningen innehåller som standard den här partitionskonfigurationen. Därför *måste du inte definiera själv*. Anpassa inte standardkonfigurationen för partitionen. Om du tar bort eller ändrar den kan det leda till oväntade fel.
- Basdimensioner som definieras i partitionskonfigurationen ska inte definieras i [produktindex hierarkikonfigurationer](inventory-visibility-configuration.md#index-configuration).
- Din [hierarkikonfiguration för produktindex](inventory-visibility-configuration.md#index-configuration) måste omfatta minst en indexhierarki (som exempelvis innehåller basdimensionen `Empty`), annars misslyckas frågorna med felet "Ingen indexhierarki har ställts in."
- Datakälla `@iv` är en fördefinierad datakälla och de fysiska mått som definierats i `@iv` med prefixet `@` är fördefinierade mått. Måtten är en fördefinierad konfiguration för allokeringsfunktionen. Det gör att du inte ändrar eller tar bort dem eller du kanske stöter på oväntade fel när du använder allokeringsfunktionen.
- Du kan lägga till nya fysiska mått till det fördefinierade beräknade `@iv.@available_to_allocate` måttet, men du får inte ändra dess namn.
- Om du har återställt din Supply Chain Management-databas kan den återställda databasen innehålla data som inte längre är konsekventa med data som tidigare synkroniserats med Lagersynlighet till Dataverse. Den här data inkonsekvensen kan orsaka systemfel och andra problem. Därför är det viktigt att du alltid rensar alla lagersynlighetsdata från Dataverse innan du återställer en Supply Chain Management-databas. För mer information, se [Rensa lagersynlighetsdata från Dataverse innan du återställer Supply Chain Management-databasen](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
