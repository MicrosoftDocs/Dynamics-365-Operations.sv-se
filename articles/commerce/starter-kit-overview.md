---
title: Modulbibliotek – översikt
description: Denna artikel innehåller en översikt över Microsoft Dynamics 365 Commerce-modulbiblioteket.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: d9dc07b3f6417c7e284c6555c2818c2a782d7683
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268957"
---
# <a name="module-library-overview"></a>Modulbibliotek – översikt

[!include [banner](includes/banner.md)]

Denna artikel innehåller en översikt över Microsoft Dynamics 365 Commerce-modulbiblioteket.

Modulbiblioteket Dynamics 365 Commerce är en samling moduler som kan användas för att skapa en näthandelssajt. Moduler har både användargränssnitt och funktionsbeteenden.

Teman kan användas i moduler i modulbiblioteket för att ändra utseende och känsla. I teman används övergripande formatmallar (CSS). Ett tema för en fiktiv näthandelssajt med namnet "Fabrikam" tillhandahålls som en del av modulbiblioteket och kan användas som referens.

## <a name="module-library-modules"></a>Moduler för modulbibliotek

Följande typer av moduler finns i modulbiblioteket:

- **Behållarmodul** – en behållarmodul är en enkel modul som fungerar som värd för andra moduler. Den styr layouten för modulerna som finns inuti.
- **Marknadsföringsmoduler** – marknadsföringsmoduler omfattar innehållsblock-, textblock-, videospelar- och karusellmoduler. Alla dessa moduler kan användas för att presentera innehåll. De kan placeras på vilken sida som helst och styrs av data från innehållshanteringssystemet (CMS).
- **Modulerna sidhuvud och sidfot** – modulerna sidhuvud och sidfot visas i sidhuvudet och sidfoten på alla webbplatssidor. Dessa moduler kan konfigureras efter behov via egenskaper.
- **Sökmoduler** – produkter kan identifieras med hjälp av sökmodulen i rubriken. Sökresultat visas på sidan med sökresultat. Produkter kan också upptäckas på kategorisidor, som är dedikerade sidor för varje kategori som stöds i kanalens navigeringshierarki. Dessutom kan förfiningsmoduler användas för att ytterligare filtrera resultat på sökresultat och kategorisidor.
- **Moduler för produktinformationssida** – produktinformationssidor använder flera moduler för att visa produktinformation. I modulen inköpsruta kan kunderna visa produkter och lägga till dem i vagnen. Andra moduler som till exempel modulen tekniska specifikationer visar produktinformation. Modulen värderingar och recensioner kan användas för att visa och ge recensioner.
- **Modulen Köp online, hämta i butik** – Modulen Köp online, hämta i butik är integrerad med Bing Maps. Den kan användas för att hitta butiker i närheten där kunderna kan hämta produkter som de har köpt.
- **Inköpsmoduler** – i inköps moduler ingår modulen kundvagn, som kan användas för att lägga till artiklar i kundvagnen. Kassamodulen visar leveransadress, leveransalternativ och presentkort, bonusprogram och kreditkortsinformation så att en order kan bearbetas. När en order har placerats kan orderbekräftelsemodulen användas för att visa bekräftelseinformationen.
- **Moduler för kontohantering** – med hjälp av inloggningsmodulen kan kunderna logga in på ett befintligt konto och registreringsmodulen skapa ett nytt konto. När ett konto har skapats kan modulen för orderhistorik användas för att visa nya order och modulen orderspecifikationer kan användas för att visa orderdetaljer.
- **Rekommendationsmodulen-** – rekommendationerna visas med modulen produktplacering. Den här modulen stöder de algoritmiska och redaktionella listor som kan visas på alla sidor.

## <a name="additional-resources"></a>Ytterligare resurser

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
