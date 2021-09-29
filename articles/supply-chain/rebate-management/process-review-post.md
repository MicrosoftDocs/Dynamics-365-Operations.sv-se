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
ms.openlocfilehash: db3c7561a7249930def2e519f3b6718c429fa3ba
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500485"
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

## <a name="create-source-transactions"></a>Skapa källtransaktioner

Du kan skapa försäljnings- eller inköpsorder som har källtransaktioner, antingen före eller efter att du skapar ett tillämpligt rabatthanteringserbjudande.

Du kan ställa in varje erbjudanderad så det automatiskt skapas en rabattreservering genom att bokföra antingen leverans eller faktura för en försäljningsorder eller inköpsorder. Ställ in fältet **Transaktionstyp** för erbjudanderaden som *Leverans* eller *Faktura* och ställ in alternativet **Bearbeta vid bokföring** som *Ja*. Om fältet **Transaktionstyp** är inställt på *Order*, inaktiveras bearbetning vid bokföringen. För källtransaktioner som skapades efter att ett erbjudande aktiverats, kan du fortfarande bearbeta reserveringarna enligt beskrivningen i avsnittet [Bearbeta rabatthanteringserbjudande](#process-deals) senare i det här avsnittet.

### <a name="enable-price-details"></a>Aktivera prisinformation

Innan du kan skapa källtransaktioner måste du aktivera alternativet **Aktivera prisinformation** för kundreskontra.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. På fliken **Priser** på snabbfliken **Prisinformation**, anger du alternativet **Aktivera prisinformation** som *Ja*.

### <a name="create-a-source-transaction"></a>Skapa en källtransaktion

Följ dessa steg för att skapa en källtransaktion.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Välj **Ny**.

    Om du vill efterlikna det sätt som rabattanspråk genereras måste du skapa en försäljningsorder, där produkt och kvantitet berättigar kunden för en rabatt.

1. Ange eller välj en kund som ska berättigas till rabatterbjudande i fältet **Kundkonto**.
1. Skapa försäljningsordern genom att välja **OK**.
1. På snabbfliken **Försäljningsorderrader** lägger du till en rad och ställer in följande fält för den:

    - **Artikelnummer** – Ange en artikel som berättigar till en rabatt.
    - **Kvantitet** – Ange en kvantitet som berättigar till ett rabatterbjudande som omfattar en rad där fältet **Bas** är inställt på *Kvantitet*.
    - **Enhetspris** – Ange ett pris som berättigar till ett rabatterbjudande som omfattar en rad där fältet **Bas** är inställt på *Värde*.
    - **Plats** – Välj en plats där produkten är tillgänglig och som berättigar till ett rabatterbjudande.
    - **Distributionslager** – Välj ett distributionslager där produkten är tillgänglig och som berättigar till ett rabatterbjudande.

1. På snabbfliken **Försäljningsorderrader**, i verktygsfältet, väljer du **Försäljningsorderrad \> Prisinformation**. Kommandot är endast tillgängligt om du har aktiverat prisinformation enligt föregående avsnittet.
1. På sidan **Prisinformation** markerar du snabbfliken **Rabatthantering**. På snabbfliken visas alla rabatthanteringserbjudanden som gäller för den aktuella orderraden och det beräknade rabattbeloppet i ordervalutan. Observera att beloppen endast är uppskattningar av framtida rabattanspråk. De faktiska rabattbeloppen kan skilja sig. Här är några av de faktorer som kan påverka de faktiska beloppen:

    - Den totala försäljningsvolymen som kunden har uppnått för ett periodiskt rabatterbjudande.
    - Om kunden returnerade alla kvantiteter eller delkvantiteter.
    - Om den tillämpliga försäljningsordern har uppnått transaktionstypen (*Order, Leverans* eller *Faktura*) som definierats för rabatthanteringserbjudandet.
    - Erbjudandets **Utgående** värde. Ett tomt rabattbelopp visas för erbjudanden där **Utgående** är inställt som *Artikel*.

1. Observera att avsnittet för **Marginalberäkning** på snabbfliken **Information** innehåller följande fält. Dessa fält läggs till av rabatthantering. Alla visar värden per enhet (men fälten på snabbfliken **Rabatthantering** visas totalvärden för raden).

    - **Rabattbelopp för rabatthantering** (endast försäljningsorder)
    - **Royaltybelopp för rabatthantering** (endast försäljningsorder)
    - **Leverantörsrabattbelopp för rabatthantering** (försäljningsorder och inköpsorder)

1. Stäng sidan **Prisinformation**.
1. Om försäljningsordern inte berättigar till de rabatter som du just har visat, följer du dessa steg för att exkludera rabatter. (Vanligtvis exkluderar du dock inte rabatter.)

    1. På snabbfliken **Försäljningsorderrader** väljer du relevant rad.
    1. Ställ in alternativet **Exkludera från rabatthantering** till *Ja* på fliken **Pris och rabatt** på snabbfliken **Radinformation**. Det här alternativet gäller inte för inköpsorder. Dessutom exkluderas endast kundrabatter när alternativet är inställt som *Ja*. Kundens royaltyrabatter och leverantörsrabatter gäller fortfarande.

1. Välj **Bokför följesedel** i gruppen **Generera** på fliken **Plocka och packa** i åtgärdsrutan.
1. På snabbfliken **Parametrar** i fältet **Kvantitet** väljer du *Allt*.
1. Välj **OK**.
1. Om du uppmanas att bekräfta åtgärden väljer du **OK**.
1. I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.
1. På snabbfliken **Parametrar** i fältet **Kvantitet** väljer du *Allt* eller *Följesedel*.
1. Välj **OK**.
1. Om du uppmanas att bekräfta åtgärden väljer du **OK**.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Bearbeta rabatthanteringserbjudanden

När du bearbetar ett erbjudande beräknar systemet alla relevanta rabatter och royalties som har ställts in. Endast valda erbjudanden som har beräkningsperioder som är klara att beräknas och som har statusen *Aktiv* kommer att bearbetas. När bearbetningen är klar genererar systemet en uppsättning transaktioner som du kan granska och sedan bokföra.

> [!NOTE]
> I alla fall bearbetas rabatter på den nivå som anges i varje erbjudandes **Stäm av efter** genom inställning ( *Avtal* eller *Rad*). Du kan göra beräkningar med en rad endast för erbjudanden där **Stäm av efter** anges till *Rad*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Bearbeta alla rader för en eller flera erbjudanden

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Markera raden för varje erbjudande som du vill behandla (eller öppna det erbjudande som du vill behandla).
1. I åtgärdsfönstret, på fliken **Rabatthanteringsinformation** i gruppen **Generera**, välj ett av följande kommandon:

    - **Process \> Etablera** – Etablera en uppsättning upplupningar för varje relevant rabattavtal, men lägg inte upp dem. Den här menyalternativet är inte tillgängligt för erbjudanden där fältet **Rabattutleverans** är inställt på *Artikel*.
    - **Process \> Rabatthantering** – Behandla en serie transaktioner som ger rabatten för varje erbjudande.
    - **Process \> skriva av** – För varje källtransaktion för rabattavtalet och den angivna perioden, bearbeta avvikelsen mellan beloppen som bokförts för en avsättning och för rabatthantering. Den här menyalternativet är inte tillgängligt för erbjudanden där fältet **Rabattutleverans** är inställt på *Artikel*.

1. I dialogrutan som visas, ange fälten **Från datum** och **Till datum** för att definiera datumintervallet för beräkningen.
1. Klicka på **OK** om du vill köra beräkningen.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Bearbeta en eller flera specifika avtalsrader för ett valt erbjudande

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Öppna det erbjudande som du vill bearbeta en rad från.
1. Välj fliken **Rader** i det övre högra hörnet.
1. På snabbfliken **Rabatthantering** markerar du raden för varje avtalsrad som du vill bearbeta.
1. Välj ett av följande kommandon i verktygsfältet på snabbfliken **Rabatthantering**. (Dessa kommandon är bara tillgängliga för erbjudanden där fältet **Stäm av** efter är inställt på *Rad*.)

    - **Process \> Etablera** – Etablera en uppsättning upplupningar för varje relevant erbjudanderad, men lägg inte upp dem. Den här menyalternativet är inte tillgängligt för erbjudanden där fältet **Rabattutleverans** är inställt på *Artikel*.
    - **Process \> Rabatthantering** – Behandla en serie transaktioner som ger rabatten för varje erbjudanderad.
    - **Process \> skriva av** – För varje källtransaktion för rabattavtalet och den angivna perioden, bearbeta avvikelsen mellan beloppen som bokförts för en avsättning och för rabatthantering. Den här menyalternativet är inte tillgängligt för erbjudanden där fältet **Rabattutleverans** är inställt på *Artikel*. 

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

### <a name="process-deals-by-using-the-rebate-workbench"></a>Bearbeta erbjudanden med workbench för rabatt

Istället för att bearbeta specifika erbjudanden eller rader kan du använda *workbench för rabatt* för att bearbeta flera erbjudanden samtidigt. Om du vill kan du även använda postfilter och/eller ställa in ett återkommande schema. Du behöver inte markera några rader. Alla rader som uppfyller de datum- och filterkrav som du anger bearbetas av systemet.

Om du vill bearbeta erbjudanden genom att använda workbench för rabatt följer du dessa steg.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
1. I åtgärdsfönstret, på fliken **Workbench för rabatt** i gruppen **Bearbeta** väljer du ett av följande kommandon:

    - **Bearbeta \> Reservera** – Reservera en uppsättning periodiseringar för varje relevant erbjudanderad, men bokför inte periodiseringen.
    - **Process \> Rabatthantering** – Behandla en serie transaktioner som ger rabatten för varje erbjudanderad.
    - **Bearbeta \> Avskrivning** – Bearbeta avvikelsen mellan reservering och rabatthantering som bokförts för varje källtransaktion för rabatterbjudandet och den angivna perioden.

1. I dialogrutan **Rabatthantering** som visas i avsnittet **Period** , ange fälten **Från-datum** och **Till-datum** för att ange datumintervall för beräkningen.
1. I avsnittet **Garantiperiod** anger du fälten **Från-datum** och **Till-datum** för att ange datumintervallet för garantier för beräkningen.
1. På snabbfliken **Poster som ska ingå** kan du ställa in filter för att begränsa den uppsättning erbjudanden som batchjobbet kommer att bearbetas. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. På snabbfliken **Kör i bakgrunden** kan du ställa batchbearbetning och schemaläggningsalternativ efter behov. Inställningarna fungerar på samma sätt som de fungerar för andra typer av batchjobb.
1. Välj **OK** för att köra och/eller planera beräkningen.

## <a name="view-and-edit-rebate-management-transactions"></a>Visa och redigera transaktioner för rabatthantering

När du bearbetar en eller flera affärer skapar systemet transaktioner som du kan visa och kanske redigera innan du bokför dem.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Visa och redigera transaktioner för rabatthantering genom att använda listsidan med rabatterbjudanden

Följ dessa steg för att visa och redigera transaktioner för rabatthantering genom att använda listsidan med rabatterbjudanden.

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

    - Välj **Bokför** i åtgärdsfönstret om du vill bokföra anspråket för alla relevanta rader. Om du använder en anspråksprocess (när alternativet **Använd anspråksprocess** har aktiverats på sidan **Rabatthanteringsparametrar**), bokförs enbart de rader som har markerats som **Begärd**. Annars bokförs alla källtransaktioner för den valda rabattransaktionen. Knappen **Bokför** är bara tillgänglig för rabattransaktioner. Den är inte tillgänglig för reserverings- och bortskrivningstransaktioner. I dialogrutan **Bokför** ställs fälten **Från datum** och **Till datum** automatiskt in. Ange fältet **Bokföringsdatum** och välj **OK**.
    - Om du vill justera beloppet som visas för en öppen eller icke-bokförd transaktion markerar du transaktionen och följer sedan ett av följande steg:

        - Redigera värdet i fältet **Korrigerat belopp**.
        - I åtgärdsfönstret, välj **ange korrigering**. Ange sedan ett värde i listrutan som visas i fältet **Korrigerat belopp**.

> [!NOTE]
> Om du använder en anspråksprocess, när du behandlar nästa period kommer transaktionslistan att innehålla alla icke-begärda transaktioner från föregående bokföring, plus eventuella nya transaktioner för vald period.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Visa och redigera transaktioner för rabatthantering genom att använda workbench för rabatt

Följ dessa steg för att visa och redigera transaktioner för rabatthantering genom att använda workbench för rabatt.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
1. Ställ in fältet **Visa** till *Inte bokfört*.
1. På sidan **Workbench för rabatt** visas en lista med transaktionerna. Varje transaktion innehåller relevant information. Informationen varierar beroende på transaktionstyp. På den här sidan kan du utföra följande åtgärder:

    - Om du vill visa mer information om en transaktion markerar du den och väljer sedan fliken **Allmänt**, **Ekonomisk dimension** eller **Dimension**.
    - Om du använder en anspråksprocess kan du markera transaktionerna som antingen anspråkstagna eller inte anspråkstagna. Välj relevanta rader och välj sedan, i åtgärdsfönstret, på fliken **Workbench för rabatt** ett av följande kommandon. (Du aktiverar anspråksprocesser på sidan [**Parametrar för rabatthantering**](rebate-management-parameters.md).)

        - **Ställ in som ianspråkstagna** – Markera de valda transaktionerna som anspråkstagna.
        - **Ställ in som inte ianspråkstagna** – Markera de valda transaktionerna som inte anspråkstagna.

    - Om du vill bokföra anspråk på en eller flera rader markerar du de relevanta raderna. Sedan väljer du **Bokför** på fliken **Workbench för rabatt** i åtgärdsrutan. Knappen **Bokför** är tillgänglig för reserverings-, rabatt- och avskrivningstransaktioner. I dialogrutan **Bokför** ställs fälten **Från datum** och **Till datum** automatiskt in. Ange fältet **Bokföringsdatum** och välj **OK**.
    - Om du vill justera beloppet som visas för en öppen eller icke-bokförd transaktion markerar du transaktionen och följer sedan ett av följande steg:

        - Redigera värdet i fältet **Korrigerat belopp**.
        - Sedan väljer du **Ange korrigering** på fliken **Workbench för rabatt** i åtgärdsrutan. Ange sedan ett värde i listrutan som visas i fältet **Korrigerat belopp**.

> [!NOTE]
> Om du använder en anspråksprocess, när du behandlar nästa period kommer transaktionslistan att innehålla alla icke-begärda transaktioner från föregående bokföring, plus eventuella nya transaktioner för vald period.

## <a name="post-rebates-transactions"></a>Bokför rabattransaktioner

Om du vill bokföra värdet av en bearbetad reservering, ett rabatthanteringsbelopp och en bortskrivning måste du köra bokföringsprocessen. Bokföringsprocessen markerar reserverings-, rabatthantering- eller avskrivningstransaktioner som bokförda och skapar måltransaktionen. Om du inte behöver granska måltransaktionen kan dessa transaktioner ställas in så att de bokförs automatiskt.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Ställ in systemet att bokföra alla måltransaktioner automatiskt

För att ställa in ditt system för att bokföra alla måltransaktioner så snart de genereras genom bokföring av provision, rabatthanteringsbelopp och avskrivning, slå på **Bokför journaler automatiskt** och/eller alternativet **Boka automatiskt fritextfakturor** på sidan **Parametrar för rabatthantering**. Mer information finns i [parametrar för rabatthantering](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Bokför transaktioner för alla rader för en eller flera erbjudanden

När du har bearbetat relevanta erbjudanden följer du dessa steg för att granska och bokföra genererade transaktioner för alla rader för en eller flera erbjudanden.

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Markera raden för varje erbjudande som du vill bokföra (eller öppna det erbjudande som du vill bokföra).
1. I åtgärdsfönstret, på fliken **Rabatthanteringsinformation** i gruppen **Generera**, välj ett av följande kommandon:

    - **Bokför \> Etablera** – Bokför tillgängliga periodiseringstransaktioner som du har skapat.
    - **Bokför \> Rabatt** – Bokför tillgängliga rabattransaktioner som du har skapat.
    - **Bokför \> Skriva av** – Bokför tillgängliga avskrivningstransaktioner som du har skapat.

1. I dialogrutan, ange fältet **Bokföringsdatum**. Ange sedan fälten **Från datum** och **Till datum** för att definiera datumintervallet för de transaktioner som måste bokföras.
1. Välj **OK** när du vill bokföra transaktioner.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Boka transaktioner för en eller flera specifika avtalsrader för ett valt erbjudande

När du har bearbetat relevanta erbjudanden följer du dessa steg för att granska och bokföra genererade transaktioner för en eller mer specifika avtalsrader för valt avtal. Proceduren gäller endast erbjudanden där fältet **Stäm av** efter är inställt på *Rad*.

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

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Bokför transaktioner med workbench för rabatt

När du har bearbetat reserverings-, rabatt- eller avskrivningstransaktioner följer du dessa steg och använder workbench för rabatt för att granska och bokföra de genererade transaktionerna för en eller flera specifika transaktionsrader för alla erbjudanden.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
1. I rutnätet markerar du alla transaktionsrader som du vill bokföra. Du kan välja ej bokförda reserverings-, rabatt- och/eller avskrivningstransaktioner. Följande regler gäller:

    - Systemet bokför även alla rader som har samma värde för **Rabatttransaktionsnummer** som de rader du väljer.
    - Systemet bokför inga rader av transaktionstypen *Rabatt* som inte har markerats som anspråkstagna.
    - Om du markerar rader som redan har bokförts hoppar systemet över de bokförda raderna.
    - Knappen **Bokför** är endast tillgänglig om du väljer minst en icke bokförd rad.

1. I åtgärdsfönstret, på fliken **Workbench för rabatt** i gruppen **Bearbeta**, väljer du **Bokför**.
1. I dialogrutan **Bokför** ställer du in fältet **Bokföringsdatum**. Fälten **Från-datum** och **Till-datum** ställs in automatiskt baserat på det tidigaste värdet för **Från-datum** och det senaste värdet för **Till-datum** för de markerade raderna.
1. Välj **OK** när du vill bokföra transaktioner.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Granska journaler för rabatthantering

När transaktionerna har bokförts kan du granska de journaler, dokument eller artiklar som de resulterar i. Måltransaktionerna för rabatter och royalties baseras på betalningstypen som har angetts i bokföringsprofilen och rabattens utdatatyp. Om till exempel rabattutleveransen är inställd på *Artikel* skapas en försäljningsorder för en kundrabatt och en inköpsorder skapas för en leverantörsrabatt. Dessa order kan visas via måltransaktionerna. Alternativt, om betalningen är inställd på att använda leverantörsreskontra, skapas en leverantörsfaktura för leverantören som är inställd på kunden för kundrabatter.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Granska journaler genom att använda listsidan för rabatterbjudanden

Granska journalposterna som är kopplade till ett rabatthanteringserbjudande genom att följa dessa steg.

1. Öppna lämplig [listsida för rabatterbjudanden](rebate-management-deals.md) för den typ av erbjudande du vill arbeta med.
1. Välj erbjudandet som du vill granska journalposter för.
1. I åtgärdsfönstret, på fliken **Rabatthanteringserbjudanden** i gruppen **Transaktioner**, välj **Transaktioner** eller **Garantitransaktioner**, beroende på vilken typ av transaktioner som du vill visa.
1. Ställ in fältet **Visa** som *Allt* eller *Bokfört*.
1. Sök efter och välj den transaktionssamling som du vill kontrollera och välj sedan en av följande knappar i åtgärdsfönstret. (Dessa knappar är endast tillgängliga när det finns relevanta bokföringar för den valda transaktionssamlingen.)

    - **Måltransaktioner** – Granska relevanta journaler och andra typer av dokument som genererades av den valda affären.
    - **Artiklar** - Granska relevanta försäljnings- eller inköpsorder som genererades av den valda affären.

1. En lista över relevanta journaler, dokument eller artiklar visas. Om du vill visa mer information om en journal, ett dokument eller ett objekt väljer du dess rad och väljer sedan i åtgärdsfönstret **Visa information**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Granska journaler med workbench för rabatt

För att granska journaler med workbench för rabatt följer du dessa steg.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
1. Ställ in fältet **Visa** som _Allt_ eller _Bokfört_.
1. Sök reda på och välj den rad som du vill granska. I åtgärdsfönstret, på fliken **Workbench för rabatt** i gruppen **Visa**, väljer du sedan **Måltransaktioner**. Den här knappen är enbart tillgänglig om det finns relevanta bokföringar för den valda raden.
1. En lista över relevanta journaler, dokument eller artiklar visas. Om du vill visa mer information om en journal, ett dokument eller ett objekt väljer du dess rad och väljer sedan i åtgärdsfönstret **Visa information**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Transaktioner för rabatthantering i workbench för avdrag

När du bokför en rabatthanteringstransaktion som har något av följande värden för **Betalningstyp** skapar systemet en kundavdragsjournal eller en fritextfaktura för det relevanta kundkontot:

- Kundavdrag
- Momsfaktura och kundavdrag
- Handelsutgift
- Rapportering

När en måltransaktion har skapats och bokförts, blir den tillgänglig som en öppen transaktion på sidan **Workbench för avdrag** (**Försäljning och marknadsföring \> Handelsavdrag \> Avdrag \> Workbench för avdrag**). Öppna transaktioner har värdet **Anspråkstyp** för *Rabatthantering* och ett värde för **Rabattransaktionsnummer** är tillgängligt för spårning. Datumet ställs in som bokföringsdatum för måltransaktionen Rabatthantering. För att använda workbench för avdrag när du vill kvitta öppna transaktioner mot befintliga avdrag för samma kundkonto ska du välja **Underhåll \> Matcha** i åtgärdsrutan.

Mer information finns i [Hantera avdrag med workbench för avdrag](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Rensa ej bokförda transaktioner

När du har bearbetat reserverings-, rabatt- eller avskrivningstransaktioner följer du dessa steg för att rensa valda, ej bokförda transaktioner.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
2. Ställ in fältet **Visa** till *Inte bokfört*.
3. Sök efter och välj de transaktioner som ska raderas. I åtgärdsfönstret, på fliken **Workbench för rabatt** i gruppen **Bearbeta**, väljer du sedan **Rensa**.
4. Välj **OK** för att radera transaktionerna som inte bokförts.

## <a name="cancel-a-posted-provision"></a>Annullera en bokförd reservering

När du har bearbetat och bokfört en reservering följer du dessa steg för att annullera bokförda reserveringstransaktioner.

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Workbench för rabatt**.
2. Ställ in fältet **Visa** som *Bokfört*.
3. Sök efter och välj de reserveringstransaktioner som ska annulleras. I åtgärdsfönstret, på fliken **Workbench för rabatt** i gruppen **Bearbeta**, väljer du sedan **Annullera reservering**.
4. Välj **OK** för att återföra transaktionerna.

Dessa reserveringsåterföringar visas också i relevanta [Rabatthanteringsjournaler](#review-journals).
