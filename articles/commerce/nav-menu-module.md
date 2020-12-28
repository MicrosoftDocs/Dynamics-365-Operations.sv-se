---
title: Modulen navigeringsmeny
description: Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "4415968"
---
# <a name="navigation-menu-module"></a>Modulen navigeringsmeny

[!include [banner](includes/banner.md)]

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
| Aktivera navigeringsmeny med flera nivåer | **Sant** eller **falskt** | När den här egenskapen är aktiverad kan navigeringsmenyn visa flera nivåer i navigeringsvyn. Den här funktionen är endast i Dynamics 365 Commerce version 10.0.15. |
| Antal nivåer | heltal | Den här egenskapen definierar antalet nivåer som ska visas om egenskapen **Aktivera navigering i flera nivåer** är inställd på **True**. |
| Statiskt menyalternativ| Matris med värden| Statiska menyalternativ som associerar ett menyalternativnamn med en länk till en statisk webbplatssida. Du kan skapa menyalternativ under andra menyalternativ. Statiska menyer visas som standard på rotnivå och kommer att läggas till i kanalens navigeringshierarki om den finns. |
| Visa rotmenyn | **Sant** eller **falskt** | När den här egenskapen är aktiverad kan navigeringsmenyn definieras under en anpassad rot (t.ex. **handla nu**). Den här funktionen är endast i Dynamics 365 Commerce version 10.0.15. |
| Rotmeny | sträng | Den här egenskapen kan användas för att definiera text för en anpassad rot om egenskapen **Visa rotmeny** är inställd på **True**. |

Följande illustration visar ett exempel på en kategoribild som visas på navigeringsmenyn för webbplatsen Fabrikam.
![Exempel på en navigeringsmodul med kategoribilder](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Lägg till en modul för navigeringsmeny i en sidhuvudmodul

Mer information om hur du lägger till en modul för navigeringsmeny i en sidhuvudmodul finns i [sidhuvudmodulen](author-header-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Modul för navigeringssökväg](add-breadcrumb.md)

[Modul för webbplatsväljare](site-selector.md)

[Modul för inköpsruta](add-buy-box.md)

[Cookie-kompatibilitet](cookie-compliance.md)

[Modul för sidhuvud](author-header-module.md)
