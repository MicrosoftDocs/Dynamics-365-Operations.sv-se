---
title: Inköpsavtal
description: Det här avsnittet innehåller information om inköpsavtal. Ett inköpsavtal är ett kontrakt som ålägger en organisation att köpa en angiven kvantitet eller ett visst belopp via flera framtida inköpsorder. I utbyte mot detta åtagande får köparen särskilda priser och rabatter.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal, PurchLine, AgreementLines
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9cd3c18129724cc67560aee7bf9fc0e5dcd2ebc3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017197"
---
# <a name="purchase-agreements"></a>Inköpsavtal

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om inköpsavtal. Ett inköpsavtal är ett kontrakt som ålägger en organisation att köpa en angiven kvantitet eller ett visst belopp via flera framtida inköpsorder. I utbyte mot detta åtagande får köparen särskilda priser och rabatter. 

Inköpsavtal kan gälla för en viss kvantitet av en produkt, ett specifikt valutabelopp av en produkt eller ett specifikt valutabelopp av produkter i en anskaffningskategori. Priserna och rabatterna av inköpsavtalet åsidosätter priser och rabatter som anges i andra handelsavtal.  

På sidan **Inköpsavtal** kan du skapa, tillämpa och följa upp inköpsavtal som finns mellan din organisation och leverantörerna. Efter att du har skapat ett inköpsavtal kan du till exempel beställa direkt från det. Varje inköpsavtal har en giltighetstid som definieras av personen som skapar inköpsavtalet. Inköpets leveransdatum måste ligga inom valideringsperiodens giltighetsdatum.  

När du har skapat ett inköpsavtal måste du aktivera det innan det börjar gälla. Aktivera ett inköpsavtal genom att ställa in alternativet **Markera avtal som giltigt** på **Ja**. 

Om du vill förhindra att ditt inköpsavtal används och bekräftas markerar du avtalsstatusen som **stängd**. Du kan fortfarande uppdatera statusen till **effektiv** när som helst efter att du har gjort den här ändringen.

## <a name="responsible-workers-on-purchase-agreements"></a>Ansvarsfulla arbetstagare på inköpsavtal

Du kan identifiera en primär ansvarig arbetstagare och sekundär ansvarig arbetare på inköpsavtal klassificering. Dessa värden kommer att ärvas av det resulterande inköpsavtalet. Du behöver inte lägga till ansvariga arbetstagare till inköpsavtalet och de kan ändras direkt på basis av varje ärende på själva inköpsavtalet. Du kan inte ange en sekundär ansvarig arbetare utan en primär ansvarig arbetare, även om du inte behöver ha en sekundär ansvarig arbetare. Du kan inte ange samma arbetsprocesser som både den primära och sekundära ansvariga arbetaren.

> [!IMPORTANT]
> Innan du kan använda funktionen ansvariga part måste den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:
> 
> - **Modul:** *anskaffning och källa*
> - **Funktionsnamn:** *Ansvarig part för inköpsavtal*

## <a name="commitment-types"></a>Utfästelsetyper
Varje rad i ett inköpsavtal är en utfästelse att köpa något. Du kan använda rader från flera inköpsorder för att uppfylla utfästelsen. Det finns fyra typer av utfästelser:

-   **Utfästelse för produktkvantitet** – Du köper en viss kvantitet av en produkt.
-   **Utfästelse för produktvärde** – Du köper ett visst valutabelopp av en produkt.
-   **Värdeutfästelse för produktkategori** – Du köper ett visst valutabelopp i en anskaffningskategori. Beloppet kan gälla för en katalogartikel eller annan artikel.
-   **Värdeutfästelse** – Du köper ett visst valutabelopp av en produkt eller produkter i valfri anskaffningskategori.

## <a name="pricing-terms-for-purchase-agreements"></a>Prisvillkor för inköpsavtal
Prisvillkoren kan variera, beroende på typen av åtagande. Prisvillkoren från inköpsavtalen åsidosätter eventuella andra prisvillkor som har ställts in för handelsavtal. I tabellen nedan beskrivs de prisrelaterade fälten som påverkas av varje utfästelsetyp. Fält som innehåller **Ja** kan uppdateras på en orderrad.

| Utfästelsetyp                   | Enhetspris | Prisenhet | Rabatt i procent | Kassarabattbelopp |
|-----------------------------------|------------|------------|------------------|----------------------|
| Utfästelse för produktkvantitet       | Ja        | Ja        | Ja              | Ja                  |
| Utfästelse för produktvärde          |            |            | Ja              |                      |
| Värdeutfästelse för produktkategori |            |            | Ja              |                      |
| Värdeutfästelse                  |            |            | Ja              |                      |

## <a name="policies-for-purchase-agreements"></a>Policy för inköpsavtal
Följande regler påverkar hur länken mellan en inköpsavtalsutfästelse och motsvarande inköpsorderrader fungerar:

