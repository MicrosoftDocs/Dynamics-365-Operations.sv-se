---
title: Skapa och bearbeta avvikelser
description: Detta ämne beskriver hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 933efff1be545816504ab31f7a3135bf79996d7b8a50dac9fcc5b994e57a8965
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747971"
---
# <a name="create-and-process-nonconformances"></a>Skapa och bearbeta avvikelser

[!include [banner](../../includes/banner.md)]

Detta ämne beskriver hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder. Vanligtvis utförs avvikelsehanteringen av en kvalitetsansvarig. En förutsättning är att du har en kvalitetsorder tillgänglig. (Mer information om hur du skapar en kvalitetsorder finns i [Inspektera kvaliteten på varorna](inspect-quality-goods.md) .)

Innan en användare kan bearbeta godkännandet av en avvikelse måste han eller hon tilldelas en medarbetare i fältet **Person** på sidan **Användare**. Innan användaren kan använda dokumentnoteringarna måste alternativet **Aktivera dokumenthantering** dessutom ställas in på *Ja* bland användarens alternativ.

## <a name="create-a-nonconformance"></a>Skapa en avvikelse

Gör så här om du vill skapa en avvikelse.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa avvikelse** väljer du i fältet **Problemtyp** den typ av problem som hittats i samband med inspektion.
1. Välj **OK**.

## <a name="approve-or-reject-a-nonconformance"></a>Godkänn eller avvisa en avvikelse

Om du vill godkänna eller avvisa en avvikelse följer du dessa steg:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till en korrigering för avvikelser som är godkända.

1. I åtgärdsfönstret väljer du **Funktioner \> Godkänn en avvikelse** om du vill godkänna avvikelsen, eller **Funktioner \> Vägra avvikelse** om du vill avisa den. Du kan koppla godkända avvikelser till [relaterade funktioner](../quality-operations.md). På det här sättet kan du registrera arbete som utförs som en del av avvikelsehanteringen och bearbetningen av korrigeringshanteringen.
1. Du uppmanas att bekräfta ditt val. Klicka på **Ja** när du vill fortsätta.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Lägg till åtgärder och annan information till avvikelser

När du har skapat en avvikelse kan du börja lägga till relaterade åtgärder och ange ytterligare information om dessa åtgärder. Du kan bara lägga till relaterade funktioner för avvikelser som är godkända.

Förutom den grundläggande informationen kan du lägga till följande information till en funktion:

- **Artiklar** – Du kan skapa en lista över artiklar som förbrukas för att utföra korrigeringen. Artiklarna kan till exempel vara produkter som krävs för att reparera utrustning eller ingredienser som krävs för att omarbeta en färdig produkt.
- **Kvalitetsavgifter** – Du kan skapa en lista med avgifter som uppstår eller debiteras externa källor.
- **Tidrapport** – Du kan skapa en logg över den tid som varje medarbetare ägnar åt funktionen.

De återstående inställningarna är valfria. Kostnaden för respektive artikel, kvalitetsavgifter och tidrapporten summeras och visas i funktionen. Du kan inte redigera fältet **Kostnad** direkt i funktionen.

### <a name="create-an-operation-for-a-nonconformance"></a>Skapa en funktion för en avvikelse

Gör så här om du vill skapa en funktion för en avvikelse:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.

1. Klicka på **Relaterade funktioner** i åtgärdsfönstret.
1. På sidan **Relaterade funktioner** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Åtgärd** – Välj koden för den åtgärd som ska utföras för avvikelsen.
    - **Orsak** – Ange en detaljerad beskrivning som förklarar varför funktionen behövs.
    - **Försäljningsorder** – Om den valda funktionskoden är relaterad till försäljningsordertypen ska du välja den försäljningsorder som du kopplar funktionen till.
    - **Inköpsorder** – Om den valda funktionskoden är relaterad till inköpsordertypen ska du välja den inköpsorder som du kopplar funktionen till.

