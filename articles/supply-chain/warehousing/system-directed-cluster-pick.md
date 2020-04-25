---
title: Systemdirigerad klusterplockning
description: Det här avsnittet innehåller en översikt över systemstyrd klusterplockning i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 390e0a3379a6482e99a13f4f7835b5264e3747ac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217251"
---
# <a name="system-directed-cluster-picking"></a>Systemdirigerad klusterplockning

[!include [banner](../includes/banner.md)]

Klusterplockning är en del plockningsprocess som låter dig plocka artiklar för flera order samtidigt genom att klustra dem i plockningskluster. Du måste sedan besöka plockplatsen bara en gång. Den här funktionen används vanligtvis med små orderplockning eller kvantiteter som är mindre än antalet fall.

När Systemstyrd klusterplockning har ställts in kan du klusterplocka arbetshuvuden baserat på ett systemgenererat kluster. Systemet klusterplockar order upp till antalet befattningar som anges i klusterprofilen. Därför kan du plocka flera order samtidigt utan att manuellt skapa ett kluster.

Systemstyrd klusterplockning erbjuder ett alternativ till manuell klusteruppbyggnad, där en klusterprofil används för att skapa ett kluster. Flera installationsrelaterade rader måste definieras i klusterprofilen innan de används:

- **Antal positioner** motsvarar antalet order som ska placeras i ett kluster. Därför motsvarar antalet last.
- **Bryt kluster** avgör när klustret ska brytas.
- **Generera kluster-ID** styr om kluster-ID kommer att genereras av systemet eller anges av användaren.
- **Sortera verifieringstyp** avgör om positionsverifiering krävs.

Ett nytt menyalternativ för mobila enheter används för systemstyrd klusterplockning. Klusterprofil-ID måste anges för alternativet **dirigerad av**. Dessutom kan den systeminriktade frågeordningen gruppera order, baserat på företagsspecifika kriterier. Därför kan du ytterligare optimera tilldelningen av arbetsorder genom att ange anpassade sorteringskriterier på den systeminriktade frågeordningen.

När systemstyrd klusterplockning görs, visas lagerarbetare med ett kluster där plockorder har förtilldelats till klusterbefattningar. Därför kan arbetstagarna börja plocka en artikel för flera arbetsorder genom att besöka plockplatsen bara en gång. Plockningsprocessen för systemstyrd klusterplockning är densamma som processen för användarstyrd klusterplockning.

## <a name="set-up-system-directed-cluster-picking"></a>Ställ in systemdirigerad klusterplockning

### <a name="create-cluster-profiles"></a>Skapa klusterprofiler

Klusterprofiler styr hur systemet skapar varje kluster. Om det krävs olika kluster bör en annan klusterprofil skapas för varje menyalternativ för mobila enheter.

1. Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.
2. Välj **Ny**.
3. I fältet **Klusterprofil-ID** ange **2 position**.
4. Skriv **2 position** i fältet **Namn**.
5. På snabbfliken **Allmänt** ange följande fält:

    - **Generera kluster-ID** : Ange det här alternativet **Ja**. Det här alternativet avgör om kluster-ID skapas automatiskt av systemet eller om användaren ska skapa den i början av plockning.
    - **Aktivera positioner:** ange det här alternativet till **Ja**. Det här alternativet avgör om positionsnamnen genereras automatiskt baserat på inställningen av positionsnamn. Om den här alternativet är inställt på **Nej** används registreringsskylt-ID för positionen.
    - **Antal positioner:** Ange **2**. Det här fältet bestämmer det maximala antalet positioner som klustret kan ha (det vill, det maximala antalet rutor, laster och så vidare).
    - **Positionsnamn:** Välj **numeriskt**, så att befattningar namnges med hjälp av kontinuerliga tal. Om du väljer **alfabetiskt** namnges positionerna i alfabetisk ordning.
    - **Bryt kluster på:** Välj **placera**. Det här fältet avgör när klustret bryts.
    - **Sortera verifieringstyp:** Välj **positionsskanning**. Det här fältet bestämmer om sätta i position-steget verifieras.

6. På snabbfliken **klustersortering** kan du definiera sorteringskriterier genom att skapa en ny rad och ange följande fält:

    - **Sekvensnummer:** det här fältet bestämmer sekvensen som systemet sorterar efter. Ett värde anges automatiskt, men du kan ändra det som du behöver.
    - **Fältnamn:** välj **WMSLocationId**. Det här fältet bestämmer det fält som raden använder för sorteringskriterier.
    - **Sortering:** Välj **stigande**. Det här fältet anger om sorteringen görs i stigande eller fallande ordning.

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

