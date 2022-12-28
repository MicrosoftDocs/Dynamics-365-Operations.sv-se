---
title: Medvetenhet mellan funktionen redovisningskvittning före årsbokslutet
description: I den här artikeln förklaras hur du använder funktionen Medvetenheten mellan redovisningskvittningar innan årsbokslutprocessen körs.
author: kweekley
ms.date: 12/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832180"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Medvetenhet mellan funktionen redovisningskvittning före årsbokslut

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Förbereda för funktionen redovisningskvittning före årsbokslut

En större ändring av funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen **Medvetenhet**) är att redovisningskvittning inte kan göras över räkenskapsår. Denna begränsning under flera år är endast relevant för redovisningskvittning, inte för kvittningar i kundreskontra eller leverantörsreskontra.

Innan funktionen **Medvetenhet** aktiveras får det räkenskapsår som genomgår årsbokslut inte ha några redovisningstransaktioner som kvittas över räkenskapsår. Alla transaktioner som har bokförts på räkenskapsåret som du kör årsbokslutet för måste specifikt tas bort från transaktioner som har bokförts till ett annat räkenskapsår. Transaktionerna kan sedan kvittas på nytt mot transaktioner inom samma räkenskapsår.

I den här artikeln beskrivs vilka steg som krävs för att identifiera, oreglera och åter kvitta redovisningstransaktioner som kvittas över räkenskapsår. I det exempel som ges har räkenskapsåret 2021 stängts och du förbereder att köra årsbokslut för räkenskapsåret 2022.

## <a name="example-setup"></a>Exempel på konfiguration

I bilden nedan visas de transaktioner som bokförts för huvudkonto 110190. Redovisningstransaktionerna i grönt kvittas under samma räkenskapsår och behöver inte ändras. Transaktionerna i rött kvittas i redovisningen, men de har transaktionsdatum i olika räkenskapsår. Dessa transaktioner måste identifieras, och redovisningskvittning måste kanske återföras.

![Redovisningstransaktioner.](./media/YEC1.png)

## <a name="example"></a>Exempel

Följ dessa steg om din organisation vill använda funktionen **Medvetenhet** innan årsbokslutet för räkenskapsåret 2022 körs.

> [!NOTE]
> Årsbokslut för 2021 och tidigare räkenskapsår måste endast köras igen om nya transaktioner bokförs på räkenskapsåret 2021 eller tidigare. När du slutför följande procedur bokförs inga nya transaktioner till 2021. Årsbokslutsprocessen måste inte köras om.
>
> Redovisningstransaktioner som kvittas över räkenskapsår kan förbli redovisningsreglerade om de inte kvittas mot en transaktion som bokfördes in 2022 eller senare. Om du till exempel har kvittat transaktioner över 2019 och 2020 kan de fortsätta att kvittas.

1. Valfritt: Aktivera funktionen **Medvetenhet** .

    - Om du väljer att aktivera funktionen måste du inaktivera den senare, enligt vad som anges. Fördelen med att aktivera funktionen nu är att du tillfälligt hindrar användarna från att kvitta redovisningstransaktioner som har bokförts i olika räkenskapsår.
    - Om du väljer att inte aktivera funktionen rekommenderar vi att du ber teamet att inte kvitta transaktioner över räkenskapsår. Om kvittning per år sker efter det att följande steg har slutförts, måste du upprepa stegen för att identifiera och oreglera redovisningstransaktionerna.

