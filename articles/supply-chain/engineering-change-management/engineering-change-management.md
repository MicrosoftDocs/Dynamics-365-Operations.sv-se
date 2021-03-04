---
title: Hantera ändringar av konstruktionsprodukter
description: Det här ämnet innehåller information om konstruktionsändringshantering. Konstruktionsändringshantering innehåller strukturerade processer för att hantera ändringar i konstruktionsprodukter, från att föreslå, begära och göra ändringar, granska och godkänna ändringar, bedöma deras inverkan på befintliga transaktioner och följa upp dem.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 314563e083434832ee04d9c19deb17cec221ae02
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438125"
---
# <a name="manage-changes-to-engineering-products"></a>Hantera ändringar av konstruktionsprodukter

[!include [banner](../includes/banner.md)]

Konstruktionsändringshantering innehåller strukturerade processer för hantering av ändringar av konstruktionsprodukter. Du kan använda processen *begäran om konstruktionsändring* för att föreslå och begära ändringar och sedan använda processen *teknisk ändringsorder* för att faktiskt göra ändringarna. Användarna kan skapa begäran om teknisk ändring eller tekniska ändringsorder, och då har du en process för att granska och godkänna dem, bedöma deras inverkan på befintliga transaktioner och följa upp dem.

## <a name="engineering-change-requests"></a>Begäranden om konstruktionsändring

Med processen för begäran om teknisk ändring kan du registrera en begäran om ändringar från alla relevanta avdelningar i ditt företag. Det spelar ingen roll om du arbetar som en tekniker eller i tillverknings-, anskaffnings-, lager- eller försäljningsavdelningen: alla kan använda en begäran om teknisk ändringsbegäran för att begära en ändring. Den här ändringen kan vara en idé för en ny produkt, ett problem som du har upptäckt medan du arbetade med en befintlig produkt, ett förslag till förbättringar av en befintlig produkt eller något annat.

När någon har skickat en begäran om ändring hanteras processen för *granskning och godkännande* av ett arbetsflöde som identifieras vem som måste godkänna ändringen (t.ex. produktägaren).

Om du vill ställa in ett arbetsflöde för konstruktionsändringsorder eller tekniska ändrings begäran, gå till **Konstruktionsändringshantering \> Tekniska arbetssflöden**. Välj **ny**, välj om arbetsflödet ska användas för att granska konstruktionsändringsorder eller tekniska ändringsbegäran och konfigurera sedan arbetsflödet.