-   **Max framtvingas** – Den totala kvantiteten eller beloppet för alla orderrader kan inte överskrida kvantiteten eller beloppet som anges i den relaterade utfästelsen.
-   **Pris och rabatt är fasta** – Priset på en orderrad och priset på den relaterade utfästelsen måste vara samma. Om priset på orderraden ändras, bryts länken till utfästelsen. Om länken bryts bidrar orderraden inte till att uppfylla utfästelsen.
-   **Minsta frisläppningsbelopp och Högsta frisläppningsbelopp** – Om ett belopp anges visas ett meddelande om du gör en ändring av en orderrad som gör att orderraden skiljer sig från den relaterade utfästelsen.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Uppfyllelseberäkningar för inköpsavtal
Uppfyllelsekvantiteter och belopp visas på fliken **Uppfyllelse** på snabbfliken **Radinformation** på sidan **Inköpsavtal**.  

Du kan också visa det resterande beloppet eller kvantiteten som krävs för att uppfylla utfästelsen i området **Uppfyllelse**.  

I området **Avtal** visar den totala kvantiteten eller det totala beloppet som försäljningsavtalsraden är giltig för.  

Du kan nå inköpsorderraderna och fakturaraderna som bidrar till uppfyllelseberäkningen genom att välja åtgärden **Relaterad information** på raderna eller i huvudet för ett inköpsavtal.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Bekräftelser och versionshistorik för inköpsavtal
När ett inköpsavtal bekräftas lagras den aktuella versionen av inköpsavtalet i ett historikregister. Om du ändrar inköpsavtalet, kan du bekräfta det igen för att lagra en annan version av inköpsavtalet i historiken. Om du inte bekräftar ett inköpsavtal, kan du fortfarande använda det för att skapa inköpsorder. Den historiska information för inköpsavtalet lagras emellertid inte. Du kan granska eller skriva ut alla versioner av avtalet. Därefter kan du dela ändringarna med leverantören för att erhålla godkännande.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Tillämpa inköpsavtal i beställningsprocessen
När du skapar en inköpsorder kan du tillämpa ett inköpsavtal på den. Information från villkoren för avtalet, till exempel betalningsvillkoren, leveransvillkor och leveransadress, kopieras då till sidhuvudet i inköpsordern. Om inköpsordern innehåller en eller flera rader för produkter eller kategorier som omfattas av inköpsavtalet används priser och rabatter från inköpsavtalet för dessa rader. Beloppet eller kvantiteten på orderraden bidrar till uppfyllandet av utfästelsen i inköpsavtalet. Samma inköpsorder kan inkludera både rader som inte hör till ett inköpsavtal och rader som har en utfästelse för ett inköpsavtal.  

Du kan bara välja ett inköpsavtal när du skapar en inköpsorder. Du kan inte välja ett inköpsavtal efter att inköpsordern har skapats.  
I vissa fall där inköpsorder skapas indirekt kan du kontrollera om Supply Chain Management automatiskt ska söka efter tillämpliga inköpsavtal. Du kan till exempel göra det när du kopplar automatiskt bekräftade inköpsorder eller skapar inköpsorder som baseras på försäljningsorder.

## <a name="matching-policy-on-purchase-agreements"></a>Matchningspolicy för inköpsavtal
Du kan definiera en radmatchningspolicy i inköpsavtalets rubrik. Den här radmatchningspolicyn respekterar policyn för parametrar på leverantörsreskontra när fältet **Tillåt åsidosättning av matchningspolicy** på sidan **Parametrar för leverantörsreskontra** (på snabbfliken **Pris- och kvantitetsmatchning**) anges till **Högre än företagspolicy**. Dokument som refererar till inköpsavtalet kommer att använda radmatchningspolicyn som definieras på inköpsavtalshuvudet om inget annat har definierats för motsvarande artikel, artikel och leverantör, eller kategoriinköpspolicy.

## <a name="purchase-agreements-and-intercompany-trade"></a>Inköpsavtal och koncernintern handel
Koncerninterna handelsrelationer kan skapas mellan leverantörskonton och kundkonton som finns i olika juridiska personer. När en försäljnings- eller inköpsorder skapas för en av parterna skapas en koncernintern orderkedja. I orderkedjan skapas försäljningsordern och inköpsordern i de motsvarande juridiska personerna.  

Du kan skapa ett inköpsavtal eller ett försäljningsavtal för en av de koncerninterna handelsparterna. Du kan sedan skapa motsvarande försäljningsavtal eller inköpsavtal för den andra koncerninterna handelsparten i den andra juridiska personen.  

Om du skapar en koncernintern inköpsorder med det koncerninterna inköpsavtalet i en juridisk person använder motsvarande koncerninterna försäljningsorder motsvarande koncerninterna försäljningsavtal i den andra juridiska personen. Uppfyllelsen av försäljningsavtalsutfästelserna och uppfyllandet av inköpsavtalen synkroniseras, på samma sätt som den koncerninterna försäljningsordern och den koncerninterna inköpsordern synkroniseras.

## <a name="financial-dimensions-on-purchase-agreements"></a>Ekonomiska dimensioner på inköpsavtal
Du kan kopiera ekonomiska dimensioner till dokumenthuvuden eller till enskilda rader i ett inköpsavtal. Om du ändrar dimensionerna i avtalshuvudet eller på avtalsraden påverkar inte ändringen frisläppta order, men den återspeglas i alla nya order.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Skapa ett nytt inköpsavtal](tasks/create-purchase-agreement.md)

[Skapa en inköpsfrisläppningsorder från ett inköpsavtal](tasks/create-purchase-release-order-purchase-agreement.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]