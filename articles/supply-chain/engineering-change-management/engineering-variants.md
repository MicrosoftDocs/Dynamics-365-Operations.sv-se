---
title: Generera varianter för tekniska produkter
description: I denna artikel beskrivs hur du genererar varianter för tekniska produkter
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 08feb66dedfa79f5a21a7723a22f3bef883431e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870765"
---
# <a name="generate-variants-for-engineering-products"></a>Generera varianter för tekniska produkter

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du genererar varianter för tekniska produkter.

## <a name="turn-variant-generation-for-engineering-products-on-or-off"></a>Aktivera eller inaktivera generering av varianter för konstruktionsprodukter

Funktionen som beskrivs i denna artikel kräver att både funktionen *Konstruktionsändringshantering* och *Variantgenerering för tekniska produkter* är aktiverade för systemet. Information om hur du aktiverar och inaktiverar funktionerna finns i [Översikt över hantering av tekniska ändringar](product-engineering-overview.md).

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Generera en eller flera nya varianter av en teknisk produkt

Du kan skapa en eller flera nya varianter av en produkt utan att kopiera information från en befintlig produkt. Det är praktiskt om du behöver skapa flera produktvarianter samtidigt.

Följande procedur är ett exempel på hur du skapar flera varianter som innehåller färgdimensionen.

1. Öppna sidan **Släppta produkter** (gå till exempel till **Konstruktionsändringshantering \> Vanligt \> Släppta produkter**).
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Ny**, väljer du **Teknisk produkt**.
1. Dialogrutan **Ny produkt** öppnas. Välj rätt **Teknikkategori**.
1. Om den valda teknikkategorin innehåller variantdimensioner kan du konfigurera värden för dem nu. Om kategorin har dimensionen **Färg** kan du ange den som *Blå* för det här exemplet.
1. Gör andra inställningar som behövs. Skapa produkten genom att välja **OK**.
1. Produkten och den blå V-1-varianten skapas och den nya produkten öppnas.
1. Lägg till en strukturlista och flöde till varianten vid behov.
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Produktmall** väljer du **Produktdimensioner**.
1. Sidan **Produktdimensioner** öppnas. På den här sidan finns en flik för varje tillgänglig dimension. På varje flik lägger du till en rad för varje värde som du vill stödja för varje relevant dimension. (I det här exemplet kan du lägga till rader på fliken **Färg** för *Vit*, *Gul* och *Grön*).
1. Stäng sidan och välj **Frisläppta produktvarianter**. Lägg märke till att den första varianten som du skapat (blå V-1) visas.
1. I åtgärdsrutan, på fliken **Produktvariant**, välj **Variantförslag**.
1. Följ något av följande steg i dialogrutan **Variantförslag**:

    - Högst upp i dialogrutan finns ett avsnitt för varje tillgänglig dimension. För varje dimension markerar du kryssrutan för varje värde som du vill skapa ett variantförslag för och väljer sedan **Föreslå** i verktygsfältet. Relevanta förslag läggs till i avsnittet **Föreslagna varianter**.
    - Välj **Föreslå alla** i verktygsfältet om du vill generera variantförslag för alla tillgängliga kombinationer av dimensionsvärden. Förslagen läggs till i avsnittet **Föreslagna varianter**.

1. I avsnittet **Föreslagna varianter**, markera kryssrutan för varje variant som du vill skapa. Välj **Skapa** för att generera och släppa de valda varianterna till konstruktionsföretaget. Följande villkor gäller:

    - Ingen av de skapade varianterna kommer att ha en strukturlista eller ett flöde.
    - Attributen för dessa varianter kommer som standard från teknikkategorin och kopieras inte från föregående variant.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Generera en variant som en kopia av en annan produktvariant

Du kan skapa en variant av en produkt baserat på en annan produktvariant. Strukturlistan och flödet från källproduktvarianten kopieras till den nya varianten. Det kan vara användbart för diskreta tillverkningsprodukter där du kan behöva skapa strukturlistan baserat på en startstrukturlista och hålla reda på ändringarna från föregående variant. För att kunna spåras registrerar systemet vilken variant som kopierats för att skapa en ny kopia.

Följande procedur är ett exempel på hur du skapar en ny variant som innehåller färgdimensionen genom att skapa en kopia av en befintlig variant

1. Öppna sidan **Släppta produkter** (gå till exempel till **Konstruktionsändringshantering \> Vanligt \> Släppta produkter**).
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Ny**, väljer du **Teknisk produkt**.
1. Dialogrutan **Ny produkt** öppnas. Välj rätt **Teknikkategori**.
1. Om den valda teknikkategorin innehåller variantdimensioner kan du konfigurera värden för dem nu. Om kategorin har dimensionen **Färg** kan du ange den som *Blå* för det här exemplet.
1. Gör andra inställningar som behövs. Skapa produkten genom att välja **OK**.
1. Produkten och den blå V-1-varianten skapas och den nya produkten öppnas.
1. Lägg till strukturlista och flöde till varianten vid behov.
1. Lägg till attribut till produktvarianten vid behov.
1. Lägg till blå V-1 produktvariant i en ändringsorder.
1. Ange **Påverkan** som *Ny variant*.
1. Välj det nya färgvärdet (t.ex. *Vit*). Observera att följande villkor gäller: 
    - Den nya varianten har strukturlista och flöde som har kopierats från föregående variant.
    - Den nya varianten har attributen som har kopierats från föregående variant.
1. Godkänn ändringsordern.
1. Bearbeta ändringsordern. När ordern har bearbetats skapas den nya V-1-varianten och släpps till teknikföretaget.
