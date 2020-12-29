---
title: Automatiska uppdateringar för leveranser
description: Det här ämnet innehåller en översikt över funktioner som tillhandahåller automatiska uppdateringar för leveranser.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7fa2684340f5ce45b99ff9aee9937071f936b81a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437466"
---
# <a name="shipment-auto-updates"></a>Automatiska uppdateringar för leveranser

[!include [banner](../includes/banner.md)]

Funktionen för automatisk leveransuppdatering uppdaterar automatiskt kvantiteter (både ökningar och minskningar) på en lastrad som är kopplad till en leverans, efter att lasten har frisläppts till ett lagerställe. Den här funktionen är aktiverad tills lastraden för leveransen eller lasten bearbetas på en påfyllnad. När orderuppdateringar används kan de flöda automatiskt till lagerstället, utan manuell inblandning, tills lagerarbetet skapas.

När funktionen automatiska uppdateringar för leveranser inte används, minskar bara kvantiteten automatiskt tills lagerarbetet skapas. Användarna måste manuellt uppdatera eller ta bort rader och de måste sedan återsläppa rader om orderkvantiteter ökas eller nya order rader läggs till. Genom att använda funktionen för automatiska uppdateringar för leveranser kan företag sömlöst tillhandahålla uppdateringar av lagret utan att behöva oroa sig för att relaterade försändelser och laster inte ska återspegla uppdateringar av order rader.

Funktionen automatiska uppdateringar för leveranser gäller både försäljningsorderrader och överföringsorderrader och den är aktiverad för ett visst lagerställe. Därför kan företagen använda olika policyer för automatiska uppdateringar för leveranser över lagerställen, eftersom de kräver det. Som standard används den policyn automatiska uppdateringar för leveranser för kvantitetsminskningar för alla lagerställen som använder lagerstyrningsprocesser. När den här standardpolicyinställningen används minskar bara kvantiteten automatiskt genom till en leverans och last tills lagerarbetet skapas. Detta beteende påminner om det beteende som användes innan funktionen för automatisk uppdatering av leveransen infördes.

## <a name="main-elements-of-the-functionality"></a>Huvudelement i funktionen

Funktionen för automatisk uppdatering av leverans är i huvudsak beroende av leveransstatus för att bestämma om kvantiteten på en lastrad ska ändras när en ändring görs på en försäljningsorderrad eller överföringsorderrad. Den förlitar sig också på leveransstatusen för att fastställa när en ny lastrad automatiskt ska läggas till i en befintlig last. När leveransstatus är **påfylld** eller högre sker ingen automatisk uppdatering.

Påfyllningsstatus övervägs också för automatiska uppdateringar. Om den påfyllnad som är kopplad till lastraden har status **hålls**, **körs**, **frisläppt**, **plockad** eller **levererad** om en användare försöker minska kvantiteten på en lastrad (via en minskning av kvantiteten på försäljningsorderrad eller överföringsorderraden) visas följande felmeddelande: "reservationer kan inte tas bort eftersom det finns arbete skapat som använder reservationerna." När påfyllnad har en av de tidigare nämnda påfyllnadsstatus och en användare försöker indirekt öka lastradens kvantitet genom att öka kvantiteten på försäljningsorderraden eller överföringsorderraden, är kvantiteten på lastraden inte automatiskt öka. I det här fallet måste lastraden uppdateras manuellt.

## <a name="scenarios"></a>Scenarier

Funktionen för automatisk uppdatering av leverans stöder fyra scenarier: lägga till en ny orderrad, öka kvantiteten på en orderrad, minska kvantiteten på en orderrad och ta bort en orderrad.

