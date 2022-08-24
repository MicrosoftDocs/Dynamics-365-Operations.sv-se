---
title: Prenumerationsmodul
description: Denna artikel handlar om prenumerationsmoduler och beskriver hur du lägger till dessa på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 7ea9364f77455e7189b6f8784eabb793f9b6bad6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268297"
---
# <a name="subscribe-module"></a>Prenumerationsmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om prenumerationsmoduler och beskriver hur du lägger till dessa på webbsidorna i Microsoft Dynamics 365 Commerce.

Prenumerationsmoduler kan användas på webbplatssidor för att samla in kundinformation för nyhetsbrev eller erbjudanden.

I följande bild visas ett exempel på en prenumerationsmodul i sidfoten på en webbplatssida för Adventure Works.

![Exempel på en prenumerationsmodul i sidfoten på en webbplatssida för Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - Prenumerationsmodulen finns tillgänglig i modulbiblioteket för Commerce per Dynamics 365 Commerce-version 10.0.20.
> - Prenumerationsmodulen ingår i Adventure Works-temat.
> - Prenumerationsmodulen kräver ett dataåtgärdstillägg fungerar tillsammans med vissa leverantörer av marknadsföringsmeddelanden, så att nyhetsbrev eller kampanjmeddelanden via e-post kan skickas efter det att kundinformationen har registrerats.

## <a name="subscribe-module-properties"></a>Egenskaper för prenumerationsmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En textrubrik för prenumerationsmodulen, som t.ex. **Prenumerera på nyhetsbrevet** eller **Registrera dig och få 10 % rabatt**. |
| Stycke     | Stycketext | Prenumerationsmodulen stöder text i RTF-format för att tillhandahålla ytterligare information för uppmaningen till åtgärd i sidhuvudet. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Lägg till en prenumerationsmodul på en ny sida

Om du vill lägga till en modul för prenumerationslista på en ny sida och konfigurera erforderliga egenskaper i Commerce-webbplatsskaparen följer du stegen nedan.

1. Gå till **Mallar** och öppna marknadsföringsmallen för webbplatsens startsida (eller skapa en ny marknadsföringsmall).
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Prenumerera** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och öppna webbplatsens startsida (eller skapa en ny startsida med hjälp av marknadsföringsmallen).
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Prenumerera** och klicka sedan på **OK**.
1. I egenskapsfönstret för prenumerationsmodulen lägger du till en rubrik, till exempel **Prenumerera**.
1. Lägg till stycketext, t.ex. **Senaste trender, utföranden och erbjudanden. Finns du med i listan? Prenumerera och få de senaste snabberbjudandena!**
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Adventure Works-tema](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
