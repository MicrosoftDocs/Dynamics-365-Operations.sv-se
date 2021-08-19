---
title: Försäljningsavtal – översikt
description: Det här ämnet innehåller information om försäljningsavtal. Ett försäljningsavtal är ett kontrakt där kunden förbinder sig att köpa produkter i en viss mängd eller för ett visst ett belopp över tid, i utbyte mot specialpriser och rabatter.
author: omulvad
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage, SalesAgreementInvoiceJournal, SalesAgreementInvoicePart
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "9554"
- intro-internal
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cff7125e4ba6b27c60253d6dc5ef37b0fd61267800000ea75cb8fb5d3b7a6ccd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779192"
---
# <a name="sales-agreements-overview"></a>Försäljningsavtal – översikt

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om försäljningsavtal. Ett försäljningsavtal är ett kontrakt där kunden förbinder sig att köpa produkter i en viss mängd eller för ett visst ett belopp över tid, i utbyte mot specialpriser och rabatter.

En försäljningsavtal är ett kontrakt som binder kunden till att köpa produkter i en viss kvantitet eller för ett specifikt belopp över tid, i utbytet mot speciella särskilda priser, rabatter, och andra särskilda villkor, till exempel betalnings- och leveransvillkor. Priserna och rabatterna i inköpsavtalet åsidosätter eventuella priser och rabatter som anges i andra handelsavtal som kan finnas.  

Giltighetsperioden för försäljningsavtalsraden anges med fälten **Giltighetsdatum** pch **Utgångsdatum** på avtalet. En kunds försäljningsorder kvalificerar för avtaltermerna om begärt transportdatum är inom giltighetstiden. Alla försäljningsorderrader som är kopplade till ett försäljningsavtal, bidrar till uppfyllelse av det försäljningsavtalet.  

