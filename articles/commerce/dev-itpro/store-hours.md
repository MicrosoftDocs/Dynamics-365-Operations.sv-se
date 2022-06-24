---
title: Skapa och uppdatera öppettider
description: I denna artikel beskrivs hur du skapar och uppdaterar öppettider i Commerce Headquarters.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 99d2f06be959e00656901c6ca8fc79fac32a3a6f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884375"
---
# <a name="create-and-update-store-hours"></a>Skapa och uppdatera öppettider

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Översikt

Från en enda plats kan återförsäljare skapa, underhålla och hantera öppettiderna för olika butiker över geografiska regioner. Öppettiderna kan sedan visas på kassaterminalerna. På så sätt kan kassörerna dela med sig av öppettiderna till kunder och bättre hjälpa dem som är intresserade av lager i andra butiker. Öppettiderna kan också skrivas ut på kvitton om kunder vill gå tillbaka till butiken senare.

Det går att konfigurera flera öppettider för olika kanaler. Dessa kanaler är bland annat fysiska butiker, kundtjänster, mobila enheter och näthandelsplatser.

Om en kund har en upphämtningsorder för en annan butik, kan kassören välja datum när upphämtningen blir tillgänglig i den butiken. Butikssökningen ger en referens till datumen och öppettiderna. Kassören kan välja ett datum och en plats, och kan också skriva ut ett upphämtningskvitto som inkluderar öppettiderna.

Den här funktionen är tillgänglig i Microsoft Dynamics 365 Retail version 8.1.2 och senare versioner.

## <a name="configure-store-hours"></a>Konfigurera butikens öppettider

Om du vill konfigurera butikens öppettider, följ dessa steg.

1. Gå till **Butik och handel** \> **Kanalinställningar** \> **Butikens öppettider**.
2. Välj **Ny** om du vill skapa en ny mall för butikens öppettider. Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret.
3. I dialogrutan **Lägg till intervall** definierar du datumintervallet, öppettiderna och eventuella helgdagar som krävs.

    - Om öppettiderna inte ändras väljer du **Slutar aldrig** i fältet **Slutdatum**.
    - Om öppettiderna gäller en viss månad, vecka eller dag ställer du in lämpliga datum i fälten **Startdatum** och **Slutdatum**.

    > [!NOTE]
    > Du kan skapa flera mallar med överlappande start- och slutdatum. Därför kan du t.ex. definiera öppettider för butiker i olika tidszoner.

    ![Dialogrutan Lägg till intervall.](../dev-itpro/media/Storehours1.png "Dialogrutan Lägg till intervall")

4. Associera mallen för öppettider med butikerna där den ska användas. I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.

    - Det går bara att associera en öppettidsmall till varje butik.
    - Välj butiker, regioner eller organisationer med pilknapparna. Kalendern kommer att vara tillgänglig för butikerna eller butiksgrupperna och den visas i kassan för referens.

    ![Dialogrutan Välj organisationsnoder.](../dev-itpro/media/Storehours2.png "Dialogrutan Välj organisationsnoder")

5. På sidan **Distributionsschema**, kör du jobben **1070** och **1090** för att göra öppettiderna tillgängliga för kassan.

## <a name="add-store-hours-to-printed-receipts"></a>Lägga till öppettider på utskrivna kvitton

Följ dessa steg för att lägga till öppettider på de utskrivna kassakvittona.

1. Öppna kvittodesignern.
2. Välj **Sidfot** i det nedre vänstra hörnet.
3. Dra elementet **Butikens öppettider** från det vänstra fönstret till sidfoten längst ned i kvittomallen.
4. Du kan redigera standardetiketten i elementet **Butikens öppettider** efter behov.
5. Spara kvittot och stäng kvittodesignern.
6. På sidan **Distributionsschema** kör du jobben **1070** och **1090**.
7. Logga in i kassan.
8. Slutför en försäljning och välj att skriva ut ett kvitto.

I kassakvitton ingår nu butikens öppettider. Om helgdagar inkluderades i mallen visas de på kvittot.

![Kvittoexempel.](../dev-itpro/media/Storehours3.png "Kvittoexempel")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]