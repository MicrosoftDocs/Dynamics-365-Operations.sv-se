---
title: Modul för webbplatsväljare
description: Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: bd54695f54b501631f916328c05bfd47e538d50d
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055840"
---
# <a name="site-selector-module"></a>Modul för webbplatsväljare

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Om ett företag har olika webbplatser på olika marknader, regioner och språk, behöver webbplatsanvändarna ett enkelt sätt att växla mellan platserna och välja sin föredragna webbplats att handla på. I det här scenariot kan du använda modulen webbplatsväljare för att söka på flera webbplatser.

Modulen webbplatsväljare måste vara konfigurerad med en lista över platser (marknader, regioner eller språk) som webbplatsanvändarna kan bläddra i.

> [!NOTE]
> Modulen webbplatsväljare är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.

I följande bild visas ett exempel på en modul för webbplatsväljare som finns i rubriken på en webbplatssida.

![Exempel på en modul för webbplatsväljare i rubriken till en webbplatssida](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Egenskaper för modul för webbplatsväljare

| Egenskapsnamn | Värde                 | beskrivning |
|---------------|-----------------------|-------------|
| Rubrik       | Text                  | Rubriken för modulen. |
| Webbplatsalternativ  | Namn, bild, URL      | Den här egenskapen anger ett namn, en länk till webbplatsens startsida och en valfri bild som ska visas för varje webbplats som ingår i modulen. Bilden kan vara en flagga eller en del representation av en marknad, region eller nationella inställningar. |

## <a name="add-a-site-selector-module-to-a-page"></a>Lägg till modulen för webbplatsväljare till en sida

Modulen webbplatsväljare kan läggas till i [huvudmodul](author-header-module.md) under platsen för webbplatsväljare. När den har lagts till kan du definiera modulens rubrik och webbplatsalternativ.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för navigeringssökväg](add-breadcrumb.md)

[Modul för navigeringsmeny](nav-menu-module.md)
