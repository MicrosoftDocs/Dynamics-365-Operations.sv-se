---
title: Anslut ett experiment och redigera varianter
description: I det här avsnittet beskrivs hur du ansluter ett experiment till en tredjepartstjänst till Dynamics 365 Commerce och hur du redigerar varianter för experimentet.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: c295f6f8170b6314ddf2d0c3582343b312c815b6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238664"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Anslut ett experiment och redigera varianter

I det här avsnittet beskrivs hur du ansluter ditt experiment i Commerce och ändrar varianterna så att de överensstämmer med din hypotes. 

I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i olika avsnitt.

[ ![Experimentets användarresa – anslut och redigera](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

När du har [ställt in experimentet](experimentation-setup.md) i en tjänst från tredje part, ska du ansluta experimentet i Dynamics 365 Commerce och redigera experimentets varianter.

## <a name="planning-considerations"></a>Att tänka på vid planering

Innan du kopplar ditt experiment i Commerce måste du fatta vissa beslut som påverkar hur ditt innehåll hanteras i Commerce.

### <a name="determine-the-scope-of-your-experiment"></a>Bestäm räckvidden för ditt experiment
När du ansluter ett experiment uppmanas du att definiera testets omfång. Experiment definieras som **del** omfattning eller **hel** omfattning.
- Välj **del** om du vill göra ett experiment på en viss del av sidan. Om du väljer det här alternativet måste du identifiera vilka moduler som ingår i experimentet. Ändringar som görs av delar av standardsidan eller fragment som inte är relaterade till experimentet synkroniseras automatiskt över varianter.
- Välj **hel** om du vill göra ett experiment med en hel sida eller ett fragment. Separata kopior av standardsidan eller fragmentet skapas. Du behöver inte välja vilka moduler som ska ingå i experimentet, eftersom hela redigeringsytan kan ändras. Du kan lägga till, ta bort och ändra ordning på modulerna efter behov. Men om ändringar görs på den standard sida eller det fragment som experimentet associeras med, måste dessa ändringar synkroniseras manuellt över alla varianter.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Om du associerar experimentet med en sida som använder en layout, kan du bara omfatta experimentet med **hel**.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Bestäm om du vill schemalägga när experimentet publiceras
Om du vill schemalägga när experimentet publiceras på din aktiva webbplats, kontrollerar du att det innehåll du vill associera med experimentet finns tillgängligt i en publiceringsgrupp *innan* du ansluter experimentet. 

Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).


## <a name="connect-your-experiment"></a>Anslut ditt experiment
Om du vill ansluta ditt experiment startar du guiden **Ansluta experiment**. Guiden vägleder dig genom de steg som krävs för att ansluta experimentet. När du slutför guiden är experimentet anslutet och varianter skapas och kan redigeras.

För att komma igång med att ansluta ditt experiment i Commerce webbplatsskaparen, följ dessa steg.

1. Starta guiden **Anslutningsförsök** genom att välja **Experiment** i det vänstra navigeringsfönstret och sedan välja **Anslut**. Du kan också öppna guiden från en sida eller ett fragmentredigerare genom att redigera den och välja **Anslut experiment** i kommandofältet.

    > [!NOTE]
    > En sida kan bara kopplas till ett experiment åt gången. Om du vill ansluta en sida till ett annat experiment tar du först bort experimentet som sidan är ansluten till för tillfället.

1. Välj sidan eller fragmentet som du vill köra ditt experiment på.
1. Ange att experimentets omfattning till **del** eller **hel**, baserat på det val du gjorde i avsnittet [avgör omfattningen av experiment](#determine-the-scope-of-your-experiment) ovan.
    > [!NOTE]
    > Funktionen **Experiment på sidor eller fragment** måste vara aktiverat om du vill experimentera på hela sidan eller avsnittet. Se ämnet [Experimentera i Dynamics 365 Commerce](experimentation-overview.md) för mer information.
    
1. I det sista steget, välj **Skapa varianter och avsluta guiden**. varianter skapas för experimentet. 

## <a name="edit-your-variations"></a>Redigera dina varianter
När du avslutar guiden skapas varianter åt dig. 

Därefter ska du redigera varianterna så att de återspeglar de val du behöver kontrollera i experimentet. Välj en av följande procedurer som motsvarar den omfattning du väljer för experimentet i avsnittet [avgöra omfattningen av experimentet](#determine-the-scope-of-your-experiment) ovan.

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Redigera varianter för experiment med delomfattning
Följ dessa steg om du har definierat omfattningen av experimentet som ett **del** i avsnittet **Anslut experiment**.

1. Använd den nedrullningsbara menyn för varianter under kommandofältet för att redigera varje variant baserat på den ursprungliga hypotesen. Du kanske också vill fastställa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.
1. Välj vilken modul som ska experimenteras, välj tre punkter (...) och välj sedan **Lägg till i experimentet**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Redigera varianter för experiment med hel omfattning
Om du har definierat omfattningen av experimentet som **hel** i guiden **Anslut experiment**, i redigeringsvy, använder du den nedrullningsbara menyn för varianter under kommandofältet för att redigera varje variant utifrån den ursprungliga hypotesen. 

> [!NOTE]
> Du kanske också vill fastställa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.

## <a name="previous-step"></a>Föregående steg
[Konfigurera ett experiment](experimentation-setup.md) 


## <a name="next-step"></a>Gå vidare
[Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]