---
title: Skapa notifieringsregler
description: Det här avsnittet innehåller information om notifieringar och förklarar hur du skapar en notifieringsregel så att du meddelas om händelser, t.ex. ett datum som anländer eller en viss händelse som inträffar.
author: tjvass
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 4fe97ca8e1eecdc064ad4d21d5acdeade9f33d9c
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694505"
---
# <a name="create-alert-rules"></a>Skapa notifieringsregler

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Komma igång

Innan du ställer in en notifieringsregel måste du bestämma när eller i vilka situationer du vill få notifieringar. När du vet vilka händelser du vill meddelas om, går du till sidan där de data som orsakar händelsen visas. Händelsen kan vara ett datum eller en viss händelse som inträffar. Därför måste du hitta sidan där datumet anges eller där fältet ändras eller den nya posten som har skapats visas. När du har den här informationen kan du skapa notifieringsregeln.

När du skapar en notifieringsregel måste du definiera de kriterier som måste uppfyllas innan en notifiering utlöses. Kriterier är i grunden en matchning av förekomsten av en händelse och uppfyllandet av bestämda villkor. När en händelse inträffar börjar systemet kontrollera enligt villkoren som är angivna.

## <a name="ensure-the-alert-batch-jobs-are-running"></a>Se till att notifieringar körs i batch-jobbet

Batchjobben för notifieringar om dataändring och förfallodatum måste köras för att de notifieringsvillkor som ska behandlas och meddelanden ska skickas. Om du vill köra batchjobb går du till **Systemadministration** > **Periodiska uppgifter** > **Aviseringar** och lägga till nya batch-jobb för **Ändringsbaserade notifieringar** och/eller **Notifieringar om förfallodatum**. Välj ett långt och ofta kört batchjobb **återkommande** och ange **inget slutdatum** med **Upprepningsmönster** på **Minuter** och **Antal** på **1**.

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

På snabbfliken **Notifiera mig** i dialogrutan **Skapa notifieringsregel** kan du ange vilken användare som ska få notifieringar. Ditt användar-ID är markerad som standard. Möjligheten att ändra den användare som får notifieringen är begränsad till organisationsadministratörer.

## <a name="alerts-as-business-events"></a>Notifierar som affärshändelser

Notifieringar kan skickas externt med hjälp av ramverket för affärshändelse. När du skapar en notifiering ställer du in **Organisationsomfattande** till **Nej** och anger **Skicka externt** till **Ja**. När notifieringen utlöser affärshändelsen kan du utlösa ett flöde som skapats i Power Automate med hjälp av **När en affärshändelse händer** utlöses på Finance and Operations kopplingen eller uttryckligen skicka händelsen till en slutpunkt för affärs händelser via **Katalogen affärshändelser**.

## <a name="create-an-alert-rule"></a>Skapa en notifieringsregel.

0. Se till att notifieringar körs i batch-jobbet (se ovan).
1. Öppna sidan som innehåller de data som ska övervakas.
2. I åtgärdsfönstret, på fliken **Alternativ** i gruppen **Andel** markerar du **Skapa notifieringsregel**.
3. I dialogrtuan **Skapa notifieringsregel** i fältet **Fält** markerar du fältet som du vill övervaka.
4. I fältet **Händelse** väljer du typ av fält.
5. På snabbfliken **Notifiera för** väljer du önskat alternativ. Om du vill skicka notifieringen som en affärshändelse kontrollerar du **Organisationsomfattande** är inställt på **Nej**.
6. Om du vill att notifieringsregeln ska inaktiveras på ett visst datum väljer du ett slutdatum på snabbfliken **Notifiera tills**.
7. På snabbfliken **Notifiera med** på fältet **Ämne**, acceptera standardämnet för e-postmeddelandet eller ange ett nytt ämne. Texten som används som ämne för e-postmeddelandet som du får när en notifiering initieras. Om du vill skicka notifieringen som en affärshändelse ställer du in **skicka externt** till **Ja**.
8. Skriv ett valfritt meddelande i fältet **Meddelande**. Den text används som meddelandet som du får när en notifiering utlöses.
9. Välj **OK** om du vill spara inställningarna och skapa notifieringsregeln.

## <a name="limitations-and-workarounds"></a>Begränsningar och lösningar

### <a name="workaround-for-creating-alerts-for-the-secondary-data-sources-of-a-form"></a>Lösning för att skapa varningar för sekundära datakällor i ett formulär
Det går inte att skapa notifieringar för vissa sekundära datakällor i formulär. När du till exempel skapar notifieringar i formuläret kund eller leverantör bokföringsprofil, är endast fälten i huvudet (CustLedger eller VendLedger) tillgängliga och inte dimensionskontona. Lösningen för den här begränsningen är att använda **SysTableBrowser** för att öppna registret som primär datakälla. 
1. Öppna registret formuläret **SysTableBrowser**.
    ```
        https://<EnvironmentURL>/?cmp=USMF&mi=SysTableBrowser&TableName=<TableName>
    ```
2. Skapa en notifiering från formuläret SysTableBrowser.

