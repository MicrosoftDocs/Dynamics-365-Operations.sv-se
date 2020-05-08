---
title: Skapa, beräkna och bokföra utdrag för en butik
description: Det här avsnittet beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141024"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Skapa, beräkna och bokföra utdrag för en butik

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik. Det finns också batchjobb som kan konfigureras för samma uppgifter. Stegen för att konfigurera och att köra batchjobb finns i andra avsnitt. För att slutföra den här proceduren måste du ha transaktioner som slutfördes i kassan och sedan samlats in till Dynamics 365 Commerce. I den här insamlingen används demonstrationsföretaget USRT.

1. Välj **butiksekonomi** från startsidan.
2. Välj **Nytt utdrag**.
3. I fältet **Butiksnummer** väljer du ett alternativ iden nedrullningsbara listan.
4. Välj **OK**.
5. Gruppen **Inställningar** har inställningar för att kontrollera vilka transaktioner som ingår i utdraget och hur de grupperas till utdragsrader. Du kan öppna gruppen **Inställningar** och ändra inställningarna, eller använda standardinställningarna.  
    - Fältet **Utdragmetod** definierar hur utdragsraderna grupperas.  
    - Välj en medarbetare eller ett register i fältet **Personal/register** om du vill beräkna ett utdrag för den specifika medarbetaren eller registret.  
6. Markera ett alternativ i fältet **Stängningsmetod**.
7. Välj **beräkna utdrag** från åtgärdsfönstret.
8. Välj **Ja**.
    - När du har beräknat utdraget måste det finnas rader som skapas med totalbelopp för varje betalningsmetod och utdragmetod som användes.  
    - Ange ett räknat belopp på varje rad om det behöver anges eller uppdateras. Det beräknade fältet fylls i med belopp från kassaavstämningar som gjorts i kassan.  
9. Välj **Bokför utdrag** från åtgärdsfönstret.
10. Välj **Nära**.
11. Stäng fönstret.
12. På startsidan väljer du **butiksekonomi**.
13. Välj fliken **Bokförda utdrag**.
