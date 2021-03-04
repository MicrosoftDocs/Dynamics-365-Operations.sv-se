---
title: Ställa in en butikskanal
description: I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a9291dddf7d4dc080b6eb1ec60702de32a761f45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415794"
---
# <a name="set-up-a-retail-channel"></a>Ställa in en butikskanal


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). Varje butikskanal kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal. Du måste ställa in alla dessa element innan du kan skapa en butikskanel. 

Innan du skapar en butikskanal ska du kontrollera att du följer [kanalförutsättningarna](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Skapa och konfigurera en ny butikskanal

1. I navigeringsfönstret, gå till **Moduler \> Kanaler \> Butiker \> Alla butiker**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Namn** ange ett namn på den nya kanalen.
1. Markera ett unikt butiksnummer i fältet **Butiksnummer**. Numret kan vara alfanumeriskt och får innehålla högst 10 tecken.
1. I listrutan **juridisk person** anger du den relevanta juridiska personen.
1. I listrutan **lagerställe** anger du lämpligt lagerställe.
1. Välj lämplig tidszon i fältet **Butikens tidszon** .
1. I listrutan **Momsgrupp**, välj en lämplig momsgrupp för butiken.
1. Välj lämplig valuta i fältet **valuta**.
1. I fältet **Kundens adressbok** ange en giltig adressbok.
1. I fältet **Standardkund** ange en giltig standardkund.
1. I fältet **Funktionsprofil** välj en funktionsprofil om tillämpligt.
1. I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post.
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar hur en ny butikskanal skapas.

![Ny butikskanal](media/channel-setup-retail-1.png)

I bilden nedan visas ett exempel på butikskanal.

![Exempel på butikskanal](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Andra inställningar

Det finns flera andra inställningar som kan ställas in i avsnitten **Utdrag/stängning** och **Diverse**, baserat på butikens behov.

Se även [Skärmlayouter för kassan (POS)](pos-screen-layouts.md) för information om att ställa in standardskärmlayouten i avsnittet **skärmlayout** och [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) för inställningsinformation om avsnittet **Maskinvarustationer**.

I bilden nedan visas ett exempel på konfiguration av butikskanal.

![Exempel på butikskanalkonfiguration](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Konfiguration av ytterligare kanal

Det finns ytterligare objekt som måste konfigureras för en kanal som kan hittas i **åtgärdsfönstret** under avsnittet **inställningar**.

Ytterligare uppgifter som krävs för online-kanalkonfigurering inkluderar inställning av betalningsmetoder, kontantdeklaration, leveranssätt, inkomst/utgiftskonto, avsnitt, tilldelning av uppfyllelsegrupp och kassaskåp.

Följande bild visar olika ytterligare alternativ för inställning av butikskanaler på fliken **Inställningar**.

![Ställ in en kanal](media/channel-setup-retail-4.png)

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

### <a name="set-up-cash-declaration"></a>Inställningar för kontantavstämning

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kontantavstämning**.
1. I åtgärdsfönstret, välj **Ny** och skapa sedan alla beteckningar för **mynt** och **anteckning** som kan användas.

I bilden nedan visas ett exempel på en kontantavstämning.

![Inställningar för kontantavstämningar](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Ställ in leveranssätt

Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.  

Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.

1. I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.
1. I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.
1. I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen. Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.

I bilden nedan visas ett exempel på ett leveranssätt.

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Ställ in intäkts-/utgiftskonto

Så här ställer du in intäkts-/utgiftskonto.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **intäkts-/utgiftskonto**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Under **Namn**, ange ett namn.
1. Under **Söknamn**, ange ett söknamn.
1. Under **kontotyp**, ange kontotypen.
1. Ange text för **meddelanderad 1**, **meddelanderad 2**, **följesedeltext 1** och **följesedeltext 2** efter behov.
1. Under **bokföring**, ange bokföringsinformation.
1. Klicka på **Spara** i åtgärdsfönstret.

I följande bild visas ett exempel på ett intäkts-/utgiftskonto.

![Ställ in intäkts-/utgiftskonton](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Ställ in avsnitt

Så här ställer du in avsnitt.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **avsnitt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Under **avsnittsnummer**, ange ett avsnittsnummer.
1. Under **beskrivning** ange en beskrivning.
1. Under **avsnittsstorlek**, ange en avsnittsstorlek.
1. Konfigurera ytterligare inställningar för **allmän** och **försäljningsstatistik** efter behov.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-a-fulfillment-group-assignment"></a>Ange tilldelning av uppfyllelsegrupp

Så här ställer du in en tilldelning av uppfyllelsegrupp.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Tilldelning av uppfyllelsegrupp**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.
1. I listrutan **Beskrivning**, ange en beskrivning.
1. Klicka på **Spara** i åtgärdsfönstret

I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.

![Ange tilldelning av uppfyllelsegrupp](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Ställ in kassaskåp

Så här ställer du in kassaskåp.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **Kassaskåp**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange ett namn på kassaskåp.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]