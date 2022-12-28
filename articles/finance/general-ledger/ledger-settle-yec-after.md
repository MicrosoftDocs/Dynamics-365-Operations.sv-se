---
title: Medvetenhet mellan funktionen redovisningskvittning efter årsbokslut
description: I den här artikeln förklaras hur du använder funktionen Medvetenheten mellan redovisningskvittningar efter årsbokslutprocessen körs.
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832185"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Medvetenhet mellan funktionen redovisningskvittning efter årsbokslut

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Förbereda för funktionen redovisningskvittning före årsbokslut

En större ändring av funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen **Medvetenhet**) är att redovisningskvittning inte kan göras över räkenskapsår. Denna begränsning under flera år är endast relevant för redovisningskvittning, inte för kvittningar i kundreskontra eller leverantörsreskontra.

Innan funktionen **Medvetenhet** aktiveras får det räkenskapsår som genomgår årsbokslut inte ha några redovisningstransaktioner som kvittas över räkenskapsår. Alla transaktioner som har bokförts på räkenskapsåret som du kör årsbokslutet för måste specifikt tas bort från transaktioner som har bokförts till ett annat räkenskapsår. Transaktionerna kan sedan kvittas på nytt mot transaktioner inom samma räkenskapsår.

Den här artikeln beskrivs vilka steg som krävs för att identifiera, oreglera och åter kvitta redovisningstransaktioner som kvittas över räkenskapsår. I det exempel som ges har räkenskapsåret 2022 stängts. Fokus ligger på att förbereda redovisningskvittningstransaktioner före årsbokslutet för 2023 körs.

## <a name="example-setup"></a>Exempel på konfiguration

I bilden nedan visas de transaktioner som bokförts för huvudkonto 110190. Redovisningstransaktionerna i grönt kvittas under samma räkenskapsår och behöver inte ändras. Transaktionerna i rött kvittas i redovisningen, men de har transaktionsdatum i olika räkenskapsår. Dessa transaktioner måste identifieras, och redovisningskvittning måste kanske återföras.

![Redovisningstransaktioner.](./media/afterYEC1.png)

## <a name="example"></a>Exempel

Följ dessa steg om din organisation vill använda funktionen **Medvetenhet** innan du kör årsbokslutet för räkenskapsåret 2022.

> [!NOTE]
> Årsbokslut för 2022 och tidigare räkenskapsår måste endast köras igen om nya transaktioner bokförs på räkenskapsåret 2022 eller tidigare. När du slutför följande procedur bokförs inga nya transaktioner till 2022. Årsbokslutsprocessen måste inte köras om.
>
> Redovisningstransaktioner som kvittas över räkenskapsår kan förbli redovisningsreglerade om de inte kvittas mot en transaktion som bokfördes in 2023 eller senare. Om du till exempel har kvittat transaktioner över 2019 och 2020 kan de fortsätta att kvittas.

1. Slutför årsbokslutet för 2022 utan att funktionen **Medvetenhet** har aktiverats.
2. Valfritt: Aktivera funktionen **Medvetenhet** efter att årsbokslutet för 2022 har slutförts. Ett årsbokslut betraktas som slutfört när alla justeringar bokförs och processen för årsbokslutet inte körs igen.

    > [!IMPORTANT]
    > Funktionen **Medvetenhet** får inte aktiveras om årsbokslutet för 2022 körs igen. Fördelen med att aktivera funktionen nu är att du hindrar användarna från att kvitta redovisningstransaktioner som har bokförts i olika räkenskapsår.

    Om årsbokslutet inte har slutförts kan du gå vidare i nästa steg utan att aktivera funktionen **Medvetenhet**. Du aktiverar funktionen senare om det anges.

3. På sidan **Redovisningskvittning** identifierar du summan av alla transaktioner som kvittas över räkenskapsåren 2022 och 2023. Observera att 2021-transaktioner kvittades mot 2022-transaktioner är inte relevanta eftersom året redan har stängts för 2022. Dessa transaktioner kan förbli kvittade.

    1. Ange ett datumintervall för hela räkenskapsåret 2022. Ange till exempel 1 januari 2022 till 31 december 2022 om du använder ett kalenderår som räkenskapsår.
    2. I fältet **Status**, välj **Kvittad**.
    3. Filtrera på ett redovisningskonto åt gången.

        - Du måste upprepa de här stegen för varje redovisningskonto som redovisningskvittning sker för.
        - Om andra redovisningskonton inte längre är inställda för redovisningskvittning måste du tillfälligt lägga till dem igen i inställningen för redovisningskvittning. Slutför sedan dessa steg om dessa redovisningskonton har transaktioner under 2023 som kvittas mot transaktioner i 2022 eller tidigare.

    4. Välj och håll ned (eller högerklicka) i kolumnen **Status** och välj för att gruppera denna kolumn.
    5. Välj och håll ned (eller högerklicka) i kolumnen **Belopp i transaktionsvaluta** och välj för att gruppera hela kolumn.

        - Om du kvittar transaktioner bara i 2022 blir summan 0 (noll).
        - Om du har transaktioner som kvittats över räkenskapsår blir summan inte 0 (noll).

    6. Identifiera vilka transaktioner som kvittades mellan 2022 och 2023 genom filtrering av värdet för **kvittningsdatum** . Om du filtrerar på ett kvittningsdatum som är 1 januari 2023 till och med 31 december 2023 får du totalt 700 $, vilket är summan av transaktionerna som redovisningen kvittades för mellan 2022 och 2023.

    ![Totala redovisningstransaktioner för 2022.](./media/afterYEC2.png)

