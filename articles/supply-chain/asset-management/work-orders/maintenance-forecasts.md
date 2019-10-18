---
title: Underhållsprognoser
description: I det här avsnittet beskrivs underhållsprognoser i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024509"
---
# <a name="maintenance-forecasts"></a>Underhållsprognoser

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


När du skapar en arbetsorder skapar du arbetsorderjobb med relaterade tillgångar och underhållsjobbtyper. När du väljer en underhållsjobbtyp som innehåller underhållsprognoser, kopieras prognoserna automatiskt till arbetsordern.

Du kanske kan lägga till eller ta bort prognosrader på en arbetsorder. Inställningen av ett livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera prognosrader. 

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder i listan och klicka på **Prognos**. I **Underhållsprognos för arbetsorder** visas prognosrader från den typ av underhållsjobb som valts i arbetsorderjobbet.


## <a name="add-hours-forecast-to-a-work-order"></a>Lägga till timprognos i en arbetsorder

1. Välj det arbetsorderjobb som du vill lägga till en prognos för.

2. På snabbfliken **Timmar**, klicka på **Lägg till** för att skapa en ny rad.

3. Välj en kategori i fältet **Kategori**.

4. Infoga antal prognostiserade timmar i fältet **Timmar**.

5. I fältet **Radegenskap** väljer du den kostnadstyp som ska användas på raden.


## <a name="add-items-forecast-to-a-work-order"></a>Lägga till artikelprognos i en arbetsorder

Det finns tre sätt att lägga till artiklar i en underhållsprognos för arbetsorder: du kan skapa rader för artiklar (reservdelar) som inte ingår i reservdelslistan eller tillgångsstrukturen, du kan välja reservdelar från listan med godkända reservdelar, och du kan välja artiklar från tillgångsstrukturen.

1. Välj det arbetsorderjobb som du vill lägga till en prognos för.

2. Välj på snabbfliken **Artiklar**.

3. Klicka på **Lägg till** om du vill skapa en ny rad för en reservdel som inte finns med i reservdelslistan eller tillgångsstrukturlistan.

4. Välj artikeln i fältet **Artikelnummer**.

5. Infoga kvantitet i fältet **Försäljningskvantitet** och välj en kvantitetsenhet i fältet **Enhet**.

6. Infoga självkostnad och valuta i de relevanta fälten och välj en **Radegenskap**.

7. Om du vill ändra listan över de dimensioner som visas på artikelraderna klickar du på **Lager** > **Visa dimensioner**, väljer dimensioner och väljer sedan "Ja" på växlingsknappen **Spara inställningar** .

8. Om du vill lägga till en godkänd reservdel i underhållsprognosen klickar du på **Lägg till reservdelar**, väljer reservdelen, redigerar relaterad informationen om det behövs och klickar på **OK**.

9. Om du vill lägga till tillgångsstrukturartiklar i prognosen klickar du på **Lägg till strukturlisteartiklar**, väljer den aktuella artikeln, redigerar relaterad information klickar på **OK**.

10. Klicka på **Artikel där den används** om du vill få en översikt över var artikeln på den valda raden används i Tillgångshantering, i relation till tillgångar, standardvärden för underhållsjobbtyper, reservdelar och arbetsorder. 



## <a name="add-expense-forecast-to-a-work-order"></a>Lägga till utgiftsprognos i en arbetsorder

1. I det här avsnittet beskrivs hur du lägger till en utgiftsprognos till en arbetsorder. På vänstra sidan av formuläret väljer du det arbetsorderjobb som du vill lägga till en prognos för.

2. Välj snabbfliken **Utgift**.

3. Klicka på **Lägg till** om du vill skapa en ny rad.

4. Välj en kategori i fältet **Kategori**.

5. I fältet **Kvantitet** anger du kvantiteten.

6. Infoga självkostnad, försäljningsvaluta och försäljningspris i de relevanta fälten.

7. I fältet **Radegenskap** väljer du den kostnadstyp som ska användas på raden.

>[!NOTE]
>På snabbfliken **Underhållsprognossummor** visas en översikt över antalet rader som har skapats på varje flik, för det valda arbetsorderjobbet och för arbetsordern. Du kan också visa en summa för prognostiserad arbetstid för arbetsorderjobbet och för arbetsordern.

![Figur 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Automatisk uppdatering av arbetsorderprognoser

I Tillgångshantering kan du automatiskt uppdatera alla ändringar av arbetsorderprognoser för timkostnader, artikelkostnader och utgifter som har uppdaterats i andra moduler. Detta görs för att se till att de senaste självkostnaderna alltid används i dina arbetsorderprognoser. Det går också att göra liknande uppdateringar för [prognoser för underhållsjobbtyper](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Klicka på **Tillgångshantering** > **Periodiskt** > **Prognos** > **Uppdatera arbetsorderprognos**.

2. I den nedrullningsbara dialogrutan **Uppdatera arbetsorderprognos** kan du lägga till urval för specifika arbetsorder eller arbetsorderjobb om det behövs. Klicka på **Filter** för att göra urvalen.

3. På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.

4. Klicka på **OK** för att starta progonosuppdateringen.


![Figur 2](media/07-work-orders.png)

