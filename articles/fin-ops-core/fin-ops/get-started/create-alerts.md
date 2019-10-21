---
title: Skapa notifieringsregler
description: Det här avsnittet innehåller information om notifieringar och förklarar hur du skapar en notifieringsregel så att du meddelas om händelser, t.ex. ett datum som anländer eller en viss händelse som inträffar.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: c37ddc52ef576a15dd35cc155e99821c74631a46
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180724"
---
# <a name="create-alert-rules"></a>Skapa notifieringsregler

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Komma igång

Innan du ställer in en notifieringsregel måste du bestämma när eller i vilka situationer du vill få notifieringar. När du vet vilka händelser du vill meddelas om, går du till sidan där de data som orsakar händelsen visas. Händelsen kan vara ett datum eller en viss händelse som inträffar. Därför måste du hitta sidan där datumet anges eller där fältet ändras eller den nya posten som har skapats visas. När du har den här informationen kan du skapa notifieringsregeln.

När du skapar en notifieringsregel måste du definiera de kriterier som måste uppfyllas innan en notifiering utlöses. Du kan se kriterier som en matchning av förekomsten av en händelse och uppfyllandet av bestämda villkor. När en händelse inträffar börjar systemet kontrollera enligt villkoren som är angivna.

## <a name="events"></a>Händelser

Den händelse som utlöser en notifieringsregel kan vara ett datum som anländer eller en viss händelse som inträffar. Utlösare för händelser definieras på snabbfliken **Notifiera när** i dialogrutan **Skapa notifieringsregel**. Händelser som är fördefinierade för ett visst fält beror på vilken utlösare som har valts.

Om du t.ex. ställer in en notifieringsregel för fältet **Startdatum** är händelser för förfallodatum lämpliga. Därför är händelsetypen **förfaller i** tillgänglig för det fältet. Men för ett fält som t.ex. **Kostnadsställe**, är en händelse för förfallodatum inte lämplig. Därför är händelsetypen **förfaller i** inte tillgänglig. I stället är händelsetypen **har ändrats** tillgänglig.

## <a name="event-types"></a>Händelsetyper

Tre typer av händelser kan inträffa:

- **Händelser av typerna skapa och radera** – de här händelserna utlöser en notifiering när en post skapas eller tas bort.
- **Händelser av uppdateringstyp** – de här händelserna utlöser en notifiering när data i ett visst fält ändras.
- **Händelser för förfallodatum** – händelserna utlöser en notifiering när ett datum anländer.
    
Ändringar som görs kan startas av en användare. Till exempel ändrar en användare leveransdatum för en inköpsorder. Alternativt kan ändringar göras som en del av en process. Till exempel fältet **Status** på en sida ändras för att reflektera livscykeln för olika processer i systemet.

## <a name="conditions"></a>Villkor

På snabbfliken **Notifiera för** i dialogrutan **Skapa notifieringsregel** kan du välja villkoren för att styra när du får en varning om händelser.

Du kan exempelvis ange att systemet ska varna när status för inköpsorder ändras, men bara om status matchar en viss uppsättning villkor. Särskilt om du vill notifieras när status för en inköpsorder anges till **inlevererad**. Denna ändring av status är den händelse som utlöser notifieringen.

Sedan måste du bestämma vilka inköpsorder som du vill få notifieringar om. Du kan t.ex. välja något av följande alternativ: Dessa alternativ definierar villkoren för notifieringsregeln.

- **Aktuell markerad post** – Du får en notifiering när status för en viss inköpsorder ändras till **Inlevererad**.
- **Alla poster** – Du får en notifiering när status för en inköpsorder ändras för en artikel på den aktiva sidvyn. Du kan använda de avancerade filterfunktionen som finns på sidan för att skapa regler för en specifik uppsättning poster. Du kan till exempel skapa en notifiering som utlöses för alla inköpsorder för kunder i en viss kundgrupp.
    
## <a name="expiry-of-rule"></a>Regelutgång

På snabbfliken **Notifiera tills** i dialogrutan **Skapa notifieringsregel** kan du ange hur länge notifieringsregeln ska vara aktiv.

## <a name="alert-contents"></a>Notifieringsinnehåll

På snabbfliken **Notifiera med** i dialogrutan **Skapa notifieringsregel** anger du ämnestexten och meddelandetexten som varningsmeddelandet ska använda.

## <a name="user-id"></a>Användar-ID

På snabbfliken **Notifiera mig** i dialogrutan **Skapa notifieringsregel** kan du ange vilken användare som ska få notifieringar. Ditt användar-ID är markerad som standard. Det här alternativet är begränsat till administratörer i organisationen.

## <a name="create-an-alert-rule"></a>Skapa en notifieringsregel.

1. Öppna sidan som innehåller de data som ska övervakas.
2. I åtgärdsfönstret, på fliken **Alternativ** i gruppen **Andel** markerar du **Skapa notifieringsregel**.
3. I dialogrtuan **Skapa notifieringsregel** i fältet **Fält** markerar du fältet som du vill övervaka.
4. I fältet **Händelse** väljer du typ av fält.
5. På snabbfliken **Notifiera för** väljer du ett alternativ.
6. Om du vill att notifieringsregeln ska inaktiveras på ett visst datum väljer du ett slutdatum på snabbfliken **Notifiera tills**.
7. På snabbfliken **Notifiera med** på fältet **Ämne**, acceptera standardämnet för e-postmeddelandet eller ange ett nytt ämne. Texten som används som ämne för e-postmeddelandet som du får när en notifiering initieras.
8. Skriv ett valfritt meddelande i fältet **Meddelande**. Den text används som meddelandet som du får när en notifiering utlöses.
9. Välj **OK** om du vill spara inställningarna och skapa notifieringsregeln.
