---
title: Livscykeltillstånd för funktionsplats
description: I denna artikel beskrivs hur du konfigurerar funktionsplatstillstånd och livscykelmodeller i Tillgångshantering.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationLifecycleModel, EntAssetFunctionalLocationLifecycleState
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae56c2b734339343b134be95abe0ce40b70c8a0e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8934670"
---
# <a name="functional-location-lifecycle-states"></a>Livscykeltillstånd för funktionsplats

[!include [banner](../../includes/banner.md)]

 

I denna artikel beskrivs hur du konfigurerar livscykeltillstånd och livscykelmodeller för funktionsplats i Tillgångshantering. Livscykeltillstånd för funktionsplats anger de tillstånd som en funktionsplats kan gå igenom, till exempel skapat, aktiv och avslutad. Du kan visa alla funktionsplatser, oavsett livscykeltillstånd, på listsidan **alla funktionsplatser**. Du kan ändra tillståndet för en funktionsplats genom att markera den på listsidan **alla funktionsplatser** och välja **uppdatera funktionsplatstillstånd**.

## <a name="set-up-functional-location-lifecycle-states"></a>Ställ in funktionsplatsens livscykeltillstånd

1. Välj **Tillgångshanterings** > **inställningar** > **funktionsplatser** > **livscykeltillstånd**.
2. Välj **Ny** för att skapa ett nytt funktionsplatstillstånd.
3. Infoga tillstånds-ID i fältet **livscykeltillstånd** och ett namn för funktionsplatstillståndet i fältet **namn**. I fältet **livscykelmodeller** kan du se antalet livscykelmodeller för funktionsplats som använder funktionsplatstillståndet.
4. På snabbfliken **allmänt** väljer du "Ja" på växlingsknappen **aktiva** om funktionsplatsen ska vara aktiv i det här tillståndet.
5. Välj "Ja" på växlingsknappen **Skapa tillgångar** om det ska vara möjligt att automatiskt skapa en tillgång med samma namn som funktionsplatsen och installera den på funktionsplatsen i det här tillståndet.  
>[!NOTE]
>Den här växlingsknappen är kopplad till fältet **tillgångstyp** på snabbfliken **Allmänt** i formuläret **funktionsplatstyper** (**Tillgångshanterings** > **inställningar** > **funktionsplatser** > **funktionsplatstyper**).

6. Välj "Ja" på växlingsknappen **Byt namn på plats** om det ska vara möjligt att ändra namnet på funktionsplatsen i det här tillståndet.
7. Välj "Ja" på växlingsknappen **Nya underplatser** om det ska vara möjligt att lägga till nya underplatser till funktionsplatsen i det här tillståndet.
8. Välj "Ja" på växlingsknappen **Installera tillgång** om det ska vara möjligt att installera tillgångar på funktionsplatsen i det här tillståndet.
9. Välj "Ja" på växlingsknappen **Ta bort funktionsplatser** om det ska vara möjligt att ta bort funktionsplatsen i det här tillståndet.
10. Välj en tillgångsstatus i fältet **livscykeltillstånd** om du vill att tillgångens livscykeltillstånd för alla tillgångar som är installerade på funktionsplatsen ska uppdateras automatiskt i det här tillståndet. Exempel: om du stänger en funktionsplats och anger livscykeltillståndet för funktionsplats till "avslutat", kanske du vill ändra livscykeltillståndet för de tillgångar som är installerade på den funktionsplatsen automatiskt till "används inte".


>[!NOTE]
>Livscykeltillstånd för funktionsplats, livscykelmodeller och typer är relaterade och används på samma sätt som livscykeltillstånd för arbetsorder, livscykelmodeller för arbetsorder och arbetsordertyper. 

## <a name="set-up-functional-location-lifecycle-models"></a>Ställ in funktionsplatsens livscykelmodeller

När du har skapat de livscykeltillstånd som krävs för dina funktionsplatser kan de delas upp i grupper. Detta görs för att skapa livscykelmodellflödet som kan användas för olika typer av funktionsplatser. Som ett minimum ska en standardlivscykelmodell för funktionsplats skapas.

1. Välj **Tillgångshanterings** > **inställningar** > **funktionsplatser** > **livscykelmodeller**.
2. Skapa en ny livscykelmodell genom att välja **Nytt**.
3. Infoga livscykelmodell-ID i fältet **livscykelmodell** och ett namn för livscykelmodellen i fältet **namn**. I fälten **funktionsplatstyper** och **livscykeltillstånd** kan du se antalet funktionsplatstyper som använder livscykelmodellen och antalet tillstånd som har valts i livscykelmodellen.
4. På snabbfliken **livscykeltillstånd** väljer du de tillstånd som ska inkluderas i modellen. Detta görs genom att klicka på ett tillstånd i avsnittet **Återstående livscykeltillstånd** och klicka på ![framåtpilknappen.](media/02-setup-for-functional-locations.png) .
5. Om du vill markera alla tillgängliga tillstånd för en modell klickar du på knappen ![välj alla tillgängliga tillstånd.](media/03-setup-for-functional-locations.png) . Alla tillstånd överförs till avsnittet **markerade livscykeltillstånd**.
6. Om du vill ta bort ett valt tillstånd från modellen markerar du tillståndet i avsnittet **markerade livscykeltillstånd** och väljer sedan ![bakåtpilknappen](media/04-setup-for-functional-locations.png) .
7. Välj **uppdateringar av livscykeltillstånd** för att definiera vilka livscykeltillstånd som kan följa ett valt tillstånd.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
