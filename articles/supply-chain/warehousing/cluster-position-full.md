---
title: Klusterposition full
description: Det här ämnet innehåller information om funktionen klusterposition. Den här funktionen erbjuder ett alternativ till en striktare tillämpning av regler för arbetsavbrott när klusterplockning används, eftersom det möjliggör en större felmarginal i volymetriska begränsningar för behållare eller last.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9c90380cb5d109e331a2552ba779525b66d10fa6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001109"
---
# <a name="cluster-position-full"></a>Klusterposition full

[!include [banner](../includes/banner.md)]

Funktionen *Klusterposition full* erbjuder ett alternativ till en striktare tillämpning av regler för arbetsavbrott när klusterplockning används, eftersom det möjliggör en större felmarginal i volymetriska begränsningar för behållare eller last. I ett vanligt scenario ryms inte alla objekt på en arbetsorder i en vald behållare. Lagerarbetare som är klusterplockning har få alternativ i det här scenariot: de måste antingen byta till en större behållare eller arbeta med deras arbetsledare för att komma in i en annan lösning.

Med den här funktionen kan du köra knappen **Full** på en av arbetsenheterna i ett kluster. I äldre versioner är det här alternativet bara tillgängligt för plockning med vanlig order, inte för klusterplockning. Den här funktionen skiljer sig emellertid från standardknappen **full** för alla på så vis att den avbryter det återstående arbetet. Det föreslår inte att användaren lägger till en annan lagerplats i samma kluster och det nya arbetet skapas inte automatiskt.

## <a name="turn-on-the-cluster-position-full-feature"></a>Aktivera funktionen för klusterposition full

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Klusterposition full*

## <a name="setup"></a>Ställ in

Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du ställer in och använder funktion *Klusterposition full*.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda exempelscenariot som vägledning för att arbeta med den här funktionen i ett produktionssystem. I så fall måste du dock ersätta dina egna värden för varje inställning som beskrivs här.

### <a name="cluster-profiles"></a>Klusterprofiler

Du måste ange om kluster-ID ska genereras automatiskt, hur många positioner som används, när kluster bryts och hur plockningsarbetet sekvenseras och verifieras.

1. Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.
1. I listfönstret, välj **Skapa kluster**.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Generera kluster-ID:** *Ja*
    - **Aktivera positioner:** *Ja*
    - **Antal positioner:** *2*
    - **Positionsnamn:** *numerisk*
    - **Bryt kluster på:** *placera*
    - **Sortera verifieringstyp:** *positionsskanning*

1. På snabbfliken **klustersortering**. Rutnätet bör vara tomt (dvs inte ha några rader).

### <a name="work-templates"></a>Arbetsmallar

Du måste definiera hur plockningsarbetet för klusterplockning skapas.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ställ in knappen högst upp på sidan **arbetsordertyp** till *försäljningsorder*.
1. Se till att följande arbetsmallar från demonstrationsdata visas i listan. Om de inte är tillgängliga kan du inte slutföra scenariot.

    - 61 SO steg
    - 61 SO klusterplockning

### <a name="location-directives"></a>Platsdirektiv

Du måste ange var artiklar plockas från och var de placeras.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I listrubriken, ange **Inköpsorder** i fältet till *Försäljningsorder*.
1. Se till att följande försäljningsorderdirektiv från demonstrationsdata visas i listan. Om de inte är tillgängliga kan du inte slutföra scenariot.

    - 61 klusterplockning
    - 61 SO välj order

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

Du måste konfigurera ett menyalternativ för mobila enheter för att använda befintligt arbete som dirigeras av klusterplockning. I menyalternativet för mobila enheter för klusterplockning måste parametern **Tillåt delning av arbete** vara aktiverad och arbetsklassen *SO plocka* måste läggas till.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I listfönstret, välj **Skapa klusterplockning**.
1. Välj **Redigera** i åtgärdsfönstret.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Dirigerad av:** *klusterplockning*
    - **Generera ID-nummer:** *Ja*
    - **Tillåt delning av arbete:** *Ja*
    - **Kluster profil-ID:** *skapa kluster*

    Acceptera standardvärden för alla andra fält.

1. På snabbfliken **Arbetsklasser** lägger du till följande två rader, om det behövs:

    - Rad 1 (förekommer vanligen i demonstrationsdata):

        - **Arbetsklass-ID:** *Försäljning* 
        - **Typ av arbetsorder:** *försäljningsorder*

    - Rad 2 (förekommer förmodligen inte i demonstrationsdata):

        - **Arbetsklass-ID:** *SO plockning*
        - **Typ av arbetsorder:** *försäljningsorder*

