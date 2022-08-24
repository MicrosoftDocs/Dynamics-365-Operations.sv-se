---
title: Platsdirektiv för plockning i åldersfördelat lager
description: I denna artikel beskrivs hur du använder platsdirektivstrategier för först in, först ut (FIFO) och sist in, först ut (LIFO) vid plockning.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: fc4348f8207f4f6c8a0b694bc3e57beb29449a15
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219485"
---
# <a name="location-directive-inventory-picking-aging"></a>Platsdirektiv för plockning i åldersfördelat lager

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du använder platsdirektivstrategier för först in, först ut (FIFO) och sist in, först ut (LIFO) vid plockning. Dessa strategier fungerar tillsammans med åldersdatumen som registreras för platser som ska spåras när lagret först har registrerats i lagerstället. Funktionen *Platsdirektiv för plockning i åldersfördelat lager* använder datumet på platsen för bestämning av ålder. Funktionen *Distributionslagrets platsstatus* uppdaterar datumet på platsen, baserat på datumet från ID-numret.

Du kan använda FIFO- och LIFO-strategier för att skicka både spårade artiklar och icke-spårade artiklar, baserat på det datum då lagret registrerades i lagerstället. Den här funktionen kan vara särskilt användbar vid icke-spårade lager, där utgångsdatum inte kan användas för sortering.

När lagret först tas emot eller skapas i lagerstället uppdaterar systemet det relevanta ID-numret så att aktuellt datum visas som åldersdatum. Detta datum används sedan i strategier för positionering av platser för att identifiera det äldsta eller senaste lagret i lagerstället. Om lagret flyttas till en plats som inte spåras av ett ID-nummer, uppdateras själva platsen med åldersinformation och denna information används sedan av strategierna.

## <a name="turn-on-the-feature"></a>Aktivera en funktion

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. *Lagerställets platsstatus* version 10.0.29 är den här funktionen aktiverad som standard. Mer information finns i [Lagerställets platsstatus](warehouse-location-status.md).
1. *Platsdirektiv för plockning i åldersfördelat lager*

## <a name="feature-requirements"></a>Funktionskrav

Om du vill använda den här funktionen måste du konfigurera alternativet **Aktivera platsstatus** till *Ja* för varje [platsprofil](tasks/create-location-profile.md) som används för lagerhantering. Om du vill ange det här alternativet för en platsprofil går du till **lagerstyrning \> inställningar \> lager \> platsprofiler** och väljer platsprofil. Du hittar alternativet på snabbfliken **Allmänt**.

## <a name="feature-scenarios"></a>Funktionsscenarier

Det här avsnittet innehåller exempel som visar hur du konfigurerar och använder strategier för FIFO och LIFO.

> [!TIP]
> Det här avsnittet innehåller två scenarier, ett för FIFO och ett för LIFO. I de procedurer som tillhandahålls förutsätts det att du ska göra båda scenarierna i ordning. Vi rekommenderar att du gör båda scenarierna så att du kan uppleva skillnaderna mellan de två strategierna.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom dessa scenarier med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda dessa scenarier som vägledning för funktionen när du använder ett produktionssystem. I så fall måste du dock ersätta dina egna värden för varje inställning som beskrivs här.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Ställ in scenarier

Demonstrationsdata kräver inställning och lagerjusteringar för att stödja scenarierna. Följ dessa steg för att skapa de lagerdata som krävs för att du ska kunna arbeta genom FIFO- och LIFO-scenarierna.

1. Logga in på ett system där demodata är installerad och välj den juridiska personen **USMF**.
1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I listan över platsprofiler, välj **FLOOR-05**.
1. På snabbfliken **allmänt** anger du alternativet **Aktivera platsstatus** till *Ja*.
1. Välj **Spara**.
1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I listan över platsdirektiv väljer du **63 plocka skapande av behållare**.
1. Välj **Redigera** om du vill placera sidan i redigeringsläge.
1. På snabbfliken **platsdirektivåtgärder** hittar du raden där fältet **Sekvensnummer** anges till *1* och gör sedan något av följande:

    - Om du konfigurerar ett FIFO-scenario ändrar du värdet för fältet **strategi** till platsen för *platsåldrande FIFO*.
    - Om du konfigurerar ett LIFO-scenario ändrar du värdet för fältet **strategi** till platsen för *platsåldrande LIFO*.

1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. I frågerutan på fliken **Intervall** välj **Lägga till** för att lägga till en rad och ange sedan följande värden:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *zon-ID*
    - **Kriterier:** *Våning*

