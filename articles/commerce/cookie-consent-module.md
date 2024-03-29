---
title: Modul för samtycke till cookies
description: Denna artikel handlar om modul för cookie-samtycke och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 8ca4cc1ffcf8229589591dce6e4666b78bba3890
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276281"
---
# <a name="cookie-consent-module"></a>Modul för samtycke till cookies

[!include [banner](includes/banner.md)]

Denna artikel handlar om modul för cookie-samtycke och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

Modul för cookie-samtycke uppmanar webbplatsanvändare att uttryckligen lämna samtycke till att tillåta cookies för alla funktioner eller moduler som spårar webbläsarcookies. Samtycke krävs första gången en webbplatsanvändare bläddrar i en ny webbläsarsession. När samtycke tas emot spåras det och webbplatsens användare kommer inte att tillfrågas om medgivande igen. Mer information finns i [kompatibilitet med cookies](cookie-compliance.md).

Om samtycke från webbplatsanvändare inte tas emot, återges inte alla funktioner eller moduler som kräver cookie-samtycke på sidan. Till exempel betalningsmodulen, modulen för sociala resurser och önskad butik kräver alla cookie-samtycke och kommer inte att återges om användarens samtycke inte har mottagits på webbplatsen. 

En modul för cookie-samtycke kan konfigureras på sidans rubrikfragment så att den kan användas när sidan läses in. Modulen för cookie-samtycke ska ha ett tydligt meddelande som informerar användaren om cookie-användning på webbplatsen och ska innehålla en länk till platsens integritetssida.

I följande bild visas ett exempel på ett samtyckesmeddelande för en cookie med en länk till platsens sekretesspolicy sida som visas i rubriken på en webbplatssida.
![Exempel på en modul för cookie-samtycke.](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Egenskaper för modul för cookie-samtycke

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| RTF-format                  | RTF-format | Anger ett RTF-meddelande till webbplatsanvändare som webbplatsen använder webbläsarcookies och som användarna bör acceptera för att använda cookies för webbplatsen. |
| Länkar | URL | En eller flera länkar kan läggas till på en webbplats sekretesspolicy som beskriver de typer av cookies som spåras på webbplatsen. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Lägga till en modul för cookie-samtycke på webbplatssidor

Om du vill lägga till en modul för cookie-samtycke på flera webbplatssidor kan den läggas till i ett avsnitt på en delad sidrubrik. När du har lagt till huvudavsnittet på alla webbplatssidor kommer ett meddelande om godkännande för cookies automatiskt att återges första gången en webbplatsanvändare navigerar till en webbplatssida.

Mer information om fragment och moduler för rubriker finns i [huvudmodul](author-header-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul för sidhuvud](author-header-module.md) 

[Cookie-kompatibilitet](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
