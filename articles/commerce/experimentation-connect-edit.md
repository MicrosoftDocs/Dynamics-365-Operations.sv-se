---
title: Anslut ett experiment och redigera varianter
description: I denna artikel beskrivs hur du ansluter ett experiment i en tredjepartstjänst till Dynamics 365 Commerce och hur du redigerar varianter för experimentet.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942832"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Anslut ett experiment och redigera varianter

I denna artikel beskrivs hur du ansluter ditt experiment i Commerce och ändrar varianterna så att de överensstämmer med din hypotes. 

I bilden nedan visas alla steg som ingår när du konfigurerar och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar.

[ ![Experimentets användarresa – anslut och redigera.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

När du har [ställt in experimentet](experimentation-setup.md) i en tjänst från tredje part, ska du ansluta experimentet i Dynamics 365 Commerce och redigera experimentets varianter.

## <a name="connect-your-experiment"></a>Anslut ditt experiment
Om du vill ansluta ditt experiment startar du guiden **Ansluta experiment**. Guiden vägleder dig genom de steg som krävs för att ansluta experimentet. När du slutför guiden är experimentet anslutet och varianter skapas och kan redigeras.

För att komma igång med att ansluta ditt experiment i Commerce webbplatsskaparen, följ dessa steg.

1. Starta guiden **Anslutningsförsök** genom att välja **Experiment** i det vänstra navigeringsfönstret och sedan välja **Anslut**. Du kan också öppna guiden från en sida eller ett fragmentredigerare genom att redigera den och välja **Anslut experiment** i kommandofältet.

    > [!NOTE]
    > - En sida kan bara kopplas till ett experiment åt gången. Om du vill ansluta en sida till ett annat experiment tar du först bort experimentet som sidan är ansluten till för tillfället.
    > - Du kan bara experimentera på sidor som har en anpassad layout. Om sidan har en förinställd layout kan du först konvertera den till en anpassad layout. Du kan göra detta genom att gå till sidan och välja **Konvertera till anpassad layout** i kommandofältet. Mer information om layouter finns i [Förinställd och anpassade layouter](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Om du kopplar till ett experiment från fliken **Experiment** i vänster navigeringsfönster väljer du experimentnamnet i listan som visas.
1. Välj sidan eller fragmentet som du vill köra ditt experiment på.
1. I det sista steget, välj **Skapa varianter och avsluta guiden**. varianter skapas för experimentet. 

> [!NOTE]
> Om du vill schemalägga när experimentet publiceras på din aktiva webbplats, kontrollerar du att det innehåll du vill associera med experimentet finns tillgängligt i en publiceringsgrupp *innan* du ansluter experimentet. Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).

## <a name="edit-your-variations"></a>Redigera dina varianter

När du lämnar guiden **Anslut experiment** skapas variationer åt dig. Följ nedanstående steg för att redigera varianterna så att de återspeglar de val du behöver kontrollera i experimenthypotesen.

1. Använd den nedrullningsbara menyn för varianter under kommandofältet för att redigera varje variant baserat på den ursprungliga hypotesen. Du kanske också vill fastställa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.
1. Välj vilken modul som ska experimenteras, välj tre punkter (...) och välj sedan **Lägg till i experimentet**.

> [!NOTE]
> Överväg att skapa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.

## <a name="previous-step"></a>Föregående steg
[Konfigurera ett experiment](experimentation-setup.md) 


## <a name="next-step"></a>Gå vidare
[Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
