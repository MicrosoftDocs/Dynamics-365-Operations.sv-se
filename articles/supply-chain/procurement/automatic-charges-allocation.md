---
title: Automatisk allokering av tillägg
description: Med funktionen för tillägg i Microsoft Dynamics 365 Supply Chain Management kan du automatiskt fördela tillägg till inköpsorder eller försäljningsorder.
author: GalynaFedorova
ms.date: 09/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a0dd10ba7ce0f6eca2549edb227eb9116edea2d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857501"
---
# <a name="automatic-allocation-of-charges"></a>Automatisk allokering av tillägg

[!include [banner](../includes/banner.md)]

Beroende på vilken kund du arbetar med, eller den artikel som du säljer, kanske du vill använda särskilda tilläggsavgifter. Med funktionen *tillägg* i Microsoft Dynamics 365 Supply Chain Management kan du automatiskt fördela tillägg till inköpsorder eller försäljningsorder.

Automatiska tillägg eller automatiska tillägg tillämpas automatiskt när du skapar en försäljningsorder eller en inköpsorder. Du kan definiera automatiska tillägg för specifika leverantörer, kunder, grupper av leverantörer eller artiklar. Du kan också definiera auto tillägg som gäller för alla kunder eller leverantörer, artiklar.

## <a name="set-up-parameters"></a>Konfigurera parametrar

Sidan **Anskaffnings- och inköpsparametrar** har några inställningar som är särskilt relevanta när du vill fördela avgifter automatiskt. Om du vill slutföra denna inställning, följ dessa steg.

1. Gå till **Anskaffning och källa \> Inställningar \> Anskaffnings- och källparametrar**.
1. Öppna fliken **Priser**.
1. På snabbfliken **Priser**, gör följande inställningar:
    - **Sök efter automatiska tillägg för rubrik** – Anger om tillägg automatiskt ska fördelas för inköpsorderrubriker. Ställ in detta till *Ja* om du vill använda automatisk allokering av avgifter.
    - **Sök efter automatiska tillägg för rad** – Anger om tillägg automatiskt ska fördelas för inköpsorderrader. Ställ in detta till *Ja* om du vill använda automatisk allokering av avgifter.

## <a name="set-up-charges-codes"></a>Ställa in en tilläggskoder

Om du vill fördela tillägg måste du först definiera tilläggskoder.

1. Gör något av följande:

    - För inköpsorder: gå till **Leverantörsreskontra \> Ställa in tillägg \> Kod för tillägg**.
    - För försäljningsorder: gå till **Kundreskontra \> Ställa in tillägg \> Kod för tillägg**.

1. I åtgärdsfönstret, välj **Ny** för att skapa en ny tilläggskod.
1. Ange följande fält i nya posten:

    - **Kod för tillägg** – ange en kod för tilläggen.
    - **Beskrivning** – Ange en beskrivning av tilläggen.
    - **Momsgrupp för artikel** – Välj en artikelmomsgrupp, om detta är tillämpligt.
    - **Fördela** – Ange värdet för det här alternativet till *Ja* om du vill bedöma dina debiteringar. Det här alternativet är endast tillgängligt för försäljningsorder.
    - **Högsta beloppet** – Ange det högsta tillåtna beloppet för tilläggskoden. Det här fältet används för att validera tillägg för leverantörsfakturor. Den är bara tillgänglig för inköpsorder.

        > [!NOTE]
        > Aktivera funktionen för att validera tillägg för inköpsorder genom att gå till **Leverantörsreskontra \> Inställning \> Parametrar för leverantörsreskontra**. På snabbfliken **Fakturavalidering** i avsnittet **Fakturavalidering** ange alternativet **Aktivera fakturamatchningsvalidering** till *Ja*.

1. Snabbfliken **Bokföring** innehåller avsnittet **Debet** och **Kredit**. Ställ in följande fält, beroende på redovisningen som du vill bokföra tilläggen på:

    - **Typ** – Välj den typ av konto som du bokför till (*redovisning*, *kund* eller *artikel*).
    - **Bokföring** – Välj den typ av bokföring som ska skapas (t.ex. *Mäklaravgift* eller *Kundkvittning*).
    - **Konto** – Välj det konto som tillägget ska bokföras på.

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="create-charge-groups"></a>Skapa tilläggsgrupper

Tilläggsgrupper tilldelar automatiskt specifika tillägg till en grupp av kunder eller leverantörer. I följande underavsnitt beskrivs hur du skapar och tilldelar dessa tilläggsgrupper.

### <a name="charge-groups-for-purchase-orders"></a>Tilläggsgrupper för inköpsorder

Skapa tilläggsgrupper för inköpsorder enligt följande steg.

1. Gå till **Leverantörsreskontra \> Ställa in tillägg \> Leverantörstilläggsgrupp**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet och ange följande fält:

    - **Tilläggsgrupp** – ange namnet på tilläggsgruppen.
    - **Beskrivning** – Ange en beskrivning av tilläggsgruppen.

