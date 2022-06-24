---
title: Felsöka prestandaproblem med tillägget Store Commerce
description: I den här artikeln förklaras hur du felsöker prestandaproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2022-05-12
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b690e35b2df736f3e277260e6f752ef5240b0938
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870502"
---
# <a name="troubleshoot-store-commerce-performance-issues"></a>Felsöka prestandaproblem med tillägget Store Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln förklaras hur du felsöker prestandaproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.

- När du felsöker prestandaproblem för Store Commerce ska du undvika fjärrinloggning. Logga istället in direkt på Store Commerce-enheten.
- Om programmet Store Commerce är långsamt kontrollerar du processor, minne, nätverk och diskanvändning genom att använda Uppgiftshanteraren eller Resursövervakaren. Se till att det inte finns någon betydande förbrukning av enhetens resurser.
- Kontrollera din status för nätverksanslutningar och bekräfta att HTTPS-förfrågningar/-svar inte tar mer än ett par sekunder.
