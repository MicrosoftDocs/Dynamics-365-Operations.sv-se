---
title: Bearbeta, granska och bokföra rabatter
description: I det här avsnittet beskrivs hur du bearbetar dina rabatthanteringserbjudanden, beräknar deras rabatter, granskar transaktionerna som genereras, bokför transaktioner och granskar bokföringarna.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5188fa271cd9eb24140a9edcf507a3da72b61074
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020541"
---
# <a name="process-review-and-post-rebates"></a>Bearbeta, granska och bokföra rabatter

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du bearbetar dina rabatthanteringserbjudanden, beräknar deras rabatter, granskar transaktionerna som genereras, bokför transaktioner och granskar bokföringarna.

## <a name="change-the-status-of-a-deal"></a>Ändra status på ett erbjudande

Du kan tilldela en status till varje erbjudande för att spåra det. Denna status är bara avsett för information.

1. Välj ett erbjudande (till exempel på sidan [**Alla rabatthanteringserbjudanden**](rebate-management-deals.md)).
1. I åtgärdsfönstret på fliken **Rabatthanteringserbjudanden** i gruppen **Underhåll** väljer du **Ändra status**.
1. I dialogrutan **Ändra status**, ange fältet **Rabattstatus** till en ny status.
1. Välj **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Beräkna inköpspriser för FIFO

Den periodiska uppgiften **Beräkna FIFO-inköpspris** måste köras för att beräkna rabatter för erbjudanden där fältet [erbjudanden](rebate-management-deals.md) där fältet **Prisbas** anges till *FIFO*. Systemet använder en regel för först in, först ut (FIFO) för att beräkna värdet på det lager som säljs. Det här värdet används sedan för att beräkna leverantörsrabatterna.

Gå till **Rabatthantering \> Periodiska uppgifter \> Beräkna FIFO-inköpspris**. Välj **OK** för att köra beräkningen i dialogrutan som visas.

## <a name="process-rebate-management-deals"></a>Bearbeta rabatthanteringserbjudanden

När du bearbetar ett erbjudande beräknar systemet alla relevanta rabatter och royalties som har ställts in. Endast valda erbjudanden som har beräkningsperioder som är klara att beräknas och som har statusen *Aktiv* kommer att bearbetas. När bearbetningen är klar genererar systemet en uppsättning transaktioner som du kan granska och sedan bokföra.

> [!NOTE]
> I alla fall bearbetas rabatter på den nivå som anges i varje erbjudandes **Stäm av efter** genom inställning ( *Avtal* eller *Rad*). Du kan göra beräkningar med en rad endast för erbjudanden där **Stäm av efter** anges till *Rad*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Bearbeta alla rader för en eller flera erbjudanden

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Markera raden för varje erbjudande som du vill behandla (eller öppna det erbjudande som du vill behandla).
1. I åtgärdsfönstret, på fliken **Rabatthanteringsinformation** i gruppen **Generera**, välj ett av följande kommandon:

    - **Process \> Etablera** – Etablera en uppsättning upplupningar för varje relevant rabattavtal, men lägg inte upp dem.
    - **Process \> Rabatthantering** – Behandla en serie transaktioner som ger rabatten för varje erbjudande.
    - **Process \> Skriv av** – Omvänd tidigare bokförda transaktioner för att avskriva dem så att nya rabattransaktioner kan beräknas.

1. I dialogrutan som visas, ange fälten **Från datum** och **Till datum** för att definiera datumintervallet för beräkningen.
1. Klicka på **OK** om du vill köra beräkningen.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Bearbeta en eller flera specifika avtalsrader för ett valt erbjudande

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Öppna det erbjudande som du vill bearbeta en rad från.
1. Välj fliken **Rader** i det övre högra hörnet.
1. På snabbfliken **Rabatthantering** markerar du raden för varje avtalsrad som du vill bearbeta.
1. Välj ett av följande kommandon i verktygsfältet på snabbfliken **Rabatthantering**. (Dessa kommandon är bara tillgängliga för erbjudanden där fältet **Stäm av** efter är inställt på *Rad*.)

    - **Process \> Etablera** – Etablera en uppsättning upplupningar för varje relevant erbjudanderad, men lägg inte upp dem.
    - **Process \> Rabatthantering** – Behandla en serie transaktioner som ger rabatten för varje erbjudanderad.
    - **Process \> Skriv av** – Omvänd tidigare bokförda transaktioner för att avskriva dem så att nya rabattransaktioner kan beräknas.

