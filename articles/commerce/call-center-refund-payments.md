---
title: Bearbetning av återbetalningar i kundcenter
description: I denna artikel beskrivs hur återbetalningar skapas via kundcenter när returer skapas, eller när order eller orderrader annulleras.
author: hhainesms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b1f3462529d501d9a5c279fd15dec69cb447cd51
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276930"
---
# <a name="refund-payment-processing-in-call-centers"></a>Bearbetning av återbetalningar i kundcenter

I denna artikel beskrivs hur återbetalningar skapas via kundcenter när returer skapas, eller när order eller orderrader annulleras.

En användare som skapar en returorder för en kund som kundtjänstanvändare i Microsoft Dynamics 365 Commerce-administrationen använder sidan **Returorder** för att skapa materialauktoriseringen för initialreturen (RMA). RMA definierar produkterna som kunden vill returnera eller byta och skapar en kopplad returförsäljningsorder med ordertypen **Returnerad order**. Denna kopplade returnerade order används för att spåra bokföringen av det returnerade lagret och eventuella kreditnotor eller betalningsåterbetalningar som bokförts.

Om alternativet **Aktivera orderslutförande** har angetts som **Ja** för kundtjänstkanalen måste den kundtjänstanvändare som skapar aktuell RMA köra bearbetningsflödet för orderslutförande genom att välja **Slutför** på sidan **Returorder**. Funktionen **Slutför** ger en beräknad retursammanfattning som beskriver det förfallna återbetalningsbeloppet. När den är korrekt konfigurerad skapas dessutom en återbetalningsrad systematiskt mot den returnerade ordern.

Kundtjänstlogiken bestämmer betalsättet för återbetalningsraden, baserat på betalsättet som användes för den ursprungliga ordern. Om den returorder som skapas inte är länkad till en ursprunglig order, används ett standardbetalsätt som tas från en systemparameter.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Hur en kundtjänst fastställer vilket betalningsätt som ska användas för en returorder

Kundtjänsten använder betalningsättet för den ursprungliga ordern för att bestämma vilket betalsätt som ska användas för en returorder. Här följer hur den här processen fungerar för följande ursprungliga betalsätt:

- **Normal** (kontant) eller **Check** – När en returorder som skapas hänvisar till en originalorder som betalats med hjälp av den normala (kontant) eller checkbetalningstypen hänvisar kundtjänstprogrammet till konfigurationer på sidan **Återbetalningsmetoder för kundtjänst**. På den här sidan kan organisationer definiera, efter ordervaluta, hur återbetalningar utfärdas till kunder för order som ursprungligen betalades med hjälp av det normala betalsättet eller checkbetalsättet. På sidan **Återbetalningsmetoder** för kundtjänst kan även organisationer välja om en systemgenererad återbetalningscheck ska skickas till kunden. I dessa scenarier hänvisar kundtjänstlogiken till valutan för returordern och använder sedan värdet för **Betalsätt för butik** för valutan för att skapa en återbetalningsrad på returförsäljningsordern. Senare kopplas en kundreskontrabetalningsjournal (AR) som använder det mappade betalsättet AR till valutan.

    I följande bild visas konfigurationen för ett scenario där en kund returnerar produkter från en försäljningsorder som är kopplad till valutan USD och som ursprungligen betalades med det normala betalsättet eller checkbetalsättet. I detta scenario utfärdas en återbetalning till kunden via en systemgenererad återbetalningscheck. AR-betalsättet **REF-CHK** har konfigurerats som ett betalsätt för återbetalningscheck.

    ![Konfigurera återbetalningsmetoder för kundtjänst för normala betalningar och ursprungliga checkbetalningar.](media/callcenterrefundmethods.png)

    > [!NOTE]
    > Kundkontot stöds inte av en återbetalningsmetod för kontanter eller checkbetalningar.

- **Kreditkort** – När en skapad returorder hänvisar till en ursprunglig order som har betalats med kreditkort använder kundtjänstlogiken för återbetalningar samma ursprungliga kreditkort för returordern.
- **Förmånskort** – När en skapad returorder hänvisar till en ursprunglig order som har betalats med ett förmånskort använder kundtjänstlogiken för återbetalningar samma ursprungliga förmånskort för återbetalningen.
- **Presentkort** (internt) – När en returorder som skapas hänvisar till en originalorder som betalats med ett presentkort som utfärdats från Dynamics 365 Commerce (internfunktionen för presentkort), skickar kundtjänstlogiken för återbetalning av betalningar återbetalningen till samma, ursprungliga presentkortsnummer.
- **Presentkort** (externt) – När en returorder som skapas hänvisar till en originalorder som betalats med hjälp av ett externt presentkort från en tredje part, använder kundtjänstlogik för återbetalningar den standardreturbetalningsmetod som definieras på fliken **RMA/Retur** på sidan **Kundtjänstparametrar**.

Om det ursprungliga orderbetalsättet av någon anledning är okänd, eller om flera betalsätt användes för att betala den ursprungliga ordern, använder kundtjänstlogiken det standardbetalsätt som definierats på fliken **RMA/Retur** på sidan **Kundtjänstparametrar**.

