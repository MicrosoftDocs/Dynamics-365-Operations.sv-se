---
title: Funktionen Medvetenhet mellan redovisningskvittning före årsbokslut använder förfrågningssidan
description: I den här artikeln förklaras hur du använder funktionen Medvetenheten mellan redovisningskvittningar genom att använda den nya förfrågningssidan innan årsbokslutet körs.
author: kweekley
ms.date: 12/15/2022
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
ms.openlocfilehash: b138d2d5e88ff7f2ca2240cf256a4938f55a5606
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853164"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close-using-the-inquiry-page"></a>Funktionen Medvetenhet mellan redovisningskvittning före årsbokslut använder förfrågningssidan

En större ändring av funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen **Medvetenhet**) är att redovisningskvittning inte kan göras över räkenskapsår. Denna begränsning under flera år är endast relevant för redovisningskvittning, inte för kvittningar i kundreskontra eller leverantörsreskontra.

Innan funktionen **Medvetenhet** aktiveras får det räkenskapsår som genomgår årsbokslut inte ha några redovisningstransaktioner som kvittas över räkenskapsår. Alla transaktioner som har bokförts på räkenskapsåret som du kör årsbokslutet för måste specifikt tas bort från transaktioner som har bokförts till ett annat räkenskapsår. Transaktionerna kan sedan kvittas på nytt mot transaktioner inom samma räkenskapsår.

I den här artikeln beskrivs vilka steg som krävs för att identifiera, oreglera och åter kvitta redovisningstransaktioner som kvittas över räkenskapsår. I det exempel som ges har räkenskapsåret 2021 stängts och du förbereder att köra årsbokslut för räkenskapsåret 2022.

Med Microsoft Dynamics 365 Finance version 10.0.29, kan du identifiera, ange och återställa redovisningstransaktioner genom att använda en ny förfrågningssida som är tillgänglig. Om du inte är det för närvarande använder Ekonomi version 10.0.29 eller senare, kan du hitta stegen för att identifiera, avmarkera och återställa redovisningstransaktionerna i följande artiklar:

- [Medvetenhet mellan funktionen redovisningskvittning före årsbokslut](ledger-settle-yec.md)
- [Medvetenhet mellan funktionen redovisningskvittning efter årsbokslut](ledger-settle-yec-after.md)