1. Stäng sidorna.

### <a name="add-items-to-an-operation"></a>Lägga till artiklar i en funktion

Följ de här stegen om du vill lägga till artiklar i en funktion.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.

1. Klicka på **Relaterade funktioner** i åtgärdsfönstret.
1. På sidan **Relaterade åtgärder** markerar du den funktion som du vill lägga till artiklar i.
1. Klicka på **Artiklar** i åtgärdsfönstret.
1. På sidan **Relaterade funktioner** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Artikelnummer** – Välj den produkt som ska förbrukas under den markerade funktionen.
    - **Kvantitet** – Ange antalet artiklar som ska förbrukas.

    > [!NOTE]
    > Du kan visa kostnaden för artikeln i fältet **Kostnad** på fliken **Allmänt**. Kostnaden som visas kommer från kostnaden som ställs in på sidan **Frisläppt produkt**. Kostnaden kan inte uppdateras direkt på sidan **Relaterad funktionsartikel**. Kostnaden för alla artiklar som läggs till på sidan **Relaterade funktionsartiklar** läggs till automatiskt i fältet **avgift** på sidan **Relaterade funktioner**.

1. Upprepa föregående steg för varje ytterligare artikel som du måste lägga till.
1. Stäng sidorna.

### <a name="add-quality-charges-to-an-operation"></a>Lägg till kvalitetsavgifter för en funktion

Följ de här stegen om du vill lägga till kvalitetsavgifter i en funktion.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.

1. Klicka på **Relaterade funktioner** i åtgärdsfönstret.
1. På sidan **Relaterade funktioner** markerar du den funktion som du vill lägga till kvalitetsavgifter i.
1. Välj **Kvalitetsavgifter** i åtgärdsfönstret.
1. På sidan **Relaterade funktionsavgifter** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Debiteringskod** – Välj den kvalitetsavgift som du vill lägga till.
    - **Beskrivning** – Ange en detaljerad beskrivning av avgiften.
    - **avgiftsvärde** – Ange avgiftsbeloppet.

1. Upprepa föregående steg för varje ytterligare avgift som du måste lägga till.
1. Stäng sidorna.

> [!NOTE]
> Beloppet i fältet **Avgiftsvärde** summeras automatiskt för samtliga kvalitetsavgifter och adderas till alla andra eventuella belopp i fältet **Kostnad** på sidan **Relaterade funktioner**.

### <a name="create-a-timesheet-on-an-operation"></a>Skapa en tidrapport för en funktion

Följ de här stegen om du vill lägga till en tidrapport i en funktion.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.

1. Klicka på **Relaterade funktioner** i åtgärdsfönstret.
1. På sidan **Relaterade funktioner** markerar du den funktion som du vill lägga till en tidrapport i.
1. Klicka på **Tidrapport** i åtgärdsfönstret.
1. På sidan **Relaterade funktionstidrapporter** väljer du i åtgärdsfönstret **Ny** för att kunna lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Datum** – Ange det datum då arbetet utfördes. Som standard är detta fält inställt på det aktuella datumet.
    - **Medarbetare** – Välj den medarbetare som utfört arbetet. Som standard ställs det här fältet in på den medarbetare som tilldelats den aktuella användaren.
    - **Funktionstimmar** – Ange antalet timmar som har arbete pågick på den valda funktionen.
    - **Fakturerades** – Markera den här kryssrutan om tiden har debiterats en kund eller leverantör på en faktura.

    > [!NOTE]
    > Du kan visa kostnaden i fältet **Kostnad** på fliken **Allmänt**. Kostnaden beräknas med den kurs som du definierar på sidan **Lagerhanteringsparametrar**.

1. Upprepa föregående steg för varje ytterligare tidrapportrad som du måste lägga till.
1. Stäng sidorna.