1. Gå till **Inställningar för arbetsbekräftelse** i åtgärdsfönstret.
1. Välj **Redigera**.
1. Ange följande värden på raden i rutnätet.
    - **Arbetstyp** - *plockning*
    - **Produktbekräftelse** - *Markera kryssrutan*

1. Välj **Spara** i åtgärdsfönstret och stäng sidan.

## <a name="create-picking-work"></a>Skapa plockarbete

Innan du kan starta klusterplockning måste du skapa ett visst utgående arbete. Den klusterprofil som du skapade tidigare anger två klusterpositioner. Därför måste minst två arbets-ID skapas för plockning av försäljningsorder. I det här scenariot inträffar transaktionerna i lagerställe *61* och de använder artiklarna *L0101* och *T0100*. Demonstrationsdata bör ha tillräcklig lagerbehållning av dessa artiklar. Kontrollera att det finns tillräckligt med lager för att slutföra transaktionerna.

### <a name="create-sales-order-1"></a>Skapa försäljningsorder 1

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa försäljningsorder 1 genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-010*
    - **Lagerställe:** *61*

1. Välj **OK**.
1. Den nya försäljningsordern öppnas. På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:

    - **Artikelnummer:** *T0100*
    - **Kvantitet:** *5*

1. På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.
1. På snabbfliken **försäljningsorderrader** lägger du till en andra rad som har följande inställningar:

    - **Artikelnummer:** *L0101*
    - **Kvantitet:** *20*

1. På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.
1. För varje rad som du just har lagt till följer du stegen nedan för att reservera lagret:

    1. Välj den rad som du vill reservera.
    2. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
    3. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
    4. Stäng sidan **Reservation**.

1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    När släppningen är klar får du informationsmeddelanden som visar påfyllnads- och last-ID som skapades.

### <a name="create-sales-order-2"></a>Skapa försäljningsorder 2

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa försäljningsorder 2 genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-011*
    - **Lagerställe:** *61*

1. Välj **OK**.
1. Den nya försäljningsordern öppnas. På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:

    - **Artikelnummer:** *L0101*
    - **Kvantitet:** *20*

1. På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.
1. På snabbfliken **försäljningsorderrader** lägger du till en andra rad som har följande inställningar:

    - **Artikelnummer:** *T0100*
    - **Kvantitet:** *2*

1. På snabbfliken **Radinformation** på fliken **Leverans** ange fältet **Bekräftat leveransdatum** till dagens datum.
1. För varje rad som du just har lagt till följer du stegen nedan för att reservera lagret:

    1. Välj den rad som du vill reservera.
    2. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
    3. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
    4. Stäng sidan **Reservation**.

1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    När släppningen är klar får du informationsmeddelanden som visar påfyllnads- och last-ID som skapades.

### <a name="get-work-ids-and-license-plate-numbers"></a>Hämta arbets-ID och ID-nummer

Två arbets-ID ska ha skapats, där alla har två plockningsrader. Följ dessa steg för att hitta arbets-ID:n och tilldelningarna av ID-nummer.

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. I rutnätet **översikt** söker du i kolumnen **Ordernummer** efter de två försäljningsorder som du just har skapat. Anteckna motsvarande arbets-ID för varje försäljningsorder.
1. Markera raden för varje försäljningsorder om du vill visa relaterad information i rutnätet **rader**. Anteckna platsen som varje artikel ska plockas från.
1. Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.
1. I åtgärdsfönstret välj **Dimensioner** om du vill öppna dialogrutan **Dimensionsvisning**.
1. Kontrollera att kryssrutorna **ID-nummer**, **Lagerställe** och **Artikelnummer** är markerade och välj sedan **OK**.
1. I rutan **Filter** ange följande filter:

    - **Artikelnummer** – **är ett av** – *L0101* och *T100*
    - **Lagerställe** – **börjar med** – *61*

1. Anteckna vilket värde **ID-numret** visar.

## <a name="example-scenario"></a><a name="example-scenario"></a>Exempelscenario

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Flödeskörning av mobila enheter – arbetsbekräftelse inställningar för produkten

1. Logga in på distributionslagerappen en användare i lager ställe *61*.
1. Gå till **utgående \> Skapa klusterplockning**.

    Sidan **UPPGIFT: tilldela arbete till kluster** visas.

