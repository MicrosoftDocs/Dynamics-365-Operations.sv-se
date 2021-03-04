---
title: Hantera leasing med ramverket för import av leasing
description: I det här ämnet beskrivs hur du använder importramverket för leasing för att justera flera leasingar samtidigt.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d7a7d2afd8f352bc167ec8c0a354ee4ac0a9e77b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448212"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Hantera leasing med ramverket för import av leasing

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du använder importramverket för leasing för att justera flera leasingar i ett steg. Genom att använda den här funktionen kan du spara tid och du kan också se till att ändringarna blir mer exakta genom att minska risken för mänsklig fel. Dessutom kan den här funktionen ansluta Microsoft Dynamics 365 Finance med externa dataentiteter för att effektivt ladda upp data.

Följande dataentiteter kan användas för att integrera Leasing av tillgångar med externa system:

- Mellanlagring av leasingavtal
- Mellanlagring av betalningskontrakt
- Mellanlagring av verkställande kontrakt

Du kan använda importprocessen för att justera en leasing, uppdatera icke-ekonomisk information och lägga till nya leasingar. Du kan visa och redigera leasinginformationen innan du importerar den.

Systemet kan köra följande tre processer via importsviten för leasingen.

| Processtyp  | beskrivning |
|---------------|-------------|
| Lägg till post    | Migrerade leasingar som har den här processtypen skapar en leasing i systemet. Betalningsplanen måste bekräftas manuellt och journalposten för det första bokföringstillfället måste bokföras manuellt efter migreringen. |
| Uppdatera post | Migrerade leasingar som har den här processtypen uppdaterar fältvärden för en leasing som redan finns i systemet. Endast de fält som har markerats på sidan **Uppdatera valda fält** uppdaterats. Vi rekommenderar att du väljer icke-finansiella fält på sidan **Uppdatera valda fält** eftersom den här processtypen inte justerar leasingen. |
| Justera post | Migrerade leasingar som har den här processtypen justerar leasingen. Denna justering medför en finansiell leasingändring av leasingen. När leasingen bearbetas skapar systemet en ny betalningsplan genom att använda nya data från importsviten för leasingen. Systemet bekräftar inte betalningsplanen och bokför inte justeringsjournalposten. |

När information har laddats upp via arbetsytan **Datahantering** öppnar du sidan **Importhuvud** (**Leasing av tillgångar \> Ramverk för import av leasing \> Importhuvud**). På den här sidan visas alla importer av de tre dataentiteter som listades tidigare.

Om du vill visa mellanlagringsdata för leasing innan bearbetningen körs väljer du **Mellanlagringsdata**.

Med jämförelsefunktionen kan du jämföra en post som du importerar med motsvarande post som redan finns i systemet. Om du vill jämföra en enskild leasingpost väljer du en leasing lån och väljer sedan **Jämför**. Du bör slutföra det här steget för att generera en **Skillnader**-rapport innan du migrerar leasingposterna. Jämförelsefunktionen jämför värdena i dina mellanlagringsdata med värden för de leasingar som för närvarande finns i systemet.

> [!NOTE]
> Jämförelsefunktionen fungerar inte för leasingar som har processtypen **Lägg till post** eftersom det inte finns något att jämföra med denna leasing.
>
> Om du vill jämföra flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Jämför** och välja **Jämför**.

För varje entitet kan du visa skillnaderna mellan vad som finns i systemet och vad som finns i mellanlagringstabellerna. Välj **Visa skillnader** för varje entitet i mellanlagringstabellerna. Dialogrutan som visas visar det aktuella värdet och det föreslagna mellanlagringsvärdet.

Du kan också uppdatera ditt mellanlagringsvärde genom att ändra det i kolumnen **Nytt värde** och sedan välja **Uppdatera mellanlagring**.

Du kan validera leasingar för att säkerställa att posterna kan föras in i systemet utan att några fel uppstår. Innan en leasingpost migreras kör systemet flera valideringar för att kontrollera att posten kommer att importeras utan problem. Om du vill validera en enskild leasing väljer du **Validera**.

> [!NOTE]
> Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Validera** och välja **Jämför**.

Om du vill bearbeta en enskild leasing väljer du **Migrera leasingposter** på sidan **Importhuvud**. När en leasing migreras utför systemet den åtgärd som anges i fältet **Processtyp**.

> [!NOTE]
> Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Validera** och välja **Jämför**.

När leasingarna jämförs kan du köra en rapport för att visa skillnaderna för varje leasing som ingår i import-ID:t. Om du vill köra rapporten för en leasing lån väljer du denna leasing i mellanlagringsdata och väljer sedan **Jämför och visa rapport \> Rapporten Skillnader**.

> [!NOTE]
> Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Förfrågningar och rapporter \> Rapporten Skillnader** och välja **Jämför**.

## <a name="set-up-update-fields"></a>Konfigurera uppdateringsfält

Om du använder ramverket för import av leasing för att uppdatera leasingar och process typen är **Uppdatera post** kan du välja vilka fält som ska uppdateras.

1. Gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Konfigurera \> Välj fält att uppdatera**.
2. Välj de fält som ska uppdateras på sidan som visas och välj sedan den gröna pilen för att flytta dem till listan **Valda fält**. Endast fält i listan **Valda fält** kan uppdateras med hjälp av importsviten för leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]