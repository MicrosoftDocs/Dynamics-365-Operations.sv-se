---
title: Kontrollera tillgängligheten för sidinnehåll
description: I denna artikel beskrivs hur du kontrollerar tillgängligheten för sidinnehåll i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: caccb6085947193e4a5f8a8555722dd073f0c275
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884770"
---
# <a name="verify-page-content-accessibility"></a>Kontrollera tillgängligheten för sidinnehåll

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du kontrollerar tillgängligheten för sidinnehåll i Microsoft Dynamics 365 Commerce.

När du är klar med att ändra en sida bör du se till att innehållet är tillgängligt för alla på webben. I handelsredigeringsverktyg kan du enkelt kontrollera tillgängligheten för sidans innehåll med hjälp av den integrerade [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-tjänsten. Den här tjänsten verifierar sidans innehåll mot de senaste [tillgänglighetsriktlinjerna för World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).

[Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integreringen måste vara aktiverad på klient- eller platsnivå innan du kan använda den.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Aktivera Microsoft Accessibility Insights för alla webbplatser i din klientorganisation

Gör så här om [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integrering för alla Commerce-webbplatser i din klientorganisation.

> [!NOTE]
> För att komma åt klientinställningar måste du vara inloggad på Commerce som systemadministratör.

1. Logga in på Commerce som systemadministratör.
1. I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.
1. Under **innehavarinställningar** väljer du **funktioner**.
1. Ställ in alternativet **Hjälpmedelskontroll** till **på**.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Aktivera Microsoft Accessibility Insights för en enskild webbplats

Gör så här om [Microsoft Accessibility Insights](https://accessibilityinsights.io/)-integrering för en enda Commerce-webbplatser.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.
1. Under **Webbplatsinställningar** väljer du **funktioner**.
1. Ställ in alternativet **Hjälpmedelskontroll** till **på**.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Kontrollera tillgängligheten för innehållet på startsidan

Om du vill använda den integrerade tjänsten [Microsoft Accessibility Insights](https://accessibilityinsights.io/) för att skanna och verifiera innehållet på din startsida i Commerce.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **sidor**.
1. Sök och välj startsidan för att öppna den i sidredigeraren.
1. Klicka på **Hjälpmedelskontroll** i kommandofältet. Sidan **Hjälpmedelskontroll** visas.
1. När skanningen är klar granskar du innehållet i rapporten.
1. Om några kontroller misslyckades markerar du varje objekt som har misslyckats för att expandera det så att du kan visa mer information.
1. Om du vill stänga rapporten när du är klar med granskningen bläddrar du längst ned på sidan **Hjälpmedelskontroll** och väljer **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