1. Klicka på **Spara** i åtgärdsfönstret.
1. Gå till **leverantörsreskontra \> leverantörer \> alla leverantörer** och antingen öppna en befintlig leverantör eller skapa en ny leverantör.
1. På snabbfliken **Standardvärden för inköpsorder** i avsnittet **Inköpsorder** anger du **Tilläggsgrupp** till tilläggsgruppen som du just skapade.

### <a name="charge-groups-for-sales-orders"></a>Tilläggsgrupper för försäljningsorder

Skapa tilläggsgrupper för försäljningsorder enligt följande steg.

1. Gå till **Kundreskontra \> Ställa in tillägg \> Tilläggsgrupper för kunder**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet och ange följande fält:

    - **Tilläggsgrupp** – ange namnet på tilläggsgruppen.
    - **Beskrivning** – Ange en beskrivning av tilläggsgruppen.

1. Klicka på **Spara** i åtgärdsfönstret.
1. Gå till **Kundreskontra \> Kunder \> Alla kunder** och öppna en befintlig kund eller skapa en ny kund.
1. På snabbfliken **Standardvärden för inköpsorder** i avsnittet **Försäljningsorder** anger du **Avgiftsgrupp** till avgiftsgruppen som du just skapade.

## <a name="define-auto-charges"></a>Definiera automatiska tillägg

När dina tilläggskoder har ställts in följer du dessa steg för att definiera de automatiska tilläggen.

1. Gör något av följande:

    - För inköpsorder: gå till **Anskaffning och källa \> Inställningar \> Tillägg \> Automatiska tillägg**.
    - För försäljningsorder: gå till **Kundreskontra \> Inställningar \> Ställa in tillägg \> Automatiska tillägg**.

1. I listfönstret, i fältet **Nivå**, välj nivån där din automatiska tillägg gäller:

    - *Huvud* – Tillämpa tillägg i orderrubriken.
    - *Rad* – Tillämpa tillägg till orderrader.

1. Välj en befintlig automatisk avgift om du vill redigera den eller välj **ny** om du vill definiera en ny automatisk kostnad.
1. I listan **Kontokod**, välj ett av följande värden för att ange omfattningen av konton som påverkas:

    - *Tabell* – Tilldela tillägg till en viss kund eller leverantör.
    - *Grupp* – Tilldela tillägg till en tilläggsgrupp.
    - *Alla* – Tilldela tillägg till alla kunder och leverantörer.

1. I fälten **Kundrelation** eller **Leverantörsrelation** väljer du en specifik kund eller leverantör om du anger fältet **Kontokod** till *Tabell*. Om du anger fältet **Kontokod** till *Grupp*, välj en kund- eller leverantörstilläggsgrupp.
1. I fältet **Artikelkod**, välj ett av följande värden för att ange omfattningen av artiklar som påverkas. Du kan välja en artikel kod, när du definierar auto tillägg på radnivå.

    - *Tabell* – Tilldela tillägg till en viss artikel.
    - *Grupp* – Tilldela tillägg till en avgiftsgrupp för artiklar.
    - *Alla* – Tilldela tillägg till alla artiklar.

1. I fältet **Artikelrelation** välj en specifik artikel om du anger fältet **Artikelkod** till *Tabell*. Om du anger fältet **Artikelkod** till *Grupp*, väljer du en avgiftsgrupp för artiklar.
1. **Endast för försäljningsorder:** I fältet **Kod för leveranssätt** väljer du ett av följande värden för att ange omfattningen av de leveranslägen som kommer att påverkas:

    - *Tabell* – Tilldela tillägg på ett visst leveranssätt.
    - *Grupp* – Tilldela tillägg till en viss leveranssättsgrupp.
    - *Alla* – Tilldela tillägg till alla leveranssätt.

