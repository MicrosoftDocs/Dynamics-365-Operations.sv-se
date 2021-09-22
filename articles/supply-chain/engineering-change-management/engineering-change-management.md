---
title: Hantera ändringar av konstruktionsprodukter
description: Det här ämnet innehåller information om konstruktionsändringshantering. Konstruktionsändringshantering innehåller strukturerade processer för att hantera ändringar i konstruktionsprodukter, från att föreslå, begära och göra ändringar, granska och godkänna ändringar, bedöma deras inverkan på befintliga transaktioner och följa upp dem.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2fe94ea1afb74520ee97268f62d42832bad5c3df
ms.sourcegitcommit: 07fada750de54e2907377df2a9f7dae497c3b66e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7467432"
---
# <a name="manage-changes-to-engineering-products"></a>Hantera ändringar av konstruktionsprodukter

[!include [banner](../includes/banner.md)]

Konstruktionsändringshantering innehåller strukturerade processer för hantering av ändringar av konstruktionsprodukter. Du kan använda processen *begäran om konstruktionsändring* för att föreslå och begära ändringar och sedan använda processen *konstruktionsändringsorder* för att faktiskt göra ändringarna. Användarna kan skapa begäran om konstruktionsändring eller konstruktionsändringsorder, och då har du en process för att granska och godkänna dem, bedöma deras inverkan på befintliga transaktioner och följa upp dem.

## <a name="engineering-change-requests"></a>Begäranden om konstruktionsändring

Med processen för begäran om konstruktionsändring kan du registrera en begäran om ändringar från alla relevanta avdelningar i ditt företag. Det spelar ingen roll om du arbetar som en tekniker eller i tillverknings-, anskaffnings-, lager- eller försäljningsavdelningen: alla kan använda en begäran om konstruktionsändringsbegäran för att begära en ändring. Den här ändringen kan vara en idé för en ny produkt, ett problem som du har upptäckt medan du arbetade med en befintlig produkt, ett förslag till förbättringar av en befintlig produkt eller något annat.

När någon har skickat en begäran om ändring hanteras processen för *granskning och godkännande* av ett arbetsflöde som identifieras vem som måste godkänna ändringen (t.ex. produktägaren).

Om du vill ställa in ett arbetsflöde för konstruktionsändringsorder eller konstruktionsändrings begäran, gå till **Konstruktionsändringshantering \> Konstruktionsarbetssflöden**. Välj **ny**, välj om arbetsflödet ska användas för att granska konstruktionsändringsorder eller konstruktionsändringsbegäran och konfigurera sedan arbetsflödet.

