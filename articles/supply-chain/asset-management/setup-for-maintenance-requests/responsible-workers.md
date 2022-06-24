---
title: Ansvariga underhållsarbetare
description: I denna artikel beskrivs hur du konfigurerar ansvariga underhållsarbetare i Tillgångshantering.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9535be3161253e88083b5add7ac55c12364aa383
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875604"
---
# <a name="responsible-maintenance-workers"></a>Ansvariga underhållsarbetare

[!include [banner](../../includes/banner.md)]

 

Ansvariga underhållsarbetare kan relateras till tillgångstyper, tillgångar, funktionsplatser, kategorier för underhållsjobbtyper, underhållsjobbtyper, underhållsjobbtypvarianter och handel. De kan användas på arbetsorder och underhållsbegäranden för att indikera en preferens för underhållsarbetare som ska ansvara för en arbetsorder. (Dessa underhållsarbetare är dock inte nödvändigtvis samma arbetstagare som är schemalagda för att utföra arbetsordern.) Användning av den här funktionen är valfri. Det kan till exempel användas för att välja ansvariga arbetare eller arbetargrupper för specifika arbetstyper eller arbetsområden.

Under en livscykel för arbetsorder eller en livscykel för underhållsbegäran kan ansvarig underhållsarbetare ändras eller uppdateras. Den här ändringen eller uppdateringen kan vara relaterade till exempelvis en ändring i livscykeltillståndet för underhållbegäran eller livscykelstatus för arbetsorder.

Inställningen på sidan **ansvariga underhållsarbetare** används *inte* vid schemaläggning av arbetsorder.

> [!NOTE]
> I Tillgångshantering kan du också konfigurera *önskade* underhållsarbetare som kan allokeras till arbetsorder under arbetsorderplanering.

Innan du kan konfigurera ansvariga underhållsarbetare måste du konfigurera arbetare och underhållsgrupper som ska vara tillgängliga för val. Information om hur du konfigurerar arbetare och underhållsarbetsgrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Ställ in ansvariga underhållsarbetare

1. Välj **Tillgångshantering** \> **inställning** \> **arbetare** \> **ansvariga underhållsarbetare**.
2. Välj **Ny** för att skapa en post.
3. Skapa först en standardinställning för ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp där du endast anger fältet **ansvarig underhållsarbetargrupp** och/eller **ansvarig arbetare**. Lämna de återstående fälten tomma. Den här standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern.

    > [!NOTE]
    > När en underhållsbegäran skapas, när en ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp görs tillgänglig för markering på sidan **alla underhållsbegäran**, går Tillgångshantering igenom alla ansvariga underhållsarbetsposter för att söka efter en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker Tillgångshantering först efter en matchning för fältet **handel**. Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtypvariant** och så vidare. Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtyp** och så vidare. Som du kan se i layouten på sidan, innebär detta beteende att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshanteraren varje post från höger till vänster för en match (första **handel**, sedan **underhållsjobbtypvariant**, sedan **underhållsjobbtyp**, sedan **kategori för underhållsjobbtyp**, sedan **sedan funktionsplats**,sedan **tillgång** och slutligen **tillgångstyp**). Om ingen matchning hittas används den standardpost som inte har några val i dessa sju fält.

Följande illustration visar ett exempel på sidan **Ansvariga underhållsarbetare**.

![Sidan Ansvariga underhållsarbetare.](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]