---
title: Rapportering av valuta i obalans när årsbokslutet körs
description: I den här artikeln förklaras hur rapporteringsvalutan kan vara ur balans när årsbokslutet körs.
author: kweekley
ms.date: 12/12/2022
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
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850268"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Rapportering av valuta i obalans när årsbokslutet körs

När du har aktiverat funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen **Medvetenhet**), kan redovisningstransaktioner som har kvitterats inte längre att inkluderas i ingående balans för nästa räkenskapsår när redovisningens årsbokslut körs. Om redovisningstransaktioner som kvittas exkluderas, kan det bli problem för kunder vid årsbokslutet om redovisningen definieras med en rapporteringsvaluta.

Redovisningskvittning utförs endast för redovisningsvalutan. När redovisningstransaktioner kvittas säkerställer valideringen bara att debet i redovisningsvalutan är lika med kredit i redovisningsvalutan. Beloppen i rapporteringsvalutan för dessa redovisningstransaktioner valideras inte och debet kanske inte är lika med kredit. Dessutom beräknar och bokför inte redovisningskvittning automatiskt en vinst/förlust i rapporteringsvalutan.

På grund av dessa begränsningar måste en vinst/förlust-transaktion finnas i rapporteringsvalutan när redovisningskvittning genomförs. Om vinst/förlust inte inkluderas i redovisningskvittningen leder årsbokslutet till ett meddelande om att saldot inte kan balanseras.

Följande exempel går igenom stegen för hur du tar upp det här problemet innan årsbokslutet körs.

## <a name="example-setup"></a>Exempel på konfiguration

Om du vill ställa in detta exempel, aktivera funktionen **Medvetenheten** och ställa in huvudkonto 110180 för redovisningskvittning. I följande bild visas redovisningstransaktionerna som bokförts i den juridiska personen DEMF. Redovisningsvalutan för DEMF är amerikanska dollar (USD) och rapporteringsvalutan är euro (EUR).

![Bokförda redovisningstransaktioner i rapporteringsvalutan.](./media/reporting-currency-1.png)

På sidan **Redovisningskvittningar** visas redovisningstransaktionerna för huvudkonto 110180. Markera och håll (eller högerklicka) på rutnätet och välj sedan **Infoga kolumner**. Lägg till kolumnen **belopp i rapporteringsvaluta** så att alla belopp i transaktionsvalutan, redovisningsvalutan och rapporteringsvalutan visas.

![Belopp i rapporteringsvalutakolumnen som läggs till på sidan Redovisningskvittningar.](./media/Ledger-settlement2.png)

De två första redovisningstransaktionerna för 100,00 EUR kvittas som en grupp, och de följande två redovisningstransaktionerna för 200,00 EUR kvittas som en annan grupp. (De två transaktionerna har olika kvittnings-ID.) Den här inställningen visar att organisationer kommer att ha flera grupper av redovisningstransaktioner som kvittas vid olika tider och har olika kvittningsdatum. När kvittningen är slutförd visar sidan **Redovisningskvittningar** följande information när den filtreras för att visa transaktioner som har status **Kvittad**.

![Kvittade transaktioner på sidan för redovisningskvittningar.](./media/Settled-trans-filtered3.png)

På sidan **Redovisningskvittningar** välj och håll ned (eller högerklicka) i kolumnen **Belopp** och välj **Summera den här kolumnen**. Upprepa det här steget för kolumnen **Belopp i rapporteringsvaluta**. Redovisningsvalutan måste ha skillnaden 0 (noll) för att kvittningen ska ske. Det finns dock ingen validering av kvittningsbeloppet för rapporteringsvalutan. I följande bild visas en skillnad på -27,79 USD för rapporteringsvalutan.

![Skillnad för rapporteringsvalutan.](./media/Difference4.png)

## <a name="year-end-close"></a>Årsbokslut

Om årsbokslutet nu körs för 2022 slutar processen med ett fel som inte går att balansera. Detta fel orsakas direkt av att rapporteringsvalutan inte har något redovisningskvittningsbelopp som netto blir 0 (noll).

