---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d2fe07790f64f7e7f672980f80a3e56804cefd66
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351547"
---
# <a name="creating-work-orders"></a>Skapa arbetsorder

[!include [banner](../../includes/banner.md)]

När du har schemalagt förebyggande underhållsjobb är nästa steg att skapa arbetsorder för jobben. Du kan genomföra det här steget genom att använda ett av underhållsschemana. De schemalagda jobben i ett underhållsschema kan ha olika referenstyper som beskrivs i följande tabell:

| Referenstyp | beskrivning |
|---|---|
| Underhållsplaner | Förebyggande underhållsjobb baserade på underhållsplanens typer *Tid* eller *Räknare*. |
| Underhållsomgångar | Förebyggande underhållsjobb som innehåller flera tillgångar som kräver en liknande typ av underhåll. |
| Underhållsbegäran | En manuellt skapad begäran om underhåll eller reparation av en tillgång. Denna begäran kan konverteras till en arbetsorder. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Skapa arbetsorder baserat på din underhållsplan

Skapa arbetsorder som baseras på din underhållsplan genom att följa dessa steg.

1. Öppna någon av följande sidor, beroende på hur du vill välja tidsplaner uppgifter för dina arbetsorder:

    - Alla underhållsscheman (**Hantering av tillgångar \> Hanteringsschema \> Alla underhållsscheman**)
    - Öppna underhållsschemarader (**Hantering av tillgångar \> Hanteringsschema \> Öppna underhållsschemarader**)
    - Öppna underhållsschemapooler (**Hantering av tillgångar \> Hanteringsschema \> Öppna underhållsschemapooler**)

1. Markera kryssrutan i rutnätet för varje planerat underhållsjobb som du vill skapa en arbetsorder för. Välj **Arbetsorder** i åtgärdsfönstret.

    Dialogrutan **Skapa arbetsorder** visas. Det totala antalet prognostimmar för de valda raderna visas i fältet **Prognostimmar för underhåll**.

    ![Dialogrutan Skapa arbetsorder.](media/18-preventive-maintenance.png)

1. I avsnittet **Parametrar** ange antalet arbetsorder som ska skapas. Välj ett av följande alternativ:

    - **En arbetsorder per rad** – Skapa en arbetsorder per underhållsplansrad.
    - **En arbetsorder per** – Skapa arbetsorder som grupperas enligt inställningarna för de andra alternativen som blir tillgängliga när du väljer det här alternativet.

1. Välj vilken arbetsordertyp som ska användas för alla arbetsorder som du skapar i fältet **Typ av arbetsorder**.
1. Välj **OK** för att skapa arbetsorder i enlighet med dina inställningar.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Gruppera arbetsorderrader som skapas automatiskt när en underhållsplan körs

Med hjälp av den här funktionen kan du definiera regler för gruppering av arbetsorderrader under en enskild arbetsorder när systemet är inställt på att generera arbetsorder automatiskt, baserat på en underhållsplan. Tidigare kunde automatiskt genererade arbetsorder bara innehålla en rad. Du kan nu dock gruppera arbetsorder efter till exempel tillgång, tillgångstyp eller funktionell plats. (Manuellt genererade arbetsorder kan redan grupperas på det här sättet, på det sätt som beskrivs i det föregående avsnittet av det här avsnittet.)

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Aktivera gruppering för automatiskt genererade arbetsorder

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Tillgångshantering*
- **Funktionens namn:** *Använd regler för att gruppera arbetsorder när du kör en underhållsplan*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Ange gruppering för automatiskt genererade arbetsorder

Ange gruppering för automatiskt genererade arbetsorder med följande steg.

1. Gå till **Tillgångshantering \> Inställning \> Förebyggande underhåll \> Underhållsplaner**.
1. Följ de här stegen för varje plan där du vill generera grupperade arbetsorder:

    1. Välj planen i listfönstret.
    1. På snabbflikarna **Rader** kontrollerar du att kryssrutan **Skapa automatiskt** har markerats på varje rad.

1. Gå till **Tillgångshantering \> Periodisk \> Förebyggande underhåll \> Schemalägg underhållsplaner**.
1. Ange tidshorisont för planen i dialogrutan **Schemaunderhållsplaner** i avsnittet **Period** (hur långt du kan se framåt när du söker efter planerade underhållsjobb som genererar arbete).
1. Ställ in alternativet **Skapa arbetsorder automatiskt från schema** till *Ja*.
1. Välj ett av följande alternativ i området **Arbetsorder**:

    - **En arbetsorder per rad** – Skapa en arbetsorder per underhållsplansrad. (Det här alternativet ger samma funktion som är tillgänglig när funktionen *Använd regler för att gruppera arbetsorder när du kör en underhållsplan* är avaktiverad.)
    - **En arbetsorder per** – Skapa arbetsorder som grupperas enligt inställningarna för de andra alternativen som blir tillgängliga när du väljer det här alternativet.

1. Om du vill att alternativen ska gälla när du bara kör några av dina underhållsplaner, på snabbfliken **Poster att inkludera** lägg till filter du vill ha som med andra batchjobb i Microsoft Dynamics 365 Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** ställer du in alternativ för batch och tidsplanering efter behov, på samma sätt som du kan göra för andra batchjobb i Supply Chain Management.
1. Välj **OK** för att köra och/eller planera de valda underhållsplanerna.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]