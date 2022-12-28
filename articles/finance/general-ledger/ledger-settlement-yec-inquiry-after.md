---
title: Funktionen Medvetenhet mellan redovisningskvittning efter årsbokslut använder förfrågningssidan
description: I den här artikeln förklaras hur du använder funktionen Medvetenheten mellan redovisningskvittningar genom att använda den nya förfrågningssidan efter att årsbokslutet körs.
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853151"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Funktionen Medvetenhet mellan redovisningskvittning efter årsbokslut använder förfrågningssidan

En större ändring av funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen **Medvetenhet**) är att redovisningskvittning inte kan göras över räkenskapsår. Denna begränsning under flera år är endast relevant för redovisningskvittning, inte för kvittningar i kundreskontra eller leverantörsreskontra.

Innan funktionen **Medvetenhet** aktiveras får det räkenskapsår som genomgår årsbokslut inte ha några redovisningstransaktioner som kvittas över räkenskapsår. Alla transaktioner som har bokförts på räkenskapsåret som du kör årsbokslutet för måste specifikt tas bort från transaktioner som har bokförts till ett annat räkenskapsår. Transaktionerna kan sedan kvittas på nytt mot transaktioner inom samma räkenskapsår.

I den här artikeln beskrivs vilka steg som krävs för att identifiera, oreglera och åter kvitta redovisningstransaktioner som kvittas över år. I det exempel som ges har räkenskapsåret 2022 stängts. Fokus ligger på att förbereda redovisningskvittningstransaktioner före årsbokslutet för 2023 körs.

Med Microsoft Dynamics 365 Finance version 10.0.29, kan du identifiera, ange och återställa redovisningstransaktioner genom att använda en ny förfrågningssida som är tillgänglig. Om du inte är det för närvarande använder Microsoft Dynamics 365 Finance version 10.0.29 eller senare, kan du hitta stegen för att identifiera, avmarkera och återställa redovisningstransaktionerna i följande artiklar:

- [Medvetenhet mellan funktionen redovisningskvittning före årsbokslut](ledger-settle-yec.md)
- [Medvetenhet mellan funktionen redovisningskvittning efter årsbokslut](ledger-settle-yec-after.md)

