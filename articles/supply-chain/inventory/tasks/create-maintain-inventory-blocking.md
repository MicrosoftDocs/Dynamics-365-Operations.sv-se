---
title: Skapa och underhålla en lagerspärr
description: I detta ämne beskrivs hur du kan använda en lagerspärr i syfte att förhindra att fysiskt lager reserveras av andra utgående källdokument.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956168"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Skapa och underhålla en lagerspärr

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du kan använda en lagerspärr i syfte att förhindra att fysiskt lager reserveras av andra utgående källdokument. Innan du inleder förfarandena i detta ämne måste du ha en artikel för vilken fysiskt lager finns att tillgå.

## <a name="block-inventory"></a>Spärra lager

Följ de här stegen om du vill skapa en lagerspärrpost så att lagret spärras.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken för den nya spärrposten anger du fältet **Artikelnummer** som den artikel som du vill spärra och anger en beskrivning.
1. På snabbfliken **Allmänt**, i fältet **Kvantitet**, anger du antalet artiklar som ska spärras.
1. På snabbfliken **Lagerdimensioner** anger du den plats och det lagerställe där artiklarna som du vill spärra finns för närvarande.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Uppdatera villkoren för lagerspärrren

Följ de här stegen om du vill uppdatera en lagerspärrpost.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.
1. I listfönstret väljer du relevant spärrpost.
1. Redigera posten efter behov. Exempelvis kanske du ändrar värdet för fältet **Förväntat datum** i syfte att indikera när det spärrade lagret förväntas bli tillgängligt för reservation. Om alternativet **Förväntade inleveranser** har valts visas datumet på den förväntade transaktionen. (Alternativet **Förväntade inleveranser** väljs som standard när du manuellt skapar en spärrpost.)
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="unblock-inventory"></a>Lås upp lager

Följ de här stegen om du vill ta bort en lagerspärrpost så att lagret låses upp.

1. Gå till **Lagerhantering \> Periodiska uppgifter \> Lagerspärr**.
1. I listfönstret väljer du relevant spärrpost.
1. Välj sedan **Ta bort** i åtgärdsfönstret.
1. Du uppmanas att bekräfta funktionen. Klicka på **Ja** när du vill fortsätta.
1. Stäng sidan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
