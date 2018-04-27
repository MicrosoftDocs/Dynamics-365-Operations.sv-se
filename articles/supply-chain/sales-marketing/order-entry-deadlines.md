---
title: "Deadlines för orderregistrering"
description: "Den här artikeln innehåller information om deadlines för orderregistrering. En deadline för orderregistrering är en sluttid som bestämmer om en kundorder behandlas (och genomförs) som om det togs emot den aktuella dagen eller nästa dag."
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 31308e64d4871a4d09540df16fdcd02cc83bd0be
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="order-entry-deadlines"></a>Deadlines för orderregistrering

[!INCLUDE [banner](../includes/banner.md)]

Den här artikeln innehåller information om deadlines för orderregistrering. En deadline för orderregistrering är en sluttid som bestämmer om en kundorder behandlas (och genomförs) som om det togs emot den aktuella dagen eller nästa dag.

I många företag kommer bara försäljningsorder som inkommer före en viss tid att behandlas som om de kom in samma dag. Alla order som har inlevererats efter den tiden ska behandlas som om de inlevereras nästa vardag. Den här sluttiden för order kallas deadline för orderregistrering.  

Deadlines för orderregistrering används som inmatning av orderlöfte. Därför hjälper de dig att hantera kundens förväntningar om orderleveranser. Kunder kan till exempel se om de gör någon beställning med dig innan en viss tidpunkt, att du kommer att leverera varor på samma dag. Men om de missar denna deadline kan de förvänta leveransen först på nästa arbetsdag. Du kan ange deadlines för orderregistrering utifrån dina lagerställefunktioner och transportföretagets tidsscheman.  

På sidan **Deadlines för orderregistrering** anger du tider för orderregistrering för alla veckodagar. Om alla order inlevererad efter den angivna tiden ska de behandlas som om de inlevereras nästa dag. Som standard är tiden 23:59, det vill säga en minut före midnatt den aktuella dagen. Du kan ändra standardtiderna så att de stämmer med faktisk deadline för ut- eller inleverans.  

Du kan definiera deadline för order för en specifik kundgrupp. Du kan till exempel ange att en specifik kundgrupp har deadlines för orderregistrering som infaller senare än andra kunder. I det här fallet definierar du först grupper för deadlines för orderregistrering på sidan **Deadlinegrupper för orderregistrering**. Du kan sedan tilldela grupper till kunder på sidan **Kunder**.  

Om verksamheten inom ditt företag är utspridd på flera siter kan du skapa en deadline för order per site. Om siterna finns i olika tidszoner skapar du en deadline för orderregistrering för sitens tidszon. När du arbetar med säljorder och säljofferter konverteras deadline för order till din tidszon på sidan **Tillgängliga speditions- och inleveransdatum**.  

På sidan **Aktivera kombinationer för deadline för orderregistrering** definierar du de kombinationer av siter och deadlinegrupper för orderregistrering som tillåts.

## <a name="example-order-entry-deadline"></a>Exempel: Deadline för orderregistrering
Deadline för orderregistrering på tisdagar har ställts in på 16:00. På en särskild tisdag klockan 17:00 försöker du att ange det aktuella datumet som transportdatum. (Observera att det inte finns någon produktionstid för det här exemplet.) Om kryssrutan **Leveransdatumkontroll** är markerad får du en varning med information om att datumet inte är giltigt. Denna varning visas på sidan **Tillgängligt transport- och inleveransdatum** där du kan sedan välja andra datum.

## <a name="example-different-order-entry-deadlines-per-site"></a>Exempel: Olika deadline för orderregistreringar per site
Ditt företag bedriver sin verksamhet på två siter. Siterna finns i andra tidszoner, som visas i följande tabell.

| Webbplats A                      | Plats B                       |
|-----------------------------|-----------------------------|
| Kalifornien                  | Florida                     |
| Pacific, normaltid | Eastern, normaltid |

Plats A och B har definierat följande deadlines för orderregistrering.

| Dagen i veckan             | A: Deadlines för orderregistrering (PST) | B: Deadlines för order (EST) |
|-----------------------------|--------------------------------|--------------------------------|
| Måndag                      | 13:00:00                          | 14:00:00                          |
| Tisdag                     | 13:00:00                          | 14:00:00                          |
| Onsdag                   | 13:00:00                          | 14:00:00                          |
| Torsdag                    | 13:00:00                          | 14:00:00                          |
| Fredag                      | 13:00:00                          | 14:00:00                          |

Du behandlar order och du befinner dig i Utah där tidzonen är MST (Mountain Standard Time). Det innebär att så länge du skickar order till site A före kl. 14:00 (MST) och till site B före kl. 12:00 (MST), så klarar du orderdeadline för båda siterna.  

Följande tabeller visar deadline för order för site A och B konverterat till MST-tid.

| Plats A: PST         | Plats A: MST        | Plats B: EST           | Plats B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 14:00:00                 | 12:00:00              |

**Obs!** Om justering av sommartid gäller, kommer deadline för order att justeras i enlighet därmed.

## <a name="example-same-order-entry-deadline-per-site"></a>Exempel: Samma deadline för order per site
Ditt företag bedriver sin verksamhet på två siter. Siterna finns i andra tidszoner, som visas i följande tabell.

| Webbplats A                      | Plats B                       |
|-----------------------------|-----------------------------|
| Kalifornien                  | Florida                     |
| Pacific, normaltid | Eastern, normaltid |

Plats A och B har definierat följande deadlines för orderregistrering.

| Dagen i veckan | PST och EST |
|-----------------|-------------|
| Måndag          | 13:00:00       |
| Tisdag         | 13:00:00       |
| Onsdag       | 13:00:00       |
| Torsdag        | 13:00:00       |
| Fredag          | 13:00:00       |

Du behandlar order och du befinner dig i Utah där tidzonen är MST. Det innebär att så länge du skickar order till site A före kl. 14:00 (MST) och till site B före kl. 11:00 (MST), så klarar du orderdeadline för båda siterna. 

Följande tabeller visar deadline för order för site A och B konverterat till MST-tid.

| Plats A: PST         | Plats A: MST        | Plats B: EST           | Plats B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 13:00:00                 | 11:00:00              |

**Obs!** Om justering av sommartid gäller, kommer deadline för order att justeras i enlighet därmed.

<a name="see-also"></a>Se även
--------

[Leveransplaner](delivery-schedules.md)




