---
title: Skapa, beräkna och bokföra utdrag för en butik
description: Denna artikel beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 740857e6a902e21588855eef5e36cac68e560898
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873288"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Skapa, beräkna och bokföra utdrag för en butik

[!include [banner](../includes/banner.md)]

Denna artikel beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik. Det finns också batchjobb som kan konfigureras för samma uppgifter. Stegen för att konfigurera och att köra batchjobb finns i andra artiklar. För att slutföra den här proceduren måste du ha transaktioner som slutfördes i POS och sedan samlats in till Dynamics 365 Commerce. I den här insamlingen används demonstrationsföretaget USRT.

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
    - Ange ett räknat belopp på varje rad om det behöver anges eller uppdateras. Det beräknade fältet fylls i med belopp från kassaavstämningar som gjorts i POS.  
9. Välj **Bokför utdrag** från åtgärdsfönstret.
10. Välj **Nära**.
11. Stäng fönstret.
12. På startsidan väljer du **butiksekonomi**.
13. Välj fliken **Bokförda utdrag**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]