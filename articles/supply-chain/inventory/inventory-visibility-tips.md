---
title: Tips för Lagersynlighet
description: Det här avsnittet innehåller några tips som du bör ta hänsyn till när du ställer in och använder tillägget Lagersynlighet.
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
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952425"
---
# <a name="inventory-visibility-tips"></a>Tips för Lagersynlighet

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller några tips som du bör ta hänsyn till när du ställer in och använder tillägget Lagersynlighet.

- Tillägget Lagersynlighet stöder för närvarande endast Microsoft Dataverse miljöer som har skapats med hjälp av Microsoft Dynamics Lifecycle Services (LCS). Om din Dataverse-miljö har skapats på något annat sätt (till exempel genom att använda administratörscentret för Power Apps), och om den är länkad till din Dynamics 365 Supply Chain Management-miljö, måste du först kontakta produktteamet för Lagersynlighet om du vill åtgärda mappningsproblemet. Du kan kontakta teamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). Teamet hjälper dig att känna till när din miljö är klar för installation av Lagersynlighet.
- Om du har fler än en LCS-miljö kan du skapa olika Azure Active Directory (Azure AD) program för varje miljö. Om du använder samma program-ID och klientorganisations-ID för att installera tillägget Lagersynligt för olika miljöer, uppstår ett tokenproblem för äldre miljöer. Det är bara den sista instansen av tillägget Lagersynligt som installerades som kommer att vara giltig.
- Lagerhantering stöds för närvarande inte för miljöer med molnbaserad värd. Den stöds bara för nivå 2+-miljöer.
- Application Programming Interface (API) stöder för närvarande frågor upp till 100 enskilda artiklar efter `ProductID` värde. Flera `SiteID` och `LocationID` värden kan också anges i varje fråga. Maxgränsen definieras som `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- Bulk-API:t kan returnera maximalt 512 poster för varje begäran.
- Datakällan `fno` är reserverad för Supply Chain Management. Om tillägget Lagerhantering är integrerat i en Supply Chain Management-miljö leveranskedjan rekommenderar vi att du inte tar bort konfigurationer som är relaterade till `fno` i [datakällan](inventory-visibility-configuration.md#data-source-configuration).
- Lagersynlighet kan inte ändra data för `fno` datakällan. Dataflödet är enväg, vilket innebär att alla kvantitetsändringar för `fno` datakällan måste komma från din Supply Chain Management-miljö. Därför kan du inte använda API:t för att skicka begäran om behållningsändring eller reservation för `fno` datakällan.
- Om du lägger till en eller flera nya mått i din Supply Chain Management-miljö, bör du också lägga till dem i Lagerhantering. Alla kvantitetsändringar för nya mått måste dock komma från din Supply Chain Management-miljö.
- För närvarande består [partitionskonfigurationen](inventory-visibility-configuration.md#partition-configuration) partitionskonfigurationen av två grunddimensioner (`SiteId` och `LocationId`) som anger hur data distribueras. Operationer under samma partition kan leverera högre prestanda till lägre kostnad. Lösningen innehåller som standard den här partitionskonfigurationen. Därför *måste du inte definiera själv*. Anpassa inte standardkonfigurationen för partitionen. Om du tar bort eller ändrar den kan det leda till oväntade fel.
- Basdimensioner som definieras i partitionskonfigurationen ska inte definieras i [produktindex hierarkikonfigurationer](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
