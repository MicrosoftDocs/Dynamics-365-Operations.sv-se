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
ms.openlocfilehash: e24bceac9457212ecaafda876d19ba62df049371
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2021
ms.locfileid: "7471846"
---
# <a name="generate-variants-for-engineering-products"></a>Generera varianter för tekniska produkter

[!include [banner](../includes/banner.md)]

Avsnittet beskriver hur du genererar varianter för tekniska produkter.

## <a name="turn-on-variant-generation-for-engineering-products"></a>Aktivera generering av varianter för konstruktionsprodukter

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Konstruktionsändringshantering*
- **Funktionsnamn:** *Generering av varianter för konstruktionsprodukter*

> [!IMPORTANT]
> Funktionen *Generering av varianter för konstruktionsprodukter* visas i systemet först när du har aktiverat konfigurationsnyckeln *Konstruktionsändringshantering*. Instruktioner finns i [Konstruktionsändringshantering – översikt](product-engineering-overview.md).

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