> [!NOTE]
> Beloppet i fältet **Kostnad** summeras automatiskt för samtliga tidrapportrader och adderas till alla andra eventuella belopp i fältet **Kostnad** på sidan **Relaterade funktioner**.

## <a name="add-a-correction-to-a-nonconformance"></a>Lägg till en korrigering av en avvikelse

Om du vill lägga till en korrigering i en avvikelse gör du följande:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till en korrigering för avvikelser som är godkända.

1. I åtgärdsfönstret väljer du **Korrigeringar**.
1. I åtgärdsfönstret på sidan **Korrigeringar** väljer du **Ny** för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Diagnos** – Välj den diagnostyp som identifierar den typ av korrigering som du skapar.
    - **Medarbetare** – Välj den person som är ansvarig för korrigeringen.
    - **Korrigeringsprioritet** – Välj ett alternativ för att ange hur korrigeringen ska prioriteras (*Låg*, *Normal* eller *Hög*).
    - **Begärt datum** – Ange det datum då korrigeringsåtgärden begärdes.
    - **Planerat datum** – Ange det datum då korrigeringen förväntas vara slutförd.
    - **Kortsiktig lösning** – Markera den här kryssrutan om korrigeringsåtgärden endast korrigerar avvikelsen under en kort tid.

1. Stäng sidorna.

## <a name="mark-a-correction-as-completed"></a>Markera en korrigering som slutförd

Om du vill markera en avvikelse som slutförd gör du följande:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.

    > [!NOTE]
    > Du kan bara lägga till en korrigering för avvikelser som är godkända.

1. I åtgärdsfönstret väljer du **Korrigeringar**.
1. På sidan **Korrigeringar** i rutnätet väljer du den korrigering som du vill markera som slutförd.
1. Välj **Markera som slutförd** i åtgärdsfönstret.
1. Du uppmanas att bekräfta ditt val. Välj **OK** om du vill fortsätta. **Slutförandedatum och -tid** ställs in på aktuellt datum och aktuell tid, och kryssrutan **Slutförd** markeras.
1. Stäng sidan.

## <a name="reopen-a-completed-correction"></a>Öppna upp en slutförd korrigering på nytt

Gör så här om du vill öppna upp en slutförd korrigering på nytt:

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.
1. Markera den avvikelse som du vill uppdatera i listan.
1. I åtgärdsfönstret väljer du **Korrigeringar**.
1. På sidan **Korrigeringar** i rutnätet väljer du den korrigering som du vill öppna på nytt.
1. Välj **Öppna på nytt** i åtgärdsfönstret.
1. Du uppmanas att bekräfta ditt val. Välj **OK** om du vill fortsätta. Värdet rensas från fältet **Slutförandedatum och -tid**, och kryssrutan **Slutförd** avmarkeras.
1. Stäng sidan.

Du kan nu göra ytterligare redigeringar eller uppdateringar av korrigeringen. När du är klar kan du markera korrigeringen som slutförd igen.

## <a name="close-a-nonconformance"></a>Stäng en avvikelse

Gör så här om du vill stänga en avvikelse.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.
1. Välj en kvalitetsorder i rutnätet.
1. I åtgärdsfönstret väljer du **Frågor \> Avvikelser**.
1. På sidan **Avvikelser** markerar du avsedd avvikelse i rutnätet.
1. I åtgärdsfönstret väljer du **Funktioner \> Stäng avvikelse**.
1. Du uppmanas att bekräfta ditt val. Klicka på **Ja** när du vill fortsätta.
1. Stäng sidorna.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](../quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](../enable-quality-management.md)
- [Medarbetare som ansvarar för godkännande av avvikelse](../quality-responsible-workers.md)
- [Karantänzoner för avvikelser](../quality-quarantine-zones.md)
- [Diagnostyper för avvikelser](../quality-diagnostic-types.md)
- [Kvalitetsavgifter avvikelser](../quality-charges.md)
- [Funktioner för avvikelser](../quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
