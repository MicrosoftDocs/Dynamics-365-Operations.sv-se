---
title: Produkter och kategorier saknas efter en miljökopia
description: Denna artikel innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en webbplats har kopierats mellan olika miljöer eller i samma miljö.
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
ms.openlocfilehash: 0c094f6da7756d2a6a3b80ebdb211d7b78148813
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851115"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Produkter och kategorier saknas efter en miljökopia

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan hjälpa till när produkter och kategorier saknas när en webbplats har kopierats mellan olika miljöer eller i samma miljö.

## <a name="description"></a>beskrivning

När en webbplats har kopierats från en miljö till en annan, eller inom samma miljö, saknas produkter och kategorier från webbplats. Produkter och kategorier saknas i näthandelsbutiken och på fliken **Produkter** i Commerce-webbplatsbyggaren.

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