1. Ange arbets-ID för försäljningsorder 1 om du vill tilldela det till klusterposition 1.
1. Välj **OK** (kryssmarkeringssymbol).
1. Ange arbets-ID för försäljningsorder 2 om du vill tilldela det till klusterposition 2.
1. Välj **OK** (kryssmarkeringssymbol).

    Sidan **UPPGIFT: Skapa klusterplockning: plockning** visas och visar *objekt L0101 2 PL*.

Eftersom klusterprofilen ställer in antalet positioner till 2, dirigerar systemet automatiskt till den första konsolideringsplockningen: två lastpallar (PL) för artikel *L0101*.

Du kan när som helst under följande steg välja fliken **Detaljer** vill visa ytterligare information om uppgiften, t.ex. plockningsplatsen.

1. Ange fältet **ITEM** till *L0101*. Detta bekräftar artikelnumret, vilket krävs för det här menyalternativet (du har konfigurerat det tidigare genom att välja **Inställningar för arbetsbekräftelse** på sidan **menyalternativ för mobila enheter** när du skapade menyalternativet).
1. Ange det ID-nummer som är kopplat till artikeln på det lagerställe som plockas. Du ska plocka två lastpallar.
1. Ange fältet **LP** till *LP\_PICK\_01*.
1. Välj **OK** (kryssmarkeringssymbol).

    Sidan **UPPGIFT: sortera: skapa plockningsklustret** visas. Här kan du sortera de två plockade lastpallarna på en plockposition. Den här befattningen kan vara en last eller en behållare som används för att separera det plockade lagret efter försäljningsorder.

1. Visa de detaljer som visas för artikeln (*L0101*) och kvantiteten (*20* ea) som ska sorteras i position 1 (för försäljningsorder 1).
1. Ställ in fältet **POSITION NA** till *1*.
1. Välj **OK** (kryssmarkeringssymbol).
1. Visa de detaljer som visas för artikeln (*L0101*) och kvantiteten (*20* ea) som ska sorteras i position 2 (för försäljningsorder 2).
1. Ställ in fältet **POSITION NA** till *2*.
1. Välj **OK** (kryssmarkeringssymbol).

    Sidan **UPPGIFT: Skapa klusterplockning: plockning** visas och visar *objekt T0100 7 ea*.

I det här scenariot kan position 1 inte acceptera hela kvantiteten av artiklar som måste plockas för att uppfylla försäljningsorder 1. En position måste markeras som full. I det här scenariot ska du utföra en delvis plockning av den andra artikeln. Den andra artikeln plockas delvis för position 1 och nytt arbete skapas för att plocka den resterande kvantiteten för att uppfylla ordern.

1. Välj Meny-knappen (kallas ibland hamburger eller knappen hamburger) och välj sedan **Position full**.
1. Identifiera den befattning som är full och välj *1*.
1. Välj **OK** (kryssmarkeringssymbol).
1. Ange den plockningskvantitet som kan fortfarande plockas på position 1. Systemet kan bestämma vilket artikelnummer som plockas.
1. Ange *2*.
1. Välj **OK** (kryssmarkeringssymbol).
1. Bekräfta artikelnumret för att slutföra plockningen av den återstående artikeln på position 2.
1. Ange fältet **ITEM** till *T0100*.
1. Välj **OK** (kryssmarkeringssymbol).
1. Ange det ID-nummer som artikeln plockas från genom att ställa in fältet **LP** på *LPREPL04* .
1. Välj **OK** (kryssmarkeringssymbol).
1. Visa de detaljer som visas för artikeln (*T0100*) och kvantiteten (*2* ea) som ska sorteras i position 2 (för försäljningsorder 2).
1. Ställ in fältet **POSITION NA** till *2*.
1. Välj **OK** (kryssmarkeringssymbol).
1. Visa de detaljer som visas för artikeln (*T0100*) och kvantiteten (*2* ea) som ska sorteras i position 1 (för försäljningsorder 1).
1. Ställ in fältet **POSITION NA** till *1*.
1. Välj **OK** (kryssmarkeringssymbol).

    Sidan **UPPGIFT: skapa plockningsklustret: placera** visas.

I det här scenariot har klusterplockningen slutförts och användaren måste föra in de plockade artiklarna från position 1 och position 2 till mellanlagringsplatsen *STAGE01* .

1. Granska informationen på sidan. Det visar att en total kvantitet på *44* kommer att placeras på mellanlagringsplatsen.
1. Välj **OK** (kryssmarkeringssymbol).

    Du får ett meddelande att "klustret är slutfört".

Nu kan du använda **försäljningsplockning** för att plocka den resterande kvantiteten. Du kan sedan använda menyobjektet **försäljningslast** för att flytta artiklarna från mellanlagringsplatsen till lastkaj.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]