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
ms.openlocfilehash: fef4eb7063f4acdbca5fab2ad33ec10e0cb603bd
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2022
ms.locfileid: "9169057"
---
# <a name="troubleshoot-store-commerce-performance-issues"></a>Felsöka prestandaproblem med tillägget Store Commerce

[!include [banner](../includes/banner.md)]

I den här artikeln förklaras hur du felsöker prestandaproblem i programmet Microsoft Dynamics 365 Commerce Store Commerce.

- När du felsöker prestandaproblem för Store Commerce ska du undvika fjärrinloggning. Logga istället in direkt på Store Commerce-enheten.
- Om programmet Store Commerce är långsamt kontrollerar du processor, minne, nätverk och diskanvändning genom att använda Uppgiftshanteraren eller Resursövervakaren. Se till att det inte finns någon betydande förbrukning av enhetens resurser.
- Kontrollera din status för nätverksanslutningar och bekräfta att HTTPS-förfrågningar/-svar inte tar mer än ett par sekunder.
