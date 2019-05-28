---
title: Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller
description: Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b7018f9d4926321341af94efd13911e2c69f5f5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544012"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller. I den här inspelningen används demonstrationsföretaget USP2.


## <a name="assign-the-cost-object-controller-role"></a>Tilldela rollen kostnadsobjektcontroller
1. Gå till Systemadministration > Användare > Användare.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Användarnamn med värdet "alicia".
3. Klicka på länken på den valda raden i listan.
4. Klicka på Tilldela roller.
5. Hitta och markera önskad post i listan.
6. Klicka på OK.

## <a name="enable-access-list-security"></a>Aktivera listan åtkomstsäkerhet
1. Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.
2. Hitta och markera önskad post i listan.
    * Välj Organisation.  
3. Klicka på Redigera.
4. Välj Ja i fältet Hierarki för åtkomstlista.
5. Klicka p Visa hierarki

## <a name="assign-access-rights-to-user"></a>Tilldela åtkomsträttigheter till användare
1. Klicka på Ny.
2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet Användar-ID.
    * Välj Administratör.  
4. Välj Organization\CEO\CFO\FIM i trädet.
5. Klicka på Ny.
6. Markera vald rad i listan.
7. Ange eller välj ett värde i fältet Användar-ID.
    * Välj Alicia.  
8. Klicka på Spara.

## <a name="enable-access-rights-in-cost-accounting"></a>Aktivera åtkomsträttigheter i Kostnadsredovisning
1. Gå till Kostnadsredovisning > Inställningar > Parametrar.
2. Klicka på fliken Allmänt.
3. Välj Ja i fältet Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar.
4. Klicka på Spara.
5. Stäng sidan.
6. Gå till Kostnadsredovisning > Inställningar > Konfiguration av arbetsytan för kostnadsstyrning.
7. Klicka på Redigera.
8. Välj Ja i fältet Publicerad.
    * Om du väljer Ja kan en användare med någon av följande fyra roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor, ansvarig kostnadsredovisare och kostnadsobjektcontroller. Om du väljer Nej kan bara en användare med någon av följande fyra roller se rapporter: kostnadsredovisningschef, kostnadsrevisor och kostnadsredovisare.    
9. Klicka på Spara.

