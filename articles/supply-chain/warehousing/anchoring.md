---
title: Förankring
description: I det här avsnittet beskrivs hur du aktiverar och använder ankare.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a17574cccbdf6f26f0453bda67eabaa16d559cd3
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505604"
---
# <a name="anchoring"></a>Förankring

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om förankringsprocess till lagerställe. Det beskriver den konfiguration som krävs och den logik som körs när en lagerarbetare ändrar antingen mellanlagringsplatsen eller inläsningsplatsen.

Med hjälp av förankringsfunktionen kan du åsidosätta mellanlagrings- eller inläsningsplatsen. Alla öppna puts skickas sedan till den nya mellanlagrings- eller inläsningsplatsen som du anger.

Den här funktionen kan hjälpa arbetare att bli mer effektiva när de levererar varor. Nedan följer några exempel:

- En arbetare som måste lägga objekt för beställning 1 på en mellanlagringsplats vid brygga 1 kan inte slutföra den här åtgärden eftersom en tidigare last inte har rensat platsen. I stället för att vänta på att mellanlagringplatsen Dock 1 blir tillgänglig, kan arbetaren välja att använda mellanlagringsplatsen för Dock 2. I det här fallet åsidosätter arbetaren den föreslagna mellanlagringsplatsen. Placeringsplatsen för alla återstående artiklar för arbete uppdateras då till mellanlagringsplatsen Docka 2.
- En arbetare som måste utföra flera plockningar för samma leverans kan vara säker på att alla placerade artiklar finns på samma plats. Därför krävs mindre tid att läsa in artiklarna i lastbilen.

Du konfigurerar ankare för mobila enheter-menyalternativ genom att använda alternativet **Ankare**. Om du anger detta alternativ till *ja*, kan du använda fältet **förankra efter** för att ange om du vill ankra med sändning eller last. Om du ställer in fältet **Förankra efter** till *Leverans*, efterföljande öppna placeringar kommer att ändras till den nya platsen för den försändelsen. Om du ställer in fältet *Last*, efterföljande öppna placeringar kommer att ändras till den nya platsen för den lasten.

> [!IMPORTANT]
> Platsen för efterföljande öppna placeringar ändras bara på arbetsraderna som genereras från samma arbetsmallrad. Med andra ord ankar systemet de placeringsrader som härstammar från samma arbetsmallrad.

Det här avsnittet innehåller ett scenario som visar hur förankring fungerar. Under scenariot skapar du uppsättningar med försäljningsorder och släpper varje uppsättning till lagerstället. Du åsidosätter sedan den föreslagna mellanlagringsplatsen och kontrollerar att allt återstående arbete med en lagerplats har dirigerats till den nya platsen.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Scenario: Göra demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på *USMF* innan du börjar.

## <a name="scenario-setup"></a>Scenarioinställningar

Innan du arbetar dig genom exempelscenariot måste du aktivera förankring för det relevanta menyalternativet för mobil enhet.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Ställa in ett menyalternativ för mobila enheter för att möjliggöra förankring

Följ de här stegen om du vill aktivera förankring för en menyartikel på en mobil enhet.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Markera posten med namnet *Försäljningsplockning* i listrutan. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta eller ställ in följande värden för posten:

    - **Menyalternativnamn:** *Försäljningsplockning*
    - **Titel:** *Försäljningsplockning*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*
    - **Styrs av:** *Användarstyrd*
    - **Förankring:** *Ja*

        Denna inställning gör att systemet förankrar flera arbetsorderrader tillsammans under försäljningsplockningen.

    - **Förankring efter:** *Last*

        Den här inställningen gör att systemet förankrar efter last.

    - **Åsidosätt målets ID-nummer:** *Ja*
    - **Åsidosätt ID-nummer vid plockning:** *Ja*
    - **Håll arbetet låst av användare:** *Ja*
    - **Tillåt överplockning:** *Ja*

### <a name="set-up-a-work-template-to-enable-staging"></a>Ställ in en arbetsmall för att aktivera mellanlagring