4. Upprepa steg 3 för räkenskapsåret 2023. Summan ska matcha summan 700 $ från 2022 eftersom inga 2023-transaktioner kvittades mot 2024-transaktioner.

    ![Totala redovisningstransaktioner för 2023.](./media/afterYEC3.png)

5. Om du aktiverar funktionen **Medvetenhet** i steg 2 måste du inaktivera den innan du går vidare till steg 6. I nästa steg återför du den redovisningskvittning som passerat räkenskapsår. Om funktionen **Medvetenhet** är aktiverad kan redovisningskvittning inte återföras för räkenskapsåret 2022. Därför måste du inaktivera funktionen innan du fortsätter.
6. När funktionen **Medvetenheten** har inaktiverats använder du samma filter på sidan **Redovisningkvittning** för att återföra redovisningskvittningen för de detaljerade transaktionerna.

    1. Gå tillbaka till sidan **Redovisningskvittning** och filtrera transaktionsdatum för 2023. Sök sedan efter de detaljerade transaktioner som utgör 700 $ totalsumman. Det är inte enkelt att filtrera den här informationen. Du kanske måste skicka data till Microsoft Excel för att utvärdera dem.
    2. När du har listat transaktioner väljer du redovisningstransaktionerna på sidan **Redovisningkvittning** och markerar **Markera markerad**. Du behöver inte se båda förkontran av redovisningstransaktionerna som kvittades. Om du markerar antingen debet eller kredit, allt som har samma värde för **kvittnings-ID** att återföras även om värdet **markerat belopp** inte var **0** (noll).
    3. Välj **Återför markerade transaktioner** för att oreglera transaktionerna.

    ![Återför transaktioner.](./media/afterYEC4.png)

7. Bokför en justerad allmän journal så att den ingående balansen för 2023 delas upp i två belopp: den andel som kvittas mot transaktionen för räkenskapsåret 2022 och den del som ännu inte kvittats 2023.

    - **Andel av den ingående balansen som kvittas mot föregående år:** Det första beloppet 700 $ baserat på de summor som hittades som kvittades mellan 2022 och 2023.
    - **Del av den ingående balansen som inte kvittas mot föregående år:** Det andra beloppet är differensen mellan den ingående balansen och det första beloppet på 525 $. Resterande belopp är 1700 $ – 700 $= 1000 $.

    På det här sättet kan du kvitta 2023-transaktionerna mot den 700 $ som ursprungligen kvittas mot 2022-transaktionen. Det här steget är bara nödvändigt eftersom redovisningskvittning inte tillåter delvis kvittning.

    1. Gå till den allmänna journalen och bokför justeringen. Din organisation måste bestämma vilket transaktionsdatum som ska användas, baserat på de perioder som är öppna 2023.
    2. Du kanske tillfälligt måste stänga av parametern **Tillåt inte manuell inmatning** på sidan **Huvudkonto**. Denna justering bokförs inte om huvudkontot inte tillåter manuell inmatning.

    ![Justering läggs inte upp.](./media/afterYEC5.png)

8. Du kan nu återställa de oreglerade transaktionerna. Återgå till sidan **Redovisningenskvittning** och begränsa datumintervallet till 1 januari 2022, till och med 31 december 2022. Illustrationen som följer visar dessa ej kvitterade transaktioner sm nu finns.

    ![Oreglerade transaktioner.](./media/afterYEC6.png)

    - Ingående saldo på 1 700 $ kan kvittas mot justeringen för - 1 700 $.
    - De detaljerade transaktioner som inte kvittats för 700 $ kan kvittas mot justeringen för 700,00 $.

9. Återaktivera funktionen **Medvetenhet**.
10. Efter att funktionen **Medvetenhet** är aktiverad kan redovisningskvittning inte göras mellan räkenskapsår. Det kan bli ytterligare att dela upp det återstående 1 000 $ till mindre belopp innan du kan kvitta mot nya transaktioner 2023. Vissa kunder väljer att bokföra dessa detaljer under steg 8 där 1 000 $ delas upp ytterligare för att representera de oreglerade transaktionerna från 2022. Detta tillvägagångssätt gör i grund och botten det som funktionen **Medvetenhet** gör under bara innevarande år. Nästa år görs det automatiskt med hjälp av inställningen **Behåll detaljer** i inställningen för redovisningskvittning.
