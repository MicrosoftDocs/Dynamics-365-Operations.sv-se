---
title: Hantera avdrag med workbench för avdrag
description: I det här avsnittet beskrivs hur du använder workbench för avdrag för att bearbeta kundbetalningar som omfattar avdrag.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 04d7c1de85978f7915246fd835a0866cefb6de310bba240ebcadc57089e10521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735121"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Hantera avdrag med workbench för avdrag

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du använder workbench för avdrag för att bearbeta kundbetalningar som omfattar avdrag.

En kund som ska få rabatt kan välja att inte vänta på utbetalning av rabatten. I stället kan kunden skicka en betalning som inkluderar ett avdrag för rabattbeloppet. För att hantera den här typen av transaktioner kan du använda workbench för avdrag för att matcha avdrag för att öppna kredittransaktioner, dela avdrag, neka avdrag och slriva av avdrag.

> [!NOTE]
> Workbench för avdrag har länge varit en del av försäljnings- och marknadsföringsfunktionen i Microsoft Dynamics 365 Supply Chain Management. Nu har den förbättrats så att även fungera med den nyare modulen **Rabatthantering**. I det här avsnittet beskrivs hur du använder både äldre funktioner och funktioner för Rabatthantering i workbench för avdrag. Om du inte har [aktiverat modulen **Rabatthantering** för systemet](rebate-management-enable.md) kommer vissa av funktionerna som beskrivs här inte att vara tillgängliga.

## <a name="prerequisites"></a>Förutsättningar

### <a name="set-up-the-old-deduction-management-system"></a>Ställa in det gamla systemet för hantering av avdrag

Du kan använda workbench för avdrag tillsammans med de gamla funktionerna för hantering av avdrag i Supply Chain Management även om du inte använder modulen **Rabatthantering**. Du måste dock först förbereda systemet så som beskrivs i det här avsnittet.

Innan du kan använda workbench för avdrag måste du utföra de inställningsuppgifter som beskrivs i [Ställ in hanteringav avdrag](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). Du bör också ha något slags rabattavtal som är inställt för kunden: antingen en kundrabatt, som beskrivs i [Ställa in och underhålla kundrabatter](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates) eller en handelsavdragsrabatt.

Om du använder ett avdrag för kundrabatt måste du utföra följande uppgifter:

- [Ställa in dina kundrabatter](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Godkänna och bearbeta rabatten så du kan använda workbench för avdrag.

Om du använder ett avdrag för handelsavdragsrabatt måste du utföra följande uppgifter:

- Ställa in återfaktureringsrabatter.
- Tillämpa återfaktureringsrabatter.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Konfigurera kundreskontra och avdrag

Systemet registrerar alla avdragshändelser i en anspråksjournal. Därför måste ditt system inkludera en journal som kan användas för detta syfte. Om du inte redan har en anspråksjournal ställer du in den nu. Journalen behövs för att skapa avdrag skapas direkt i workbench för avdrag, på kundkvittnings- eller kundsida.

För att ställa in en ny anspråksjournal för avdrag ska du följa de här stegen.

1. Gå till **Redovisning \> Journalkonfiguration \> Journalnamn**.
1. Välj **Ny** och ange följande fält för det nya journalnamnet:

    - **Namn** – Ange ett unikt namn för anspråksjournalen.
    - **Beskrivning** – Ange en beskrivning av den nya journalen.
    - **Journaltyp** – Välj *Daglig*.
    - **Verifikationsserie** – Tilldela en befintlig nummerserie. Du kan även skapa en ny nummerserie som har företagsomfattning och tilldela den det nya journalnamnet.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. Ställ in fältet **Namn på anspråksjournal** på fliken **Avdrag** på snabbfliken **Allmänt** som det journalnamn som du just skapade.
1. På snabbfliken **Returorder** ställer du in följande fält:

    - **Skapa returorder** – Ange det här alternativet för att ange vad systemet ska göra när ett kvantitetsbaserat anspråk godkänns:

        - *Ja* – Skapa en returorder.
        - *Nej* – Skapa en negativ försäljningsorder.

    - **Skapa utan kopplad faktura** – Välj ett värde för att ange vad systemet ska göra när ett kvantitetsbaserat anspråk godkänns men ingen faktura är kopplad:

        - *Godkänn* – Skapa en returorder.
        - *Varning* – Skapa en returorder, men visa följande varningsmeddelande: "Anspråk är inte kopplat till en faktura".
        - *Fel* – Skapa inte en returorder och visa följande felmeddelande: "Anspråk är inte kopplat till en faktura. Uppdateringen har avbrutits".

    - **Skapa returorder före godkännande av avdrag** – Ställ in alternativet som *Ja* om returorder kan skapas innan anspråket godkänns. Inställningen gäller bara för kvantitetsbaserade anspråk där alternativet **Skapa returorder** är inställt som *Ja*.

### <a name="configure-general-ledger-parameters"></a>Konfigurera parametrar för redovisning

När en anspråksjournal skapas för ett nytt avdrag skapas också två nya kundtransaktioner: en för att kompensera anspråksbeloppet mot den ursprungliga fakturan och en där en kunds skuld motsvarande anspråksbeloppet registreras (eftersom anspråket ännu inte har godkänts). Därför måste du ställa in ditt system så att en enda verifikation kan ha flera kundrader.

För att en enskild verifikation ska ha flera kundrader följer du dessa steg.

1. Gå till **Redovisning \> Redovisningsinställning \> Allmänna redovisningsparametrar**.
1. Ställ in alternativet **Tillåt flera transaktioner inom en verifikation** som *Ja* på snabbfliken **Allmänt** på fliken **Redovisning**.
1. Om du får ett varningsmeddelande väljer du **Stäng** för att godkänna ändringen.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Skapa avdragsorsaker

Systemet kräver att användarna anger en orsak för varje avdrag som de anger direkt i workbench för avdrag, på kundkvittnings- eller kundsidan. Orsaken avgör hur avdraget hanteras när det godkänns.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Avdragsorsaker**.
1. Välj **Ny** för att lägga till en rad till rutnätet och ställ sedan in följande fält för den:

    - **Anspråksorsak** – Ange ett unikt namn för orsaken.
    - **Beskrivning** – Ange en beskrivning av orsaken om du vill ge mer information om hur den ska användas.
    - **Anspråksbas** – Välj anspråksbas för anspråksorsaken:

        - *Prisbaserat* – Skapa en fritextkredit vid godkännande.
        - *Kvantitetsbaserat* – Skapa en negativ försäljningsorder eller returorder vid godkännande.

    - **Returorsakskod** – Välj en returorsakskod som ska användas som värde för **Returorsakskod** för returordern.
    - **Typ** – välj en favdragstyp. Värdet för **Avdragskompensation** för den valda typen används för att ställa in fältet **Avdragskompensation** när ett avdrag eller anspråk skapas. Avdragstyper definieras på sidan **Avdragstyper** (**Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Avdragstyper**).
    - **Bokföringskonto för anspråk** – Det här fältet är endast tillgängligt när fältet **Anspråksbas** är inställt på *Prisbaserat*. När ett prisbaserat anspråk godkänns tilldelar systemet det redovisningskonto du väljer här som värde för **Huvudkonto** för utkastet till fritextkreditfaktura.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Ställa in periodisk uppgift för kvittning av godkända avdrag

För avdrag som skapas med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida kan du ställa in en periodisk uppgift för *Kvittning av godkända avdrag* som automatiskt matchar värden och belopp för avdrag och krediter med matchande **avdrags-ID**.

För att tidsplanera uppgiften går du till **Försäljning och marknadsföring \> Periodiska uppgifter \> Kvittning av godkända avdrag** och ställer in alternativ, filter och tidsplan, precis som med andra typer av periodiska uppgifter.

> [!NOTE]
> Om alternativet **Automatisk kvittning** är inställt som *Ja* på fliken **Kvittning** på sidan **Parametrar för kundreskontra** (**Kundreskontra \> Inställning \> Parametrar för kundreskontra**) kommer den periodiska uppgiften *Kvittning av godkända avdrag* inte att utföra något eftersom krediten kvittas automatiskt.

## <a name="create-a-deduction"></a>Skapa ett avdrag

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Skapa en avdragsjournalpost med hjälp av kundbetalningsjournalen

Följ stegen för att skapa en avdragsjournalpost.

1. Gå till **kundreskontra \> Betalningar \> Kundbetalningsjournal**.
1. Välj **Ny** om du vill lägga till en rad i rutnätet.
1. Välj namnet på journalen i fältet **Namn** för den nya raden.
1. Klicka på **Rader** i åtgärdsrutan.
1. Ange datum, företagskonto och kundkontonummer.
1. I fältet **Faktura** väljer du den faktura som avdraget är associerat med.
1. Ange det belopp som kunden betalade i fältet **Kredit**.
1. Välj **OK** för att bekräfta att beloppet är mindre än totalbeloppet av den markerade transaktionen.
1. Välj en motkontotyp och ett motkonto.
1. Välj **Avdrag** i verktygsfältet ovanför rutnätet.
1. I åtgärdsrutan på sidan **Avdrag** väljer du **Ny** för att lägga till en rad i rutnätet. Fältet **Avdrags-ID** för den nya raden ställs automatiskt in.
1. I fältet **Typ** ska du välja avdragstyp.
1. I fältet **Belopp** anger du beloppet som visas i fältet **Saldo** under avdragslistan. Detta belopp representerar det belopp som kunden drog av från betalningen.
1. Stäng sidan **Avdrag**. Du dirigeras tillbaka till sidan **Kundbetalningar** som nu visar en ny rad för avdraget.
1. Välj **Validera \> Validera** i åtgärdsrutan. Du bör få följande meddelande: ”Journal är OK”.
1. Klicka på **Bokföra** i åtgärdsfönstret.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Skapa avdrag med workbench för avdrag

För att skapa ett avdrag i workbench för avdrag ska du följa dessa steg.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Välj **Underhåll \> Nytt avdrag** i åtgärdsrutan.

    I dialogrutan **Nytt avdrag** ställs fältet **Avdrags-ID** in utifrån den nummersekvens för **Avdrags-ID** som definierats på sidan **Parametrar för hantering av handelsavdrag** (**Försäljning och marknadsföring \> Inställning \> Handelsavdrag \> Parametrar för hantering av handelsavdrag**).

1. Ange följande fält.

    - **Kundkonto** – Välj det kundkonto som avdraget gäller.
    - **Externt anspråksnummer** – Ange kundens anspråksreferens.
    - **Anspråksbelopp** – Ange anspråksbeloppet inklusive moms. Fältet måste vara positivt.
    - **Valuta** – Välj valuta för avdraget. Standardvärdet är den valuta som har angetts för det valda kundkontot.
    - **Anspråksbas** – Välj anspråksbas. Anspråksbasen avgör vilken typ av kredittransaktion som skapas efter det att avdraget eller anspråket har godkänts.

        - *Prisbaserat* – Ett utkast till fritextfaktura skapas.
        - *Kvantitetsbaserat* – En negativ försäljningsorder eller returorder skapas.

    - **Anspråksdatum** – Välj datum för anspråket. Standardvärdet är det aktuella datumet.
    - **Anspråksorsak** – Välj orsakskod som gäller för det aktuella avdraget. Anspråksbasen du har valt påverkar vilka alternativ som gäller. Mer information om hur du skapar och konfigurerar anspråksorsaker som går att välja här finns i avsnittet [Skapa avdragsorsaker](#deduction-reasons) tidigare i det här avsnittet.
    - **Noteringar** – Lägg till eventuella noteringar. När anspråket har godkänts kan godkännaren redigera eller lägga till noteringar.
    - **Skapa anspråksjournal** – Ange om anspråksjournalen ska skapas när anspråket eller avdraget skapas:

        - *Ja* – Systemet skapar och bokför en allmän journal med hjälp av anspråksjournalen som ställs in på sidan **Parametrar för kundreskontra**. (Mer information finns i [Konfigurera kundreskontra och avdrag](#accounts-receivable-deductions) tidigare i det här avsnittet.) När en faktura bifogas anspråket används anspråksjournalen för att minska saldot på den aktuella fakturan. Om anspråket senare avvisas återförs anspråksjournal och kvittningar (om en faktura har kopplats).
        - *Nej* – Ingen anspråksjournal skapas just nu. Den skapas när anspråket godkänns. En faktura kan fortfarande kopplas till det nya anspråket, även om en anspråksjournal inte skapats. Kvittning kan dock inte göras utan anspråksjournal.

1. Välj **OK**.

    Ett nytt avdrag har skapats. Om du ställer in alternativet **Skapa anspråksjournal** som *Ja* bokförs följande transaktioner:

    - **Två nya kundtransaktioner** – En transaktion motbokar anspråksbeloppet mot den ursprungliga fakturan. Den andra transaktionen registrerar en kunds skuld motsvarande anspråksbeloppet, eftersom anspråket ännu inte har godkänts. Den ursprungliga fakturatransaktionen och motbokning av anspråkstransaktionen markeras automatiskt för kvittning när du kopplar fakturan genom att välja **Underhåll \> Bifoga faktura** i åtgärdsrutan.
    - **Två motbokningstransaktioner** – Dessa transaktioner bokförs på **Motbokning avdrag** i redovisningen.
    - **Anspråksjournal** – Välj fliken **Referenser** för att visa anspråksjournal för varje avdrag som visas på workbench för avdrag. Anspråksjournalen visas i fältet **Journalbatchnummer**. Du kan även visa anspråksjournalen på fliken **Avdragshändelser**. Där kommer det att ha värdet *Match* för **Uppdateringstyp**.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Skapa ett avdrag från en kundkvittning

Processen för att skapa ett avdrag från en kundkvittning liknar processen för att skapa ett avdrag i workbench för avdrag. Men kund och fakturavaluta ställs automatiskt in och fakturan kopplas. Du behöver inte välja **Underhåll \> Bifoga faktura** i åtgärdsrutan när du skapar ett anspråk eller avdrag via kvittningssidan för kunder.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund som du vill skapa ett avdrag för.
1. I åtgärdsrutan på fliken **Inkasso** i gruppen **Kvitta** väljer du **Kvitta transaktioner**.
1. Välj fakturan som du vill skapa avdraget mot i dialogrutan **Ställa in transaktioner** på fliken **Översikt**.
1. Välj **Avdrag \> Nytt avdrag** i verktygsfältet.

    I dialogrutan **Nytt avdrag** ställs fältet **Avdrags-ID** in utifrån den nummersekvens för **Avdrags-ID** som definierats på sidan **Parametrar för hantering av handelsavdrag** (**Försäljning och marknadsföring \> Inställning \> Handelsavdrag \> Parametrar för hantering av handelsavdrag**). Fältet **Kundkonto** är inställt på det kundkonto som avdraget gäller.

1. Ange följande fält.

    - **Externt anspråksnummer** – Ange kundens anspråksreferens.
    - **Anspråksbelopp** – Ange anspråksbeloppet inklusive moms. Fältet måste vara positivt.
    - **Valuta** – Välj valuta för avdraget. Standardvärdet är den valuta som har angetts för det valda kundkontot.
    - **Anspråksbas** – Välj anspråksbas. Anspråksbasen avgör vilken typ av kredittransaktion som skapas efter det att avdraget eller anspråket har godkänts.

        - *Prisbaserat* – Ett utkast till fritextfaktura skapas.
        - *Kvantitetsbaserat* – En negativ försäljningsorder eller returorder skapas.

    - **Anspråksdatum** – Välj datum för anspråket. Standardvärdet är det aktuella datumet.
    - **Anspråksorsak** – Välj orsakskod som gäller för det aktuella avdraget. Anspråksbasen du har valt påverkar vilka alternativ som gäller. Mer information om hur du skapar och konfigurerar anspråksorsaker som går att välja här finns i avsnittet [Skapa avdragsorsaker](#deduction-reasons) tidigare i det här avsnittet.
    - **Noteringar** – Lägg till eventuella noteringar. När anspråket har godkänts kan godkännaren redigera eller lägga till noteringar.
    - **Skapa anspråksjournal** – Ange om anspråksjournalen ska skapas när anspråket eller avdraget skapas:

        - *Ja* – Systemet skapar och bokför en allmän journal med hjälp av anspråksjournalen som ställs in på sidan **Parametrar för kundreskontra**. (Mer information finns i [Konfigurera kundreskontra och avdrag](#accounts-receivable-deductions) tidigare i det här avsnittet.) När en faktura bifogas anspråket används anspråksjournalen för att minska saldot på den aktuella fakturan. Om anspråket senare avvisas återförs anspråksjournal och kvittningar (om en faktura har kopplats).
        - *Nej* – Ingen anspråksjournal skapas just nu. Den skapas när anspråket godkänns. En faktura kan fortfarande kopplas till det nya anspråket, även om en anspråksjournal inte skapats. Kvittning kan dock inte göras utan anspråksjournal.

1. Välj **OK**.

    Ett nytt avdrag har skapats. Om du ställer in alternativet **Skapa anspråksjournal** som *Ja* bokförs följande transaktioner:

    - **Två nya kundtransaktioner** – En transaktion motbokar anspråksbeloppet mot den ursprungliga fakturan. Den andra transaktionen registrerar en kunds skuld motsvarande anspråksbeloppet, eftersom anspråket ännu inte har godkänts. Den ursprungliga fakturatransaktionen och motbokning av anspråkstransaktionen markeras automatiskt för kvittning när du kopplar fakturan genom att välja **Underhåll \> Bifoga faktura** i åtgärdsrutan.
    - **Två motbokningstransaktioner** – Dessa transaktioner bokförs på **Motbokning avdrag** i redovisningen.
    - **Anspråksjournal** – Välj fliken **Referenser** för att visa anspråksjournal för varje avdrag som visas på workbench för avdrag. Anspråksjournalen visas i fältet **Journalbatchnummer**. Du kan även visa anspråksjournalen på fliken **Avdragshändelser**. Där kommer det att ha värdet *Match* för **Uppdateringstyp**.

    Du returneras till sidan **Kvitta transaktioner**, som nu visar den valda fakturan som markerad. Knappen **Bokför** är bara tillgänglig om du ställer in alternativet **Skapa anspråksjournal** som *Ja*. Om den är tillgänglig väljer du **Bokför** om du vill minska saldot på fakturan med värdet för **Anspråksbelopp**.

### <a name="create-a-deduction-from-a-customer-page"></a>Skapa ett avdrag från en kundsida

Processen för att skapa ett avdrag från en kundsida liknar processen för att skapa ett avdrag i workbench för avdrag. Kunden ställs dock in automatiskt.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund som du vill skapa ett avdrag för.
1. I åtgärdsrutan, på fliken **Inkasso** i gruppen **Avdrag** markerar du **Skapa avdrag**.

    I dialogrutan **Nytt avdrag** ställs fältet **Avdrags-ID** in utifrån den nummersekvens för **Avdrags-ID** som definierats på sidan **Parametrar för hantering av handelsavdrag** (**Försäljning och marknadsföring \> Inställning \> Handelsavdrag \> Parametrar för hantering av handelsavdrag**). Fältet **Kundkonto** är inställt på det kundkonto som avdraget gäller.

1. Ange följande fält.

    - **Externt anspråksnummer** – Ange kundens anspråksreferens.
    - **Anspråksbelopp** – Ange anspråksbeloppet inklusive moms. Fältet måste vara positivt.
    - **Valuta** – Välj valuta för avdraget. Standardvärdet är den valuta som har angetts för det valda kundkontot.
    - **Anspråksbas** – Välj anspråksbas. Anspråksbasen avgör vilken typ av kredittransaktion som skapas efter det att avdraget eller anspråket har godkänts.

        - *Prisbaserat* – Ett utkast till fritextfaktura skapas.
        - *Kvantitetsbaserat* – En negativ försäljningsorder eller returorder skapas.

    - **Anspråksdatum** – Välj datum för anspråket. Standardvärdet är det aktuella datumet.
    - **Anspråksorsak** – Välj orsakskod som gäller för det aktuella avdraget. Anspråksbasen du har valt påverkar vilka alternativ som gäller. Mer information om hur du skapar och konfigurerar anspråksorsaker som går att välja här finns i avsnittet [Skapa avdragsorsaker](#deduction-reasons) tidigare i det här avsnittet.
    - **Noteringar** – Lägg till eventuella noteringar. När anspråket har godkänts kan godkännaren redigera eller lägga till noteringar.
    - **Skapa anspråksjournal** – Ange om anspråksjournalen ska skapas när anspråket eller avdraget skapas:

        - *Ja* – Systemet skapar och bokför en allmän journal med hjälp av anspråksjournalen som ställs in på sidan **Parametrar för kundreskontra**. (Mer information finns i [Konfigurera kundreskontra och avdrag](#accounts-receivable-deductions) tidigare i det här avsnittet.) När en faktura bifogas anspråket används anspråksjournalen för att minska saldot på den aktuella fakturan. Om anspråket senare avvisas återförs anspråksjournal och kvittningar (om en faktura har kopplats).
        - *Nej* – Ingen anspråksjournal skapas just nu. Den skapas när anspråket godkänns. En faktura kan fortfarande kopplas till det nya anspråket, även om en anspråksjournal inte skapats. Kvittning kan dock inte göras utan anspråksjournal.

1. Välj **OK**.

    Ett nytt avdrag har skapats. Om du ställer in alternativet **Skapa anspråksjournal** som *Ja* bokförs följande transaktioner:

    - **Två nya kundtransaktioner** – En transaktion motbokar anspråksbeloppet mot den ursprungliga fakturan. Den andra transaktionen registrerar en kunds skuld motsvarande anspråksbeloppet, eftersom anspråket ännu inte har godkänts. Den ursprungliga fakturatransaktionen och motbokning av anspråkstransaktionen markeras automatiskt för kvittning när du kopplar fakturan genom att välja **Underhåll \> Bifoga faktura** i åtgärdsrutan.
    - **Två motbokningstransaktioner** – Dessa transaktioner bokförs på **Motbokning avdrag** i redovisningen.
    - **Anspråksjournal** – Välj fliken **Referenser** för att visa anspråksjournal för varje avdrag som visas på workbench för avdrag. Anspråksjournalen visas i fältet **Journalbatchnummer**. Du kan även visa anspråksjournalen på fliken **Avdragshändelser**. Där kommer det att ha värdet *Match* för **Uppdateringstyp**.

## <a name="create-a-credit-note-for-a-customer"></a>Skapa en ny kreditnota för en kund

Du kan sedan, vid behov, skapa en kreditfaktura på kundens konto som representerar rabatt, när en godkänd rabatt finns för kunden. Krediteringen visas sedan i workbench för avdrag, där den kan matchas mot ett avdrag.

Gör så här om du vill skapa en kreditfaktura.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Välj kunden.
1. I åtgärdsrutan på fliken **Inkasso** i gruppen **Kvitta** väljer du **Kvitta transaktioner**.
1. Välj den transaktion som rabatten gäller i dialogrutan **Kvitta transaktioner**.
1. Välj vilken typ av rabattprogram som gäller i verktygsfältet på menyn **Funktioner**.
1. På sidan **Rabatt** på fliken **Översikt** markerar du kryssrutan **Markera** bredvid relevant rabatt-ID.
1. Välj **Funktioner \> Skapa kreditfaktura** i åtgärdsrutan.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Bearbeta ett avdrag i workbench för avdrag

I workbench för avdrag du kan matcha avdrag mot öppna kredittransaktioner, delade avdrag, nekade avdrag och avskrivna avdrag.

Slutför en eller flera av följande procedurer i underavsnitten nedan, beroende på hur du vill bearbeta ett avdrag. Du kan kombinera procedurerna efter behov. Du kan till exempel dela in ett avdrag i två delar och sedan matcha en del mot en kredit men lämna den återstående delen i workbench för att matcha mot en annan kredit senare. Du kan också matcha ett avdrag till en kredit som är mindre än avdragbeloppet, och sedan neka eller skriva av återstående saldo för avdraget.

### <a name="match-a-deduction-to-a-credit"></a>Matcha ett matcha avdrag mot en kreditering

Följ de här stegen för att matcha ett avdrag mot en kredit.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. I avsnittet **Öppna transaktioner** markerar du kryssrutan **Markera** för krediten som ska matchas mot avdraget. Om flera krediter anges kan du välja mer än en kredit att matcha mot avdraget. Om du vill att de krediter som matchar avdragets belopp automatiskt ska väljas av systemet väljer du, i verktygsfältet, ett lämpligt alternativ i menyn **Välj avdragsbelopp**.
1. I åtgärdsrutan väljer du **Underhåll \> Matcha**. Systemet matchar avdraget mot krediten. Om saldo återstår för avdraget visas det i fältet **Resterande belopp** på fliken **Avdrag**.

    > [!NOTE]
    > För avdrag som har skapats med kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida är kommandot **Underhåll \> Match** endast tillgängligt om fältet **Anspråksstatus** har ställts in som *Godkänt*. Det här kommandot kan användas för att manuellt matcha den prisbaserade eller kvantitetsbaserade transaktionen med den associerade krediten i avsnittet **Öppna transaktioner**. Krediten skapas antingen när avdraget godkänns (genom att använda kommandot **Underhåll \> Godkänn avdrag**) eller när det kopplas till en befintlig kredit enligt beskrivningen i [Krediter som skapas utanför processen för att godkänna avdrag](#credits-outside-approval) längre ner i det här avsnittet. Den periodiska uppgiften *Kvitta godkända avdrag* (**Försäljning och marknadsföring \> Periodiska uppgifter \> Kvitta godkända avdrag**) kan även användas för att automatiskt matcha avdrag och krediter med matchande värde för **avdrags-ID** och matchande belopp.

### <a name="split-a-deduction"></a>Dela ett avdrag

Gör på följande sätt för att dela ett avdrag.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. I åtgärdsrutan väljer du **Underhåll \> Dela**.
1. Ange det belopp som ska delas från huvudavdraget i fältet **Dela belopp** i dialogrutan **Dela**. Välj sedan **OK**.
1. På fliken **Avdrag** ser du att en ny post visas för det delade beloppet. Den ursprungliga avdragsposten innehåller resten av avdragssaldot. Nu kan du hantera de två delarna av den ursprungliga rabatten separat.
1. Välj den ursprungliga avdragsposten och sedan fliken **Referenser**. I fältet **Dela belopp** visas beloppet som har delats från det ursprungliga beloppet.

### <a name="attach-an-invoice-to-a-deduction"></a>Koppla en faktura till ett avdrag

Du kan koppla en faktura till ett avdrag om avdraget har skapats med kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida, och om ingen faktura är kopplad till det (d.v.s. om kolumnen **Faktura** är tom).

Koppla en faktura till ett avdrag genom att följa dessa steg.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. Välj **Underhåll \> Koppla faktura** i åtgärdsrutan.
1. Välj en faktura i dialogrutan **Koppla faktura** och sedan **OK**.
1. Följ ett av följande steg i dialogrutan **Kvitta transaktioner** beroende på om en anspråksjournal bokfördes när avdraget skapades:

    - Om en anspråksjournal har bokförts, visar fakturan som du valde och anspråksjournalens kundkredittransaktion en bockmarkering i kolumnen **Markera**. Vald **bokföring** Resterande saldo på den kopplade fakturan minskas med anspråksbeloppet.
    - Om en anspråksjournal inte har bokförts, har ingen transaktion en bockmarkering i kolumnen **Markera**. Eftersom du inte kan motboka en anspråksjournal förrän avdraget har godkänts väljer du **Avbryt**.

### <a name="detach-an-invoice-from-a-deduction"></a>Koppla bort en faktura från ett avdrag

Du kan koppla bort en faktura från ett avdrag om avdraget har skapats med kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida om en faktura är kopplad till det (d.v.s. om kolumnen **Faktura** visar ett fakturanummer) och om fältet **Anspråksstatus** är *Öppen*. Du kan genomföra den här uppgiften eftersom en felaktig faktura har kopplats. Fakturan tas bort från avdraget och återstående saldot uppdateras om det minskats när fakturan kopplades.

Gör så här för att koppla bort en faktura.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. Välj **Underhåll \> Koppla bort faktura** i åtgärdsrutan.

### <a name="approve-a-deduction"></a>Godkänna ett avdrag

Du kan godkänna avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida. Men du kan bara godkänna avdrag där fältet **Anspråksstatus** är *Öppen*.

Gör på följande sätt för att godkänna ett avdrag.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. Välj **Underhåll \> Godkänn avdrag** i åtgärdsrutan.
1. Redigera eller lägg till information för värdet **Notering** i dialogrutan **Godkänn avdrag**.
1. Om avdraget är prisbaserat och en faktura inte har kopplats till det väljer du en artikelmomsgrupp. Vanligtvis anges artikelmomsgruppen på fakturan. Därför måste artikelmomskoden anges när det inte kopplas till en faktura.
1. Välj **OK**.

    I detta läge kan inga ytterligare ändringar göras av avdraget. Om alternativet **Skapa anspråksjournal** har ställts in som *Nej* när avdraget skapades, skapas och bokförs anspråksjournalen när avdraget godkänns. När avdraget har godkänts skapas och öppnas krediten automatiskt. Typen beror på avdragets värde för **Anspråksbas**:

    - *Prisbaserat* – Om avdraget är prisbaserat skapas en fritextfaktura för kundkontot. Du kan lägga till en beskrivning och bokföra krediten. Följande fält fylls i från avdraget när utkastet skapas:

        - **Avdrags-ID** – Det här fältet läggs till i huvudet för att möjliggöra spårning tillbaka till avdraget.
        - **Huvudkonto** – Värdet bestäms av värdet för **Bokföringskonto för anspråk** som anges för avdragsorsaken som tilldelas avdraget.
        - **Artikelmomsgrupp** – Värdet bestäms av den kopplade fakturan eller av det värde som du valde när du godkände avdraget.
        - **Enhetspris** – Värdet är krediten för avdragets anspråksbelopp.
        - **Fakturatext** – Som standard ställs det här fältet in som värdet för avdragets **Noteringar**.

    - *Kvantitetsbaserat* – Om avdraget är kvantitetsbaserat skapas en öppen försäljningsorder eller returorder. Inställningen **Skapa returorder** på sidan **[Parametrar för kundreskontra](#accounts-receivable-deductions)** avgör om en försäljningsorder eller en returorder skapas när avdraget godkänns. Sidan **Kopiera order** visas och filtreras för att visa rader där fältet **Fakturakonto** är inställt på avdragets kundkonto. Följ dessa steg:

        1. På snabbfliken **Fakturor** visar avsnittet **Huvud** försäljningsfakturor där värdet för **Fakturakonto** matchar avdragets kundkonto. Välj en passande försäljningsfaktura.
        1. Avsnittet **Rader** visar rader från den valda försäljningsfakturan. Markera kryssrutan **Markera** för varje rad som du vill kopiera. Alternativt markerar du kryssrutan **Markera alla** för försäljningsordern i avsnittet **Huvud** för att markera alla rader.
        1. Justera värdet för **Kvantitet** för en eller flera rader efter behov.

            Alla rader som du hittills har markerat visas på snabbfliken **Markerade rader eller huvuden som ska kopieras**.

        1. Upprepa de två föregående stegen tills alla rader som behövs visas på snabbfliken **Markerade rader eller huvud som ska kopieras**.
        1. Välj **OK**.

            Den nya returordern öppnas och följande fält ställs automatiskt in:

            - **Avdrags-ID** – Det här fältet läggs till i huvudet för att möjliggöra spårning tillbaka till avdraget.
            - **Returorsakskod** – Som standard ställs det här fältet in på värdet för **Returorsakskod** som anges för avdragorsaken som tilldelas avdraget.

När krediten har fakturerats visas den i avsnittet **Öppna transaktioner** i workbench för avdrag mot tillämpligt **Avdrags-ID** och dess fält **Anspråkstyp** är inställt som *Övriga krediter*. Krediten är tillgänglig tills den kvittas mot avdraget på något av följande sätt:

- Du kvittar det manuellt genom att välja **Underhåll \> Matchning** i åtgärdsrutan.
- Det kvittas automatiskt av periodiska jobbet *Kvitta godkända anspråk* (**Försäljning och marknadsförings \> Periodiska uppgifter \> Kvitta godkända anspråk**).
- Kvittas automatiskt eftersom alternativet **Automatisk kvittning** på fliken **Kvittning** på sidan **Parametrar för kundreskontra** är inställt som *Ja*.

Om du vill visa den kredit som skapas när avdraget har godkänts, kan du även använda knappen **Öppen kredit** i avsnittet **Öppna transaktioner** i workbench för avdrag.

### <a name="create-a-return-order"></a>Skapa en returorder

Du kan skapa en returorder avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida. Följande villkor måste dock uppfyllas:

- Fältet **Anspråksbas** ställs in på *Kvantitetsbaserat*.
- Fältet **Anspråksstatus** är inställt som *Öppen*.
- Alternativet **Skapa returorder** på fliken **Avdrag** på sidan **[Parametrar för kundreskontra](#accounts-receivable-deductions)** är inställt som *Ja*.
- Alternativet **Skapa returorder före godkännande av avdrag** på fliken **Avdrag** på sidan **[Parametrar för kundreskontra](#accounts-receivable-deductions)** är inställt som *Ja*.

Följ dessa steg för att skapa en returorder.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. I åtgärdsrutan väljer du **Underhåll \> Skapa returorder**.
1. Redigera eller lägg till information till befintliga värdet för **Notering** i dialogrutan **Godkänn avdrag** vid behov och välj sedan **OK**.
1. I dialogrutan **Kopiera order** på snabbfliken **Fakturor** visar avsnittet **Huvud** försäljningsfakturor där värdet för **Fakturakonto** matchar avdragets kundkonto. Välj en passande försäljningsfaktura.
1. Avsnittet **Rader** visar rader från den valda försäljningsfakturan. Markera kryssrutan **Markera** för varje rad som du vill kopiera. Alternativt markerar du kryssrutan **Markera alla** för försäljningsordern i avsnittet **Huvud** för att markera alla rader.
1. Justera värdet för **Kvantitet** för en eller flera rader efter behov.

    Alla rader som du hittills har markerat visas på snabbfliken **Markerade rader eller huvuden som ska kopieras**.

1. Upprepa de två föregående stegen tills alla rader som behövs visas på snabbfliken **Markerade rader eller huvud som ska kopieras**.
1. Välj **OK**.

    Den nya returordern öppnas och följande fält ställs automatiskt in:

    - **Avdrags-ID** – Det här fältet läggs till i huvudet för att möjliggöra spårning tillbaka till avdraget.
    - **Returorsakskod** – Som standard ställs det här fältet in på värdet för **Returorsakskod** som anges för avdragorsaken som tilldelas avdraget.

### <a name="deny-a-deduction"></a>Neka ett avdrag

Gör på följande sätt för att neka ett avdrag.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. I åtgärdsrutan väljer du **Underhåll \> Neka**.
1. Välj orsakskoden för nekandet i dialogrutan **Neka** och välj sedan **OK**.
1. I fältet **Visa** under åtgärdsrutan väljer du *Stängt*.

    Det nekade avdraget visas på fliken **Avdrag** och fältet **Resterande belopp** för avdraget ställs in på *0,00*.

    För avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida inträffar följande:

    - På fliken **Referenser** uppdateras fälten i avsnittet **Nekande**.
    - Om du valde att skapa anspråksjournalen när avdraget skapades, och om en faktura har kopplats till avdraget och minskat fakturans saldo, kopplas fakturan bort och resterande saldo på den tidigare kopplade fakturan ökas med det avvisade anspråksbeloppet.
    - Avdragets fält **Status** ställs in som *Stängt*.
    - Avdragets fält **Anspråksstatus** ställs in som *Avvisat*.

Följ dessa steg för att återkalla ett nekande.

1. På fliken **Avdrag** väljer du ett nekat avdrag.
1. Välj **Återkalla nekande** i åtgärdsfönstret.

    För avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida inträffar följande:

    - På fliken **Referenser** uppdateras fälten i avsnittet **Nekande**.
    - Avdragets fält **Status** ställs in som *Öppet*.
    - Avdragets fält **Anspråksstatus** ställs in som *Öppet*.

### <a name="write-off-a-deduction"></a>Skriva av ett avdrag

Följ dessa steg för att skriva av ett avdrag.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** för avdraget som ska bearbetas.
1. I åtgärdsrutan väljer du **Underhåll \> Avskrivning**.
1. Välj orsakskod för avskrivningen i dialogrutan **Avskrivning** och välj sedan **OK**.
1. Välj *Öppet* i fältet **Visa**.

    Det avskrivna avdraget visas på fliken **Avdrag** och fältet **Resterande belopp** för avdraget ställs in på *0,00*.

    För avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida inträffar följande:

    - På fliken **Referenser** uppdateras fälten i avsnittet **Avskrivning**.
    - Om du skapade anspråksjournalen när avdraget skapades, registreras en anspråksjournal för avdragets avskrivningsorsakskod. Du kan visa den här posten på fliken **Avdragshändelser**, där dess värde **Uppdateringstyp** är *Avskrivning*.
    - Avdragets fält **Status** ställs in som *Stängt*.
    - Avdragets fält **Anspråksstatus** ställs in som *Avskrivet*.

Följ dessa steg för att återkalla en avskrivning.

1. På fliken **Avdrag** väljer du ett nekat avdrag.
1. I åtgärdsrutan väljer du **Återkalla avskrivning**.

    För avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, på kundkvittnings- eller kundsida inträffar följande:

    - På fliken **Referenser** uppdateras fälten i avsnittet **Avskrivning**.
    - Om du skapade anspråksjournalen när avdraget skapades, registreras en anspråksjournal för avdragets avskrivningsorsakskod. Du kan visa den här posten på fliken **Avdragshändelser**, där dess värde **Uppdateringstyp** är *Återkalla avskrivning*.
    - Avdragets fält **Status** ställs in som *Öppet*.
    - Avdragets fält **Anspråksstatus** ställs in som *Öppet*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Krediter som skapas utanför processen för att godkänna avdrag

Det här avsnittet gäller enbart avdrag som har skapats med hjälp av kommandot **Nytt avdrag** i workbench för avdrag, kundkvittnings- eller kundsida.

Andra användare kan redan ha skapat en fritextfaktura, returorder eller negativ försäljningsorder för en kunds anspråk utanför processen **Godkänn avdrag**. När det befintliga avdraget godkänns i workbench för avdrag skapas automatiskt ytterligare en fritextfaktura, returorder eller negativ försäljningsorder. I det här avsnittet beskrivs hur du kopplar befintliga krediter till ett avdrag innan avdraget godkänns för att förhindra dubbla krediter.

### <a name="attach-a-credit-to-deduction"></a>Koppla en kredit till avdrag

Det här avsnittet beskriver hur du kan koppla en kredit till ett avdrag från krediten.

Efter att en kredit kopplats till avdraget kan du kan du visa det med knappen **Öppen kredit** i verktygsfältet i avsnittet **Öppna transaktioner** i workbench för avdrag.

När en kredit har fakturerats och avdraget har godkänts visas krediten i avsnittet **Öppna transaktioner** i workbench för avdrag mot tillämpligt **Avdrags-ID** och dess fält **Anspråkstyp** ställs in som *Övriga krediter*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Koppla en fritextfaktura till ett avdrag

Följ dessa steg för att koppla en fritextfaktura till ett avdrag.

1. Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.
1. Välj den tillämpliga fakturan.
1. Välj **Koppla kredit till avdrag** på fliken **Faktura** i åtgärdsfönstret. Den här knappen är endast tillgänglig om fritextfakturans fält **Avdrags-ID** är tomt. Ett tomt fält indikerar att fritextfakturan inte redan är kopplad till ett avdrag.
1. På sidan **Koppla kredit till avdrag** kan du välja *ett* avdrag. Endast öppna *prisbaserade* avdrag kan väljas.
1. Välj **OK**. Fältet **Avdrags-ID** ställs in i fritextfakturans huvud.

#### <a name="attach-a-return-order-to-a-deduction"></a>Koppla en returorder till ett avdrag

Koppla en returorder till ett avdrag genom att följa dessa steg.

1. Gå till **Kundreskontra \> Order \> Alla returorder**.
1. Välj tillämpligt mottaget eller öppet RMA-nummer (Return Merchandise Authorization).
1. Välj **Koppla kredit till avdrag** på fliken **Returorder** i åtgärdsrutan. Knappen är endast tillgänglig om returorderns fält **Avdrags-ID** är tomt. Ett tomt fält indikerar att returordern inte redan är kopplad till ett avdrag.
1. På sidan **Koppla kredit till avdrag** kan du välja *ett* avdrag. Endast öppna *kvantitetsbaserade* avdrag kan väljas.
1. Välj **OK**. Fältet **Avdrags-ID** ställs in i returorderns huvud.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Koppla en försäljningsorder till ett avdrag

Koppla en försäljningsorder till ett avdrag genom att följa dessa steg.

1. Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.
1. Välj tillämplig öppen, levererad eller fakturerad försäljningsorder.
1. Välj **Koppla kredit till avdrag** på fliken **Faktura** i åtgärdsfönstret. Knappen är endast tillgänglig om försäljningsorderns fält **Avdrags-ID** är tomt. Ett tomt fält indikerar att försäljningsordern inte redan är kopplad till ett avdrag.
1. På sidan **Koppla avdrag** kan du välja *ett* avdrag. Endast öppna *kvantitetsbaserade* avdrag kan väljas.
1. Välj **OK**. Fältet **Avdrags-ID** ställs in i försäljningsorderns huvud.

#### <a name="detach-a-deduction-from-a-credit"></a>Koppla bort ett avdrag från en kredit

Om det felaktiga avdraget har kopplats kan du koppla bort det från krediten. Följande villkor måste dock uppfyllas:

- En kredit kopplas till avdraget.
- Fältet **Anspråksstatus** är inställt som *Öppen*.

För att koppla bort ett avdrag från en kredit följer du ett av dessa steg beroende på kredittyp:

- **Fritextfakturor:** Välj en faktura på sidan **Alla fritextfakturor**. Välj sedan **Koppla bort kredit från avdrag** på fliken **Faktura** i åtgärdsfönstret.
- **Returorder:** Välj en order på sidan **Alla returorder**. Välj sedan **Koppla bort kredit från avdrag** på fliken **Returorder** i åtgärdsfönstret.
- **Försäljningsorder:** Välj en order på sidan **Alla försäljningsorder**. Välj sedan **Koppla bort kredit från avdrag** på fliken **Faktura** i åtgärdsfönstret.

### <a name="attach-a-deduction-to-a-credit"></a>Koppla ett avdrag till en kredit

Det här avsnittet beskriver hur du kan koppla ett avdrag till en kredit från avdraget.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Koppla ett avdrag till en fritext-, returorder- eller försäljningsorderkredit

Följ dessa steg för att koppla ett avdrag till en fritext-, returorder- eller försäljningsorderkredit.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Välj tillämpligt öppet avdrag.
1. Välj **Underhåll \> Koppla avdrag till kredit** i åtgärdsrutan. Knappen är endast tillgänglig om fältet **Anspråksstatus** är *Öppet*.
1. På sidan **Koppla kredit** kan du välja *en* kredit. Vilken typ av kredit som visas beror på avdragets värde för **Anspråksbas**:

    - *Prisbaserat* – Sidan visar fritextfakturor för kundkontot där fältet **Avdrags-ID** är tomt. Kundrekvisitioner visas också eftersom fritextfakturan kanske inte är bokförd. Därför kan det saknas ett nummer som kan refereras.
    - *Kvantitetsbaserat* – Typ av kredit som visas beror på inställningen av alternativet **Skapa returorder** på sidan **[Parametrar för kundreskontra](#accounts-receivable-deductions)**:

        - *Ja* – Sidan visar returorder för kundkontot där fältet **Avdrags-ID** är tomt.
        - *Nej* – Sidan visar försäljningsorder för kundkontot där fältet **Avdrags-ID** är tomt.

1. Välj **OK**. Fältet **Avdrags-ID** ställs in i kreditens huvud.

Efter att en kredit kopplats till avdraget kan du kan du visa det med knappen **Öppen kredit** i verktygsfältet i avsnittet **Öppna transaktioner** i workbench för avdrag.

När en kredit har fakturerats och avdraget har godkänts visas krediten i avsnittet **Öppna transaktioner** i workbench för avdrag mot tillämpligt **Avdrags-ID** och dess fält **Anspråkstyp** ställs in som *Övriga krediter*.

#### <a name="detach-a-credit-from-the-deduction"></a>Koppla bort en kredit från ett avdrag

Om den felaktiga krediten har kopplats kan du koppla bort den från avdraget. Välj **Koppla bort avdrag från kredit** i gruppen **Underhåll** i åtgärdsfönstret. Värdet för **Avdrags-ID** tas bort från krediten.

Knappen **Koppla bort avdrag från kredit** är endast tillgänglig om följande villkor uppfylls:

- En kredit kopplas till avdraget.
- Fältet **Anspråksstatus** är inställt som *Öppen*.

## <a name="create-a-one-time-promotion"></a>Skapa ett engångserbjudande

Ibland har du kanske inte en godkänd rabatt att matcha mot ett avdrag. I detta fall kan du använda funktionen *engångserbjudande* för att matcha avdrag till ett handelsavdrag som är associerat till kunden. Funktionen *engångserbjudande* skapar ett nytt handelavdragsavtal och en marknadsföringhändelse för ett engångsbelopp. Sedan matchas engångsbeloppet med avdraget och gör bokföringarna som krävs för att stänga avdraget.

Den här funktionen är användbar om du använder handelsavtal. Mer information om handelsavdrag finns i [Hantering av handelsavdrag](../sales-marketing/trade-allowance.md).

Först måste du ställa in en mall som kan användas för att skapa det nya avtalet om handelsavdrag. Följ dessa steg för att ställa in en mall.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Mallar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fälten anger du informationen som ska visas i avtalen som skapas från mallen.
1. På nabbfliken **Kunder** i fältet **Hierarki** väljer du en hierarkinivå.
1. Markera kunden som har ett omatchat avdrag i hierarkilistan och välj sedan knappen högerpil (**\>**). Kunden läggs till i listan med **Kunder med handelsavdragsavtal**.
1. Ställ in återstående fält efter behov och stäng sedan sidan.
1. Gå till **Försäljning och marknadsföring \> Inställning \> Handelsavdrag \> Parametrar för hantering av handelsavdrag**.
1. Välj namnet på den mall som ska användas för att skapa engångserbjudanden i fältet **Mall för engångserbjudande** på fliken **Översikt**.

Sedan kan du skapa ett engångserbjudande i workbench för avdrag. Följ dessa steg för att skapa ett engångserbjudande.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. Markera kryssrutan **Markera** bredvid avdraget som ska bearbetas.
1. Välj **Underhåll \> Kvittningsavdrag som engångserbjudande** i åtgärdsfönstret.
1. I dialogrutan **Engångserbjudande** följer du dessa steg för att associera avdraget till ett eller flera budgetmedel:

    1. Välj **Nytt** och välj sedan medel-ID i fältet **Medel-ID**. Upprepa detta steg för att lägga till så många medel som du behöver.
    1. Ange den procentandel av avdraget som ska tilldelas medel i fältet **Procent** bredvid varje medel-ID. Beloppen som du anger i fälten **Procent** måste sammanlagt bli 100.

1. Välj **OK**. Systemet skapar ett nytt avtal om handelsavdrag som har ett engångsbelopp för marknadsföringshändelse och matchar engångsbeloppet mot avdraget.

## <a name="do-a-mass-update-of-deductions"></a>Gör en massuppdatering av avdrag

Om du måste göra samma ändring i flera avdrag, kan du välja de avdrag och göra en massuppdatering av deras respektive fält.

Följ dessa steg för att göra en massuppdatering.

1. Gå till **Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**.
1. I fältet **Visa** nedanför åtgärdsrutan väljer du vilken typ av avdrag som ska visas.
1. Markera kryssrutan bredvid varje avdrag som du ska uppdatera. Välj sedan **Underhåll \> Massuppdatering** i åtgärdsrutan.
1. I dialogrutan **Massuppdatering** visas de valda avdragen. Uppdatera fälten efter behov och välj **OK** för att godkänna ändringarna.