1. **Endast för försäljningsorder:** I fältet **Relation för leveranssätt** välj ett specifikt leveranssätt om du anger fältet **Kod för leveranssätt** till *tabell*. Om du anger fältet **Kod för leveranssätt** till *Grupp*, välj en leveransgrupp.
1. På snabbfliken **Rader** om du vill definiera avgifterna och tilläggstarifferna som ska användas när den aktuella Du kan använda verktygsfältet på den här snabbfliken för att lägga till så många rader som behövs. För varje rad anger du följande fält:

    - **Valuta** – Välj den valuta som ska användas för att beräkna omkostnaden.
    - **Tilläggskod** – Välj kod för tillägget.
    - **Kategori** – Välj ett av följande värden:

        - *Fast* – Tillägget anges som ett fast belopp på raden. Fasta avgifter kan användas för avgifter i orderhuvudet och på orderraderna.
        - *Stk.* – Tillägget baseras på enheten. Dessa avgifter kan bara användas för orderrader. De kommer att visas när du beräknar ordertotalen.
        - *Procent* – Tillägget anges som en procentsats på raden. Procentsatsavgifter kan användas för avgifter i orderhuvudet och på orderraderna.
        - *Koncernintern procentsats* – tillägget anges som en procentsats på raden för koncerninterna order. Koncernintern procentsats kan bara användas för orderrader.
        - *Extern* – Avgiften beräknas av en tredjepartstjänst som är associerad med en eller flera transportföretag.

    - **Avgiftsvärde** – ange avgiftsvärdet baserat på den valda kategorin.
    - **Valutakod för tillägg** – ange en valuta för tillägget om du vill använda en annan valuta än den som du har angett i fältet **Valuta**. Du kan bara använda en annan valuta om **Debettyp** eller **Kredittyp** anges till antingen *Huvudbokskonto* eller *Artikel* för den valda tilläggskoden.
    - **Från belopp** – Ange ett startbelopp som den automatiska avgiften ska tillämpas på. Beloppet i det här sammanhanget refererar till ordertotalen.
    - **Till belopp** – Ange ett slutbelopp som den automatiska avgiften ska tillämpas på. Beloppet i det här sammanhanget refererar till ordertotalen.
    - **Momsgrupp** – Ange en momsgrupp.
    - **Plats** och **Lagerställe** – Ange en plats och ett lagerställe om tillägg endast ska tas ut för en specifik plats och lager.
    - **Behåll** – Markera den här kryssrutan för att behålla avgiftstransaktionerna efter att faktureringen har slutförts, så att avgiften tillämpas varje gång du skapar en ny faktura för det valda kundkontot.

1. **Endast för försäljningsorder:** om du vill beräkna lageravgifter bör du gå till lager [skiftindelade avgifter på försäljningsorder](/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders) för att få information.

## <a name="allocate-charges-from-the-header-to-a-line"></a>Fördela avgifter från huvudet till en rad

I följande procedur beskrivs hur du tilldelar tillägg på huvudnivå till en rad. Innan du startar den här proceduren ska du redan ha en huvudnivåavgift för typen *fasta belopp* och en order där denna avgift används. Dessutom bör ordern redan ha minst en radartikel.

1. Öppna inköpsordern eller avgiftsordern.
1. I åtgärdsfönstret följer du något av följande steg:

    - För inköpsorder: På fliken **Inköp** i gruppen **Tillägg** välj **Fördela avgifter**.
    - För försäljningsorder: På fliken **Sälj** i gruppen **Tillägg** välj **Fördela avgifter**.

1. I dialogrutan **Tilldela avgifter till orderrader** ange följande fält:

    - **Tilläggsallokering** – Välj ett av följande värden för att ange hur avgifterna ska fördelas:

        - *Nettobelopp* – fördela avgifterna enligt varje radbelopp i förhållande till det totala nettobeloppet.
        - *Kvantitet* – Fördela avgifter enligt antalet enheter för varje rad i förhållande till det totala antalet enheter.
        - *Per rad* – Fördela avgifter lika mellan det totala antalet rader.

    - **Fördela tillägg på rader** – Välj ett värde som anger om avgifter ska fördelas på alla rader, enbart positiva rader eller enbart till negativa rader.
    - **Fördela alla** – Markera den här kryssrutan för att fördela avgifter till orderrader även om tilläggskoden har en annan debiteringstyp än *Artikel*.
    - **Mottagen** – Markera den här kryssrutan om du endast vill fördela tillägg på mottagna orderrader.
    - **Lagrad** – Markera den här kryssrutan om du endast vill fördela tillägg på endast inventerade orderrader.
    - **Visa val och tydliga specifika rader** – Markera den här kryssrutan om du vill exkludera specifika rader från den här allokeringen. När du markerar den här kryssrutan öppnas rutnätet **Välj rader som ska undantas från fördelning**. Rutnätet inkluderar bara de rader som matchar kriterierna som definieras av inställningarna **Fördela avgifter på rader** och **I lager**. Om du till exempel anger fältet **Fördela avgifter på rader** till *Positiva rader* och markerar kryssrutan **I lager** visar rutnätet bara rader som är både positiva och inventerade. Dessutom filtrerar rutnätet automatiskt bort alla rader som redan har inlevererats för den fullständiga kvantiteten. Medan rutnätet är öppet avmarkerar du kryssrutan **inkludera** för varje rad som ska undantas från allokeringen. 

        > [!IMPORTANT]
        > När du arbetar med fältet **Välj rader som ska undantas från fördelning** se till att lämna rutnätet öppet tills du väljer **fördela**. Om du stänger rutnätet innan du väljer **fördela**, går inställningarna i rutnätet förlorade. Därför fördelas avgifter utifrån de kriterier som du tidigare definierat.

1. Välj **fördela** om du vill använda inställningarna och stänga dialogrutan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
