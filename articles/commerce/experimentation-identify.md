---
title: Identifiera en hypotes och fastställa mätvärden för ett experiment
description: I denna artikel beskrivs hur du identifierar hypotesen och mätvärden för framgång för ett experiment som du ska köra på en näthandelssajt i Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0b6bdf160522fc93e841ec2f8a4542ff80d8f67f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852796"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Identifiera en hypotes och fastställa mätvärden för framgång för ett experiment
Den första fasen i testcykeln omfattar att identifiera hypotesen för experimentet och fastställa vilka mått du ska spåra för att utvärdera framgång. I bilden nedan visas alla steg som ingår när du [konfigurerar och kör ett experiment](experimentation-overview.md) på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar. 

[ ![Experimentets användarresa – identifiera.](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

En hypotes är ett utdrag där du förutsäger resultatet av experimentet. Många faktorer är till för att definiera en hypotes, t.ex. forskning om användarbeteende och webbdata som du har samlat in. Med hypotesen ska du definiera det antagande eller den teori du vill validera med experimentet. Ett exempel på hypotes för experimentet kan vara "*en bild av en vit t-shirt på startsidan kommer att ge en högre klickhastighet än en marinblå tröja under sommarmånaderna eftersom personer vill kunna bära något lätt och ljust färgat på sommaren.*" I så fall skapar du varianter som omfattar en vit t-shirt och en marinblå tröja och publicerar båda samtidigt.

För att validera en hypotes bör ett experiments framgång eller misslyckande kopplas direkt till användarens handlingar. till exempel om webbplatsanvändaren klickar på en länk eller knapp. Dessa åtgärder måste motsvara händelser som ska rapporteras till tjänsten för tredje part när experimentet spåras. Med tiden kommer procentandelen användare som utför åtgärden att summeras som ett mätvärde som du kan använda för att generera rapporter och utföra analyser. För att granska alla tillgängliga händelser och attribut, se [Commerce-komponenthändelser för diagnostik och felsökning](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).

## <a name="previous-step"></a>Föregående steg
[Experiment i Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Gå vidare
[Konfigurera ett experiment](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]