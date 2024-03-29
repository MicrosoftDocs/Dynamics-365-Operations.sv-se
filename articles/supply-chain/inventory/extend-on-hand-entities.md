---
title: Utöka datatabeller för lagerbehållning
description: Denna artikel innehåller ett exempel som visar hur du lägger till utökade fält i vyerna INVENTORSITEONHANDENTITY och INVENTWAREHOUSEONHANDENTITY så att funktionerna i dataentiteterna för lagerbehållning kan fungera tillsammans med tilläggen.
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 352b466a185bcd0778ea17e598129864c1547987
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906049"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Utöka datatabeller för lagerbehållning

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management tillhandahåller funktioner för [Utbyggbarhet](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) som gör att du kan [lägga till fält i register via tillägg](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md). Denna artikel innehåller ett exempel som visar hur du lägger till utökade fält i vyerna `INVENTORSITEONHANDENTITY` och `INVENTWAREHOUSEONHANDENTITY` så att funktionerna i dataentiteterna för lagerbehållning kan fungera tillsammans med tilläggen. Mer information om dataentiteter finns i [Datahantering – en översikt](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Här följer en lista över några av de tillgängliga enheterna för lagerbehållning:
>
> - Lagerbehållningen efter plats
> - Lagerbehållningen efter plats V2
> - Lagerbehållning enligt lagerställe
> - Lagerbehållning enligt lagerställe v2

När du har lagt till fält i register som används i den här `inventSiteOnHandView` vyn måste du synkronisera motorn så att tilläggen känns igen korrekt.

1. Utöka `InventSiteOnHandView` vyn genom att lägga till tilläggsfältet.
1. Utöka `InventSiteOnHandAggregatedView` vyn med tilläggsfälten.
1. Utöka `InventSiteOnHandAggregatedViewBuilder` viewBuilder-klassen genom att ändra `getExtensionFields()`-metoden. På det här sättet mappar du gamla visningsfält till nya viewBuilder när synkroniseringen körs.

Du har till exempel lagt till följande fyra fält i `InventTable`-registret via tillägg:

- Anpassat fält 1
- Anpassat fält 2
- Anpassat fält 3
- Anpassat fält 4

I så fall måste du ändra `getExtensionFields()`-metoden på följande sätt.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

När du har slutfört de här stegen kan du utöka lagerbehållningen per webbplats och lagerbehållning med dataentiteter för lagerställen genom att lägga till de nya fälten. På så sätt säkerställer du att de utökade fälten känns igen och tas med vid datamigrering som använder dessa dataentiteter.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]