2. På sidan **Redovisningskvittning** identifierar du summan av alla transaktioner som kvittas över räkenskapsåren 2021 och 2022.

    1. Ange ett datumintervall för hela räkenskapsåret 2021. Ange till exempel 1 januari 2021 till 31 december 2021 om du använder ett kalenderår som räkenskapsår.

        Om funktionen **Medvetenheten** är aktiverad får du en varning om att transaktionerna inte kan kvittas eller oregleras för ett stängt räkenskapsår. Varningsmeddelandet är inte relevant eftersom kvittningar eller oreglerade sker i det här steget.

    2. I fältet **Status**, välj **Kvittad**.
    3. Filtrera på ett redovisningskonto åt gången.

        - Du måste upprepa de här stegen för varje redovisningskonto som redovisningskvittning sker för.
        - Om andra redovisningskonton inte längre är inställda för redovisningskvittning måste du tillfälligt lägga till dem igen i inställningen för redovisningskvittning. Slutför sedan dessa steg om dessa redovisningskonton har transaktioner under 2022 som kvittas mot transaktioner under ett annat räkenskapsår.

    4. Välj och håll ned (eller högerklicka) i kolumnen **Status** och välj för att gruppera denna kolumn.
    5. Välj och håll ned (eller högerklicka) i kolumnen **Belopp i transaktionsvaluta** och välj för att gruppera hela kolumn.

        - Om du kvittar transaktioner bara i 2021 blir summan 0 (noll).
        - Om du har transaktioner som kvittats över räkenskapsår blir summan inte 0 (noll).

        I bilden nedan finns ett saldo på 525,00 $. Detta saldo är summan av de transaktioner som kvittats mot transaktioner för ett annat räkenskapsår. Summan kan inkludera transaktioner som har kvittats mellan 2021 och 2022 och transaktioner som har kvittats mellan 2022 och 2023.

        ![Redovisningstransaktioner 2021–2022.](./media/YEC2.png)

    6. Identifiera vilka transaktioner som kvittades mellan 2020 och 2021 genom ytterligare filtrering av värdet för **kvittningsdatum** . Ange ett datumintervallfilter för 1 januari 2021 till och med 31 december 2021. Inga transaktioner visas eftersom inga 2020-transaktioner kvittades mot transaktioner som bokfördes till 2021.
    7. Identifiera vilka transaktioner som kvittades mellan 2021 och 2022 genom att ändra datumfilter för värdet **kvittningsdatum** . Ange ett datumintervallfilter för 1 januari 2022 till och med 31 december 2022. Transaktionerna visas igen och summan är 525,00 $ eftersom alla transaktioner kvittades mellan 2021 och 2022.

3. På sidan **Redovisningskvittning** identifierar du summan av alla transaktioner som kvittas över räkenskapsåren 2021 och 2022.

    1. Ange ett datumintervall för hela räkenskapsåret 2022. Ange till exempel 1 januari 2022 till 31 december 2022 om du använder ett kalenderår som räkenskapsår.
    2. I fältet **Status**, välj **Kvittad**.
    3. Filtrera på ett redovisningskonto åt gången.
    4. Välj och håll ned (eller högerklicka) i kolumnen **Status** och välj för att gruppera denna kolumn.
    5. Välj och håll ned (eller högerklicka) i kolumnen **Belopp i transaktionsvaluta** och välj för att gruppera hela kolumn.

        ![Totala belopp för redovisningstransaktion.](./media/YEC3.png)

    6. Lägg till ett ytterligare filter på värdet för **Kvittningsdatum** . Ange ett datumintervallfilter för 1 januari 2022 till och med 31 december 2022. Samma totalsumma på 525,00 $ visas. Resultatet validerar att det totala beloppet för transaktioner som kvittas mellan 2021 och 2022 är 525,00 $.

        ![Redovisningstransaktioner för kvittningsdatum 2022 och 2023.](./media/YEC4.png)

    7. Ändra ytterligare filter på värdet för **Kvittningsdatum** . Ange ett datumintervallfilter för 1 januari 2023 till och med 31 december 2023. En ny summa 700 $ visas. Den här summan är det totala beloppet för transaktionerna som kvittades mellan 2022 och 2023.
 
4. Upprepa steg 3 för räkenskapsåret 2023. Summan ska matcha summan 700 $ från 2022 eftersom inga 2023-transaktioner kvittades mot 2024-transaktioner.
5. Om du aktiverar funktionen **Medvetenhet** i steg 1 måste du inaktivera den innan du går vidare till steg 6. I nästa steg återför du den redovisningskvittning som passerat räkenskapsår. Om funktionen **Medvetenhet** är aktiverad kan redovisningskvittning inte återföras för räkenskapsåret 2021. Därför måste du inaktivera funktionen innan du fortsätter.
6. När funktionen **Medvetenheten** har inaktiverats använder du samma filter på sidan **Redovisningkvittning** för att återföra redovisningskvittningen för de detaljerade transaktionerna.

    1. Gå tillbaka till sidan **Redovisningskvittning** och filtrera transaktionsdatum för 2021. Lägg till ett ytterligare filter på värdet för **Kvittningsdatum** . Ange ett datumintervallfilter från 1 januari 2022 till och med 31 december 2022. Sök sedan efter de detaljerade transaktioner som utgör 525 $ totalsumman. Det är inte enkelt att filtrera den här informationen. Du kanske måste skicka data till Microsoft Excel för att utvärdera dem.
    2. När du har listat transaktioner väljer du redovisningstransaktionerna på sidan **Redovisningkvittning** och markerar **Markera markerad**. Du behöver inte se båda förkontran av redovisningstransaktionerna som kvittades. Om du markerar antingen debet eller kredit, allt som har samma värde för **kvittnings-ID** att återföras även om värdet **markerat belopp** inte var **0** (noll).
    3. Välj **Återför markerade transaktioner** för att oreglera transaktionerna.

    ![Återför markerade transaktioner.](./media/YEC5.png)

