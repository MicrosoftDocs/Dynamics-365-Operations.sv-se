---
title: Köra och övervaka ett experiment
description: I denna artikel beskrivs hur du kör och övervakar ett experiment i en tredjepartstjänst. Det beskriver också hur du gör ändringar i varianter efter att experimentet har startats.
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
ms.openlocfilehash: c9f62c97b46fa00791de52b2804dad5edde7f625
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909593"
---
# <a name="run-and-monitor-an-experiment"></a>Köra och övervaka ett experiment

I denna artikel beskrivs hur du kör och övervakar ditt experiment i ett tredjepartsprogram och ändrar varianter vid behov. Innan du slutför stegen i denna artikel måste du först [publicera](experimentation-preview-publish.md) experimentet i Commerce. 

I bilden nedan visas alla steg som ingår när du konfigurerar och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar.

[ ![Experimentets användarresa – kör och övervaka.](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

När du har publicerat dina varianter måste du utföra experimentet med alla steg du behöver slutföra i Commerce. Nästa steg bestämmer vilken variant som ska visas för varje användare när de begär en sida. Den tredje partens tjänst gör det enkelt att fastställa, men först måste du aktivera experimentet inom tjänsten. Eftersom stegen för att aktivera ett experiment varierar från tjänst till tjänst måste du följa instruktionerna som medföljde tjänsten eller leverantören. Om experimentet inte har aktiverats visas standardversionen för sidan (utan att några varianter visas).

Du måste hålla experimentet tillräckligt länge för att samla in data för statistiskt giltiga resultat. Använd tjänsten från en annan leverantör för att övervaka de experimentbaserade data och analyser medan experimentet körs.

## <a name="adjust-your-variations"></a>Justera varianterna
Om du av någon anledning skulle behöva ändra varianterna följer du stegen nedan.

> [!IMPORTANT]
> Om du gör ändringar i ett publicerat experiment i Commerce eller från tjänsten för tredje part, kan resultaten bli betydligt effektfulla. Överväg att låta experimentet köra kursen och sedan skapa ett nytt experiment med större ändringar.

1. I Commerce webbplatsskaparen, välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet. 
1. Välj den variant som du vill uppdatera på listrutan.
1. Gör nödvändiga ändringar och förhandsgranska och publicera sedan varianterna. Mer information finns i [Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md).
1. Gå till tjänsten från tredje part för att göra eventuella experiment inställningar som är relaterade till ändring.
    
## <a name="previous-step"></a>Föregående steg
[Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md)

## <a name="next-step"></a>Gå vidare
[Höja en variant och slutföra ett experiment](experimentation-review-complete.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]