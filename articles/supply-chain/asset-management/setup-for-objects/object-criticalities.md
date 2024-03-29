---
title: Allvarlighetsgradtyper för tillgång
description: Denna artikel beskriver allvarlighetsgradtyper för tillgångar i Tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cfde9a9bc681c0d758491fc5c361b5b046e20d9d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899510"
---
# <a name="asset-criticality-types"></a>Allvarlighetsgradtyper för tillgång

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver allvarlighetsgradtyper för tillgångar i Tillgångshantering. Tillgångarnas allvarlighetsgrad är relaterad till tillgångar och överförs till arbetsorder. Det går inte att ändra på en arbetsorder. Tillgångens allvarlighetsgrad används för att beräkna allvarlighetsgrad för arbetsorder vid schemaläggning av arbetsorder. Med andra ord används den för att beräkna i vilken utsträckning ett underhållsjobb på en tillgång påverkar produktionsschemat och produktiviteten i företaget. Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för Tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md).

Om du vill konfigurera allvarlighetsgrad kan du först skapa allvarlighetsgradtyper som ska användas i tillgångsinställningarna. Du ställer sedan in allvarlighetsgrad för tillgång.

## <a name="set-up-criticality-types"></a>Ställ in allvarlighetsgradtyper

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgångar** \> **allvarlighetsgradtyper**.
2. Välj **Ny** för att skapa en post.
3. I fältet **allvarlighetsgrad** anger du ett nummer som indikerar allvarlighetsgraden.
4. Ange ett namn för allvarlighetsgradtypen i fältet **Namn**.
5. Ange en faktor i fältet **Faktor**. Den här faktorn används under beräkningen av arbetsorderplanering för att fastställa den allvarlighetsgradpost som ska användas. (Den post som har den högsta faktorn används alltid.) Den här inställningen är relevant om, som visas i följande illustration, allvarlighetsgradrader skapas som har samma allvarlighetsgradvärde.

    ![Sidan Typer av allvarlighetsgrad.](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Ställ in allvarlighetsgrad för tillgång

1. Välj **Tillgångshantering** \> **inställningar** \> **allvarlighetsgrad för tillgång**.
2. Välj **Ny** för att skapa en post.
3. Beroende på hur önskad detaljnivå för allvarlighetsgrad för tillgång, gör relevanta val i **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **jobbtyp**, **jobbtypvariant** och **jobbkrav**.

    > [!NOTE]
    > När en allvarlighetsgrad för tillgång har valts går tillgångshanteraren igenom alla poster för tillgångens allvarlighetsgrad för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord kontrollerar Tillgångshantering först **jobbehov**. Om ingen matchning hittas kontrollerar den **jobbtypvariant**. Om ingen matchning hittas kontrollerar den **jobbtyp**, osv. Som du kan se i layouten på sidan innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar Tillgångshantering varje post från höger till vänster för en matchning. Om ingen matchning hittas används den standardpost som inte har några val.

4. I fältet **allvarlighetsgrad** väljer du en av de allvarlighetsgradvärden som du skapade i föregående procedur.

### <a name="notes-about-criticality-setup"></a>Anmärkningar om inställning av allvarlighetsgrad

- Om du ändrar en tillgångs allvarlighetsgrad i den här inställningen när du redan har använt den på en arbetsorder, uppdateras inte allvarlighetsgraden på arbetsordern i enlighet med detta.
- Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderrad läggs till eller tas bort från arbetsordern.
- Om en arbetsorder innehåller flera arbetsorderjobb, används alltid den högsta allvarlighetsgraden enligt fältet **faktor** på sidan **allvarlighetsgradtyper** på arbetsordern.
- I allmänhet kan tillgångens allvarlighetsgrad ändras under en period. Allvarlighetsgrad kan påverkas av inköp av ny utrustning, renoveringar, och så vidare. Överväg att omvärdera din tillgångs allvarlighetsgrad med jämna mellanrum (till exempel en gång per år eller vartannat år) för att se till att dina allvarlighetsgraddefinitioner matchar din aktuella produktionsinställning.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]