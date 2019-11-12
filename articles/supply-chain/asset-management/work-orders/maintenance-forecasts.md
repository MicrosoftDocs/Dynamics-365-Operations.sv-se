---
title: Underhållsprognoser
description: I det här avsnittet beskrivs underhållsprognoser i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a1596b283c3eaffca25ff7f03c722a2bcce109fb
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626303"
---
# <a name="maintenance-forecasts"></a>Underhållsprognoser

[!include [banner](../../includes/banner.md)]



När du skapar en arbetsorder skapar du arbetsorderjobb med relaterade tillgångar och underhållsjobbtyper. När du väljer en underhållsjobbtyp som innehåller underhållsprognoser, kopieras prognoserna automatiskt till arbetsordern.

Du kanske kan lägga till prognosrader till en arbetsorder eller ta bort dem från en arbetsorder. Inställningen av en livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera prognosrader. Mer information om livscykeltillstånd för arbetsorder och relaterade projektfaser finns i [Prognoser, arbetsorder och projekt](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder i listan och sedan i åtgärdsfönstret på fliken > **Arbetsorder** > i gruppen **Projekt** väljer du **Prognos**. På sidan **Underhållsprognos för arbetsorder** visas prognosrader från den typ av underhållsjobb som valts i arbetsorderjobbet.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Lägga till timprognos i en arbetsorder

1. På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.

2. På snabbfliken **Timmar**, klicka på **Lägg till** för att skapa en ny rad.

3. Välj en kategori i fältet **Kategori**.

4. Infoga antal prognostiserade timmar i fältet **Timmar**.

5. I fältet **Radegenskap** väljer du den typ av tillägg som ska användas på raden.


## <a name="add-an-items-forecast-to-a-work-order"></a>Lägga till artikelprognos i en arbetsorder

Det finns tre sätt att lägga till artiklar i en underhållsprognos för arbetsorder. Du kan skapa rader för artiklar (reservdelar) som inte ingår i reservdelslistan eller tillgångsstrukturen, du kan välja reservdelar från listan med godkända reservdelar, och du kan välja artiklar från tillgångsstrukturen.

- På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.

- På snabbfliken **artiklar** lägg till artiklar i underhållsprognosen med hjälp av lämplig metod.

För att skapa en ny rad för en reservdel som inte finns med i reservdelslistan eller tillgångsstrukturlistan, följ dessa steg.

1. Markera **Lägg till**.
2. Välj en artikel i fältet **Artikelnummer**.
3. I fältet **Försäljningskvantitet** anger du kvantiteten.
4. Välj måttenhet för kvantiteten i fältet **Enhet**.
5. I fälten **Självkostnad** och **Valuta** anger du lämpliga värden.
6. I fältet **radegenskap** väljer du en rad egenskap.
7. Om du vill ändra listan över de dimensioner som visas på artikelraderna väljer du **Lager** > **Visa dimensioner**, väljer dimensioner och anger sedan alternativet **Spara inställningar** till **Ja**.

Så här lägger du till en reservdel från en godkänd reservdelslista:

1. Välj **Lägg till reservdelar**.
2. Välj reservdelen och redigera den relaterade informationen som du behöver.
3. Välj **OK**.

Gör så här om du vill lägga till en artikel från tillgångsstrukturen:

1. Välj **Lägg till strukturlisteartiklar**.
2. Välj artikeln och redigera den relaterade informationen som du behöver.
3. Välj **OK**.

Om du vill få en översikt som visar var artikeln på den valda raden används, i relation till tillgångar, underhållsjobbtypstandarder, reservdelar och arbetsorder i tillgångshantering väljer du **artikel där den används**. Mer information om översikten finns i [Artikel där den används](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Lägga till utgiftsprognos i en arbetsorder

1. På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.

2. På snabbfliken **Utgift**, klicka på **Lägg till** för att skapa en rad.

3. Välj en kategori i fältet **Kategori**.

4. I fältet **Kvantitet** anger du kvantiteten.

5. I fälten **självkostnad**, **försäljningsvaluta** och **försäljningspris** anger du lämpliga värden.

6. I fältet **Radegenskap** väljer du den typ av tillägg som ska användas på raden.

>[!NOTE]
>Snabbfliken **Underhållsprognossummor** visar en översikt över antalet rader som har skapats för det valda arbetsorderjobbet och för arbetsordern på varje snabbfliken. Den visar också visa en summa för prognostiserad arbetstid för arbetsorderjobbet och för arbetsordern.

I bilden nedan visas ett exempel på sidan **Underhållsprognos för arbetsorder**.

![Figur 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Automatisk uppdatering av arbetsorderprognoser

Om timkostnader, artikelkostnader och utgifter uppdateras i andra moduler i Microsoft Dynamics 365 for Finance and Operations kan arbetsorderprognoser i Tillgångshantering uppdateras automatiskt för att återspegla dessa förändringar. Denna kunskap hjälper till att garantera att de senaste självkostnaderna alltid används i dina arbetsorderprognoser. Du kan också göra liknande uppdateringar för [prognoser för underhållsjobbtyper](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Klicka på **Tillgångshantering** > **Periodiskt** > **Prognos** > **Uppdatera arbetsorderprognos**.

2. I dialogrutan **Uppdatera arbetsorderprognos** på snabbfliken **Poster som ska ingå** kan du lägga till urval för specifika arbetsorder eller arbetsorderjobb om det behövs. Välj **filter** och gör relevanta val.

3. På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.

4. Starta prognosuppdateringen genom att välja **OK**.


I bilden nedan visas ett exempel på sidan dialogrutan **Uppdatera arbetsorderprognos**.

![Figur 2](media/07-work-orders.png)
