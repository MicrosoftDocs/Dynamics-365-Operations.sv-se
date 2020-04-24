---
title: Plocka den äldsta batchen på en mobil enhet
description: Det här avsnittet beskriver hur du ställer in och använder alternativen att plocka den äldsta batchen från en mobil enhet.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f235c34d6369c6f0584a7bac1c1be75f3d84c9c0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215641"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Plocka den äldsta batchen på en mobil enhet

[!include [banner](../includes/banner.md)]

Du kan komma åt konfigurationen **Plocka äldsta batchen** via menyn för en mobil enhet och du kan tvinga eller varna lagerarbetare att plocka den äldsta batchen på deras nuvarande plats.  

## <a name="where-it-applies"></a>Tillämpning
Plocka den äldsta batchen konfigureras på en mobil enhets menyalternativ och påverkar plockningen av batchen under artiklar.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Hur du ställer in konfigurationen för Plocka äldsta batchen 
För artiklar som är inställda på att använda befintligt arbete kan **Plocka äldsta batchen** ställas in på **Ingen**, **Varna** eller **Tvinga** från menyn i en mobil enhet.

**Ingen**: arbetare får inga meddelanden och tillåts plocka valfri batch på sin plats.

**Varning** och **Tvinga**: en lista över batchen/batcherna med det äldsta utgångsdatumet visas ovanför batchkontrollen när arbetaren väljer en batch. Om platsen är registreringsskyltskontrollerad visas en lista över registreringsskyltar med den äldsta batchen ovanför registreringsskyltskontrollen. 
-   **Varning**: om en arbetare väljer en registreringsskylt eller en batch som inte finns i listan kommer att kontrollen att nollas och en varning indikerar att det finns en äldre batch att välja. För att kunna fortsätta arbetet kan arbetaren välja samma registreringsskylt eller batch igen.  
-   **Tvinga**: arbetare fortsätter att få meddelanden om att det inte finns en äldre batch att plocka.
