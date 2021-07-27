---
title: Förhandsgranska och publicera ett experiment
description: I det här avsnittet beskrivs hur du förhandsgranskar och publicerar ett experiment från Dynamics 365 Commerce.
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
ms.openlocfilehash: 99e873a07accd33aebfe010fbc8678cd8bc3ed9c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349314"
---
# <a name="preview-and-publish-an-experiment"></a>Förhandsgranska och publicera ett experiment

I det här avsnittet beskrivs hur du förhandsgranskar och publicerar ditt experiment Dynamics 365 Commerce när du har [kopplat experimentet och redigerat dina varianter](experimentation-connect-edit.md). I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i olika avsnitt.

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

## <a name="previous-step"></a>Föregående steg
[Ansluta till och redigera ett experiment](experimentation-connect-edit.md)

## <a name="next-step"></a>Gå vidare
[Köra och övervaka ett experiment](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]