Följ dessa steg om du vill konfigurera en arbetsmall för att aktivera mellanlagring. Den här konfigurationen stöder scenariot där en arbetare skapar artiklar för en order på en mellanlagringsplats.

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.
1. Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.
1. I rutnätet väljer du arbetsmallen **61 SO steg**.
1. I avsnittet **Arbetsmallinformation**, se till att följande rader finns och är konfigurerade enligt bilden här:

    - Rad 1:

        - **Arbetstyp:** *plockning*
        - **Obligatorisk:** markerad (= *Ja*)
        - **Arbetsklass-ID:** *SO plockning*

    - Rad 2:

        - **Arbetstyp:** *Placera*
        - **Obligatorisk:** markerad (= *Ja*)
        - **Kod för direktiv:** *steg*
        - **Arbetsklass-ID:** *SO plockning*

    - Rad 3:

        - **Arbetstyp:** *plockning*
        - **Obligatorisk:** markerad (= *Ja*)
        - **Avsluta arbetet:** *Ja*
        - **Arbetsklass-ID:** *SO last*

    - Rad 4:

        - **Arbetstyp:** *Placera*
        - **Obligatorisk:** markerad (= *Ja*)
        - **Kod för direktiv:** *Baydoor*
        - **Arbetsklass-ID:** *SO last*

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna frågeredigeraren.
1. På fliken **Intervall** ser du till att följande rad finns:

    - **Tabell:** *Tillfälliga arbetstransaktioner*
    - **Härlett register:** *Tillfälliga arbetstransaktioner*
    - **Fält:** *lagerställe*
    - **Kriterier:** *61*

1. På fliken **Sortering** ser du till att följande rad finns:

    - **Tabell:** *Tillfälliga arbetstransaktioner*
    - **Härlett register:** *Tillfälliga arbetstransaktioner*
    - **Fält:** *leverans-ID*
    - **Sökriktning:** *Stigande*

1. Välj **OK** om du vill tillämpa dina inställningar och stänga frågeredigeraren. Acceptera ändringarna om du tillfrågas om det.
1. Klicka på **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.
1. På raden där fältet **Fältnamn** anges till *Leverans-ID*, rensa kryssrutan **Gruppera efter detta fält**.

### <a name="set-up-license-plates-locations-and-inventory"></a>Ställa in licensförkortning, platser och lager

Innan du skapar försäljningsorder och försändelser måste du se till att nödvändiga platser, licensförseningar och lager finns.

1. Gå till **Hantering av distributionslager \> Inställningar \> Distributionslager \> ID-nummer** och skapa två ID-nummer:

    - MyLP1
    - MyLP2

1. Gå till **Hantering av distributionslager \> Inställningar \> Lagerställe \> Platser** och skapa följande platser om de inte redan finns.

    | Lagerställe | Plats   | Platsprofil-ID | Zon-ID   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PICK-06             | VÅNING     |
    | 61        | 06A01R3S1B | PICK-06             | VÅNING     |
    | 61        | STAGE01    | STEG               | *(Tom)* |
    | 61        | STAGE02    | STEG               | *(Tom)* |
    | 61        | STAGE03    | STEG               | *(Tom)* |
    | 61        | STAGE04    | STEG               | *(Tom)* |

1. Kontrollera att följande lager är tillgänglig. Om du måste justera inventeringen kan du skapa manuella rörelser, använda påfyllning eller använda något annat flöde.

    | Artikelnummer | Antal | Lagerställe | Plats   | ID-nummer |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | MyLP1         |
    | A0002       | 100      | 61        | 06A01R3S1B | MyLP2         |

### <a name="create-demand"></a>Skapa efterfrågan

Innan du kan prova förankringsfunktionen måste du skapa en viss efterfrågan. För det här scenariot skapar du tre försäljningsorder för samma kund.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en första försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *61*

1. Välj **OK**.
1. Den nya försäljningsordern öppnas. Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**. Ange följande värden för den här raden:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *1*

1. På verktygsfältet, välj **Lägg till rad** för att lägga till en andra försäljningsorderrad och ställa in följande värden:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *1*

