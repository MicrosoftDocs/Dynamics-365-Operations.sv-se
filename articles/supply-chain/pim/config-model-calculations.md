---
title: Beräkningar för produktkonfigurationsmodell
description: Det här avsnittet beskriver hur man skapar beräkningar för attribut i en produktkonfigurationsmodell
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f0806a5b36b04e77a5a6d10f3c2eb3d7ba680e75
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356426"
---
# <a name="product-configuration-model-calculations"></a>Beräkningar för produktkonfigurationsmodell

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur man skapar beräkningar för attribut i en produktkonfigurationsmodell.

## <a name="prerequisites"></a>Förutsättningar

Beräkningar används i en produktkonfigurationsmodell för att beräkna konfigurationsvärden för en produkt. Innan du kan börja ställa in beräkningar måste den relaterade produktkonfigurationsmodellen finnas. En översikt över inställningsprocessen för konfigurationsmodeller och relaterade uppgifter finns i [Ställa in en produktkonfigurationsmodell](set-up-maintain-product-configuration-model.md). 

## <a name="create-a-calculation"></a>Skapa en beräkning

En beräkning består av ett uttryck och ett målattribut. För mer information, se [Frågor och Svar - Beräkningar för produktkonfigurationsmodeller](calculate-product-configuration-models.md).

Följ de här stegen om du vill skapa en beräkning för en befintlig produktmodell.

1. Gå till **Produktinformationshantering \> Allmänt \> Produktkonfigurationsmodeller**.
1. Öppna en produktkonfigurationsmodell och klicka sedan på **Redigera**.
1. På snabbfliken **Beräkningar** välj **Lägg till** för att lägga till en beräkning och anger sedan följande fält:

    - **Namn** – Ange ett namn för beräkningen.
    - **Beskrivning** – Ange en beskrivning av beräkningen.
    - **Målattribut** – Välj det attribut som du ska utföra beräkningen för.

1. Välj **Redigera uttryck**.
1. I dialogrutan **Ange en beräkning**, lägg till önskade attribut, operatorer och värden i uttrycket. Mer information om hur du arbetar med dessa element finns i [Uttrycksbegränsningar och registerbegränsningar i modeller för produktkonfiguration](expression-constraints-table-constraints-product-configuration-models.md).
1. När uttrycket är klart väljer du **OK**.

## <a name="calculation-examples"></a>Beräkningsexempel

Det här avsnittet innehåller några exempel som visar hur beräkningar fungerar.

### <a name="example-1"></a>Exempel 1

Målattributet är booleskt och beräkningen använder följande villkorliga uttryck:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

Detta uttryck returnerar värdet *sant* till målattributet, om `decimalAttribute2` är större än eller lika med `decimalAttribute1`. Annars returnerar värdet *Falsk*.

### <a name="example-2"></a>Exempel 2

I det här exemplet används textattributet `textFixedList` som målattribut. Detta attribut innehåller följande fasta listor.

| Värde | Lösarvärde |
|---|---|
| A | 1a |
| B | 2b |
| C | 2c |

Följande skärmbild visar hur inställningarna för det här attributet kan se ut i systemet.

![Attributtypsinställningar, t.ex. 2.](media/model-calculations-example2.png "Attributtypsinställningar, t.ex. 2")

Attributet används i följande villkorsutdrag:

`If[integerAttribute < 150, 0, 2]`

Om `integerAttribute` är värdet mindre 150 returnerar den här satsen textvärdet för den första posten i den fasta listan, *A*. Annars returnerar det textvärdet för den tredje posten i den fasta listan, *C*.

> [!NOTE]
> Den fasta listan motsvarar en nollbaserad uppräkning (enum) och dess värden får åtkomst till av lämpligt heltalsvärde. Därför matchas det första fasta listvärdet (*A*) matchas till *0*, det andra värdet (*B*) matchas till *1* och tredje värdet (*C*) matchas till *2*.

### <a name="example-3"></a>Exempel 3

I det här exemplet används målattributet `textFixedList` från föregående exemplet. Det använder även ett annat textattribut `textAttribute`, som innehåller följande fasta listor.

| Värde | Lösarvärde |
|---|---|
| AA | 1aa |
| BB | 2bb |

Följande skärmbild visar hur inställningarna för det här attributet kan se ut i systemet.

![Attributtypsinställningar, t.ex. 3.](media/model-calculations-example3.png "Attributtypsinställningar, t.ex. 3")

Värdet för `textFixedList` attributet beräknas med hjälp av följande villkorsutdrag:

`If[textAttribute == "1aa", 0, 2]`

Om värdet `textAttribute` har löst värdet som är lika med *1aa*, detta uttryck returnerar textvärdet för den första posten i `textFixedList` fast lista, *A*. Annars returnerar den textvärdet för den tredje posten i `textFixedList` fast lista, *C*.

> [!NOTE]
> - I det villkorliga uttrycket måste solvervärdet i attributet användas.
> - Endast textattribut med fast lista kan användas i beräkningar.

## <a name="see-also"></a>Se även

- [Frågor och Svar - Beräkningar för produktkonfigurationsmodeller](calculate-product-configuration-models.md)
- [Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell](tasks/add-expression-constraint-product-configuration-model.md)
- [Översikt över produktkonfigurationsmodeller](product-configuration-models.md)
