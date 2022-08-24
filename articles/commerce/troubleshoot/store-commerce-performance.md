---
title: Felsöka prestandaproblem med tillägget Store Commerce
description: I den här artikeln förklaras hur du felsöker prestandaproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2022-05-12
ms.dyn365.ops.version: 10.0.25
ms.search.industry: Retail
ms.openlocfilehash: 0354fbac438ff00ba057993a466bbbbfdd99247d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286314"
---
# <a name="troubleshoot-store-commerce-performance-issues"></a>Felsöka prestandaproblem med tillägget Store Commerce

[!include [banner](../includes/banner.md)]

I den här artikeln förklaras hur du felsöker prestandaproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.

- När du felsöker prestandaproblem för Store Commerce ska du undvika fjärrinloggning. Logga istället in direkt på Store Commerce-enheten.
- Om programmet Store Commerce är långsamt kontrollerar du processor, minne, nätverk och diskanvändning genom att använda Uppgiftshanteraren eller Resursövervakaren. Se till att det inte finns någon betydande förbrukning av enhetens resurser.
- Kontrollera din status för nätverksanslutningar och bekräfta att HTTPS-förfrågningar/-svar inte tar mer än ett par sekunder.