Du kan skapa en försäljningsorder direkt från ett försäljningsavtal, med hjälp av åtgärden **Frisläpp order**. Alternativt kan du välja ett effektivt försäljningsavtal när du tar order (mer information finns i avsnittet ”Använda försäljningsavtal i beställningsprocessen" i denna artikel).  

> Obs! I tidigare versioner kallades försäljningsavtal för ramförsäljningsordrar.

## <a name="commitment-types"></a>Utfästelsetyper
Varje rad i ett försäljningsavtal är en utfästelse att sälja något. I allmänhet finns det två kategorier av utfästelser:

-   **Värdeutfästelse**– Kunden förbinder sig att köpa produkter för ett specifikt belopp.
-   **Kvantitetsutfästelse**– Kunden förbinder sig att köpa produkter i en specifik kvantitet.

Dessutom kan ett avtal låta kunden åta sig att köpa en specifik produkt eller produkter i en produktkategori. Genom att kombinera dessa två faktorer (värde jämfört med kvantitet och specifika produkter jämfört med produktkategorier), får du fyra typer av åtagande:

-   **Produktkvantitetsutfästelse**– Kunden förbinder sig att köpa produkter i en specifik kvantitet. Rader som använder den här utfästelsetypen definieras av ett artikelnummer och av kvantiteten och enheten som har beslutades. Fältet **Belopp** är inte tillgängligt.
-   **Produktvärdeutfästelse**– Kunden förbinder sig att köpa specifika produkter för ett specifikt belopp. Rader som använder den här utfästelsetypen definieras av ett artikelnummer och av beloppet som har beslutats. Fälten **Kvantitet** och **Enhet** är inte tillgängliga.
-   **Produktkategoriutfästelse** – Kunden förbinder sig att köpa produkter från en specifik försäljningskategori för ett specifikt belopp. Rader som använder den här utfästelsetypen definieras av en försäljningkategori i hierarkin med försäljningkategorier och ett belopp. Fälten **Kvantitet** och **Enhet** är inte tillgängliga.
-   **Värdeutfästelse** – Kunden förbinder sig att köpa någon produkt eller produkter i någon anskaffningskategori för ett specifikt belopp. Fälten **Kvantitet** och **Enhet** är inte tillgängliga.

Rader i samma försäljningsavtalet kan ha andra typer av utfästelser.

## <a name="pricing-terms-for-sales-agreements"></a>Prisvillkor för försäljningsavtal
Prisvillkoren kan variera, beroende på typen av åtagande. I en försäljningsorder som är kopplad till ett försäljningsavtal, åsidosätter prissättningtermerna från det försäljningsavtalet andra prissättningtermer som gäller baserat på handelsavtal. I tabellen nedan beskrivs de prisrelaterade fälten som påverkas av varje utfästelsetyp. "Ja" indikerar att fältet kan uppdateras på en orderrad.

| Utfästelsetyp                   | Enhetspris | Prisenhet | Rabatt i procent | Kassarabattbelopp |
|-----------------------------------|------------|------------|------------------|----------------------|
| Utfästelse för produktkvantitet       | Ja        | Ja        | Ja              | Ja                  |
| Utfästelse för produktvärde          |            |            | Ja              |                      |
| Värdeutfästelse för produktkategori |            |            | Ja              |                      |
| Värdeutfästelse                  |            |            | Ja              |                      |

## <a name="policies-for-sales-agreements"></a>Policy för försäljningsavtal
Följande regler påverkar hur länken mellan en försäljningsavtalsutfästelse och motsvarande försäljningsavtalorderrader fungerar:

-   **Max framtvingas** – Den totala kvantiteten eller beloppet för alla orderrader kan inte överskrida kvantiteten eller beloppet som anges i den relaterade utfästelsen.
-   **Pris och rabatt är fasta** – Priset på en orderrad och priset på den relaterade utfästelsen måste vara samma. Om priset på orderraden ändras, bryts länken till utfästelsen. Om länken bryts bidrar orderraden inte till att uppfylla utfästelsen.
-   **Minsta frisläppningsbelopp** och **Högsta frisläppningsbelopp** – Om ett belopp anges visas ett meddelande om du gör en ändring av en orderrad som gör att orderraden skiljer sig från den relaterade utfästelsen.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Uppfyllelseberäkningar för försäljningsavtal
Fliken **Uppfyllelse** på snabbfliken **Radinformation** på sidan **Försäljningsavtal** visar uppfyllelsekvantiteter och -belopp.  

I området **Uppfyllelse** kan du visa totala kvantiteter och belopp för alla orderrader som är länkade till det angivna försäljningsavtalet. Du kan också visa det resterande beloppet eller kvantiteten som krävs för att uppfylla utfästelsen.  

I området **Avtal** kan du visa kvantiteter och belopp från det valda försäljningsavtalet. Dessa kvantiteter och belopp är totala kvantiteter och belopp som utfästes.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Bekräftelser och versionshistorik för försäljningsavtal
När ett försäljningsavtal bekräftas lagras den aktuella versionen av försäljningsavtalet i ett historikregister. Om du ändrar försäljningsavtalet, kan du bekräfta det igen för att lagra en annan version av försäljningsavtalet i historiken.  

Om du inte bekräftar ett försäljningsavtal, kan du fortfarande använda det för att skapa försäljningsorder. Den historiska information för försäljningsavtalet lagras emellertid inte.  

Du kan granska eller skriva ut alla ändringar av bekräftelsen. Därefter kan du dela ändringarna med kunden för att erhålla godkännande.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Använda försäljningsavtal under beställningsprocessen
Om du inte släpper försäljningsorder direkt för ett försäljningsavtal, kan du ändå koppla ett försäljningsavtal till en order under orderregistreringsprocessen. När du skapar en ny försäljningsorder och väljer ett försäljningsavtal, tillämpas villkoren för avtalet, som till exempel betalningsvillkor, leveransvillkor och leveransadress på orderrubriken och länken mellan avtalet och ordern skapas. På orderraderna kan du sedan välja produkter och kategorier som anges i försäljningsavtalet och priser och rabatter kopieras från avtalet. Samma försäljningsorder kan inkludera både rader som inte hör till ett försäljningsavtal och rader som har en utfästelse för ett försäljningsavtal.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Ändra försäljningsorder som är kopplade till försäljningsavtal
Om du har skapat (frisläppt) en försäljningsorder mot ett försäljningsavtal, kan vissa fält i försäljningsorderraderna ändras om du tar bort länken till de associerade försäljningsavtalsraderna. Följande tabeller anger några av dessa fält.

| Fält                                                             | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Begärt transportdatum                                               | Om du ändrar begärt transportdatum till ett datum som infaller tidigare än värdet **Gäller från** på försäljningsavtalsraden, måste du ta bort länken till försäljningsavtalsraden innan du kan spara det ändrade transportdatumet. Om du ändrar begärt transportdatum till ett datum som infaller senare än värdet **Utgångsdatum** på försäljningsavtalsraden, måste du ta bort länken till försäljningsavtalsraden innan du kan spara det ändrade transportdatumet. |
| CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet amount | Om du ändrar värdet i något av dessa fält, och om kryssrutan **Pris och rabatt är fasta** markeras på en associerad försäljningsavtalsrad, kommer en meddelanderuta att uppmana dig till att spara ändringen. Klicka på **Ja** om du vill ta bort länken till försäljningsavtalsraden och om du vill räkna om priset. Klicka på **Nej** om du vill ta bort länken till försäljningsavtalsraden och om du inte vill räkna om priset.                                                                   |
| Nettobelopp                                                        | Om du anger ett belopp som överskrider beloppet som anges på en försäljningsavtalsrad, där kryssrutan **Max framtvingas** kommer en meddelanderuta att uppmana dig att spara det ändrade beloppet. Klicka på **Ja** om du vill ta bort länken till försäljningsavtalsraden och om du vill räkna om priset. Klicka på **Nej** om du vill ta bort länken till försäljningsavtalsraden och om du inte vill räkna om priset.                                                                 |
| Kvantitet                                                          | Om du anger en kvantitet som överskrider kvantiteten som anges på en försäljningsavtalsrad, där kryssrutan **Max framtvingas** kommer en meddelanderuta att uppmana dig att spara det ändrade beloppet. Klicka på **Ja** om du vill ta bort länken till försäljningsavtalsraden och om du vill räkna om priset. Klicka på **Nej** om du vill ta bort länken till försäljningsavtalsraden och om du inte vill räkna om priset.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Returnera en artikel som har beställts från ett försäljningsavtal
När en kund returnerar en produkt som har beställts från en försäljningsavtal, kan Supply Chain Management söka efter och automatiskt uppdatera den relaterade försäljningsavtalets utfästelse för att återspeglar ändringen i kvantitet eller ett belopp. Genom att skapa en returorder som baseras på den ursprungliga försäljningsordern som är kopplad till en försäljningsavtal, upprättar du en relation mellan försäljningsavtalutfästelsen, försäljningsorderraden och returnera orderfakturan.  

Om du inte vill dra av en returnerad artikelkvantiteten från försäljningsavtalutfästelsen, kan du använda kontrollen **Ta bort länk** på sidan **Returorder** för att ta bort länken mellan returordern och försäljningsavtalutfästelsen. Om du behöver återställa länken senare, klicka på **Skapa länk**.  

**Obs!** En returorder kan bara länkas till en försäljningsavtal. Om din kund returnerar mer än en produkt som har beställts från mer än ett försäljningsavtal, måste du skapa en ny returorder för varje produkt och skapa en länk till motsvarande försäljningsavtalet.

## <a name="automatic-search-for-sales-agreements"></a>Automatisk sökning efter försäljningsavtal
I vissa fall där försäljningsorder skapas indirekt, som till exempel när du skapar en kreditfaktura eller koncerninterna försäljningsorder, kan du kontrollera att systemet söker automatiskt efter tillämpliga försäljningsavtal.

## <a name="financial-dimensions-on-sales-agreements"></a>Ekonomiska dimensioner i försäljningsavtal
Du kan kopiera ekonomiska dimensioner till dokumenthuvuden eller till enskilda rader i ett försäljningsavtal. Du kan ändra dimensionerna i ett avtalshuvud eller avtalsrad när som helst. I det här fallet kopieras dimensionerna automatiskt till leveranshuvudet eller leveransraden på leveransordern.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]