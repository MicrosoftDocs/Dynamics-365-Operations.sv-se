---
title: Generera varianter för tekniska produkter
description: I avsnittet beskrivs hur du genererar varianter för tekniska produkter
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 57eda6a833df6ff8e91c006bbc5096554eff6c503a8b7ba2bd0b13e2f8e98f56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766171"
---
# <a name="generate-variants-for-engineering-products"></a>Generera varianter för tekniska produkter

[!include [banner](../includes/banner.md)]

Avsnittet beskriver hur du genererar varianter för tekniska produkter.

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Generera en eller flera nya varianter av en teknisk produkt

Du kan skapa en eller flera nya varianter av en produkt utan att kopiera information från en befintlig produkt. Det är praktiskt om du behöver skapa flera produktvarianter samtidigt.

Följande procedur är ett exempel på hur du skapar flera varianter som innehåller färgdimensionen.

1. Öppna sidan **Släppta produkter** (gå till exempel till **Konstruktionsändringshantering \> Vanligt \> Släppta produkter**).
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Ny**, väljer du **Teknisk produkt**.
1. Dialogrutan **Ny produkt** öppnas. Välj rätt **Teknikkategori**.
1. Om den valda teknikkategorin innehåller variantdimensioner kan du ställa in värden för dem nu. Om kategorin har dimensionen **Färg** kan du ange den som *Blå* för det här exemplet.
1. Gör andra inställningar som behövs. Skapa produkten genom att välja **OK**.
1. Produkten och den blå V-1-varianten skapas och den nya produkten öppnas.
1. Lägg till en strukturlista och flöde till varianten vid behov.
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Produktmall** väljer du **Produktdimensioner**.
1. Sidan **Produktdimensioner** öppnas. På den här sidan finns en flik för varje tillgänglig dimension. På varje flik lägger du till en rad för varje värde som du vill stödja för varje relevant dimension. (I det här exemplet kan du lägga till rader på fliken **Färg** för *Vit*, *Gul* och *Grön*).
1. Stäng sidan och välj **Varianter av släppt produkt**. Observera att den första skapade varianten (vit V-1) visas.
1. Välj **Variantförslag**.
1. Systemet föreslår varianter med de skapade färgvärdena (till exempel vit V-1, gul V-1 och grön V-1).
1. Välj föreslagna varianter och välj **OK** för att släppa varianterna till teknikföretaget. Observera att följande villkor gäller: 
    - Ingen av de skapade varianterna kommer att ha en strukturlista eller ett flöde.
    - Attributen för dessa varianter kommer som standard från teknikkategorin och kopieras inte från föregående variant.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Generera en variant som en kopia av en annan produktvariant

Du kan skapa en variant av en produkt baserat på en annan produktvariant. Strukturlistan och flödet från källproduktvarianten kopieras till den nya varianten. Det kan vara användbart för diskreta tillverkningsprodukter där du kan behöva skapa strukturlistan baserat på en startstrukturlista och hålla reda på ändringarna från föregående variant. För att kunna spåras registrerar systemet vilken variant som kopierats för att skapa en ny kopia.

Följande procedur är ett exempel på hur du skapar en ny variant som innehåller färgdimensionen genom att skapa en kopia av en befintlig variant

1. Öppna sidan **Släppta produkter** (gå till exempel till **Konstruktionsändringshantering \> Vanligt \> Släppta produkter**).
1. I åtgärdsfönstret öppnar du fliken **Produkt** och i gruppen **Ny**, väljer du **Teknisk produkt**.
1. Dialogrutan **Ny produkt** öppnas. Välj rätt **Teknikkategori**.
1. Om den valda teknikkategorin innehåller variantdimensioner kan du ställa in värden för dem nu. Om kategorin har dimensionen **Färg** kan du ange den som *Blå* för det här exemplet.
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
