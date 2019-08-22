---
title: Allvarlighetsgradtyper för tillgång
description: Det här avsnittet beskriver allvarlighetsgradtyper för tillgång i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660038060826ade9301e50143e49b53ba3fcd3ab
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783605"
---
# <a name="asset-criticalities"></a>Allvarlighetsgrad för tillgång

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här avsnittet beskriver allvarlighetsgradtyper för tillgång i tillgångshantering. Tillgångarnas allvarlighetsgrad är relaterad till tillgångar och överförs till arbetsorder. Det går inte att ändra på en arbetsorder. Tillgångens allvarlighetsgrad används för att beräkna allvarlighetsgrad för arbetsorder vid schemaläggning av arbetsorder. Med andra ord används den för att beräkna i vilken utsträckning ett underhållsjobb på en tillgång påverkar produktionsschemat och produktiviteten i företaget. Mer information om den inställning som är relaterad till beräkningen av bedömningspoäng för arbetsorderplanering finns i [i parametrar för tillgångshantering](../setup-for-objects/enterprise-asset-management-parameters.md).

Om du vill ställa in allvarlighetsgrad kan du först skapa allvarlighetsgradtyper som ska användas i tillgångsinställningarna. Du ställer sedan in allvarlighetsgrad för tillgång.

## <a name="set-up-criticality-types"></a>Ställ in allvarlighetsgradtyper

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **allvarlighetsgradtyper**.
2. Välj **Ny** för att skapa en post.
3. I fältet **allvarlighetsgrad** anger du ett nummer som indikerar allvarlighetsgraden.
4. Ange ett namn för allvarlighetsgradtypen i fältet **Namn**.
5. Ange en faktor i fältet **Faktor**. Den här faktorn används under beräkningen av arbetsorderplanering för att fastställa den allvarlighetsgradpost som ska användas. (Den post som har den högsta faktorn används alltid.) Den här inställningen är relevant om, som visas i följande illustration, allvarlighetsgradrader skapas som har samma allvarlighetsgradvärde.

    ![Figur 1](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Ställ in allvarlighetsgrad för tillgång

1. Välj **tillgångshantering** \> **inställningar** \> **allvarlighetsgrad för tillgång**.
2. Välj **Ny** för att skapa en post.
3. Beroende på hur önskad detaljnivå för allvarlighetsgrad för tillgång, gör relevanta val i **funktionsplats**, **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **jobbtyp**, **jobbtypvariant**och **jobbkrav**.

    > [!NOTE]
    > När en allvarlighetsgrad för tillgång har valts går tillgångshanteraren igenom alla poster för tillgångens allvarlighetsgrad för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord kontrollerar tillgångshantering först **jobbehov**. Om ingen matchning hittas kontrollerar den **jobbtypvariant**. Om ingen matchning hittas kontrollerar den **jobbtyp**, osv. Som du kan se i layouten på sidan innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning. Om ingen matchning hittas används den standardpost som inte har några val.

4. I fältet **allvarlighetsgrad** väljer du en av de allvarlighetsgradvärden som du skapade i föregående procedur.

### <a name="notes-about-criticality-setup"></a>Anmärkningar om inställning av allvarlighetsgrad

- Om du ändrar en tillgångs allvarlighetsgrad i den här inställningen när du redan har använt den på en arbetsorder, uppdateras inte allvarlighetsgraden på arbetsordern i enlighet med detta.
- Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderrad läggs till eller tas bort från arbetsordern.
- Om en arbetsorder innehåller flera arbetsorderjobb, används alltid den högsta allvarlighetsgraden enligt fältet **faktor** på sidan **allvarlighetsgradtyper** på arbetsordern.
- I allmänhet kan tillgångens allvarlighetsgrad ändras under en period. Allvarlighetsgrad kan påverkas av inköp av ny utrustning, renoveringar, och så vidare. Överväg att omvärdera din tillgångs allvarlighetsgrad med jämna mellanrum (till exempel en gång per år eller vartannat år) för att se till att dina allvarlighetsgraddefinitioner matchar din aktuella produktionsinställning.
