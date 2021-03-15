---
title: Ställ in en onlinekanal
description: I det här avsnittet beskrivs hur du skapar en ny onlinekanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 89a28d6d4f435b9cf0c39afc64c3caaf0b24ba19
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993638"
---
# <a name="set-up-an-online-channel"></a>Ställ in en onlinekanal


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny onlinekanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). En onlinebutik ger en kunder alternativet att köpa produkter från återförsäljarens onlinebutik såväl som från deras fysiska butik.

Om du vill skapa en onlinebutik i Commerce måste du först skapa en onlinekanal. Innan du skapar en ny onlinekanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).

Innan du kan skapa en ny plats måste minst en onlinebutik skapas i Commerce. Mer information finns i [skapa en handelsschemaläggare](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Skapa och konfigurera en ny onlinekanal

Följ stegen nedan om du vill skapa och konfigurera en ny onlinekanal.

1. I navigeringsfönstret, gå till **Moduler \> Kanaler \> Onlinebutiker**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Namn** ange ett namn på den nya kanalen.
1. I listrutan **juridisk person** anger du den relevanta juridiska personen.
1. I listrutan **lagerställe** anger du lämpligt lagerställe.
1. Välj lämplig tidszon i fältet **Butikens tidszon** .
1. Välj lämplig valuta i fältet **valuta**.
1. I fältet **Standardkund** ange en giltig standardkund.
1. I fältet **Kundens adressbok** ange en giltig adressbok.
1. I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.
1. I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar hur en ny onlinekanal skapas.

![Ny onlinekanal](media/channel-setup-online-1.png)

I bilden nedan visas ett exempel på onlinekanal.

![Exempel på onlinekanal](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a>Ställ in språk

Om din näthandelssajt ska stödja flera språk expanderar du avsnittet **språk** och lägger till ytterligare språk efter behov.

## <a name="set-up-payment-account"></a>Ställ in betalningskonto

Från avsnittet **betalningskonto** kan du lägga till en tredje parts betalningsleverantör. Information om hur du ställer in en Adyen betalningskoppling finns i [Dynamics 365 betalningskoppling för Adyen](../retail/dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Konfiguration av ytterligare kanal

Ytterligare uppgifter som krävs för inställningar av onlinekanal inkluderar inställning av betalsätt, leveranssätt och tilldelning av uppfyllelsegrupp.

I följande bild visas alternativen **leveranssätt**, **betalsätt** och **uppfyllelse av grupptilldelning** på fliken **inställning**.

![Ytterligare åtgärder för konfigurering av onlinekanal](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Ange betalsätt

Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I navigeringsfönstret väljer du önskad betalningsmetod.
1. I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.
1. Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en kontantbetalningsmetod.

![Exempel på betalsätt](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Ställ in leveranssätt

Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.  

Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.

1. I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.
1. I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.
1. I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen. Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.

I bilden nedan visas ett exempel på ett leveranssätt.

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Ange tilldelning av uppfyllelsegrupp

Så här ställer du in en tilldelning av uppfyllelsegrupp.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.
1. I listrutan **Beskrivning**, ange en beskrivning.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Ställa in en butikskanal](channel-setup-retail.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)

[Dynamics 365-betalningskoppling för Adyen](../retail/dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]