- **Lägg till en ny orderrad** – När fältet **Automatiskt uppdatera leverans** på snabbfliken **lagerställe** på sidan **lagerställen** (**lagerställehantering \> inställningar \> lagerställe \> lagerställen**) anges till **alltid**, om det finns en leverans för ordern och en ny orderrad läggs till på en försäljningsorder eller överföringsorder efter att en last redan har skapats för försäljningsordern och den befintliga lasten inte uppdateras. En ny lastrad som inte har någon referens till den befintliga lasten skapas och associeras med den befintliga leveransen. Den nya raden läggs till i lasten och frisläpps.
- **Öka kvantiteten på en orderrad** – När fältet **Automatiskt uppdatera leverans** är inställt på **Alltid**, om en leverans finns för ordern och kvantiteten på en befintlig försäljningsorderrad eller överföringsorderrad ökas efter att en last redan har skapats för försäljningsordern ökas lastraden med samma kvantitet som orderraden. Om lasten släpptes men inget arbete har skapats, ökas lastraden med samma kvantitet som orderraden.
- **Minska kvantiteten på en orderrad** – När fältet **Automatiskt uppdatera leverans** anges till **Alltid** eller **Vid ökning av kvantitet**, om det finns en leverans för beställningen och mängden på en befintlig försäljningsorderrad eller överföringsorderrad minskar efter att en last redan har skapats för försäljningsordern, uppdateras kvantiteten på den tillhörande lastraden så att den matchar, såvida inte kvantiteten på den lastraden är redan lika med eller är mindre än den nya mängden på orderraden. I så fall påverkas inte lastraden. Om lasten släpptes, men inget arbete har skapats, uppdateras kvantiteten på den tillhörandelastraden för att matcha, såvida inte kvantiteten på lastraden redan är lika med eller är mindre än den nya kvantiteten på orderraden. I så fall påverkas lastraden.
- **Ta bort en orderrad** – när fältet **automatisk uppdatering av leverans** är inställt på **alltid** eller **minskning av kvantiteten** visas ett felmeddelande om användaren försöker ta bort en orderrad som det finns en lastrad för.

## <a name="example-scenario"></a>Exempelscenario

För det här scenariet måste du ha demonstrationsdata installerad och du måste använda **USMF**-demodataföretaget.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Aktivera funktionen för automatiska uppdateringar för leveranser

Aktivera funktionen för automatiska uppdateringar för leveranser genom att följa dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
2. Välj lagerställe **24**.
3. På snabbfliken **Lagerställe** i fältet **automatisk uppdatering av leverans**, ändra värdet från **minskning av kvantiteten** till **alltid**.

När du ändrar värdet till **alltid** blir ökningar eller minskningar i kvantiteterna på försäljningsorderrader och överföringsorderrader, och eventuella tillägg till nya rader, avspeglas på leveranser och laster för det valda lagerstället, med det tidigare nämnda uppdateringsbegränsningar.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Ändra påfyllnadsmallen så att lastrader inte bearbetas automatiskt

Om du vill konfigurera påfyllnadsmallen så att den inte automatiskt bearbetar lastrader följer du dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
2. Välj påfyllnadsmall för **24 standard för leverans**.
3. Välj **Redigera**.
4. På snabbfliken **Allmänt** ange alternativet **Automatisera skapande av påfyllnad** till **Ja** och se till att alla andra alternativ är inställda på **Nej**.

Det är viktigt att inget arbete skapas och frigörs automatiskt i samband med att skapa en påfyllnadsprocess. När arbetet har skapats som är relaterat till lastraden som har skapats för försäljningsorderraden uppdateras inte lastraden längre automatiskt om kvantiteten på försäljningsorderraden ändras.

### <a name="create-a-sales-order"></a>Skapa en försäljningsorder

Följ dessa steg för att skapa en försäljningsorder.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Välj kund **US-003**.
3. Skapa en rad för artikelnummer **A0001**.
4. Ange en kvantitet **10**. (Kontrollera att du använder lagerstället **24**.)
5. Välj **Spara**.
6. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**. En leverans och en påfyllnad skapas.

Eftersom du ändrade påfyllnadsmallen i föregående procedur, skapas ingen last eller arbete. Leveransstatus är **Öppen** och påfyllnadsstatus är **skapas**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Minska kvantitet på försäljningsorderrad

