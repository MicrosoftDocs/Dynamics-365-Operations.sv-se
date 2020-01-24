---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 79d0e11946f3c6f4704d3a726d33de0378eb53bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914549"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Lägga till skriptkod på webbsidor för att stödja telemetri

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.

## <a name="overview"></a>Översikt

Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering. Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics. De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.

> [!NOTE]
> Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Skapa ett återanvändbart fragment för skriptkoden

När du har skapat ett fragment för skriptkoden kan det återanvändas på alla sidor på webbplatsen.

1. Gå till **fragment \> fragment för ny sida**.
2. Välj **Externt skript**, ange ett namn på fragmentet och klicka sedan **OK**.
3. I fragmenthierarkin väljer du underordnad modul för **skriptinmatare** för det fragment du just skapade.
4. Lägg till klientskript i egenskapsrutan till höger och ange andra konfigurations alternativ som du behöver.

## <a name="add-the-fragment-to-templates"></a>Lägg till avsnittet i mallarna

1. Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.
2. I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.
3. Markera knappen med punkter (**...**) för platsen **HTML-huvud** och välj sedan **Lägg till fragment**.
4. Markera det fragment som du har skapat för skriptkoden.
5. Spara mallen och checka in den.

> [!NOTE]
> När du är klar måste du publicera fragmentet och huvudmallen. 

## <a name="additional-resources"></a>Ytterligare resurser

[Lägg till en logotyp](add-logo.md)

[Välj ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

