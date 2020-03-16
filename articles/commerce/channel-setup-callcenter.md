---
title: Ställa in en kundtjänstkanal
description: I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057889"
---
# <a name="set-up-a-call-center-channel"></a>Ställa in en kundtjänstkanal


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

I Dynamics 365 Commerce, är kundtjänst en typ av kanal som kan definieras i programmet. Om du definierar en kanal för dina kundtjänstenheter kan systemet koppla specifika data och orderbearbetningsstandard till försäljningsorder. Ett företag kan definiera flera kundtjänstkanaler i Handel. 

Innan du skapar en ny kundtjänstkanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Skapa och konfigurera en ny kundtjänstkanal

Följ stegen nedan om du vill skapa och konfigurera en ny kundtjänstkanal.

1. I navigeringsfönstret går du till **moduler \> kanaler \> kundtjänst \> alla kundtjänster**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Namn** ange ett namn på den nya kanalen.
1. Välj lämplig **Juridisk enhet** från listrutan.
1. Välj lämplig plats för **Lagerställe** från listrutan.
1. I fältet **Standardkund** ange en giltig standardkund.
1. I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.
1. Ange informationskoden **prisåsidosättning**. Observera att du måste skapa en informationskod för denna första.
1. Tillhandahåll en informationskod **Spärrkod**. Observera att du måste skapa en informationskod för denna första.
1. Ange en informationskod **Kredit**. Observera att du måste skapa en informationskod för denna första.
1. Välj **Spara**.

Följande bild visar hur en ny kundtjänstkanal skapas.

![Ny kundtjänstkanal](media/channel-setup-callcenter-1.png)

I bilden nedan visas ett exempel på kundtjänstkanal.

![Exempel på kundtjänstkanal](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Konfiguration av ytterligare kanal

Ytterligare uppgifter som krävs för inställningar av kundtjänstkanal inkluderar inställning av betalningsmetoder och leveranssätt.

I följande bild visas konfigurationsalternativen **leveranssätt** och **betalningsmetoder** på fliken **inställning**.

![Ytterligare åtgärder för konfigurering av kundtjänstkanal](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Ange betalningsmetoder

Om du vill ställa in betalningsmetoder följer du dessa steg för varje betalningstyp som stöds på den här kanalen.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I navigeringsfönstret väljer du önskad betalningsmetod.
1. I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.
1. Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en kontantbetalningsmetod.

![Exempel på betalningsmetoder](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Ställ in leveranssätt

Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.  

Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.

1. I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.
1. I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.
1. I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen. Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.

I bilden nedan visas ett exempel på ett leveranssätt.

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Försäljningsfunktioner för kundtjänst](call-center-functionality.md)

[Ställ in alternativ för orderbearbetning för kundtjänst](set-up-order-processing-options.md)

[Kundtjänstkataloger](call-center-catalogs.md)

[Ställa in och arbeta med bedrägerivarningar](set-up-fraud-alerts.md)

[Ställa in kontinuitetsprogram för kundtjänster](set-up-continuity-program.md)
