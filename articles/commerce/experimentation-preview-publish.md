---
title: Förhandsgranska och publicera ett experiment
description: I denna artikel beskrivs hur du förhandsgranskar och publicerar ett experiment från Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 5da7a4e3c17057278d02ebd45702d1de404f0dc6
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946152"
---
# <a name="preview-and-publish-an-experiment"></a>Förhandsgranska och publicera ett experiment

I denna artikel beskrivs hur du förhandsgranskar och publicerar ditt experiment Dynamics 365 Commerce när du har [kopplat experimentet och redigerat dina varianter](experimentation-connect-edit.md). I bilden nedan visas alla steg som ingår när du konfigurerar och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar.

[ ![Experimentets användarresa – granska och publicera.](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Förhandsgranska experimentvarianterna
Du kan förhandsgranskavarianterna och fortsätta redigera dem tills de ser ut som de ska.

För att förhandsgranska dina experimentvarianter i Commerce webbplatsskaparen, följ dessa steg.

1. Från rullgardinsmenyn varianter under kommandofältet för att välja innehållet du vill förhandsgranska. 
1. Klicka på **förhandsversion** i kommandofältet. En förhandsversion av hur innehållet kommer att se ut när det publiceras visas.
1. Om du vill förhandsgranska en annan variant markerar du den i variantens listruta och väljer **förhandsversion** igen.

## <a name="publish-your-experiment"></a>Publicera experimentet
Om du inte använder en publiceringsgrupp för att schemalägga när experimentet går i drift och du vill publicera direkt, väljer du **publicera** i kommandofältet. Alla varianter som hör till experimentet kommer att publiceras.
    
> [!IMPORTANT]
> Om sidan har en opublicerad URL måste du först publicera URL:en eller så visas den inte för webbplatsanvändarna. För detaljer, se [Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Använda publiceringsgrupper för att schemalägga när experimentet går i drift
varianter som skapas i webbplatsskaparen kan schemaläggas för publicering med hjälp av en publiceringsgrupp. I en publiceringsgrupp kan du ansluta en sida eller ett avsnitt till experimentet genom att välja **experiment** i det vänstra navigeringsfönstret. Du kan också göra detta genom att markera **Sidor** eller **Fragment** och följa instruktionerna i [Anslut ett experiment och redigera variationer](experimentation-connect-edit.md). Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).

När du använder publiceringsgrupper med experiment finns det några viktiga överväganden att tänka på.
- När du lägger till en sida eller ett avsnitt som har ett experiment som körs på en publiceringsgrupp, tas experimentet bort från sidan eller avsnittet i publiceringsgruppen.
- Experiment som är anslutna till sidor på en aktiv webbplats är inte tillgängliga för sidor i publiceringsgrupper och tvärtom. På samma sätt är sidor som har experiment som körs på den aktiva platsen inte tillgängliga för andra experiment i publiceringsgrupper och vice versa.
- När du publicerar eller schemalägger en publiceringsgrupp, publiceras allt innehåll i publiceringsgruppen, oavsett om det finns ett experiment som är associerat med publiceringsgruppen.
- Eftersom en publiceringsgrupp fortsätter att behållas efter att den har publicerats på en aktiv plats, kommer experimenten i publiceringsgruppen också att sparas. Därför kommer du inte att kunna associera andra experiment med samma sida eller fragment. Du undviker den här begränsningen genom att ta bort alla publiceringsgrupper med beständiga experiment. Om du vill ta bort ett experiment på en pågående webbplats som också finns i en publiceringsgrupp ska du ta bort den från publiceringsgruppen först.

### <a name="force-variations-for-testing"></a>Force-variationer för testning

När experimentet är live kan du bifoga experiment-ID:t och variations-ID:t till standardsidans URL för att framtvinga fram en variation för testning eller automation. Om till exempel URL-adressen för standardsidan är `https://fabrikam.com/modern/homepage` kan du tvinga fram en variation med en URL-adress som exempelvis `https://fabrikam.com/modern/homepage?exp=18012910471|18024360464`. I **förhandsgranskningsupplevelsen** som förklaras ovan kan du hämta ID för experiment och variant från förhandsgranskningens URL.

## <a name="previous-step"></a>Föregående steg
[Ansluta till och redigera ett experiment](experimentation-connect-edit.md)

## <a name="next-step"></a>Gå vidare
[Köra och övervaka ett experiment](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