I följande bild visas fältet **Betalsätt** på fliken **RMA/Retur** på sidan **Kundtjänstparametrar**.

![Fältet Betalsätt på fliken RMA/Retur på sidan Kundtjänstparametrar.](media/callcenterrefundparameters.png)

> [!NOTE]
> De regler för återbetalningsbearbetning som beskrivits tidigare gäller även för order eller orderrader som en kundtjänstanvändare annullerar i Commerce headquarters. Om en orderannullering eller specifika orderrader medför överbetalningar, används samma regler för att generera återbetalningsrader.

Vanligtvis genomgår en returorder en standardprocess där lager tas emot (eller kasseras), en följesedel bokförs mot returordern, och sedan körs en fakturabokföringsprocess för returförsäljningsordern. Returförsäljningsordern kopplas och genereras systematiskt som en del i processen med att skapa returordern. I vanliga fall utfärdas inga återbetalningar till kunder förrän fakturan för returförsäljningsordern bokförs.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Detta händer när en faktura bokförs på en returförsäljningsorder

Följande scenarier förklarar vad som händer när en faktura bokförs på en returförsäljningsorder:

- Om återbetalningen på returordern gäller för ett kreditkort startas ytterligare logik när fakturan bokförs. Denna logik anropar betalningsföretaget för återbetalning till kundens kreditkort. En verifikation för återbetalning skapas och bokförs systematiskt mot kundens konto. Denna betalningsjournal kvittas mot returorderns kreditfakturaverifikation.
- Om den återbetalning som måste utfärdas gäller för betalsättet "check" skapas en kundbetalningsverifikation som använder betalsättet AR, och som måste bokföras manuellt eller skrivas ut innan betalningsverifikationen kan bokföras mot kundkontot. När de vill bearbeta återbetalningschecken kan användarna använda antingen sidan **Kundbetalningsjournal** under Kundreskontra eller den specialiserade sidan **Bearbeta återbetalningscheck** i Butik och handel.
- Om den återbetalning som måste utfärdas gäller för betalsättet för det interna presentkortet eller förmånskortet, skapas och bokförs verifikationen för återbetalning mot kundkontot när returordern faktureras. Detta faktureringssteg adderar också återbetalningsbeloppet till kundens internt spårade presentkortssaldo eller förmånspoängssaldo.
- Om ett betalsätt som använder funktionen **Kund** (till exempel ett kundkonto) är kopplat till returförsäljningsordern ignoreras kreditgränsvalideringar när betalningen bearbetas. Ingen betalningsverifikation skapas eller bokförs i denna kontext. När en kundbetalningstyp används på en returorder fungerar den kreditfakturaverifikation som fakturabokföringsprocessen skapar som kundens kreditverifikation, och indikerar en återbetalning till kundens AR-saldo.

## <a name="advance-credit"></a>Förskottskredit

När en användare bearbetar returorder som kundtjänstanvändare i en kundtjänst där alternativet **Aktivera slutförande av order** är inställt på **Ja**, kan ett undantag till den tidigare beskrivna processen för bokföring av återbetalningsbetalningar uppstå om kundtjänstanvändaren som skapar returordern konfigurerar alternativet **Förskottskredit** som **Ja** på fliken **RMA/Retur** på sidan **Parametrar för kundtjänst**. I så fall sker betalningsåterbäringen omedelbart efter det att returordern har skickats, detta genom att använda funktionen **Skicka** på sidan **Retursammanfattning**. Systemet skapar omedelbart en betalningsverifikation för förskottsbetalningskund för returvärdet, även om returförsäljningsordern ännu inte har fakturerats. Denna metod kan användas i situationer där en organisation måste utfärda återbetalningar till kunder i förväg på grund av problem med kundtjänst och därför inte vill att returnerat lager måste skickas in innan återbetalningarna utfärdats.

## <a name="replacement-orders"></a>Ersättningsorder

När en returorder utfärdas kan funktionen **Ersättningsorder** användas för att generera en ny försäljningsorder för kunden. Detta arbetssätt kan användas vid utbytesscenarier. Funktionen **Ersättningsorder** skapar ännu en försäljningsorder för de nya artiklar som måste skickas, men en korsreferenslänk på fliken **RMA/Retur** på sidan **Parametrar för kundtjänst** länkar ersättningsordern, RMA och den returnerade försäljningsordern.

När betalningar på en ersättningsorder bearbetas har organisationer två alternativ:

