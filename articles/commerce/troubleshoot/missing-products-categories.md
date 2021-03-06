---
title: Produkter och kategorier saknas efter en miljökopia
description: Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en site har kopierats mellan olika miljöer eller i samma miljö.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022408"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Produkter och kategorier saknas efter en miljökopia

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en site har kopierats mellan olika miljöer eller i samma miljö.

## <a name="description"></a>beskrivning

När en webbplats har kopierats från en miljö till en annan, eller inom samma miljö, saknas produkter och kategorier från webbplats. Produkter och kategorier saknas i e-handelsbutiken och på fliken **Produkter** i Commerce-webbplatsbyggaren.

## <a name="resolution"></a>Upplösning

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mappa numret på kanalens operativsystem till en ny kopierad webbplats i Commerce-webbplatsbyggaren

Mappa numret på kanalens operativsystem (OUN) till en ny kopierad webbplats i Commerce-webbplatsbyggaren, följ dessa steg.

1. Markera den nya kopierade webbplatsen.
1. Under **webbplatsinställningar**, välj **kanaler**.
1. Bredvid kanalens namn väljer du ellipsen (**...**) och väljer sedan **Ändra nätbutikskanal**.
1. I dialogrutan **Ändra nätbutikskanal** väljer du den kanal som du vill mappa till den nya, kopierade webbplatsen och välj sedan **OK**.
1. Välj **Spara och publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](../associate-site-online-store.md)