Mer information om det nya förfrågningsfönstret finns i [Förfrågan om redovisningskvittning](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exempel på konfiguration

I bilden nedan visas de transaktioner som bokförts för huvudkonto 110200. Transaktionerna i grönt var redovisningsreglerade under samma räkenskapsår och behöver inte ändras. Transaktionerna i rött var redovisningsreglerade, men de har transaktionsdatum i olika räkenskapsår. Dessa transaktioner måste identifieras, och redovisningskvittning måste kanske återföras.

![Bokförda redovisningstransaktioner.](./media/ledgersettlement.png)

## <a name="example"></a>Exempel

Följ dessa steg om din organisation vill använda funktionen **Medvetenhet** innan årsbokslutet för räkenskapsåret 2022 körs.

> [!NOTE]
> Årsbokslut för 2021 och tidigare räkenskapsår måste endast köras igen om nya transaktioner bokförs på räkenskapsåret 2021 eller tidigare. När du slutför följande procedur bokförs inga nya transaktioner till 2021. Årsbokslutsprocessen måste inte köras om.
>
> Redovisningstransaktioner som kvittas över räkenskapsår kan förbli redovisningsreglerade om de inte kvittas mot en transaktion som bokfördes in 2022 (året som avslutas) eller senare. Om du till exempel har kvittat transaktioner i 2019 och 2020 kan de fortsätta att kvittas.

1. Aktivera **inte** funktionen **Medvetenhet**.
2. På sidan **Redovisningskvittningar**, välj **Granska kvittningar för flera år**.
3. Identifiera alla transaktioner som har bokförts i andra räkenskapsår men kvittats mot transaktioner som har bokförts till 2022.

    1. Välj räkenskapsår 2022, räkenskapsår du vill köra årsbokslutsprocess mot.
    2. Välj ett värde i fältet **Ekonomisk dimensionsuppsättning** för att visa de ekonomiska dimensioner som du vill visa för redovisningskontot. Huvudkontot visas alltid, även om den dimensionsuppsättning som är vald inte innehåller något huvudkonto.
    3. Välj **Visa transaktioner**.

    På sidan för förfrågan visas alla transaktioner för alla redovisningskonton (även om de inte längre finns i inställningen för redovisningskvittning) från alla andra räkenskapsår som kvittas mot transaktioner som bokförts till 2022. Tre olika redovisningskonton visas.

    ![2022 kvittningar för flera år.](./media/review-cross-year.png)

3. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Exportera alla rader**. Dessa rader är alla transaktioner som måste kvittas från transaktionerna 2022 innan årsbokslutet kan köras. Du vill ha den detaljerade transaktionslistan så att du kan återställa transaktionerna på rätt sätt senare.
4. Notera de räkenskapsår som transaktionerna bokfördes för. I det här exemplet blir transaktionerna i 2021 och 2023 $.
5. På sidan för förfrågan ändrar du räkenskapsåret till 2021, det första räkenskapsåret som innehåller transaktioner som kvittades mot 2022-transaktioner.
6. Filtrera på kolumnen **Transaktionsdatum** så att bara transaktioner som bokförts till 2022 inkluderas. Dessa transaktioner är de detaljerade transaktioner från 2022 som kvittades mot transaktioner 2021.
7. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Exportera alla rader**.

    > [!IMPORTANT]
    > I följande steg kommer dessa transaktioner att oregleras och sedan kvittas mot transaktioner under 2022. Du måste underhålla den här detaljerad information i Excel.

    ![2021 kvittningar för flera år.](./media/review-cross-year.png)

8. På sidan för förfrågan ändrar du räkenskapsåret till 2023, nästa räkenskapsåret som innehåller transaktioner som kvittades mot 2022-transaktioner. 
9. Filtrera på kolumnen **Transaktionsdatum** så att bara transaktioner som bokförts till 2022 inkluderas. Dessa transaktioner är de detaljerade transaktioner från 2023 som kvittades mot transaktioner 2022. 
10. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Exportera alla rader**.

    > [!IMPORTANT]
    > I följande steg kommer dessa transaktioner att oregleras och sedan kvittas mot transaktioner under 2022. Du måste underhålla den här detaljerad information i Excel.

    ![2023 kvittningar för flera år.](./media/filter-transactions.png)

11. Upprepa de föregående stegen för varje räkenskapsår som har transaktioner som kvittades mot transaktioner under 2022. Exportera alltid detaljerade transaktioner till Excel.

    När alla detaljerade transaktioner från 2021 och 2023 har exporterats till Excel kan du kan du oreglera transaktionerna på sidan Förfrågan.

12. Ändra räkenskapsåret till 2022.
13. Markera alla poster i rutnätet och markera sedan **oreglera markerade poster**. Alla valda transaktioner i nätet kommer att vara oreglerade.

    Två varningsmeddelanden visas för att säkerställa att transaktionsdetaljerna exporteras till Excel innan transaktionerna oregleras. Om du råkar ta bort bokföringstransaktionerna av misstag innan du skickar informationen till Excel går det inte att återföra ej kvittning. 

    ![Kvittning av flera kvittningstransaktioner.](./media/revert-unsettle.png)

14. Med Excel-data kan du hitta det totala antalet transaktioner under 2021 och 2023 som kvittades mot transaktioner 2022. I det här exemplet visas transaktionerna för 2021 totalt 525 $ och transaktionerna för 2023 totalt 700 $.
15. Bokför en justerad allmän journal så att den ingående balansen för 2022 delas upp i två belopp: den andel som kvittas till räkenskapsåret 2021 och den del som ännu inte kvittats 2022.

    - **Andel av den ingående balansen som kvittas mot föregående år:** Det första beloppet 525 $ baserat på de summor som hittades som kvittades mellan 2021 och 2022.
    - **Del av den ingående balansen som inte kvittas mot föregående år:** Det andra beloppet är differensen mellan den ingående balansen och det kvittade 525 $. Resterande belopp är 1 025 $ – 525 $= 500 $.

    På det här sättet kan du kvitta 2022-transaktionerna mot den 525 $ som ursprungligen kvittas mot 2021-transaktionen. Det här steget är bara nödvändigt eftersom redovisningskvittning inte tillåter delvis kvittning.

    1. Gå till den allmänna journalen och bokför justeringen. Din organisation måste bestämma vilket transaktionsdatum som ska användas, baserat på de perioder som är öppna. Dessa transaktioner kan ha kvittats med ett kvittningsdatum från januari eller februari 2022, men justeringen kan behöva bokföras i december om det bara är den öppna perioden.
    2. Du kanske tillfälligt måste stänga av parametern **Tillåt inte manuell inmatning** för konto 110200 på sidan **Huvudkonto**. Denna justering bokförs inte om huvudkontot inte tillåter manuell inmatning.

    ![Bokföra en justerande allmän journal.](./media/not-post.png)

16. Du kan nu återställa de oreglerade transaktionerna. Gå tillbaka till sidan **Redovisningskvittningar**, ange datumintervallet 1 januari till 31 december 2022 och filtrera på huvudkontot 110200. Använd sedan de detaljerade transaktioner som du exporterat till Excel för att hitta de specifika transaktioner som måste kvittas på samma sätt. Illustrationen som följer visar dessa ej kvitterade transaktioner sm nu finns.

    ![Oreglerade transaktioner](./media/updated-unsettled.png)

    - Det ingående saldot på 1 025 $ kan avräknas mot justeringen för - 1 025 $.
    - De detaljerade transaktioner som inte kvittats för -400 $, -50 $ och -75 $ kan kvittas mot justeringen för 25 $.

17. Aktivera funktionen **Medvetenhet**. Du är nu redo att köra årsbokslutet.

    - Innan du kör årsbokslutet bör du välja alternativet **Behåll detaljer** i inställningen för redovisningskvittning för alla balansräkningskonton. Mer information finns i [Medvetenhet mellan redovisningskvittning och årsbokslut](awareness-between-ledger-settlement-year-end-close.md).
    - När du börjar årsbokslut för 2022, om det fortfarande finns transaktioner som kvittats över räkenskapsår, meddelar årsbokslutprocessen omedelbart dig. Den här situationen kan uppstå om användarna kvittar transaktioner över räkenskapsår efter att du har slutfört de föregående stegen.
    - Om 2021 och 2022 transaktioner fortfarande är avklarade måste du inaktivera funktionen **Medvetenhet** igen och upprepa de föregående stegen för att ta bort transaktionerna. Den här metoden krävs eftersom 2021 är stängt och transaktionerna inte kan kvittas under ett stängt räkenskapsår.
    - Om transaktionerna 2022 och 2023 fortfarande kvittas behöver du inte inaktivera funktionen **Medvetenhet**. Eftersom varken 2022 eller 2023 har stängts kan du använda de föregående stegen för att oreglera transaktionerna.

18. Du kan kvitta 700 $ transaktionen från 2023 mot de detaljerade transaktioner som fördes över som ingående balans 2023. Den här transaktionen kvittas inte mot den ursprungliga transaktionen 2022.

Efter att årsbokslutet för 2022 har körts kan du lämna funktionen **Medvetenhet** aktiverad från och med nu.