- Att återbetala kunden för returordern, baserat på det ursprungliga betalsättet och ta sedan fram en separat betalning för ersättningsordern. Detta alternativ kräver ingen ytterligare konfiguration.
- Ange alternativet **Använd kredit** som **Ja** på fliken **RMA/Retur** på sidan **Parametrar för kundtjänst**. I det här fallet tillämpas ett kundbetalsätt systematiskt på både returordern och ersättningsordern. Detta alternativ kan förhindra att en extern återbetalningsbetalning utfärdas. Det hjälper också till att förhindra att betalningar bearbetas i transaktionen. Det kan vara användbart i situationer där ett jämnt utbyte bearbetas, och organisationen föredrar att använda den kreditverifikation som genereras när returordern faktureras i syfta att betala fakturan som genereras av ersättningsordern. När alternativet **Använd kredit** ställs in på **Ja** måste organisationen manuellt kvitta kreditfakturan mot ersättningsorderns faktura efter att båda dessa ekonomiska dokument har skapats.

Inställningen **Ja** för alternativet **Använd kredit** gäller bara när returordern kopplas till en ersättningsorder. I det här fallet definieras kundbetalsättet som ska användas för att systematiskt betala returen och växelordern av fältet **Använd betalsättet kredit** på fliken **RMA/Retur** på sidan **Parametrar för kundtjänst**. Endast en betalning av betalningsfunktionstypen **Kund** kan väljas i det här fältet.

> [!NOTE]
> För en returorder som inte har någon kopplad ersättningsorder påverkar inställningen **Ja** för alternativet **Använd kredit** inte betalningslogiken för returordern, detta eftersom denna inställning endast gäller ersättningsorder.

![Betalningsmetodfältet Applicera krediter på fliken RMA/Retur på sidan Kundtjänstparametrar.](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Om användare som skapar ersättningsorder tänker använda alternativet **Applicera kredit** bör de inte köra funktionen **Slutför** på returordern innan de anger alternativet **Applicera kredit** som **Ja**. När funktionen **Slutför** körs beräknas och tillämpas återbetalningsbetalningen på returförsäljningsordern. Varje försök att konfigurera alternativet **Applicera kredit** som **Ja** när en återbetalningsbetalning redan har beräknats och tillämpats utlöser inte en omberäkning av fältet, och det betalsätt som har valts i fältet **Applicera betalsättet kredit** kommer inte att tillämpas. Om alternativet **Applicera kredit** måste användas i denna kontext måste användaren radera ersättningsorder och RMA och sedan börja om och skapa en ny RMA. Denna gång måste användaren se till att alternativet **Applicera kredit** är inställt på **Ja** innan funktionen **Slutför** körs.

## <a name="payment-overrides-for-call-center-returns"></a>Betalningsåsidosättningar för kundtjänstreturer

Trots att kundtjänstlogik systematiskt bestämmer betalsättet för återbetalning på det sätt som beskrivs tidigare i denna artikel, kanske användarna ibland vill åsidosätta dessa betalningar. En användare kan till exempel redigera eller ta bort befintliga rader för återbetalningar och istället tillämpa nya betalningsrader. Systemberäknade återbetalningar kan bara ändras av användare som har rätt åsidosättningsbehörighet. Dessa behörigheter kan konfigureras på sidan **Åsidosätt behörighet** i Butik och Handel. Om du vill åsidosätta en återbetalning måste användaren kopplas till en säkerhetsroll där alternativet **Tillåt alternativ betalning** är inställt på **Ja** på sidan **Åsidosätt behörigheter**.

![Tillåt alternativa betalningsalternativ på sidan Åsidosätt behörigheter.](media/overridepermissions.png)

Alternativt kan en organisation konfigurera alternativet **Tillåt åsidosättning av betalning** som **Ja** på fliken **RMA/Retur** på sidan **Kundtjänstparametrar**. I det här fallet måste en åsidosättningskod väljas i fältet **Åsidosättningskod för säkerhet**. Koden för åsidosättning av säkerhet är en alfanumerisk kod som måste hanteras externt, detta eftersom användarna inte kan visa den i Commerce headquarters efter att den har ställts in. Åsidosättningskoden ska bara vara känd av några få, betrodda personer i organisationen. När alternativet **Tillåt betalningsåsidosättning** har angetts som **Ja** kommer alla användare som inte har rätt rollbehörighet för att försöka byta betalsätt på en returorder att få möjlighet att ange en åsidosättningskod. Om de inte vet det, eller om en chef eller överordnat inte kan ange det på sidan åt dem, kan de inte åsidosätta betalsättet för returer.

> [!NOTE]
> Om åsidosättningskoden har gått förlorad eller glömts bort måste organisationen återställa den genom att ange en ny åsidosättningskod i fältet **Åsidosättningskod** på fliken **RMA/Retur** på sidan **Kundtjänstparametrar**.

![Parametrar för betalningsåsidosättande på fliken RMA/Retur på sidan Kundtjänstparametrar.](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Innan organisationer försöker åsidosätta återbetalningar som använder kreditkortsbetalningstyper, bör de kontrollera att deras kreditkortsföretag tillåter okopplade returer. Många bearbetningsföretag kräver att återbetalningar bokförs på det ursprungliga kortet. Om du försöker utfärda en återbetalning till ett kort som inte har några tidigare registreringar kan detta leda till bokföringsfel med företaget.

## <a name="additional-resources"></a>Ytterligare resurser

[Betalsätt i kundcenter](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
