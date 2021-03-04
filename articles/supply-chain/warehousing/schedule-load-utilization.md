---
title: Tidsplanera beläggningsutnyttjande
description: Det här avsnittet beskriver hur du ställer in och schemalägger beläggningen för ett lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87455077c69834c9ace6409f4cc611ae6e14beb4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437459"
---
# <a name="schedule-load-utilization"></a>Tidsplanera beläggningsutnyttjande

[!include[banner](../includes/banner.md)]

Du kan tidsplanera beläggningsutnyttjande för valda platstyper och även planera nuvarande och framtida beläggningsutnyttjande. Du kan planera belastningen för en eller flera platser för beläggningenheterna i lagerstället eller zonen, eller för en kombination av zonen och lagerstället.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Tidsplanera och visa beläggningen för ett lagerställe eller en plats

Om du vill tidsplanera beläggningen för platser, lagerställen och zoner skapar du en inställning för utrymmesutnyttjande och kopplar den till en huvudplan.

I utrymmesutnyttjandeinställningen använder du platstyper, t.ex. **Bulkplats** och **Plockplats**, för att ange hur utrymmesutnyttjande bör planeras. Du kan även ange ett lagerbeläggningläge, till exempel **Zon**.

Planeringen av framtida utrymmesutnyttjande baseras på information som beräknas från den associerade huvudplanen. Huvudplanerna resursplanerar inför inkommande och utgående order för produktion och operationer. Planeringen av tillgängligt för utrymme baseras på relationen mellan det inställda utrymmesutnyttjandet och den valda huvudplanen.

Genom att använda lagerbeläggningsläget, som du väljer i utrymmesutnyttjandesinställningen, anger du om beläggningen ska planeras för respektive lagerställe eller zon, eller om planeringen ska innehålla information om både lagerställe och zon. Du kan också ange om spärrade platser ska utelämnas från beräkningen av beläggningsutnyttjandet.

Du kan planera ut utrymmesutnyttjande genom att generera rapporten **beläggningsutnyttjande för lagerställe**. När du genererar rapporten kan du ange om beläggningsutnyttjandet ska planeras för varje plats eller mellan platser, eller för den valda beläggningsenheten, till exempel zon eller lagerställen.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Skapa ett utrymmesutnyttjande som har ställts in för ett lagerställe

1. Välj **lagerhantering**\>**inställningar**\>**Övervakning av lagerställe**\>**Utrymmesutnyttjande**.
2. Klicka på **Ny** om du vill skapa en ny utrymmesutnyttjandeinställning. Ange ett ID och ett namn för den nya inställningen.
3. Välj om översikten över utrymmesutnyttjandet ska vara efter lagerställe, zon eller lagerställe och zon i fältet **Lagringsbeläggningsläge**.
4. Ange alternativet **exkludera spärrade platser** till **Ja** för att exkludera spärrade lagerplatser från beräkningen av tillgängligt utrymme. Du kan spärra en lagerplats för in- och utleverans genom att ange spärrorsaker för platsen på fälten **Inleverans spärrad** eller **Utleverans spärrad** på snabbfliken **Andra** på sidan **Lagerplatser**.
5. Välj platstyper som ska inkluderas i utrymmesutnyttjandeberäkningen på snabbfliken **Lagertyp**. Du måste minst välja en platstyp för planeringen.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Koppla en utrymmesutnyttjandeinställning till en huvudplan

1. Välj **Lagerhantering** \> **Periodiska uppgifter** \> **Tidsplanera beläggningsutnyttjande**.
2. Välj en huvudplan i fältet **huvudplan**.
3. I fältet **Antal dagar** ange antalet dagar du vill inkludera i planen för aktuella och framtida arbetsbeläggningar.
4. Välj utrymmesutnyttjandeinställning som ska användas för planeringen av aktuella och framtida arbetsbeläggningar i fältet **utrymmesutnyttjande**.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Ange och visa information om beläggningsutnyttjandeplanen

1. Välj **lagerhantering**\>**förfrågningar och rapporter**\>**Rapporter om fysiskt lager**\>**beläggningsutnyttjande för lagerställe**.
2. I fältet **Visa efter** välj planeringen av utrymmesutnyttjandenivån:

    - **Plats** – Planera utrymmesutnyttjandet för varje plats. Den här planeringen är praktisk om du till exempel vill visa alla lagerställen för en plats, så att du kan stämma av utrymmesutnyttjandet mellan lagerställen.
    - **Beläggningsenhet** – planera utrymmesutnyttjande för zoner eller lagerställen. Sedan beräknas det tillgängliga utrymmet enligt det värde som du valde i fältet **Lagringsbeläggningsläge** på sidan **Utrymmesutnyttjande** när du har skapat utrymmesutnyttjandeinställningen.

3. Gör något av följande, beroende på vilket värde du valde i föregående steg:

    - Om du valde **Plats** i fältet **Visa efter** är fältet **Plats** tillgängligt. Markera en eller flera platser som ska inkluderas i planeringen i fältet .
    - Om du valde **Beläggningsenhet** i fältet **Visa efter** är fältet **Beläggningsenhet** tillgängligt. Välj beläggningsenhet

4. I fältet **Beläggningstyp**, välj **Volym** eller **Vikt** när du vill ange lagerställesdriftenhet för planering av utrymme.
5. I fältet **inställningar av utrymmesutnyttjandet**, välj de inställningar av utrymmesutnyttjandet som planeringen ska baseras på.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]