7. Upprepa steg 6 om du vill återföra kvittningen för de transaktioner som kvittats mellan 2022 och 2023.

    ![Återför redovisningstransaktioner.](./media/YEC6.png)

8. Bokför en justerad allmän journal så att den ingående balansen för 2022 delas upp i två belopp: den andel som kvittas mot transaktionen för räkenskapsåret 2021 och den del som ännu inte kvittats 2022.

    - **Andel av den ingående balansen som kvittas mot föregående år:** Det första beloppet 525 $ baserat på de summor som hittades som kvittades mellan 2021 och 2022.
    - **Del av den ingående balansen som inte kvittas mot föregående år:** Det andra beloppet är differensen mellan den ingående balansen och det kvittade 525 $. Resterande belopp är 1025 $ – 525 $= 500 $.

    På det här sättet kan du kvitta 2022-transaktionerna mot den 525 $ som ursprungligen kvittas mot 2021-transaktionen. Det här steget är bara nödvändigt eftersom redovisningskvittning inte tillåter delvis kvittning.

    1. Gå till den allmänna journalen och bokför justeringen. Din organisation måste bestämma vilket transaktionsdatum som ska användas, baserat på de perioder som är öppna. Dessa transaktioner kan ha kvittats med ett kvittningsdatum från januari eller februari 2022, men justeringen kan behöva bokföras i december om det bara är den öppna perioden.
    2. Du kanske tillfälligt måste stänga av parametern **Tillåt inte manuell inmatning** på sidan **Huvudkonto**. Denna justering bokförs inte om huvudkontot inte tillåter manuell inmatning.

    ![Justering läggs inte upp.](./media/YEC7.png)

9. Du kan nu återställa de oreglerade transaktionerna. Återgå till sidan **Redovisningenskvittning** och begränsa datumintervallet till 1 januari 2022, till och med 31 december 2022. Illustrationen som följer visar dessa ej kvitterade transaktioner sm nu finns.

    ![Oreglerade transaktioner.](./media/YEC8.png)

    - Det ingående saldot på 1 025 $ kan avräknas mot justeringen för - 1 025 $.
    - De detaljerade transaktioner som inte kvittats för -400 $, -50 $ och -75 $ kan kvittas mot justeringen för 525,00 $.

    ![Detaljerade transaktioner.](./media/YEC9.png)

10. Aktivera funktionen **Medvetenhet**. Du är nu redo att köra årsbokslutet.

    - Innan du kör årsbokslutet bör du välja alternativet **Behåll detaljer** i inställningen för redovisningskvittning för alla balansräkningskonton. Mer information om fördelarna med att genomföra det här steget finns i dokumentet Medvetenheten.
    - När du börjar årsbokslut för 2022, om det fortfarande finns transaktioner som kvittats över räkenskapsår, meddelar årsbokslutprocessen omedelbart dig.
    - Om 2021 och 2022 transaktioner fortfarande är avklarade måste du inaktivera funktionen **Medvetenhet** igen och upprepa de föregående stegen för att ta bort transaktionerna. Den här metoden krävs eftersom 2021 är stängt och transaktionerna inte kan kvittas under ett stängt räkenskapsår.
    - Om transaktionerna 2022 och 2023 fortfarande kvittas behöver du **inte** inaktivera funktionen **Medvetenhet**. Eftersom varken 2022 eller 2023 har stängts kan du använda de föregående stegen för att oreglera transaktionerna.

Efter att årsbokslutet för 2022 har körts kan du lämna funktionen **Medvetenhet** aktiverad från och med nu.
