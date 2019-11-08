---
title: Notifieringar – översikt
description: Det här avsnittet innehåller allmän information om notifieringar. Du kan använda notifieringar för att hålla dig informerad om händelser som du vill spåra under arbetsdagen.
author: tjvass
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: a42e836c0b72798de3375c169e45b121debd55ec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191280"
---
# <a name="alerts-overview"></a>Översikt över notifieringar

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>Om notifieringar
Notifieringar utgör ett meddelandesystem för kritiska händelser i systemet. Du kan använda notifieringar för att hålla dig informerad om händelser som du vill spåra under arbetsdagen. Du kan enkelt skapa din egen uppsättning regler så att du meddelas om försenade leveranser, raderade order, ändrade priser eller andra händelser som du behöver reagera på.

I resursplanering i företag (ERP) finns flera vanliga scenarier där notifieringsfunktionen kan användas. Nedan följer några exempel.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>Scenario 1: Skapa en notifieringsregel för nya försäljningsorder

1. Öppna sidan **Alla försäljningsorder**.
2. I åtgärdsfönstret, på fliken **Alternativ** i gruppen **Andel** markerar du **Skapa ett anpassat meddelande**.
3. I dialogrutan **Skapa notifieringsregel**, på snabbfliken **Notifiera när** i fältet **Händelse** väljer du **Post har skapats**.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>Scenario 2: Skapa en notifieringsregel för att senarelägga ett leveransdatum

1. Öppna sidan **Alla försäljningsorder**.
2. Välj ett inköpsordernummer för att komma åt inköpsorderdetaljerna.
3. Expandera snabbfliken **Inköpsorderrubrik**.
4. I åtgärdsfönstret, på fliken **Alternativ** i gruppen **Andel** markerar du **Skapa ett anpassat meddelande**.
5. I dialogrutan **Skapa notifieringsregel**, på snabbfliken **Notifiera när** i fältet **Fält** väljer du **Leveransdatum**.
6. På fältet **Händelse** väljer du **har uppskjutits**.
    
När du har stängt dialogrutan **Skapa notifieringsregel** visas din regel på sidan **Hantera notifieringsregler**. Du kan använda sidan **Hantera notifieringsregler** för att uppdatera befintliga notifieringsregler. Du kan till exempel ändra händelseutlösare, uppdatera händelsemeddelanden och uppdatera utgångsdatum. För att öppna sidan **Hantera notifieringsregler** kan du använda knappen **Avisera** på fliken **Alternativ** i åtgärdsfönstret.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>Vad händer när en notifieringsregel skapas?

När du skapar notifieringsregler kan du tilldela en fördefinierad händelse till ett visst fält. Till exempel anländer det datum som angetts i fältet eller innehållet i fältet ändras. Alternativt kan du koppla en händelse till posterna på en viss sida. Exempelvis skapas en post eller en post tas bort.

När den valda händelsen inträffar för fältet eller för en post på sidan får du en notifiering. Du skapar exempelvis en regel där du kopplar fältet **leveransdatum** till en viss inköpsorderrad med händelsen **förföll till betalning för så här länge sedan**. Du ställer in tidsramen till fem dagar. I det här fallet skickas en notifiering fem dagar efter leveransdatumet av denna inköpsorderrad.

Du kan dessutom begränsa notifieringsreglerna genom att ange villkor. Exempelvis kan du notifieras om nya inköpsorder som skapas för särskilda leverantörskonton.

## <a name="preparing-for-an-alert"></a>Förbereda för en notifiering

Innan du ställer in en notifieringsregel måste du bestämma när eller i vilka situationer du vill få notifieringar. När du vet vilka händelser du vill meddelas om, går du till sidan där de data som orsakar händelsen visas. Händelsen kan vara ett datum eller en viss händelse som inträffar. Därför måste du hitta sidan där datumet anges eller där fältet ändras eller den nya posten som har skapats visas. När du har den här informationen kan du skapa notifieringsregeln.

## <a name="components-of-an-alert-rule"></a>Komponenter för en notifieringsregel

Komponenter för en notifieringsregel

- **Händelse** – Den händelse som utlöser en notifieringsregel kan vara ett datum som anländer eller en viss händelse som inträffar. Du definierar händelser på snabbfliken **Skicka e-postaviseringar vid ändringar av jobbstatus** i dialogrutan **Skapa notifieringsregel**.
- **Villkor** – på snabbfliken **Notifiera för** i dialogrutan **Skapa notifieringsregel** kan du välja omfattningen av villkoret för att styra när du får en varning om händelser. Du kan antingen tillämpa regeln till den aktuella posten eller till alla poster som visas på sidan. Om regeln gäller för juridiska personer, kan du ange alternativet **I hela organisationen** till **Ja**.
- **Regelutgång** – på snabbfliken **Notifiera tills** i dialogrutan **Skapa notifieringsregel** kan du ange hur länge notifieringsregeln ska vara aktiv.
- **Innehåll** – på snabbfliken **Notifiera med** i dialogrutan **Skapa notifieringsregel** anger du ämnestexten och meddelandetexten som varningsmeddelandet ska använda.
- **Användare** – på snabbfliken **Vem ska notifieras** i dialogrutan **Skapa notifieringsregel** kan du ange vilken användare som ska få notifieringar. Ditt användar-ID är markerad som standard.

    > [!NOTE]
    > Det här alternativet är begränsat till administratörer i organisationen.

## <a name="email-notifications-from-alerts"></a>E-postmeddelanden från aviseringar

E-postmeddelanden från aviseringar har inte aktiverats ännu. Detta aktiveras i en kommande uppdatering.

## <a name="videos"></a>Videoklipp

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>Använda notifieringar för att övervaka filtrerade data

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3DWZ3]

Videon [hur du använder notifieringar för att övervaka filtrerad data](https://youtu.be/ZYKMcv6kl9s) (visas ovan) ingår i [Finance and Operations spellista](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som finns tillgänglig på YouTube.

### <a name="alert-rule-options"></a>Alternativ för notifieringsregel

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3E4PV]

Videon [Alternativ för notifieringsregel](https://youtu.be/cpzimwOjicM) (visas ovan) inkluderas i [Finance and Operations spellista](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.