Mer information om det nya förfrågningsfönstret finns i [Förfrågan om redovisningskvittning](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exempel på konfiguration

I bilden nedan visas de transaktioner som bokförts för huvudkonto 110200. Transaktionerna i grönt var redovisningsreglerade under samma räkenskapsår och behöver inte ändras. Transaktionerna i rött var redovisningsreglerade, men de har transaktionsdatum i olika räkenskapsår. Dessa transaktioner måste identifieras, och redovisningskvittning måste kanske återföras.

![Bokförda redovisningstransaktioner.](./media/excel.png)

## <a name="example"></a>Exempel

Följ dessa steg om din organisation vill använda funktionen **Medvetenhet** innan du kör årsbokslutet för räkenskapsåret 2022.

> [!NOTE]
> Årsbokslut för 2022 och tidigare räkenskapsår måste endast köras igen om nya transaktioner bokförs på räkenskapsåret 2022 eller tidigare. När du slutför följande procedur bokförs inga nya transaktioner till 2022. Årsbokslutsprocessen måste inte köras om.
>
> Redovisningstransaktioner som kvittas över räkenskapsår kan förbli redovisningsreglerade om de inte kvittas mot en transaktion som bokfördes in 2022 eller senare. Om du till exempel har kvittat transaktioner i 2019 och 2020 kan de fortsätta att kvittas.

1. Slutför årsbokslutet för 2022 utan att funktionen **Medvetenhet** har aktiverats.
2. Identifiera alla transaktioner som har bokförts i andra räkenskapsår men kvittats mot transaktioner som har bokförts till 2023 (nästa räkenskapsår som ska stängas).

    > [!NOTE]
    > 2021-transaktioner som kvittades mot 2022-transaktioner är inte relevanta eftersom året redan har stängts för 2022. Dessa transaktioner kan förbli kvittade.

    1. På sidan **Redovisningskvittningar**, välj **Granska kvittningar för flera år**.
    2. Välj räkenskapsår 2023, nästa räkenskapsår du vill köra årsbokslutsprocess mot.
    3. Välj ett värde i fältet **Ekonomisk dimensionsuppsättning** för att visa de ekonomiska dimensioner som du vill visa för redovisningskontot. Huvudkontot visas alltid, även om den dimensionsuppsättning som är vald inte innehåller något huvudkonto.
    4. Välj **Visa transaktioner**.

    På förfrågan visas alla transaktioner från andra räkenskapsår som kvittas mot transaktioner som bokfördes 2023.

    ![2023 kvittningar för flera år.](./media/2023-cross-settlement.png)

3. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Exportera alla rader**. Dessa rader är alla transaktioner som måste kvittas från transaktionerna 2022 innan årsbokslutet för nästa år (2023) kan köras. Du vill ha en registrering av dessa transaktioner.

    När alla detaljerade transaktioner från 2022 har exporterats till Excel kan du oreglera transaktionerna på sidan Förfrågan.

4. Markera alla poster i rutnätet och markera sedan **oreglera markerade poster**. Alla valda transaktioner i nätet kommer att vara oreglerade.

    Två varningsmeddelanden visas för att säkerställa att transaktionsdetaljerna exporteras till Excel innan transaktionerna oregleras. Om du råkar ta bort bokföringstransaktionerna av misstag innan du skickar informationen till Excel går det inte att återföra ej kvittning. 

    ![Ta bort kvittningar för flera år.](./media/revert-settlement.png)

5. Med Excel-data kan du hitta det totala antalet transaktioner under 2022 som kvittades mot transaktioner 2023. I det här exemplet blir transaktionerna för 2023 en summa på 700 $.
6. Bokför en justerad allmän journal så att den ingående balansen för 2022 delas upp i två belopp: den andel som kvittas mot transaktionen för räkenskapsåret 2022 och den del som ännu inte kvittats 2023.

    - **Andel av den ingående balansen som kvittas mot föregående år:** Det första beloppet 700 $ baserat på de summor som hittades som kvittades mellan 2021 och 2022.
    - **Del av den ingående balansen som inte kvittas mot föregående år:** Det andra beloppet är differensen mellan den ingående balansen och det kvittade 700 $. Resterande belopp är 1 700 $ – 700 $= 1 000 $.

    På det här sättet kan du kvitta 2023-transaktionerna mot den 700 $ som ursprungligen kvittas mot 2022-transaktionen. Det här steget är bara nödvändigt eftersom redovisningskvittning inte tillåter delvis kvittning.

    1. Gå till den allmänna journalen och bokför justeringen. Din organisation måste bestämma vilket transaktionsdatum som ska användas, baserat på de perioder som är öppna 2023.
    2. Du kanske tillfälligt måste stänga av parametern **Tillåt inte manuell inmatning** på sidan **Huvudkonto**. Denna justering bokförs inte om huvudkontot inte tillåter manuell inmatning.

    ![Bokföra en justerande allmän journal.](./media/no-manual4.png)

7. Du kan nu återställa de oreglerade transaktionerna. Återgå till sidan **Redovisningenskvittningar** och begränsa datumintervallet till 1 januari till och med 31 december 2023. Använd sedan de detaljerade transaktioner som du exporterat till Excel för att hitta de specifika transaktioner som måste kvittas på samma sätt. Illustrationen som följer visar dessa ej kvitterade transaktioner sm nu finns.

    ![2023 oreglerade transaktioner.](./media/2023-unsettled5.png)

    - Ingående saldo på 1 700 $ kan kvittas mot justeringen för - 1 700 $.
    - De detaljerade transaktioner som inte kvittats för 700 $ kan kvittas mot justeringen för 700,00 $.

8. Aktivera funktionen **Medvetenhet**. Du är nu redo att köra årsbokslutet.

    - Innan du kör årsbokslutet för 2023 bör du välja alternativet **Behåll detaljer** i för alla balansräkningskonton i inställningen för redovisningskvittning. Mer information finns i [Medvetenhet mellan redovisningskvittning och årsbokslut](awareness-between-ledger-settlement-year-end-close.md).
    - När du börjar årsbokslut för 2023, om det fortfarande finns transaktioner som kvittats över räkenskapsår, meddelar årsbokslutprocessen omedelbart dig. Den här situationen kan uppstå om användarna kvittar transaktioner över räkenskapsår innan funktionen **Medvetenhet** har aktiverats.
    - Om 2022 och 2023 transaktioner fortfarande är avklarade måste du inaktivera funktionen **Medvetenhet** igen och upprepa de föregående stegen för att oreglera transaktionerna. Den här metoden krävs eftersom 2022 är stängt och transaktionerna inte kan kvittas under ett stängt räkenskapsår.

Efter att årsbokslutet för 2022 har körts kan du lämna funktionen **Medvetenhet** aktiverad från och med nu.
