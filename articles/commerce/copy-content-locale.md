---
title: Kopiera innehåll till ett annat språk
description: I den här artikeln beskrivs hur du kopierar befintligt innehåll till ett annat språk på en webbplats i Microsoft Dynamics 365 Commerce-webbplatsverktyget.
author: josaw1
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 6afa871048bde22133ae083b8d56b6e99e49c401
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269272"
---
# <a name="copy-content-to-another-locale"></a>Kopiera innehåll till ett annat språk

[!include[banner](../includes/banner.md)]

I den här artikeln beskrivs hur du kopierar befintligt innehåll till ett annat språk på en webbplats i Microsoft Dynamics 365 Commerce-webbplatsverktyget.

När du skapar innehåll i Commerce-webbplatsverktyget kopplas det alltid till en spårkidentifierare, till exempel "en-us." Du kan kopiera enskilda sidor och tillgångar till ett annat språk inom samma näthandelsplats genom att ändra språk när du redigerar en innehållsartikel och sedan skapa en ny variant av artikeln. I vissa fall, till exempel när du lanserar ett helt nytt språk i din butik, finns det ingen vits med att duplicera alla innehållsartiklar på ett befintligt språk till det nya språket. Om det nya språket har samma grundspråk som ett av de befintliga språken kan du använda det befintliga språket som källspråk för kopieringsåtgärden. (Till exempel används både språket "en-us" och språket "en-au" på engelska.) På det här sättet minskar du den arbetsinsats som krävs för att språkanpassa innehållet på det nya språket.

I följande procedurer förklaras hur du lägger till ett nytt språk i en befintlig kanal, kopierar alla innehållsartiklar från ett befintligt språk till ett nytt språk, samt övervakar statusen för en kopieringsåtgärd för språk.

## <a name="add-a-new-locale"></a>Lägg till nytt språk

Följ dessa steg för att lägga till ett nytt språk i Commerce-webbplatsskaparen.

1. I webbplatsskaparen, gå till din webbplats.
1. I vänster navigeringsfönster, välj **Webbplatsinställningar** och sedan **Kanaler**.
1. Under **Kanal** väljer du den kanal du vill lägga till det nya språken i.
1. I dialogrutan för kanaler som visas till höger väljer du **Lägg till ett språk**.
1. I dialogrutan **Lägg till ett språk**, i fältet **Språk som ska stödjas** lägger du till ett språk.
1. Bekräfta att värdet för **Domän** är korrekt.
1. Under **Sökväg** anger du en unik URL-sökväg (till exempel **en-us** eller **english-us**).
1. Välj **OK**.
1. Stäng sedan dialogrutan för kanalen.
1. Under **Kanal** ska du bekräfta att det nya språket anges bredvid rätt kanal.
1. Välj **Spara och publicera**.

> [!NOTE]
> Innan det nya språkinställningen kan konfigureras i webbplatsverktyget måste den läggas till i den associerade onlinebutikskanalen i Commerce Headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Kopiera alla innehållsobjekt till ett nytt språk

Följ dessa steg för att kopiera allt innehåll till ett nytt språk i Commerce-webbplatsskaparen.

1. I webbplatsskaparen, gå till din webbplats.
1. I vänster navigeringsfönster, välj **Webbplatsinställningar** och sedan **Kanaler**.
1. Välj **Skapa språkkopia från** i kommandofältet.
1. I dialogrutan för **Skapa språkkopia** som visas till höger bekräftar du att rätt webbplats har valts under **Källwebbplats**.
1. I fältet **Källkanal** anger du källkanalen.
1. I fältet **Målkanal** anger du samma källkanal.
1. I fältet **Källspråk** anger du källspråket.
1. I fältet **Målspråk** anger du det nya språket.
1. Välj **Kopiera språk**. Ett meddelande bekräftar att åtgärden för språkversionskopiering har startat.

> [!NOTE]
> Du kan också kopiera innehåll mellan olika kanaler.

## <a name="monitor-the-status-of-the-locale-copy"></a>Övervaka status för språkversionskopia

Följ de här stegen om du vill övervaka förloppet för kopieringsåtgärden för språkversion.

1. I webbplatsskaparen, gå till din webbplats.
1. I vänster navigeringsfönster väljer du **Webbplatsinställningar** och sedan **Jobb**.
1. Under **Aktuella jobb** väljer du det jobb som du vill övervaka. I dialogrutan till höger visas jobbinformation.