För mer information om arbetsflöden, se [arbetsflödessystem, översikt](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Mer information om produktägare, se [Produktägare](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Skapa en ny begäran om konstruktionsändring

Gör något av följande om du vill skapa en begäran om konstruktionsändring:

- Gå till **Konstruktionsändringshantering \> Vanlig \> Konstruktionsändringshantering \> Begäran om konstruktionsändring** och välj **Ny** i åtgärdsfönstret.
- Öppna sidan **produktinformation** för en befintlig konstruktionsprodukt. Sedan på åtgärdsfönstret, på fliken **Konstruera** i gruppen **Konstruktionsändringshantering** välj **Begäran om konstruktionsändring \> Ny begäran om konstruktionsändring**.

En ny ändringsbegäran skapas. Du kan du ange fälten på varje snabbflik som beskrivs i följande underavsnitt.

#### <a name="general-fasttab"></a>Snabbfliken Allmänt

På snabbfliken **Allmänt** kan du ange en grundläggande beskrivning av ändringsbegäran. Följande register beskriver de fält som är tillgängliga på denna snabbflik.

| Fält | beskrivning |
|---|---|
| Ändringsbegäran | Ange ett beskrivande begäran om konstruktionsändring. |
| Befattning | Ange en kort beskrivning eller identifierar ändringarna i förfrågan. |
| Prioritet | Välj ett värde som anger hur hög prioriteten för ändringen är. Du kan anpassa de tillgängliga värdena för ditt företag efter behov. (För mer information, se [Fastställa gemensamma värden för konstruktionsändringshantering](engineering-change-management-setup.md).) |
| Kategori | Välj ett värde som beskriver den typ av ändring du begär. Du kan anpassa de tillgängliga värdena för ditt företag efter behov. (För mer information, se [Fastställa gemensamma värden för konstruktionsändringshantering](engineering-change-management-setup.md).) |
| Allvarlighetsgrad | Välj ett värde som anger hur allvarliga problemet som ska åtgärdas genom att genomföra begäran. Du kan anpassa de tillgängliga värdena för ditt företag efter behov. (För mer information, se [Fastställa gemensamma värden för konstruktionsändringshantering](engineering-change-management-setup.md).) |
| Begärt av | Namnet på användaren som skapade begäran. |
| På | Datumet då begäran skapades. |
| Status | Status för begäran. När en begäran skapas för första gången skapas *status*. När begäran godkänns ändras status till *godkänd*. Om en relaterad ändringsorder har skapats för begäran ändras status till *följa upp*. |
| Ändringsorder | Ändringsordernummer, om ändringsbegäran följdes via en ändringsorder. |

#### <a name="information-fasttab"></a>Snabbfliken information

På snabbfliken **Information** låter dig lägga till mer information om begäran.

Om du vill lägga till en rad i rutnätet väljer du **ny** i verktygsfältet ovanför rutnätet och väljer något av följande alternativ:

- **Fil** – Överför en fil.
- **Bild** – överför en bildfil.
- **Observera** – Ange en notering direkt i rutnätet.
- **URL** – Ange en URL direkt i rutnätet.

Följande register beskriver de fält som är tillgängliga på varje rad.

| Fält | beskrivning |
|---|---|
| Skapades datum och klockslag | Det datum och den tid då raden skapades. |
| Typ | Typen av information som raden skapades för (fil, bild, anteckning eller URL). |
| beskrivning | Ange en beskrivning för raden. |
| Begränsning | Ett värde som anger om den information som har lagts till kommer från en intern eller extern källa. |
| Kopplat | En markerad kryssruta anger att raden innehåller en bifogad fil (fil eller bild). Om du vill hämta den bifogade filen markerar du raden och väljer sedan **Öppna** i verktygsfältet ovanför rutnätet. |

#### <a name="products-fasttab"></a>Snabbfliken produkter

På snabbfliken **produkter** kan du ange varje produkt som påverkas av ändringsbegäran. Du kan använda knapparna i verktygsfältet för att lägga till produkter i rutnätet eller för att ta bort produkter.

Den här listan är bara avsett för information. Därför kan du lägga till så många relaterade produkter som du anser relevanta. Om du skapar en ändringsbegäran från sidan **produktinformation** för en befintlig produkt, bör produkten listas på snabbfliken **Produkter** när du har sparat posten för begäran.

#### <a name="source-fasttab"></a>Snabbfliken källa

På snabbfliken **källa** kan du spåra startpunkten för ändringsbegäran. Det är användbart om du t.ex. vill se om ändringsbegäran har skapats från en försäljningsorder, vem som skapade den och vilket företag den skapades i.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Utvärdera en ändringsbegärans affärspåverkan och skicka meddelanden

När du granskar en begäran om ändring kan du söka efter beroenden. På det här sättet kan du bedöma effekten av den begärda ändringen på öppna transaktioner, till exempel försäljningsorder, tillverkningsorder och lagerbehållning. När du granskar ändringsbegäranden kan du skicka meddelanden till dem som ansvarar för att uppfylla olika typer av relaterade order.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Granska berörda transaktioner, blockera valda transaktioner och skicka meddelanden

Granska berörda transaktioner, blockera valda transaktioner och skicka relaterade meddelanden, följ dessa steg.

1. Gå till **Konstruktionsändringshantering \> Vanlig \> Konstruktionsändringshantering \> Begäran om konstruktionsändring**.
1. Du kan antingen öppna en befintlig ändringsbegäran eller välja **ny** i åtgärdsfönstret för att skapa en ny ändringsbegäran.
1. I åtgärdsfönstret på fliken **Ändringsbegäran** i gruppen **Affärspåverkan**, välj en av följande knappar:

    - **Sök** – Skannar alla öppna transaktioner och öppnar sedan dialogrutan **Affärspåverkan till öppna transaktioner** som listar alla transaktioner som kommer att påverkas av ändringen.
    - **Visa föregående sökning** – Öppna dialogrutan **Affärspåverkan till öppna transaktioner** som visar resultatet av den föregående sökningen. (En ny sökning utförs inte.)

1. Dialogrutan **Affärspåverkan till öppna transaktioner** innehåller en uppsättning flikar, som alla visar en lista över berörda transaktioner av en viss typ (**försäljningsorder**, **inköpsorder**, **tillverkningsorder**, **lager** och så vidare). På varje flik visas även ett nummer som anger antalet berörda transaktioner av den typen. Välj en flik för att visa relevant lista.
1. Arbeta med en transaktion i listan genom att markera den och sedan välja en av följande knappar i verktygsfältet:

    - **Visa transaktion** – Öppna den valda transaktionsposten.
    - **Spärra order** – Den här knappen är endast tillgänglig på fliken **Försäljningsorder**. Markera den om du vill spärra den valda försäljningsordern.
    - **Spärra rad** – Den här knappen är endast tillgänglig på fliken **Inköpsorder**. Markera den om du vill spärra den valda inköpsorderraden.
    - **Meddela ansvarig** – Den här knappen är endast tillgänglig på fliken **Försäljningsorder**. Välj den om du vill skicka ett ändringsmeddelande till användaren som anges som ansvarig för den valda försäljningsordern. Mer information om vem som kan visa meddelanden och hur finns i [Granska och bearbeta ändringsmeddelanden för transaktioner](#review-notifications).
    - **Meddela beställare** – Den här knappen är endast tillgänglig på fliken **Inköpsorder**. Välj den om du vill skicka ett ändringsmeddelande till användaren som anges som beställare för den valda inköpsordern. Mer information om vem som kan visa meddelanden och hur finns i [Granska och bearbeta ändringsmeddelanden för transaktioner](#review-notifications).
    - **Meddela produktion** – Den här knappen är endast tillgänglig på fliken **Produktionsorder**. Till skillnad från försäljningsorder och inköpsorder har produktionsorder inte en enda användare som ställs som ansvarig för dem från fram och tillbaka. Istället tar olika arbetsledare eller planerare vanligtvis ansvar för en viss resursplats eller för en viss del av produktionen (till exempel för specifika resurser eller resursgrupper). När du väljer den här knappen får därför alla användare som ansvarar för alla resurser som är relaterade till den valda tillverkningsordern ett ändringsmeddelande. Mer information om vem som kan visa meddelanden och hur finns i [Granska och bearbeta ändringsmeddelanden för transaktioner](#review-notifications).
    - **Meddela förberedare** – Den här knappen är endast tillgänglig på fliken **inköpsrekvisition**. Välj den om du vill skicka ett ändringsmeddelande till användaren som anges som förberedare för den valda inköpsrekvisitionen. Mer information om vem som kan visa meddelanden och hur finns i [Granska och bearbeta ändringsmeddelanden för transaktioner](#review-notifications).
    - **Meddela försäljningsansvarig** – Den här knappen är endast tillgänglig på fliken **Offerter**. Välj den om du vill skicka ett ändringsmeddelande till användaren som anges som ansvarig för den valda offerten. Mer information om vem som kan visa meddelanden och hur finns i [Granska och bearbeta ändringsmeddelanden för transaktioner](#review-notifications).
    - **Kassation** – Den här knappen är endast tillgänglig på fliken **Lager**. Välj den om du vill kassera det valda lagret.
    - **Visa historik** – Öppna en historik över åtgärder som har genomförts på den valda transaktionen genom att använda dialogrutan **Affärspåverkan till öppna transaktioner**. (Historiken visar till exempel om meddelanden har skickats eller om transaktioner har spärrats.) 
    - **Visa alla transaktioner** – Öppna den fullständiga listan över alla transaktioner, inte bara de öppna transaktionerna.

> [!IMPORTANT]
> Knappen **Meddela produktion** är bara tillgänglig om funktionen *Konstruktionsmeddelanden för produktion* är aktiverad i systemet. Instruktioner finns i [Konstruktionsändringshantering – översikt](product-engineering-overview.md).

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>Granska och bearbeta meddelanden för transaktioner

Du kan läsa och bearbeta de ändringsmeddelanden som du får på följande sätt:

- Vid tillverkningsorder visas även ändringsmeddelanden för de transaktioner som du är ansvarig för i Åtgärdscentret. Knappen **Visa meddelanden** (klocksymbol) till höger om navigeringsfältet anger när ett åtgärdscenter meddelande är tillgängligt för den aktuella användaren. Välj knappen **Visa meddelanden** om du vill öppna Åtgärdscentret och granska meddelandena.
- Om du vill visa alla tillverkningsorder som ett teknikmeddelande har skickats för går du till **Tillverkningsorder \> Tillverkningsorder \> Alla tillverkningsorder**. På fliken **Produktionsorder**, i gruppen **Begäran om konstruktionsändring** i åtgärdsfönstret, väljer du **Teknikmeddelanden** för att öppna sidan **Teknikmeddelanden**.
- För tillverkningsorder kan du välja att endast granska de ändringsmeddelanden som gäller för de produktionsresurser som du hanterar. I arbetsytan **Produktionsgolvsledning** i åtgärdsfönstret välj **Konfigurera min arbetsyta** för att filtrera sidan så att den bara visar information om de produktionsenheter, grupper och/eller resurser som du hanterar. I avsnittet **Sammanfattning** visar en panel som kallas **Produktionsorder med ändrade produkter** visar ett antal meddelanden som matchar dina filterinställningar. Markera den här panelen om du vill öppna sidan **Tekniska meddelanden**, där hela listan med transaktioner som uppfyller kriterierna i filtret visas.

När du granskar tillverkningsordermeddelanden på sidan **Tekniska meddelanden**, kan du följa länkar till relaterade ändringsorder eller tillverkningsorder genom att välja kolumnvärden eller använda relaterade kommandon i åtgärdsfönstret. När du är klar med en utvärdering av en ändring, och efter att du har annullerat eller ändrat tillverkningsorder efter behov, kan du markera ett meddelande som löst. Välj aviseringen och välj sedan i åtgärdsfönstret **Lös**. Meddelandet tas bort från alla användares vyer.

> [!IMPORTANT]
> Om det ska gå att skicka meddelanden för produktionsorder måste funktionen *Konstruktionsmeddelanden för produktion* vara aktiverad i systemet. Instruktioner finns i [Konstruktionsändringshantering – översikt](product-engineering-overview.md).

### <a name="create-a-change-order-from-a-change-request"></a>Skapa en ändringsorder från en ändringsbegäran

En tekniker som granskar en konstruktionsändringsbegäran kan skapa en konstruktionsändringsorder direkt från sidan **Begäran om konstruktionsändring**. I åtgärdsfönstret på fliken **Ändringsbegäran** i gruppen **Konstruktionsändringsorder** väljer du **Kopiera länk och produkter**.

## <a name="engineering-change-orders"></a>Konstruktionsändringsorder

Konstruktionsorderändringar ger en strukturerad process för att göra ändringar i konstruktionsprodukter. Du föreslår ändringar genom att använda en kopia av de konstruktionsdata som behövs. Den verkliga huvudinformationen påverkas inte. Mer information om konstruktionsrelevanta data finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

Du kan skapa en konstruktionsändringsorder som baseras på en godkänd begäran om konstruktionsändring. Teknikerna kan också skapa konstruktionsändringsorder från grunden. Du kan inkludera flera produkter i en enskild konstruktionsändringsorder genom att följa de här stegen:

- Välj produkter manuellt.
- Använd strukturlistan om du vill inkludera produkter som är lägre i produktstrukturen (dvs. underordnade).
- Använd en där den användssökning för att inkludera produkter som är högre i produktstrukturen (dvs överordnade).

När förslaget till ändringar har slutförts hanteras gransknings- och godkännandeprocessen av ett arbetsflöde. Du kan skapa olika arbetsflöden utifrån prioritet och allvarlighetsgrad.

Om du vill ställa in ett arbetsflöde för konstruktionsändringsorder eller konstruktionsändrings begäran, gå till **Konstruktionsändringshantering \> Konstruktionsarbetssflöden**. Välj **ny**, välj om arbetsflödet ska användas för att granska konstruktionsändringsorder eller konstruktionsändringsbegäran och konfigurera sedan arbetsflödet.

För mer information om arbetsflöden, se [arbetsflödessystem, översikt](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Här är några typiska intressenter som kanske måste godkänna en konstruktionsändringsorder:

- **Produktägare** – För mer information om produktägare, se [Produktägare](product-owner.md).
- **Ansvarigt teamlead** – Fältet **tekniker** i vyn the **huvud** över konstruktionsändringsorder visar teknikern som skapade konstruktionsändringsorder. Om teknikern tillhör ett team som har definierats i systemet visar fältet **ansvarig** ledaren för det teamet.
- **Ekonomiavdelning** – ekonomiavdelningen kan behöva granska ärenden där ändringen medför höga kostnader.

Du kan välja om den konstruktionsändringsordern ska bearbetas direkt efter att den har godkänts, som en del av arbetsflödet, eller om bearbetningen ska utföras senare, som ett manuellt steg. Under bearbetningen av en konstruktionsändringsorder uppdateras teknik data på den faktiska produkten.

När du granskar en begäran om ändring, går du till åtgärdsfönstret på fliken **ändringsbegäran** i gruppen **affärspåverkan** väljer **söka** för att bedöma effekterna av den föreslagna ändringen på öppna transaktioner, såsom försäljningsorder, produktionsorder och lager. Resultaten visas i dialogrutan **Affärspåverkan till öppna transaktioner** där du kan välja påverkade transaktioner och sedan använda kommandon i verktygsfältet för att visa mer information, meddela den ansvariga användaren eller blockera transaktionen.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Konstruktionsändringsändringsorder i konstruktionseller operativa företag

Som beskrivs i [konstruktionsföretag och regler för dataägarskap](engineering-org-data-ownership-rules.md) kan de produktdata som du kan redigera variera beroende på vilken typ av juridisk person du arbetar med (ett konstruktionsföretag jämfört med ett driftföretag). Regler för dataägarskap används också för konstruktionsändringsorder. Beroende på den juridiska personen där du skapar en konstruktionsändringsorder, kan olika typer av ändringar göras. Nedan följer några exempel:

- För konstruktionsändringsorder i ett *tekniskt företag* kan du göra grundläggande ändringar i konstruktionsdata. Du kan till exempel skapa nya versioner av en produkt, ändra en produkts struktur via strukturlistan och ändra konstruktionsattributvärden. För varje produkt som påverkas väljer du ett av följande värden i fältet **påverkan**:

    - **Ingen** – Uppdatera den befintliga produktversionen (i versionsuppdateringen).
    - **Ny version** – skapa en ny version baserad på den valda produktversionen.
    - **Ny produkt** – Skapa en helt ny produkt som baseras på den valda produktversionen.
    - **Ny variant** – Skapa en ny variant baserad på den valda produktversionen. Strukturliste- och flödesinformationen kopieras.

- För konstruktionsändringsorder i ett *operationellt företag* kan du ändra produktens logistiska data. Du kan till exempel utöka den befintliga strukturlistan med inställningar för källa, lägga till lokala flöden eller lokala struktur listor och till och med utöka en strukturlista genom att lägga till nya strukturlisterader för lokala förpackningsmaterial, smörjvätskor eller instruktioner på det lokala språket. Berikningar som användarna gör i operationella företaget bevaras när nya uppdateringar skickas från konstruktionsföretaget. Mer information finns i [regler för konstruktionsföretag och dataägarskap](engineering-org-data-ownership-rules.md).

    När konstruktionsändringsorder bearbetas i konstruktionsföretaget skapas och/eller uppdateras bara produkterna i konstruktionsföretaget. Om produktens huvuddata ska också uppdateras måste du också frisläppa produkterna till operativa företag.

- Du kan frisläppa produkter direkt från konstruktionsändringsorder. Öppna ändringsordningen och sedan på åtgärdsfönstret på fliken **Ändringsorder** i gruppen **Produktversioner** välj **Frisläppa produktstruktur**. Processen fungerar precis som den fungerar när du släpper produkter från sidan **frisläppta produkter**. Mer information finns i [Frisläppa produktstruktur](release-product-structure.md).
- Du kan automatiskt frisläppa produkter från konstruktionsändringsorder, baserat på följande faktorer:

    - Återutgivning till företag där produkter tidigare har frisläppts. Välj **Sök** för att söka igenom alla tidigare versioner och välj sedan **Visa** för att visa resultaten. På sidan **Visa** visas de tidigare produktlanseringarna, och du kan välja vilka produkter som ska återlämnas. Stäng sedan sidan **Visa** och välj **Process** för att släppa valda produkter på nytt.
    - Inställningar för automatisk publicering av konstruktionsproduktkategori i frisläppningskontrollen. Du kan göra den här versionen som en del av arbetsflödet. När blocket **samla ut frisläppningsförslag** används kommer förslaget att släppas att fyllas i med frisläppning på nytt (se föregående lista) och produkter kommer att släppas till företag om kryssrutan **Automatisk frisläppning** vald i frisläppningskontrollen för den konstruktionsproduktkategorin. Du kan välja **vy** för att visa resultaten på det sätt som beskrivs i föregående listobjekt. Produkterna frigörs också när blocket **process frisläppningsförslag** används. Om du bara väljer att samla in frisläppningsförslaget som en del av arbetsflödet, kan du starta frisläppningen manuellt genom att välja **process**, som beskrivs i det föregående listobjektet.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Följa upp en konstruktionsändringsbegäran via en konstruktionsändringsorder

Så snart en konstruktionsändringsbegäran godkänns kan du följa upp den via en konstruktionsändringsorder. Du kan kombinera flera konstruktionsändrings begäran i en enda konstruktionsändringsorder. En enskild konstruktionsändringsorder kan till och med innehålla flera produkter. (Vanligtvis använder du den här metoden när samma ändring måste tillämpas på flera produkter). Du kan dock inte skapa flera konstruktionsändringsorder från en enskild konstruktionsändringsbegäran.

Om du vill följa upp en ändringsbegäran via en ändringsorder öppnar du begäran och väljer sedan i åtgärdsfönstret på fliken **Ändringsorder** i gruppen **konstruktionsändringsorder** välj **Kopiera länk och produkter**. Du kan sedan välja en befintlig konstruktionsändringsorder för att ansluta ändringsbegäran till, eller så kan du skapa en ny konstruktionsändringsorder för den specifika förfrågan.

## <a name="engineering-change-order-report"></a>Rapport om konstruktionsändringsorder

Konstruktionsändringsorder rapporter beskriver de ändringar som har gjorts i en konstruktionsändringsorder. De är användbara både under och efter gransknings- och godkännandeprocessen.

Om du vill visa en rapport för konstruktionsändringsorder öppnar du relevant ändringsorder och i åtgärdspanelen, på fliken **ändringsorder** i gruppen **vy** väljer du **Rapport för konstruktionsändringsorder**.

## <a name="fields-on-an-engineering-change-order"></a>Fält på en konstruktionsändringsorder

De flesta fält på konstruktionsändringsorder är samma fält för frisläppta produkter, konstruktionsversioner, dokument, strukturlistor (rader) och flöden (operationer). Fälten i följande tabell är dock unika för ändringsorder.

| Fält | beskrivning |
|---|---|
| Konstruktionsändringsorsaker | Välj orsak till att ändra den berörda produkten. |
| Ändringsbeskrivning | Ange en beskrivning för ändringen. |
| Nödvändiga specialverktyg | Ange om särskilda verktyg krävs för att ändringen ska tillämpas. |
| Konstruktionsmaterial disposition | Välj en materialdispositionskod för allt avfall som tillverkas när ändringen tillämpas. |
| Kundgodkännande krävs | Ange om kundgodkännande krävs innan ändringen kan tillämpas. |
| Mottog kundgodkännande | Ange status för kundens godkännande. |
| Miljö- och hälsosäkerhet | Ange om miljöhälso- och säkerhetsregler gäller för ändringen. Om de är det kan du sedan välja tillämpliga regler. |

Använd knappen **Bibehåll/kopiera ändringsinformation** för att kopiera ändringsinformation mellan berörda produkter.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
