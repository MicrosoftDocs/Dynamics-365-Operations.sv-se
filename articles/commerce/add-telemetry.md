---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
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
ms.openlocfilehash: e15ba6a0d624bd97c25936aa6d3bfafb844b66c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415775"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Lägga till skriptkod på webbsidor för att stödja telemetri

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.

## <a name="overview"></a>Översikt

Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering. Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics. De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.

> [!NOTE]
> Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Skapa ett återanvändbart fragment för skriptkoden

Med hjälp av ett fragment kan du återanvända en infogad eller extern skriptkod på alla sidor på din webbplats, oavsett vilken mall de använder.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Skapa ett återanvändbart fragment för den infogade skriptkoden

Om du vill skapa ett återanvändbart fragment för den infogade skriptoden i webbplatsskaparen följer du stegen nedan.

1. Gå till **Fragment** och välj sedan **Nytt**.
1. I dialogrutan **Nytt fragment** välj **infogat skript**.
1. Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.
1. Under det fragment som du har skapat väljer du modulen **infogat standardskript**.
1. Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**. Konfigurera sedan andra alternativ som du behöver.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Markera **Publicera**.

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Skapa ett återanvändbart fragment för den externa skriptkoden

Om du vill skapa ett återanvändbart fragment för den externa skripkoden i webbplatsskaparen följer du stegen nedan.

1. Gå till **Fragment** och välj sedan **Nytt**.
1. I dialogrutan **Nytt fragment** välj **externt skript**.
1. Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.
1. Under det fragment som du har skapat väljer du modulen **externt standardskript**.
1. I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan. Konfigurera sedan andra alternativ som du behöver.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Markera **Publicera**.

> [!NOTE]
> Om säkerhetsprincip (CSP) för innehåll är aktiverad för din webbplats måste du se till att alla externa URL:er läggs till i CSP-direktivet **skript-src** i Commerce-webbplatsskaparen. Mer information finns i [hantera säkerhetsprinciper för innehåll (CSP)](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Lägga till ett fragment som innehåller skriptkod i en mall

Följ dessa steg för att lägga till ett fragment som innehåller skriptkod till en mall i webbplatsbyggaren.

1. Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.
1. I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.
1. På platsen **HTML-huvud** markera knappen med punkter (**...**) och välj sedan **Lägg till fragment**.
1. Markera det fragment som du har skapat för skriptkoden.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Markera **Publicera**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Lägga till ett externt skript eller infogat skript direkt i en mall

Om du vill infoga ett infogat eller externt skript direkt på en uppsättning sidor som kontrolleras av en enskild mall, behöver du inte skapa ett fragment först.

### <a name="add-an-inline-script-directly-to-a-template"></a>Lägga till ett infogat skript direkt i en mall

Om du vill lägga till ett infogat skript direkt på en mall i webbplatsskaparen följer du stegen nedan.

1. Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.
1. I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.
1. I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj **infogat skript**.
1. Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**. Konfigurera sedan andra alternativ som du behöver.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Markera **Publicera**.

### <a name="add-an-external-script-directly-to-a-template"></a>Lägga till ett externt skript direkt i en mall

Om du vill lägga till ett extern skript direkt på en mall i webbplatsskaparen följer du stegen nedan.

1. Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.
1. I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.
1. I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj **externt skript**.
1. I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan. Konfigurera sedan andra alternativ som du behöver.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. Markera **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en logotyp](add-logo.md)

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till en favoritikon](add-favicon.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)