1. I dialogrutan som visas, ange fälten **Från datum** och **Till datum** för att definiera datumintervallet för beräkningen.
1. Klicka på **OK** om du vill köra beräkningen.

### <a name="process-deals-using-a-batch-job"></a>Bearbeta erbjudanden med hjälp av ett batchjobb

Istället för att bearbeta specifika avtal eller rader kan du köra ett batchjobb för att bearbeta flera erbjudanden samtidigt. Om du vill kan du även använda postfilter och/eller ställa in ett återkommande schema. Om du vill bearbeta erbjudanden genom att använda ett batchjobb följer du dessa steg.

1. Gör något av följande:

    - Gå till **Rabatthantering \> Periodiska uppgifter \> Process \> Etablera** för att tillhandahålla en uppsättning upplupningar för varje relevant erbjudande, men utan att lägga upp dem.
    - Gå till **Rabatthantering \> Periodiska uppgifter \> Process \> Rabatthantering** för att bearbeta en serie transaktioner som ger rabatten för varje transaktion.
    - Gå till **Rabatthantering \> Periodiska uppgifter \> Process \> Skriv av** för att omvända tidigare bokförda transaktioner för att avskriva dem så att nya rabattransaktioner kan beräknas.

1. I dialogrutan som visas, på snabbfliken **Parametrar** i avsnittet **Period**, ange fälten **Från datum** och **Till datum** för att definiera datumintervallet för transaktioner för beräkningen.
1. I avsnittet **Garantiperiod** ange **Från datum** och **Till datum** för att definiera datumintervallet för garantier för beräkningen.
1. På snabbfliken **Poster som ska ingå** kan du ställa in filter för att begränsa den uppsättning erbjudanden som batchjobbet kommer att bearbetas. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. På snabbfliken **Kör i bakgrunden** kan du ställa batchbearbetning och schemaläggningsalternativ efter behov. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. Välj **OK** för att köra och/eller planera beräkningen.

## <a name="view-and-edit-rebate-management-transactions"></a>Visa och redigera transaktioner för rabatthantering

När du bearbetar en eller flera affärer skapar systemet transaktioner som du kan visa och kanske redigera innan du bokför dem.

1. Gör något av följande:

    - Välj erbjudandet att visa transaktioner för (till exempel på [**Alla rabatthanteringserbjudanden**](rebate-management-deals.md)). I åtgärdsfönstret, på fliken **Rabatthanteringserbjudanden** i gruppen **Transaktioner**, välj **Transaktioner** eller **Garantitransaktioner**, beroende på vilken typ av transaktion som du vill visa.
    - Öppna ett erbjudande (till exempel [sidan **Alla rabatthanteringserbjudanden**](rebate-management-deals.md)) för att visa dess detaljer. På snabbfliken **Rabatthantering**, välj erbjudanderaden att visa transaktioner för. Sedan i verktygsfältet, välj **Transaktioner** eller **Garantitransaktioner**, beroende på vilken typ av transaktion som du vill visa. (Dessa knappar är bara tillgängliga för erbjudanden där fältet **Stäm av** efter är inställt på *Rad*.)

