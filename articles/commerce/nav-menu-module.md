---
title: Modulen navigeringsmeny
description: Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761424"
---
# <a name="navigation-menu-module"></a>Modulen navigeringsmeny

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Det primära syftet med moduler för navigeringsmenyn är att låta användarna söka efter produkter och webbplatssidor i enlighet med den hierarki för kanaler som definierats i Dynamics 365 Commerce administration. Objekt som konfigureras i en modul för navigeringsmeny visas som navigering för webbplatshuvud. Moduler för navigeringsmenyn stöder även statiska menyalternativ som länkar till andra sidor på en näthandelsplats.

Du kan lägga till modulen navigeringsmeny på en sidhuvudmodul på en sida. I det Fabrikam-temat visar navigeringsmenyn två nivåer som standard. I det Starter-temat visar navigeringsmenyn tre nivåer som standard. Om du vill ändra antalet nivåer måste du ha ett visningstillägg i temat.

Följande illustration visar ett exempel på en navigeringsmeny för Fabrikam-webbplatsen med två nivåer av kategorihierarki och vissa statiska menyalternativ.
![Exempel på en modul för navigeringsmeny](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Egenskaper för modulen navigeringsmeny

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Källa                  | **Detaljhandel**, **Manuell redigering**, **Återförsäljning och manuell redigering** | Med värdet **Detaljhandel** kan kanalnavigeringshierarkin från Commerce-administration visas på navigeringsmenyn. Med hjälp av värdet **Manuellt redigering** kan statiska menyalternativ granskas. Värdet **Återförsäljning och manuell redigering** tillåter en blandning av båda. |
| Visa kategoribilder | **Sant** eller **falskt**    | När den här egenskapen är aktiverad visas kategoribilder på navigeringsmenyn som har definierats i Commerce-administration för varje kategori. Lades till i Commerce version 10.0.14. |
| Statiskt menyalternativ| Matris med värden| Statiska menyalternativ som associerar ett menyalternativnamn med en länk till en statisk webbplatssida. Du kan skapa menyalternativ under andra menyalternativ. Statiska menyer visas som standard på rotnivå och kommer att läggas till i kanalens navigeringshierarki om den finns. |

Följande illustration visar ett exempel på en kategoribild som visas på navigeringsmenyn för webbplatsen Fabrikam.
![Exempel på en navigeringsmodul med kategoribilder](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Lägg till en modul för navigeringsmeny i en sidhuvudmodul

Mer information om hur du lägger till en modul för navigeringsmeny i en sidhuvudmodul finns i [sidhuvudmodulen](author-header-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Cookie-kompatibilitet](cookie-compliance.md)

[Modul för sidhuvud](author-header-module.md)
