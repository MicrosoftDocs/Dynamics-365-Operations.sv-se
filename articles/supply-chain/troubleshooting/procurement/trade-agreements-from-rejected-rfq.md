---
title: Handelsavtal kan skapas från avvisade anbudsförfrågningar
description: Handelsavtal kan skapas från avvisade anbudsförfrågan. Systemet hindrar inte handelsavtalsjournaler från att skapas om raden i anbudsförfrågan inte har accepterats
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 92731f0f56e6eba05043403c121939accbe26c05
ms.sourcegitcommit: 220101d2511a3164572226294ef090a43a1e6cdd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2022
ms.locfileid: "8789252"
---
# <a name="trade-agreements-can-be-created-from-rejected-rfqs"></a>Handelsavtal kan skapas från avvisade anbudsförfrågningar

## <a name="symptoms"></a>Symtom

Handelsavtal kan skapas från avvisade anbudsförfrågan. Därför hindrar systemet inte handelsavtalsjournaler från att skapas om raden i anbudsförfrågan inte har accepterats.

## <a name="resolution"></a>Lösning

Detta är det förväntat beteende. Du kan skapa handelsavtal för alla svar på en anbudsförfrågan, oavsett om de har accepterats eller avvisats. För mer information, se [översikt över begära offert (anbudsförfrågan)](/dynamics365/supply-chain/procurement/request-quotations).