1. Sidan **Transaktion för rabatthanteringsdatum** eller **Transaktion rabatthanteringsgaranti** visas. Det innehåller ett rutnät där varje rad representerar en samling transaktioner från en enda rabatt- eller garantiperiod. Välj en rad i rutnätet och välj sedan i åtgärdsfönstret **Källtransaktioner** för att visa de transaktioner som tillhör den raden
1. På sidan som öppnas visar en lista över transaktionerna av den valda typen som tillhör den valda raden. Varje transaktion ger relevanta detaljer, beroende på transaktionstyp. För garantitransaktioner kan du bara visa listan. För andra typer av transaktioner kan du utföra följande åtgärder på den här sidan:

    - Om du vill kontrollera det totala värdet av alla begärda transaktioner på sidan visar du fältet **Begärt belopp**.
    - Om du vill visa mer information om en transaktion markerar du den och väljer sedan fliken **Allmänt**, **Ekonomisk dimension** eller **Dimension**.
    - Om du vill visa eventuella reduceringar väljer du **Reduceringstransaktioner** i åtgärdsfönstret. Mer information finns i [princip för rabattreducering](rebate-reduction-principle.md).
    - Om du vill markera transaktioner som antingen anspråk eller ej gjort anspråk om du använder en skadeprocess väljer du relevanta rader och väljer sedan ett av följande kommandon i åtgärdsfönstret. (Du aktiverar skadeprocesser på [sidan **Parametrar för rabatthantering**](rebate-management-parameters.md).)

        - **Uppsättning gjort anspråk \> Alla** – Markera alla transaktioner som begärdes.
        - **Uppsättning gjort anspråk \> Valda** – Markera de valda transaktionerna som begärdes.
        - **Uppsättning ej anspråk \> Alla** – Markera alla transaktioner som ej begärdes.
        - **Uppsättning ej anspråk \> Valda** – Markera de valda transaktionerna som ej begärdes.

    - Om du vill bokföra anspråket för en eller flera rader markerar du de relevanta raderna och väljer sedan **Bokför** i åtgärdsfönstret. Knappen **Bokför** är bara tillgänglig för rabattransaktioner. Det är inte tillgängligt för avsättning och avskrivningstransaktioner. I dialogrutan **Bokför** ställs fälten **Från datum** och **Till datum** automatiskt in. Ange fältet **Bokföringsdatum** och välj **OK**.
    - Om du vill justera beloppet som visas för en öppen eller icke-bokförd transaktion markerar du transaktionen och följer sedan ett av följande steg:

        - Redigera värdet i fältet **Korrigerat belopp**.
        - I åtgärdsfönstret, välj **ange korrigering**. Ange sedan ett värde i listrutan som visas i fältet **Korrigerat belopp**.

> [!NOTE]
> När du behandlar nästa period kommer transaktionslistan att innehålla alla icke-begärda transaktioner från föregående bokföring, plus eventuella nya transaktioner för vald period.

## <a name="post-rebates-transactions"></a>Bokför rabattransaktioner

Om du vill bokföra värdet av rabatterna och avdragen måste du köra bokföringsprocessen om du inte har ställt in systemet för att bokföra dem automatiskt.

### <a name="set-up-the-system-to-post-all-transactions-automatically"></a>Ställ in systemet att bokföra alla transaktioner automatiskt

