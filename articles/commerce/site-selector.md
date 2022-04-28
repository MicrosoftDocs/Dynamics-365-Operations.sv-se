---
title: Webbplatsväljarmodul
description: Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ad4d4d5f950d0631059d8f509e9e808a9106eb98
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551705"
---
# <a name="site-picker-module"></a>Webbplatsväljarmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

Om ett företag har olika webbplatser på olika marknader, regioner och språk, behöver webbplatsanvändarna ett enkelt sätt att växla mellan platserna och välja sin föredragna webbplats att handla på. I det här scenariot kan du använda modulen webbplatsväljare för att söka på flera webbplatser. En webbplatsväljare rekommenderas även när [geografisk detektering och omdirigering](geo-detection-redirection.md) har implementerats för din näthandelsplats, detta så att kunderna har möjlighet att åsidosätta den webbplatsinställning de anger via modulen [för lands-/regionsinställningar](country-region-picker-module.md). 

Modulen webbplatsväljare måste vara konfigurerad med en lista över platser (marknader, regioner eller språk) som webbplatsanvändarna kan bläddra i. I följande bild visas ett exempel på en modul för webbplatsväljare som finns i rubriken på en webbplatssida.

![Exempel på en modul för webbplatsväljare i sidhuvudet på en webbplatssida.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Egenskaper för modul för webbplatsväljare

| Egenskapsnamn | Värde                 | Beskrivning |
|---------------|-----------------------|-------------|
| Rubrik       | Text                  | Rubriken för modulen. |
| Webbplatsalternativ  | Namn, bild, URL      | Den här egenskapen anger ett namn, en länk till webbplatsens startsida och en valfri bild som ska visas för varje webbplats som ingår i modulen. Bilden kan vara en flagga eller en del representation av en marknad, region eller nationella inställningar. |

## <a name="add-a-site-picker-module-to-a-page"></a>Lägg till modulen för webbplatsväljare till en sida

Modulen webbplatsväljare kan läggas till i platsen **webbplatsväljare** i [huvudmodul](author-header-module.md). När modulen för webbplatsväljare har lagts till kan du definiera modulens rubrik och webbplatsalternativ. Vanligtvis finns en rubrikmodul i ett rubrikfragment som kan delas på e-handelssidor för en site. I följande exempel har modulen för webbplatsväljare lagts till på platsen för **webbplatsväljare** i en huvudmodul som finns i ett rubrikavsnitt med namnet **HeaderContainer**.

![Exempel på en modul för webbplatsväljare i rubrikavsnitt.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Rubrikmodul](author-header-module.md)

[Modul för navigeringssökväg](add-breadcrumb.md)

[Modul för navigeringsmeny](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