För mer information om arbetsflöden, se [arbetsflödessystem, översikt](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Mer information om produktägare, se [Produktägare](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Skapa en ny begäran om konstruktionsändring

Gör något av följande om du vill skapa en begäran om konstruktionsändring:

- Gå till **Konstruktionsändringshantering \> Vanlig \> Konstruktionsändringshantering \> Begäran om teknisk ändring** och välj **Ny** i åtgärdsfönstret.
- Öppna sidan **produktinformation** för en befintlig teknisk produkt. Sedan på åtgärdsfönstret, på fliken **Konstruera** i gruppen **Konstruktionsändringshantering** välj **Begäran om teknisk ändring \> Ny begäran om teknisk ändring**.

En ny ändringsbegäran skapas. Du kan du ange fälten på varje snabbflik som beskrivs i följande underavsnitt.

#### <a name="general-fasttab"></a>Snabbfliken Allmänt

På snabbfliken **Allmänt** kan du ange en grundläggande beskrivning av ändringsbegäran. Följande register beskriver de fält som är tillgängliga på denna snabbflik.

| Fält | beskrivning |
|---|---|
| Ändringsbegäran | Ange ett beskrivande begäran om teknisk ändring. |
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

### <a name="evaluate-the-business-impact-of-a-change-request"></a>Utvärdera en ändringsbegärans affärspåverkan

När du granskar en begäran om ändring kan du söka efter beroenden. På det här sättet kan du bedöma effekten av den begärda ändringen på öppna transaktioner, till exempel försäljningsorder, tillverkningsorder och lagerbehållning.

1. Gå till **Konstruktionsändringshantering \> Vanlig \> Konstruktionsändringshantering \> Begäran om teknisk ändring**.
1. Du kan antingen öppna en befintlig ändringsbegäran eller välja **ny** i åtgärdsfönstret för att skapa en ny ändringsbegäran.
1. I åtgärdsfönstret på fliken **Ändringsbegäran** i gruppen **Affärspåverkan**, välj en av följande knappar:

    - **Sök** – Skannar alla öppna transaktioner och öppnar sedan dialogrutan **Affärspåverkan till öppna transaktioner** som listar alla transaktioner som kommer att påverkas av ändringen.
    - **Visa föregående sökning** – Öppna dialogrutan **Affärspåverkan till öppna transaktioner** som visar resultatet av den föregående sökningen. (En ny sökning utförs inte.)

1. Om problemet som kräver en ändring har visat sig vara kritiskt kan du spärra de öppna transaktionerna eller meddela den ansvariga användaren med hjälp av knapparna i verktygsfältet i dialogrutan **Affärspåverkan till öppna transaktioner**.

### <a name="create-a-change-order-from-a-change-request"></a>Skapa en ändringsorder från en ändringsbegäran

En tekniker som granskar en teknisk ändringsbegäran kan skapa en teknisk ändringsorder direkt från sidan **Begäran om teknisk ändring**. I åtgärdsfönstret på fliken **Ändringsbegäran** i gruppen **Teknisk ändringsorder** väljer du **Kopiera länk och produkter**.

## <a name="engineering-change-orders"></a>Konstruktionsändringsorder

Orderändringar för teknik ger en strukturerad process för att göra ändringar i tekniska produkter. Du föreslår ändringar genom att använda en kopia av de tekniska data som behövs. Den verkliga huvudinformationen påverkas inte. Mer information om teknikrelevanta data finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

Du kan skapa en teknisk ändringsorder som baseras på en godkänd begäran om teknisk ändring. Teknikerna kan också skapa tekniska ändringsorder från grunden. Du kan inkludera flera produkter i en enskild tekniska ändringsorder genom att följa de här stegen:

- Välj produkter manuellt.
- Använd strukturlistan om du vill inkludera produkter som är lägre i produktstrukturen (dvs. underordnade).
- Använd en där den användssökning för att inkludera produkter som är högre i produktstrukturen (dvs överordnade).

När förslaget till ändringar har slutförts hanteras gransknings- och godkännandeprocessen av ett arbetsflöde. Du kan skapa olika arbetsflöden utifrån prioritet och allvarlighetsgrad.

Om du vill ställa in ett arbetsflöde för konstruktionsändringsorder eller tekniska ändrings begäran, gå till **Konstruktionsändringshantering \> Tekniska arbetssflöden**. Välj **ny**, välj om arbetsflödet ska användas för att granska konstruktionsändringsorder eller tekniska ändringsbegäran och konfigurera sedan arbetsflödet.

För mer information om arbetsflöden, se [arbetsflödessystem, översikt](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Här är några typiska intressenter som kanske måste godkänna en teknisk ändringsorder:

- **Produktägare** – För mer information om produktägare, se [Produktägare](product-owner.md).
- **Ansvarigt teamlead** – Fältet **tekniker** i vyn the **huvud** över teknisk ändringsorder visar teknikern som skapade teknisk ändringsorder. Om teknikern tillhör ett team som har definierats i systemet visar fältet **ansvarig** ledaren för det teamet.
- **Ekonomiavdelning** – ekonomiavdelningen kan behöva granska ärenden där ändringen medför höga kostnader.

Du kan välja om den tekniska ändringsordern ska bearbetas direkt efter att den har godkänts, som en del av arbetsflödet, eller om bearbetningen ska utföras senare, som ett manuellt steg. Under bearbetningen av en teknisk ändringsorder uppdateras teknik data på den faktiska produkten.

När du granskar en begäran om ändring, går du till åtgärdsfönstret på fliken **ändringsbegäran** i gruppen **affärspåverkan** väljer **söka** för att bedöma effekterna av den föreslagna ändringen på öppna transaktioner, såsom försäljningsorder, produktionsorder och lager. Resultaten visas i dialogrutan **Affärspåverkan till öppna transaktioner** där du kan välja påverkade transaktioner och sedan använda kommandon i verktygsfältet för att visa mer information, meddela den ansvariga användaren eller blockera transaktionen.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Teknisk ändringsändringsorder i tekniska eller operativa företag

Som beskrivs i [teknikföretag och regler för dataägarskap](engineering-org-data-ownership-rules.md) kan de produktdata som du kan redigera variera beroende på vilken typ av juridisk person du arbetar med (ett teknikföretag jämfört med ett driftföretag). Regler för dataägarskap används också för teknisk ändringsorder. Beroende på den juridiska personen där du skapar en teknisk ändringsorder, kan olika typer av ändringar göras. Nedan följer några exempel:

- För tekniska ändringsorder i ett **tekniskt företag** kan du göra grundläggande ändringar i tekniska data. Du kan till exempel skapa nya versioner av en produkt, ändra en produkts struktur via strukturlistan och ändra tekniska attributvärden. För varje produkt som påverkas väljer du ett av följande värden i fältet **påverkan**:

    - **Ingen** – Uppdatera den befintliga produktversionen (i versionsuppdateringen).
    - **Ny version** – skapa en ny version baserad på den valda produktversionen.
    - **Ny produkt** – skapa en helt ny produkt- eller produktvariant som baseras på den valda produktversionen.

- För tekniska ändringsorder i ett **operationellt företag** kan du ändra produktens logistiska data. Du kan till exempel utöka den befintliga strukturlistan med inställningar för källa, lägga till lokala flöden eller lokala struktur listor och till och med utöka en strukturlista genom att lägga till nya strukturlisterader för lokala förpackningsmaterial, smörjvätskor eller instruktioner på det lokala språket. Berikningar som användarna gör i operationella företaget bevaras när nya uppdateringar skickas från tekniska företaget. Mer information finns i [regler för tekniska företag och dataägarskap](engineering-org-data-ownership-rules.md).

    När tekniska ändringsorder bearbetas i det tekniska företaget skapas och/eller uppdateras bara produkterna i det tekniska företaget. Om produktens huvuddata ska också uppdateras måste du också frisläppa produkterna till operativa företag.

- Du kan frisläppa produkter direkt från teknisk ändringsorder. Öppna ändringsordningen och sedan på åtgärdsfönstret på fliken **Ändringsorder** i gruppen **Produktversioner** välj **Frisläppa produktstruktur**. Processen fungerar precis som den fungerar när du släpper produkter från sidan **frisläppta produkter**. Mer information finns i [Frisläppa produktstruktur](release-product-structure.md).
- Du kan automatiskt frisläppa produkter från teknisk ändringsorder, baserat på följande faktorer:

    - Återutgivning till företag där produkter tidigare har frisläppts. Välj **Sök** för att söka igenom alla tidigare versioner och välj sedan **Visa** för att visa resultaten. På sidan **Visa** visas de tidigare produktlanseringarna, och du kan välja vilka produkter som ska återlämnas. Stäng sedan sidan **Visa** och välj **Process** för att släppa valda produkter på nytt.
    - Inställningar för automatisk publicering av teknisk produktkategori i frisläppningskontrollen. Du kan göra den här versionen som en del av arbetsflödet. När blocket **samla ut frisläppningsförslag** används kommer förslaget att släppas att fyllas i med frisläppning på nytt (se föregående lista) och produkter kommer att släppas till företag om kryssrutan **Automatisk frisläppning** vald i frisläppningskontrollen för den tekniska produktkategorin. Du kan välja **vy** för att visa resultaten på det sätt som beskrivs i föregående listobjekt. Produkterna frigörs också när blocket **process frisläppningsförslag** används. Om du bara väljer att samla in frisläppningsförslaget som en del av arbetsflödet, kan du starta frisläppningen manuellt genom att välja **process**, som beskrivs i det föregående listobjektet.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Följa upp en teknisk ändringsbegäran via en teknisk ändringsorder

Så snart en teknisk ändringsbegäran godkänns kan du följa upp den via en teknisk ändringsorder. Du kan kombinera flera tekniska ändrings begäran i en enda teknisk ändringsorder. En enskild teknisk ändringsorder kan till och med innehålla flera produkter. (Vanligtvis använder du den här metoden när samma ändring måste tillämpas på flera produkter). Du kan dock inte skapa flera tekniska ändringsorder från en enskild teknisk ändringsbegäran.

Om du vill följa upp en ändringsbegäran via en ändringsorder öppnar du begäran och väljer sedan i åtgärdsfönstret på fliken **Ändringsorder** i gruppen **Teknisk ändringsorder** välj **Kopiera länk och produkter**. Du kan sedan välja en befintlig ändringsorder för att ansluta ändringsbegäran till, eller så kan du skapa en ny teknik ändringsorder för den specifika förfrågan.

## <a name="engineering-change-order-report"></a>Rapport om konstruktionsändringsorder

Tekniska ändringsorder rapporter beskriver de ändringar som har gjorts i en teknisk ändringsorder. De är användbara både under och efter gransknings- och godkännandeprocessen.

Om du vill visa en rapport för teknisk ändringsorder öppnar du relevant ändringsorder och i åtgärdspanelen, på fliken **ändringsorder** i gruppen **vy** väljer du **Rapport för teknisk ändringsorder**.

## <a name="fields-on-an-engineering-change-order"></a>Fält på en teknisk ändringsorder

De flesta fält på teknik ändringsorder är samma fält för frisläppta produkter, tekniska versioner, dokument, strukturlistor (rader) och flöden (operationer). Fälten i följande tabell är dock unika för ändringsorder.

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