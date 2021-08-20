---
title: Produktägare
description: Det här avsnittet innehåller information om produktägare. En produktägare är en grupp användare som är ansvariga för vissa produkter. Endast gruppens medlemmar kan frisläppa dessa produkter. Produktägaren kan också användas i arbetsflödet för godkännande.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4de6399f83eeb0b0e1ea6fb13e86fb6dca456ff1c9b113e024afec97cc5b68af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766737"
---
# <a name="product-owners"></a>Produktägare

[!include [banner](../includes/banner.md)]

En produktägare är en grupp användare som är ansvariga för vissa produkter. När en produktägargrupp tilldelas en produkt kan bara medlemmarna i den gruppen frisläppa produkten. Produktägaren kan också användas i arbetsflödet för godkännande i konstruktionsändringshantering.

Produktägare är globala inställningar. De är därför tillgängliga för alla juridiska personer.

## <a name="create-a-product-owner-group"></a>Skapa en produktägargrupp

Om du vill skapa en produktägargrupp och lägga till medlemmar i den följer du stegen nedan.

1. Gå till **konstruktionsändringshantering \> inställningar \> produktägare**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Produktägare** ange ett namn för grupp.
4. I fältet **Namn** ange en beskrivning för gruppen.
5. På snabbfliken **medlemmar** lägg till de arbetare som borde vara medlemmar i gruppen.

## <a name="assign-a-product-owner-to-a-product"></a>Tilldela en produktägare till en produkt

Följ dessa steg för att tilldela en produktägare till en produkt.

1. Öppna sidan **Produktinformation** för relevant produkt eller produktmall.
1. På snabbfliken **Allmänt** ställer du in **Produktägare** till namnet på den relevanta produktägargruppen.

När en produktägare tilldelas till en produkt kan bara medlemmar i produktägargruppen inställningen **Produktägare**.

Produktägaren är även synlig på sidan **Frisläppta produkter**.

## <a name="product-owners-and-product-releases"></a>Produktägare och produktlanseringar

Endast användare från en produkts produktägargrupp kan frisläppa produkten. Det finns dock ett undantag när produkten är en underordnad artikel och dess överordnade har släppts av den överordnade ägaren. Detta innebär att om produkten ingår i strukturlistan i en annan produkt kontrolleras inte produktägaren för varje artikel i strukturlistan. Endast produktägaren till den överordnade artikeln kontrolleras.

Produktens X tilldelas till exempel produktens ägargruppen *Designa skåp*. Produkt X ingår även i strukturlistan för produkt Y, som tilldelas produktägargruppen *Designa högtalare*. Om en användare från en produktägargrupp *Designa högtalare* frisläpper produkt Y och dess strukturlista, frisläpps produkt X tillsammans med produkt Y.

## <a name="product-owners-and-approvals"></a>Produktägare och godkännanden

Eftersom produktägaren vet om vissa tekniska förändringar kommer att gynna sina produkter, är det ofta klokt att ta med dem som en del av godkännande processen i konstruktionsändringshantering. Du kan implementera den här metoden genom att ställa in produktägarna som deltagarleverantörer i de arbetsflöden som används för konstruktionsändringshantering. Systemet tilldelar sedan godkännandeuppgifter i arbetsflödena, baserat på produkter som finns i konstruktionsändringshantering och teknisk ändringsorder. För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]