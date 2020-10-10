---
title: Ansvariga underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in ansvariga underhållsarbetare i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "3890091"
---
# <a name="responsible-maintenance-workers"></a>Ansvariga underhållsarbetare

[!include [banner](../../includes/banner.md)]

 

Ansvariga underhållsarbetare kan relateras till tillgångstyper, tillgångar, funktionsplatser, kategorier för underhållsjobbtyper, underhållsjobbtyper, underhållsjobbtypvarianter och handel. De kan användas på arbetsorder och underhållsbegäranden för att indikera en preferens för underhållsarbetare som ska ansvara för en arbetsorder. (Dessa underhållsarbetare är dock inte nödvändigtvis samma arbetstagare som är schemalagda för att utföra arbetsordern.) Användning av den här funktionen är valfri. Det kan till exempel användas för att välja ansvariga arbetare eller arbetargrupper för specifika arbetstyper eller arbetsområden.

Under en livscykel för arbetsorder eller en livscykel för underhållsbegäran, ansvarig underhållsarbetare  kan ändras eller uppdateras. Den här ändringen eller uppdateringen kan vara relaterade till exempelvis en ändring i livscykeltillståndet för underhållbegäran eller livscykelstatus för arbetsorder.

Inställningen på sidan **ansvariga underhållsarbetare** används *inte* vid schemaläggning av arbetsorder.

> [!NOTE]
> I tillgångshantering kan du också ställa in *önskade* underhållsarbetare som kan allokeras till arbetsorder under arbetsorderplanering.

Innan du kan ställa in ansvariga underhållsarbetare måste du ställa in arbetare och underhållsgrupper som ska vara tillgängliga för val. Information om hur du ställer in arbetare och underhållsarbetsgrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Ställ in ansvariga underhållsarbetare

1. Välj **tillgångshantering** \> **inställning** \> **arbetare** \> **ansvariga underhållsarbetare**.
2. Välj **Ny** för att skapa en post.
3. Skapa först en standardinställning för ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp där du endast anger fältet **ansvarig underhållsarbetargrupp** och/eller **ansvarig arbetare**. Lämna de återstående fälten tomma. Den här standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern.

    > [!NOTE]
    > När en underhållsbegäran skapas, när en ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp görs tillgänglig för markering på sidan **alla underhållsbegäran**, går tillgångshantering igenom alla ansvariga underhållsarbetsposter för att söka efter en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker tillgångshantering först efter en matchning för fältet **handel**. Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtypvariant** och så vidare. Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtyp** och så vidare. Som du kan se i layouten på sidan, innebär detta beteende att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshanteraren varje post från höger till vänster för en match (första **handel**, sedan **underhållsjobbtypvariant**, sedan **underhållsjobbtyp**, sedan **kategori för underhållsjobbtyp**, sedan **sedan funktionsplats**,sedan **tillgång** och slutligen**tillgångstyp**). Om ingen matchning hittas används den standardpost som inte har några val i dessa sju fält.

Följande illustration visar ett exempel på sidan **Ansvariga underhållsarbetare**.

![Sidan Ansvariga underhållsarbetare](media/08-setup-for-requests.png)