1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan för fråga.
1. Välj **Spara** om du vill ändra platsdirektiv.
1. På en mobil enhet eller i appen *Dynamics 365 Supply Chain Management – lagerhållning* på datorn ska du följa dessa steg för att ta bort befintligt lager från lagerstället för att stödja scenarierna:

    1. Logga in på lagerställe *63* genom att använda rätt användar-ID och lösenord.
    1. På huvudmenyn, välj **Kvalitet**.
    1. I menyn **Kvalitetshantering** välj **Kassation**.
    1. På sidan **Kassation** välj fältet **LOC/LP** och ange *63\_1*.
    1. Välj **Ange** eller **OK**.
    1. Bekräfta informationen **kassation** för **justering** genom att välja **Retur** eller **OK**.

    När inventeringen av ID-nummer är justerad visas meddelandet "färdigt arbete".

    Dessa steg lämnar lagret på två platser i demonstrationsdata. Varje plats har ett annat åldersdatum. Plats *FL-001* har ett åldersdatum för 15 april 15, 2017 och platsen *FL-002* har åldersdatum 29 januari, 2017. Båda platserna innehåller artikel *A0001*.

    Om du vill visa dessa data går du till **Lagerhantering \> förfrågningar och rapporter \> behållningslistan** och filtrerar sedan på lagerställe *63* och artikel *A0001*. I raderna där fältet **Plats** anges till *FL-001* eller *FL-002*, välj en rad som har ett positivt värde för **Fysiskt lager** och välj sedan **Transaktioner** i åtgärdsfönstret. I fältet **fysiskt datum** visas ett datum som motsvarar ett av de tidigare angivna åldersdatumen.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Scenario 1: Ställ in och använd FIFO-platsåldrande

FIFO-strategin söker efter platsen som innehåller det äldsta åldersdatumet och allokerar plockning utifrån detta åldersdatum.

1. Om du inte redan har gjort det [Förbered exempeldata](#demo-set-up) som krävs för detta scenario.
1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Välj **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-001*.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *63*.

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Detta innehåller en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**. För denna orderrad anger du fältet **Artikelnummer** till *A0001* och fältet **Kvantitet** till *1*.
1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti** för att reservera den beställda kvantiteten av denna artikel från lagret i det valda lagerstället.
1. Stäng sidan **Reservation**.
1. På sidan **Försäljningsorder** i åtgärdsfönstret väljer du **Lagerställe** i gruppen **Åtgärder** välj **Släpp till distributionslager**. Du får informativa meddelanden. Systemet skapar en leverans, lägger till den i en ny last och skapar det begärda arbetet.
1. På snabbfliken **Försäljningsorderrader** på menyn **Lagerställe** välj **Arbetsdetaljer** för att öppna det arbete som har skapats för den här försäljningsordern. Observera att raden där värdet för **Arbetstyp** är *Plocka* visar ett värde för **Plats** för *FL-002*. Den här platsen innehåller det ID-nummer som har det äldsta åldersdatumet (FIFO).
1. Välj **Lagerställe \> Leveransdetaljer**.
1. På snabbfliken **Allmänt** noterar du påfyllnad-ID, så att du kan använda det i scenario 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Scenario 2: Ställ in och använd LIFO-platsåldrande

LIFO-strategin söker efter platsen som innehåller det nyaste åldersdatumet och allokerar plockning utifrån detta åldersdatum. I scenario 2 redigerar du inställningarna för scenario 1 (FIFO) och återanvänder försäljningsordern och påfyllnaden som skapades under det scenariot.

1. Innan du startar det här scenariot ställer du in och slutför det fullständiga FIFO-scenariot enligt beskrivningen i [föregående avsnitt](#fifo-demo). I det här scenariot ska du återanvända påfyllnaden och de flesta av de inställningar som har skapats för det scenariot.
1. Redigera platsdirektivet **63 plocka skapande av behållare** platsdirektivet så att det använder strategin *platsåldrande LIFO* enligt beskrivningen i den första delen i [Ställ in scenarier](#demo-set-up).

    Därefter ska du ändra påfyllnaden som skapades för försäljnings ordern i scenario 1, så att den här metoden använder strategin *platsåldrande LIFO*.

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj och öppna påfyllnad som innehåller ordern som du skapade för FIFO-scenariot.
1. I åtgärdsfönstret på fliken **Arbete** välj **Avbryt** för att avbryta arbetet som du skapade för FIFO-scenariot.
1. I Åtgärdsfönstret, på fliken **påfyllning**, i gruppen **påfyllning**, markerar du **bearbeta**.
1. När processen är slutförd, i åtgärdsfönstret på fliken **Påfyllnad** i gruppen **Relaterad information** välj **Arbete** om du vill visa det arbete som har skapats för den här påfyllnaden.
1. På sidan **Arbete** på fliken **Översikt** ska det finnas två rader. Välj raden där fältet **Arbetsstatus** är inställt på *Öppen*.
1. Observera att raden där värdet för **Arbetstyp** är *Plocka* visar ett värde för **Plats** för *FL-001*. Den här platsen innehåller det ID-nummer som har det nyaste åldersdatumet (LIFO).

I dessa fall har du sett hur positioneringsstrategin för platsen har placerats i arbete med antingen det äldsta lagret eller det senaste lagret, beroende på den valda strategin för lagerstället.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