Gör så här om du vill skapa ett nytt menyalternativ för mobila enheter för systemstyrd klusterplockning och länka klusterprofil-ID till menyalternativet mobil enhet.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
2. Välj **Ny**.
3. I fältet **menyalternativnamn** anger du ett **SD-kluster**.
4. I fältet **Titel** ange **SD-kluster**.
5. Välj **Arbete** i fältet **Läge**.
6. Ange alternativet **Använd befintligt arbete** till **Ja**.
7. På snabbfliken **Allmänt** ange följande fält:

    - **Dirigerad av:** Välj **Systemdirigerad**.
    - **Generera registreringsskylt** : Ange det här alternativet **Ja**.
    - **Klusterprofil-ID:** Välj **2 position**.

8. På snabbfliken **arbetsklasser** ställer du in den giltiga arbetsklassen för den här mobila enhetens menyalternativ genom att ange följande fält:

    - **Arbetsklass-ID**: kontrollera att **försäljning** har angetts.
    - **Typ av arbetsorder**: kontrollera att **försäljningsorder** har angetts.

9. Gör så här om du vill ange en ny systemstyrd arbetssekvensfråga:

    1. Välj **Ny**.
    2. I fältet **Sekvensnummer**, ange **1**.
    3. I fältet **Beskrivning** väljer du **Arbetsprioritet – arbets-ID**.

10. Välj på menyn **redigera fråga**.
11. Ange något av följande fält på fliken **Sortering**:

    - **Register:** Välj **Arbete**.
    - **Härlett register:** Välj **Arbete**.
    - **Fält:** Välj **arbetsprioritet**.
    - **Sökriktningarna:** Välj **Stigande**.
    - **Register:** Välj **Arbete**.
    - **Härlett register:** Välj **Arbete**.
    - **Fält:** Välj **arbets-ID**.
    - **Sökriktningarna:** Välj **Stigande**.

Systemet sorterar nu arbets-ID:n i klustret, först efter arbetsprioritet och sedan efter arbets-ID.

### <a name="set-up-a-mobile-device-menu"></a>Ställ in mobil enhet för lagerställe

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
2. Lägg till menyalternativet som du nyss skapade i önskad meny.

## <a name="example"></a>Exempel

### <a name="create-picking-work"></a>Skapa plockarbete

Innan du kan ställa in systemstyrd klusterplockning måste du skapa vissa kvalificerade utgående arbete. Den klusterprofil som du skapade tidigare anger två klusterpositioner. Därför måste du skapa minst två arbets-ID.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Skapa en försäljningsorder genom att välja **Ny**.
3. Markera en kund i fältet **Kundkonto**.
4. På snabbfliken **Allmänt** i fältet **Lagerställe**, välj lagerställe **62**.
5. Välj **OK**.
6. På snabbfliken **Försäljningsorderrader** välj **Lägg till rad**.
7. I fältet **Artikelnummer**, välj **A0001**.
8. I fältet **Kvantitet**, ange **1**.
9. Välj **Lägg till rad** för att lägga till en andra rad.
10. I fältet **Artikelnummer**, välj **A0002**.
11. I fältet **Kvantitet**, ange **3**.
12. Upprepa sedan steg 2 till och med 6.
13. I fältet **Artikelnummer**, välj **A0001**.
14. I fältet **Kvantitet**, ange **4**.
15. Välj **Lägg till rad** för att lägga till en andra rad.
16. I fältet **Artikelnummer**, välj **A0002**.
17. I fältet **Kvantitet**, ange **2**.

Reservera lagret och släpp det till lagerställe. Två olika arbets-ID skapas. Varje arbets-ID har två plockningsrader.

### <a name="run-the-mobile-device-flow"></a>Kör det mobila enhetsflödet

1. På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet.
2. Välj menyalternativet **SD-kluster** och initiera plockningen. Ett kluster skapas och de två arbets-ID:n som du skapade tidigare är kopplade till den. Om du har skapat fler än två arbets-ID:n läggs bara de första två till i klustret. Observera att arbets-ID:n läggs till i klustret i stigande ordning, som du angav i frågeinstallationen.

    > [!NOTE]
    > Det nya klustret skapas automatiskt endast om tillräckligt med ytterligare arbets-ID har skapats tidigare. I annat fall visas följande meddelande: "det går inte att hitta tillräckligt med arbete för klustret."

    När du har valt menyn visas den första plockskärmen. Systemet sammanställer alla matchande plockningsrader från de två arbets-ID:n och dirigerar dig att besöka plockplatsen en gång, så att du kan tillfredsställa båda ordrarna genom att använda en plockning. Den här processen görs på samma sätt som process för användarstyrd klusterplockning.

3. Bekräfta den första plockningen. Du måste sedan ange positionsnamnet för att bekräfta att artiklarna har satts till rätt position.
4. Upprepa den här processen tills alla objekt har plockats och satts till rätt position.
5. Det sista steget på den mobila enheten är att placera klustret till den sista platsen. När den här placeringsoperationen bekräftas stängs klustret och bryts, baserat på det värde som du anger för fältet **Bryt kluster vid** i klusterprofilen. Arbets-ID:n är också stängda.
6. Ett meddelande om att "klustret har slutförts" visas på den mobila enheten.