![Felmeddelande som anger att redovisningskvittningsbeloppet är t 0 (noll).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Bokföra vinst/förlust i rapporteringsvaluta

För att årsbokslutet ska kunna köras måste skillnaden i rapporteringsvalutabeloppet redovisas, vanligtvis som en vinst eller förlust och inkluderas i redovisningskvittningen. Rapporteringsvalutans vinst/förlust kan bokföras på flera sätt:

- Om huvudkontot är leverantörsreskontra eller kundreskontra kommer kvittningen av AR/AP av dessa dokument att generera den vinst/förlust som krävs. Denna redovisningspost måste inkluderas i redovisningskvittningen när motsvarande redovisningstransaktioner från fakturan, betalningar, kreditfakturor och så vidare kvittas.
- Om huvudkontot är ett konto förutom leverantörsreskontra eller kundreskontra, måste vinsten/förlusten anges manuellt. När vinsten/förlusten bokförs bestäms detaljnivån för redovisningsposten av din organisation.
- Identifiera det vinst/förlustbelopp i rapporteringsvaluta som måste bokföras för varje huvudkonto.

Som tidigare beskrivits kan denna bokföring göras på sidan **Redovisningskvittningar** .

1. Filtrera till det datumintervall som du vill bokföra vinsten/förlusten för. Om du planerar att bokföra en vinst/förlust per månad, ska du filtrera fram varje månad. Om du tänker bokföra en vinst/förlust per räkenskapsår filtrerar du för hela året.
2. Filtrera på huvudkontot.
3. Filtrera efter status så att endast **kvittade** transaktioner visas.
4. Addera summan av kolumnen **Belopp i rapporteringsvaluta**.
5. Om du vill bokföra vinsten/förlusten på en mer finare nivå, kan du filtrera kvittnings-ID:t, ekonomiska dimensioner och så vidare. Det totala beloppet för kolumnen **Belopp i rapporteringsvaluta** representerar det belopp som vinsten/förlusten kommer att bokföras för.
6. Gå till **Redovisning \> Journalposter \> Justeringsjournaler för rapporteringsvaluta**.
7. Ange transaktionen för vinsten/förlusten. Den här journalen bokför endast en justering i rapporteringsvalutan. Beloppen i transaktionsvalutan och redovisningsvalutan som bokförs är alltid 0 (noll). Om den här journalen inte har använts tidigare kan du behöva skapa ett journalnamn som har journaltypen **Justering av rapporteringsvaluta** på **redovisning \> journalinställning \> journalnamn**.
8. Denna justering bokförs inte om huvudkontot inte tillåter manuell inmatning. Du kanske tillfälligt måste stänga av parametern **Tillåt inte manuell inmatning** på sidan **Huvudkonto**.

![Manuell inmatning på sidan Bokföringsorder.](./media/Manual-entry6.png)

När du har bokfört justeringsjournalen går du tillbaka till sidan **Redovisningskvittningar** och väljer det huvudkonto som du bokförde vinsten/förlusten för. Vinst-/förlustjusteringen måste inkluderas i en redovisningskvittning. Eftersom rapporteringsvalutabeloppet inte måste inbringa netto till 0 (noll) kan du ta bort eventuella tidigare transaktioner och kvitta dem igen, men inkludera vinsten/förlusten den här gången. Hur exakt du vill bokföra vinst/förlust och kvittning av denna vinst/förlust i redovisningskvittningar är upp till din organisation.

I bilden nedan visas att transaktionerna för 200 EUR har oreglerats och sedan markerats för kvittning igen. Vid den här tidpunkten kommer de att inkludera vinst-/förlustjusteringen.

![Vinst-/förlustjustering på sidan Redovisningskvittningar.](./media/gain-loss7.png)

När transaktionerna har kvittats ändrar du filtret **Status** så att sidan visar **Kvittade** transaktioner. Summan av kolumnen **Belopp rapporteringsvaluta** är nu 0 (noll). Årsbokslutet kan nu köras utan fel.

![Framgångsrikt årsbokslut.](./media/Zero-settled8.png)