För att ställa in ditt system för att bokföra alla transaktioner så snart de genereras, slå på **Bokför journaler automatiskt** och/eller alternativet **Boka automatiskt fritextfakturor** på sidan **Parametrar för rabatthantering**. Mer information finns i [parametrar för rabatthantering](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Bokför transaktioner för alla rader för en eller flera erbjudanden

Om du inte använder automatisk bokföring följer du dessa steg för att granska och bokföra de genererade transaktionerna för alla rader för ett eller flera erbjudanden efter att du bearbetat relevanta erbjudanden.

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Markera raden för varje erbjudande som du vill bokföra (eller öppna det erbjudande som du vill bokföra).
1. I åtgärdsfönstret, på fliken **Rabatthanteringsinformation** i gruppen **Generera**, välj ett av följande kommandon:

    - **Bokför \> Etablera** – Bokför tillgängliga periodiseringstransaktioner som du har skapat.
    - **Bokför \> Rabatt** – Bokför tillgängliga rabattransaktioner som du har skapat.
    - **Bokför \> Skriva av** – Bokför tillgängliga avskrivningstransaktioner som du har skapat.

1. I dialogrutan, ange fältet **Bokföringsdatum**. Ange sedan fälten **Från datum** och **Till datum** för att definiera datumintervallet för de transaktioner som måste bokföras.
1. Välj **OK** när du vill bokföra transaktioner.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Boka transaktioner för en eller flera specifika avtalsrader för ett valt erbjudande

Om du inte använder automatisk bokföring följer du dessa steg för att granska och bokföra de genererade transaktioner för en eller flera specifika transaktionsrader för en vald transaktion.

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Öppna affären som har en rad som du vill bokföra transaktioner för.
1. Välj fliken **Rader** i det övre högra hörnet.
1. På snabbfliken **Rabatthantering** markerar du raden för varje avtalsrad som du vill bokföra.
1. Välj ett av följande kommandon i verktygsfältet på snabbfliken **Rabatthantering**. (Dessa kommandon är bara tillgängliga för erbjudanden där **Stäm av** efter är inställt på *Rad*.)

    - **Bokför \> Etablera** – Bokför tillgängliga periodiseringstransaktioner som du har skapat.
    - **Bokför \> Rabatt** – Bokför tillgängliga rabattransaktioner som du har skapat.
    - **Bokför \> Skriva av** – Bokför tillgängliga avskrivningstransaktioner som du har skapat.

1. I dialogrutan, ange fältet **Bokföringsdatum**. Ange sedan fälten **Från datum** och **Till datum** för att definiera datumintervallet för de transaktioner som måste bokföras.
1. Välj **OK** när du vill bokföra transaktioner.

### <a name="post-transactions-using-a-batch-job"></a>Bokföra transaktioner med hjälp av ett batchjobb

Istället för att bokföra transaktioner för specifika avtal eller rader kan du köra ett batchjobb för att bokföra transaktioner för flera erbjudanden samtidigt. Om du vill kan du även använda postfilter och/eller ställa in ett återkommande schema. Om du vill bokföra transaktioner genom att använda ett batchjobb följer du dessa steg.

1. Gör något av följande:

    - Gå till **Rabatthantering \> Periodiska uppgifter \> Bokför \> Etablera** för att bokföra tillgängliga periodiseringstransaktioner som du har skapat.
    - Gå till **Rabatthantering \> Periodiska uppgifter \> Bokför \> Rabatthantering** för att bokföra tillgängliga rabattransaktioner som du har skapat.
    - Gå till **Rabatthantering \> Periodiska uppgifter \> Bokför \> Rabatthantering** för att bokföra tillgängliga rabattransaktioner som du har skapat.

1. I dialogrutan som visas, på snabbfliken **Parametrar** i avsnittet **Period**, ange fältet **Bokföringsdatum**. Ange sedan fälten **Från datum** och **Till datum** för att definiera datumintervallet för de transaktioner som måste bokföras. 
1. I avsnittet **Garantiperiod** ange **Från datum** och **Till datum** för att definiera datumintervallet för de garantier som ska bokföras.
1. På snabbfliken **Poster som ska ingå** kan du ställa in filter för att begränsa den uppsättning erbjudanden som batchjobbet kommer att bearbetas. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. På snabbfliken **Kör i bakgrunden** kan du ställa batchbearbetning och schemaläggningsalternativ efter behov. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. Välj **OK** för att köra och/eller planera beräkningen.

## <a name="review-rebate-management-journals"></a>Granska journaler för rabatthantering

När transaktionerna har bokförts kan du granska de journaler, dokument eller artiklar som de resulterar i. Måltransaktionerna för rabatter och royalties baseras på betalningstypen som har angetts i bokföringsprofilen och rabattens utdatatyp. Om till exempel rabattutleveransen är inställd på *Artikel* skapas en försäljningsorder och kan visas via måltransaktionerna. Alternativt, om betalningen är inställd på att använda leverantörsreskontra, skapas en leverantörsfaktura för leverantören som är inställd på kunden för kundrabatter.

Granska journalposterna som är kopplade till ett rabatthanteringserbjudande genom att följa dessa steg.

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Välj erbjudandet som du vill granska journalposter för.
1. I åtgärdsfönstret, på fliken **Rabatthanteringserbjudanden** i gruppen **Transaktioner**, välj **Transaktioner** eller **Rabattransaktioner**, beroende på vilken typ av transaktioner som du vill visa.
1. Kontrollera att fältet **Visa** är inställt på *Alla* eller *Bokfört*.
1. Sök efter och välj den transaktionssamling som du vill kontrollera och välj sedan en av följande knappar i åtgärdsfönstret. (Dessa knappar är endast tillgängliga när det finns relevanta bokföringar för den valda transaktionssamlingen.)

    - **Måltransaktioner** – Granska relevanta journaler och andra typer av dokument som genererades av den valda affären.
    - **Artiklar** – Granska relevanta artiklar som genererades av den valda affären.

1. En lista över relevanta journaler, dokument eller artiklar visas. Om du vill visa mer information om en journal, ett dokument eller ett objekt väljer du dess rad och väljer sedan i åtgärdsfönstret **Visa information**.
