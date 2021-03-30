---
title: Iframe-modul
description: Det här avsnittet handlar om iframe-modulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 178469d58e5cb619c3eacfa6760f0eaec18be0dc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206142"
---
# <a name="iframe-module"></a>Iframe-modul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om iframe-modulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

En iframe-modul innehåller en iframe (infogad ram) som är värd för det externa innehållet på en webbplats. Det kan till exempel användas för att vara värd för ett YouTube-video eller PDF-filgranskare på valfri webbplatssida. 

En iframe-modul kräver en mål-URL. Sedan lagras innehållet på målsidan i ett HTML **iframe**-element. Externa URL:er måste finnas med i listan över tillåtna per webbplatsens säkerhetsprinciper för innehåll (CSP). För iframe-innehåll ska URL:er tillåtas genom att använda direktivet **frame-ancestor**. Mer information finns i [hantera säkerhetsprinciper för innehåll (CSP)](manage-csp.md).

> [!NOTE]
> iFrame-modulen är tillgänglig i Dynamics 365 Commerce 10.0.13-versionen.

I följande bild visas exempel på iframe-moduler som visar externa videoklipp på webbplatssidor.

![Exempel på iframe-moduler som visar externa videoklipp](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Egenskaper för iframe-modul

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Rubrik | Text | Rubriken för modulen. |
| Mål-URL | URL | URL:en som finns i modulen. |
| Höjd | Antal eller procent | Modulens höjd, i bildpunkter eller som ett procenttal. Till exempel kommer värdet **100** att behandlas som ett antal bildpunkter och värdet **100 %** behandlas som en procentsats. |
| Aria-etikett | Text | En ARIA-etikett (Accessible Rich Internet Applications) kan definieras för hjälpmedelsfunktioner. |

## <a name="add-an-iframe-module-to-a-page"></a>Lägg till iframe-modul till en sida

Om du vill lägga till en iframe-modul på en sida för att visa en extern video följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **Marknadsföringsmall** och välj sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du en **Marknadsföringsmall**. Under **sidnamn**, ange **Marknadsföringssida** och klicka sedan på **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I modulens egenskapsfönster, ange värdet **Bredd** till **Fyll behållare**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **iframe** och klicka sedan på **OK**.
1. I modulens egenskapsfönster, ange värdet **Mål-URL** till en extern URL för en video.
1. Ange andra egenskaper **rubrik** och **höjd**, efter behov.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.
1. Gå till marknadsföringssidan på din webbplats. Du bör se att videon återges i iframe-modulen.
 
## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]