1. Följ dessa steg för varje försäljningsrad på ordern för att reservera lager för den:

    1. På snabbfliken **Försäljningsorderrader** väljer du en försäljningsorderrad.
    1. I verktygsfältet, välj **Lager \> Reservation**.
    1. På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.
    1. Klicka på **Spara** i åtgärdsfönstret.

1. Upprepa steg 2 till och med 6 om du vill skapa en andra försäljningsorder. Ange följande värden för den:

    - I dialogrutan **Skapa försäljningsorder**:

        - **Kundkonto:** *US-001*
        - **Lagerställe:** *61*

    - På försäljningsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *2*

    - På försäljningsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *2*

1. Upprepa steg 7 om du vill reservera varje rad i försäljningsorder 2.
1. Upprepa steg 2 till och med 6 om du vill skapa en tredje försäljningsorder. Ange följande värden för den:

    - I dialogrutan **Skapa försäljningsorder**:

        - **Kundkonto:** *US-001*
        - **Lagerställe:** *61*

    - På försäljningsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *3*

    - På försäljningsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *3*

1. Upprepa steg 7 om du vill reservera varje rad i försäljningsorder 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Använd workbench för lastplanering för att skapa beläggningar och släppa dem till lagerstället

Följ dessa steg för att skapa en last för order som du har skapat för scenariot och sedan släppa den till lagerstället.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. På fliken **försäljningsrader** hitta och välj alla försäljningsorderrader för försäljningsorder 1 och försäljningsorder 2.
1. I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**.
1. I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *Stnd Load Template*.
1. Välj **OK** för att stänga dialogrutan.
1. I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du skapat.
1. På verktygsfältet, välj **Frisläpp \> frisläpp till lagerställe**.
1. I dialogrutan **Släpp last till lagerställe** välj **OK** om du vill frisläppa den valda beläggningen till lagerstället.
1. Gå till **Lagerstyrning \> Arbete \> Allt arbete** för att visa det arbete som har skapats. Du bör hitta två nya arbets-ID och en för varje leverans. Varje arbets-ID har plock- och placeringsrader som tar lagret från plockplatserna till mellanlagringsplatsen och från mellanlagringsplatsen till lagerstället. Anteckna värdet för **Arbets-ID** för första leveransen eftersom du behöver det i nästa procedur.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Plockning av försäljningsorder till mellanlagringsplatsen för den första försändelsen

1. Logga in på mobilappen för Warehouse Management en arbetare i lagerställe *61*. (I standarddemodata kan du logga in med _61_ om användar-ID och _1_ om lösenord.)
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **försäljningsplockning**.
1. Markera fältet **ID** och ange sedan arbets-ID för första leveransen.
1. Bekräfta din inmatning.
1. I fältet **LP**, ange ID-nummer för första artikeln (*MyLP1*).
1. Bekräfta din inmatning.
1. I fältet **Mål-LP**, ange valfritt nummer (registreringsskylten behöver inte existera redan).

    Du ska välja alla rader som har skapats från den bearbetade påfyllnaden på samma målnummer-ID.

1. Bekräfta din inmatning.
1. I fältet **LP**, ange ID-nummer för andra artikeln (*MyLP2*).
1. Bekräfta din inmatning.

    Tänk dig att arbetaren nu har samlat in ordern, men när de kommer till den mellanlagringsplats som anges i arbetet, tycker de att utrymmet redan är upptaget. Arbetaren kan dock se att en annan närliggande plats (*STAGE03*) är tillgänglig. Därför begär de att mellanlagringsplatsen ska ändras. Eftersom förankringsfunktionen är aktiverad uppdateras mellanlagringsplatsen automatiskt för det här och allt relaterat arbete.