Minska kvantiteten på en försäljningsorderrad enligt följande steg.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Välj den försäljningsorder som du just har frisläppt till lagerstället.
3. Välj försäljningsorderrad. I fältet **Kvantitet**, ändra värdet från **10** till **8**.
4. Från försäljningsorderraden, välj **Lagerställe \> Leveransdetaljer**. På sidan **leveransinformation** på snabbfliken **lastrader** återspeglar kvantiteten ändringen på försäljningsorderraden.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Öka kvantitet på försäljningsorderrad

Öka kvantiteten på en försäljningsorderrad enligt följande steg.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Välj den försäljningsorder som du har frisläppt tidigare till lagerstället.
3. Ändra radens kvantitet från **8** till **12**.
4. Välj **Spara**.
5. Gå tillbaka till sidan **alla försäljningsorder** och välj försäljningsordern igen.
5. I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Relaterad information**, väljer du **Leveransdetaljer**. På sidan **leveransinformation** på snabbfliken **lastrader** återspeglar kvantiteten ändringen på försäljningsorderraden.

Även om kvantiteten på lastraden har ökats från 8 till 12 förblir bara åtta artiklar reserverade, om inte automatisk reservation är aktiverad. Eftersom den kvantitet som läggs till i den befintliga leveransen inte har reserverats ännu, om påfyllnad bearbetas vid denna tidpunkt, så skapas bara arbetet för den kvantitet som redan har reserverats.

> [!NOTE]
> När kvantiteten på en orderrad minskas, påverkas inte kvantiteten på lastraden om den redan är lika med eller är mindre än den nya kvantiteten på orderraden. När kvantiteten på en orderrad ökas ökas lastraden med samma kvantitet som orderraden. Om kvantiteten på orderraden avviker från kvantiteten på lastraden finns inte differensen.

### <a name="add-a-sales-order-line"></a>Lägg till en försäljningsorderrad

Om du vill lägga till en försäljningsorderrad, gör följande steg.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Välj den försäljningsorder som du har frisläppt tidigare till lagerstället.
3. Skapa en rad för artikelnummer **A0002**.
4. I fältet **Kvantitet**, ange **10**. (Kontrollera att du använder lagerstället **24**.) Den nya raden läggs automatiskt till i den befintliga leveransen.
5. Välj **Spara**.
6. Gå tillbaka till sidan **alla försäljningsorder** och välj försäljningsordern igen.
7. I åtgärdsfönstret, på fliken **Lagerställe**, i gruppen **Relaterad information**, väljer du **Leveransdetaljer**. På sidan **leveransinformation** på snabbfliken **Lastrader** obserevra den andra lastraden.

Eftersom försäljningsorderraden som du just har lagt till i den befintliga leveransen inte har reserverats ännu, om påfyllnaden bearbetas vid denna tidpunkt, skapas endast arbete för kvantiteten på den första försäljningsorderraden och den första lastraden.

### <a name="process-a-wave"></a>Bearbeta en påfyllnad

Gör så här om du vill bearbeta en påfyllnad.

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
2. Välj den påfyllning som du skapat tidigare.
3. I Åtgärdsfönstret, på fliken **påfyllning**, i gruppen **påfyllning**, markerar du **bearbeta**.

Påfyllningen bearbetas och skapar arbete för reserverade kvantiteter på lastraderna. Leveransstatus uppdateras från **öppen** till **påfylld.** När leveransstatusen uppdateras till **påfylld**, kommer alla ändringar som inträffar, t.ex. minskningar eller ökningar i radkvantiteter, eller tillägg av nya rader till försäljningsordern, inte att påverka de befintliga lastraderna som är kopplade till den påfyllda leveransen.

Om en leverans har statusen **påfylld** eller högre, visas inte uppdateringar av kvantiteten på en försäljningsorderraden på eller valideras mot en lastrad som är kopplad till leveransen. Ändringar av kvantiteten på en lastrad måste göras direkt på lastraden.

Validering görs när arbetet har skapats för lastraden och en reservation har gjorts. En minskning av kvantiteten på försäljningsorderraden valideras sedan mot arbetsradens reservation.
