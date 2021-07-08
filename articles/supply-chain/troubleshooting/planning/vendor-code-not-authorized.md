---
title: Leverantörskod som inte är auktoriserad för en viss produkt och ett visst datum
description: När du försöker fastställa en planerad beställning eller lägga till en rad i en inköpsorder får du ett felmeddelande som anger att leverantörskoden inte är auktoriserad för en produkt och ett datum.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294185"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>Leverantörskod som inte är auktoriserad för en viss produkt och ett visst datum

Felkod: SYP4881415

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en planerad order eller lägger till en rad på en inköpsorder visas följande felmeddelande:

> Leverantörskoden %1 är inte auktoriserad för %2 på %3.

## <a name="cause"></a>Orsak

Felet inträffar eftersom fältet **Godkänd metod för leverantörskontroll** anges till *Endast varning* eller *Inte tillåten* för den angivna produkten och säljaren är för närvarande inte auktoriserad att leverera den produkten.

## <a name="resolution"></a>Lösning

Du löser det här problemet genom att antingen inaktivera leverantörskontrollen för den relevanta produkten eller godkänna leverantören.

Om du vill inaktivera leverantörskontrollen för en produkt följer du dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna relevanta produkt.
1. På snabbfliken **Inköp** ange fältet **Kontrollmetod för godkänd leverantör** till ett annat värde än *Endast varning* eller *Ej tillåtet*.

Om du vill godkänna en leverantör för en produkt följer du dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna relevanta artikeln.
1. I åtgärdsfönstret, på fliken **Inköp**, i gruppen **Godkänd leverantör**, klickar du på **Inställningar**.
1. På listsidan **Godkänd leverantör** lägger du till en rad i rutnätet och ställer in följande värden för den:

    - **Leverantör** - Välj den leverantör som ska godkännas för den aktuella produkten.
    - **Giltighetsdatum** – Välj det första datumet som leverantören godkänns för.
    - **Utgångsdatum** – Välj det sista datumet som leverantören godkänns för.

Mer information finns i [Godkänn leverantörer för specifika produkter](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).