1. Välj **Åsidosätt plats** om du vill åsidosätta den föreslagna mellanlagringsplatsen.
1. I fältet **Arbetsundantag**, ange *Mellanlagringsfältet ändrat*.
1. I fältet **Plats**, ange en mellanlagringsplats (*STAGE03*).
1. Bekräfta din inmatning. Du får ett meddelande arbetet är slutfört.
1. Gå till **Lagerstyrning \> Arbete\> Allt arbete**.
1. Öppna arbets-ID för den första försändelsen. Kontrollera att mellanlagringsplatsen har uppdaterats till den nya platsen (*STAGE03*) som har definierats med den mobila enheten.
1. Öppna arbets-ID för den andra försändelsen. Kontrollera att mellanlagringsplatsen har uppdaterats till ny mellanlagringsplats (*STAGE03*) på grund av förankringsinställningen.

> [!NOTE]
> Platsen för alla återstående öppna arbetsrader som har samma mellanlagringsplats och som genererats från samma arbetsmallrad uppdateras till den nya platsen.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Använd workbench för lastplanering för att lägga till den nya försäljningsordern i den befintliga beläggningen

Följ dessa steg om du vill lägga till en order i inläsningen och sedan frisläppa den till lagerstället.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. På fliken **försäljningsrader** hitta och välj alla försäljningsorderrader för försäljningsorder 3.
1. I åtgärdsfönstret väljer du fliken **tillgång och efterfrågan** i gruppen **Lägg till**, välj **Till befintlig last** för att lägga till de valda orderraderna till en befintlig last.
1. Välj **OK** för att stänga dialogrutan.
1. I avsnittet **Beläggningar** söker du upp samt väljer last från de föregående stegen.
1. Välj **Frisläpp \> frisläpp till lagerställe**.
1. I dialogrutan **Släpp last till lagerställe** välj **OK** om du vill frisläppa den valda beläggningen till lagerstället.
1. Gå till **Lagerstyrning \> Arbete \> Allt arbete** för att visa det arbete som har skapats. Anteckna värdet för **Arbets-ID** eftersom du behöver det i nästa procedur.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Plockning av försäljningsorder till mellanlagringsplatsen för den tredje försändelsen

1. Logga in på den mobila appen som en arbetare i lagerställe *61*.
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **försäljningsplockning**.
1. Markera fältet **ID** och ange sedan arbets-ID för tredje leveransen.
1. Bekräfta din inmatning.
1. I fältet **LP**, ange ID-nummer för första artikeln (*MyLP1*).
1. Bekräfta din inmatning.
1. I fältet **Mål-LP**, ange valfritt nummer (registreringsskylten behöver inte existera redan).
1. Bekräfta din inmatning.
1. I fältet **LP**, ange ID-nummer för andra artikeln (*MyLP2*).
1. Bekräfta din inmatning.

    Vad gäller den första lasten, tänk dig att arbetaren tycker att den angivna mellanlagringsplatsen inte är tillgänglig. Därför vill de använda en annan mellanlagringsplats (*STAGE04*).

1. Välj **Åsidosätt plats** om du vill åsidosätta den föreslagna mellanlagringsplatsen.
1. I fältet **Arbetsundantag**, ange *Mellanlagringsfältet ändrat*.
1. I fältet **Plats**, ange en mellanlagringsplats (*STAGE04*).
1. Bekräfta din inmatning. Du får ett meddelande arbetet är slutfört.
1. Gå till **Lagerstyrning \> Arbete\> Allt arbete**.
1. Öppna arbets-ID för den första försändelsen. Kontrollera att iscensättningsplatsen inte har uppdaterats till den nya mellanlagringsplatsen (*STAGE04*) eftersom den återstående öppna placeringsraden inte motsvarar arbetsmallraden för den färdiga placeringsrad.
1. Öppna arbets-ID för den andra försändelsen. Kontrollera att iscensättningsplatsen inte har uppdaterats till den nya mellanlagringsplatsen (*STAGE04*) eftersom mellanlagringsplatsen inte motsvarar uppställningsplatsen för den färdiga placeringsraden. Med andra ord har den färdiga placera arbetsrader och den återstående öppna arbetsraden olika mellanlagringsplatser och i detta fall uppdateras endast rader som har samma mellanlagringsplatser.
1. Öppna arbets-ID för den tredje försändelsen. Kontrollera att mellanlagringsplatsen har uppdaterats till ny mellanlagringsplats (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
