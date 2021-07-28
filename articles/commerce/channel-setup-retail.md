---
title: Ställa in en butikskanal
description: I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fe6262fa8a7fb27fda7642180f605376af726e54
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346068"
---
# <a name="set-up-a-retail-channel"></a>Ställa in en återförsäljarkanal

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny butikskanal i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). Varje butikskanal kan ha egna betalsätt, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal. Du måste ställa in alla dessa element innan du kan skapa en butikskanel. 

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

![Ny butikskanal.](media/channel-setup-retail-1.png)

I bilden nedan visas ett exempel på butikskanal.

![Exempel på butikskanal.](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Andra inställningar

Det finns flera andra inställningar som kan ställas in i avsnitten **Utdrag/stängning** och **Diverse**, baserat på butikens behov.

Se även [Skärmlayouter för POS](pos-screen-layouts.md) för information om att ställa in standardskärmlayouten i avsnittet **skärmlayout** och [Konfigurera och installera Retail Hardware Station](retail-hardware-station-configuration-installation.md) för inställningsinformation om avsnittet **Maskinvarustationer**.

I bilden nedan visas ett exempel på konfiguration av butikskanal.

![Exempel på butikskanalkonfiguration.](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Konfiguration av ytterligare kanal

Det finns ytterligare artiklar som måste konfigureras för en kanal som kan hittas i åtgärdsfönstret under avsnittet **Inställningar**.

Ytterligare uppgifter som krävs för online-kanalkonfigurering inkluderar inställning av betalsätt, kontantdeklaration, leveranssätt, inkomst/utgiftskonto, avsnitt, tilldelning av uppfyllelsegrupp och kassaskåp.

Följande bild visar olika ytterligare alternativ för inställning av butikskanaler på fliken **Inställningar**.

![Konfigurera kanal.](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Ange betalsätt

Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen.

1. I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Betalningsmetod**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I navigeringsfönstret väljer du önskad betalningsmetod.
1. I avsnittet **Allmänt** anger du ett **åtgärdsnamn** och konfigurerar andra önskade inställningar.
1. Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en kontantbetalningsmetod.

![Exempel på betalningsmetoder.](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a>Inställningar för kontantavstämning

1. I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Kontantavstämning**.
1. I åtgärdsfönstret, väljer du **Ny** och skapar sedan alla beteckningar för **Mynt** och **Sedlar** som kan användas.

I bilden nedan visas ett exempel på en kontantavstämning.

![Inställningar för kontantavstämningar.](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Ställ in leveranssätt

Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** i fliken **Inställningar** i åtgärdsfönstret.  

Om du vill ändra eller lägga till ett leveranssätt följer du stegen nedan.

1. I navigeringsfönstret, gå till **Moduler \> Lagerhantering \> Leveranssätt**.
1. I åtgärdsfönstret väljer du **Ny** om du vill skapa ett nytt leveranssätt, eller också väljer du ett befintligt läge.
1. I avsnittet **butikskanaler**, välj **lägg till rad** om du vill lägga till kanalen. Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.

I bilden nedan visas ett exempel på ett leveranssätt.

![Konfigurera leveranssätt.](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Ställ in intäkts-/utgiftskonto

Så här ställer du in intäkts-/utgiftskonto.

1. I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Intäkts-/utgiftskonto**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Under **Namn**, ange ett namn.
1. Under **Söknamn**, ange ett söknamn.
1. Under **kontotyp**, ange kontotypen.
1. Ange text för **meddelanderad 1**, **meddelanderad 2**, **följesedeltext 1** och **följesedeltext 2** efter behov.
1. Under **bokföring**, ange bokföringsinformation.
1. Klicka på **Spara** i åtgärdsfönstret.

I följande bild visas ett exempel på ett intäkts-/utgiftskonto.

![Konfigurera intäkts-/utgiftskonton.](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Ställ in avsnitt

Så här ställer du in avsnitt.

1. I åtgärdsfönstret väljer du fliken **Inställningar** och väljer sedan **Avsnitt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Under **avsnittsnummer**, ange ett avsnittsnummer.
1. Under **beskrivning** ange en beskrivning.
1. Under **avsnittsstorlek**, ange en avsnittsstorlek.
1. Konfigurera ytterligare inställningar för **allmän** och **försäljningsstatistik** efter behov.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-a-fulfillment-group-assignment"></a>Ange tilldelning av uppfyllelsegrupp

Så här ställer du in en tilldelning av uppfyllelsegrupp.

1. I åtgärdsfönstret väljer du fliken **Inställningar** och sedan **Tilldelning av uppfyllelsegrupp**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **uppfyllelsegrupp** väljer du en uppfyllelsegrupp.
1. I listrutan **Beskrivning**, ange en beskrivning.
1. Klicka på **Spara** i åtgärdsfönstret

I bilden nedan visas ett exempel på en inställning av tilldelning av uppfyllelsegrupp.

![Konfigurera tilldelning av uppfyllelsegrupp.](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Ställ in kassaskåp

Så här ställer du in kassaskåp.

1. I åtgärdsfönstret väljer du fliken **Inställningar** och klickar sedan på **Kassaskåp**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange ett namn på kassaskåp.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="ensure-unique-transaction-ids"></a>Säkerställa unika transaktions-ID

Från och med Commerce-versionen 10.0.18 genereras transaktions-ID för kassan (POS) sekventiellt och inkluderar följande delar:

- En fast del, som utgör en sammanslagning av butiks-ID och terminal-ID. 
- En sekventiell del som är en nummerserie. 

Mer specifikt är formatet *{store}-{terminal}-{numbersequence}*. 

Eftersom transaktions-ID:n kan skapas i offline- och onlinelägen har det hänt att instanser med dubbletter av transaktions-ID:n skapas. Att undvika dubbletter av transaktions-ID:er kräver omfattande manuella datakorrigeringar. 

I och med Commerce-version 10.0.19 har transaktions-ID-formatet uppdaterats i syfte att ta bort den sekventiella delen, och använder istället ett 13-siffrigt nummer som genererats genom beräkning av tiden i millisekunder sedan 1970. Genom denna ändring blir det nya transaktions-ID-formatet *{store}-{terminal}-{millisecondsSince1970}*. Genom denna uppdatering blir transaktions-ID:t icke-sekventiellt och säkerställer att transaktions-ID:n alltid blir unika. 

> [!NOTE]
> Transaktions-ID:n är endast avsedda för interna system, varför de måste inte vara löpande. Många länder kräver dock att inleverans-ID:n är sekventiella.

Den nya formatfunktionen för transaktions-ID kan aktiveras från arbetsytan **Funktionshantering**. 

Gör på följande sätt om du vill aktivera användning av nya transaktions-ID:n:

1. I Commerce-administrationen går du till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Filtrera fram modulen "Retail och Commerce".
1. Sök efter funktionsnamnet **Aktivera nytt transaktions-ID i syfte att undvika dubbletter av transaktions-ID:n**.
1. Välj funktionen och sedan **Aktivera nu** i det högra fönstret.  
1. Gå till **Retail and Commerce \> Retail and Commerce-IT \> Distributionsschema**.
1. Kör jobben **1070 Kanalkonfiguration** och **1170 Uppgiftsinspelare för kassa** i syfte att synkronisera den aktiverade funktionen med butikerna.
1. När ändringarna har skickats till butikerna måste kassaterminalerna stängas och öppnas igen för att det nya transaktions-ID-formatet ska kunna användas. 

> [!NOTE]
> När den nya formatfunktionen för transaktions-ID har aktiverats kan du inte inaktivera funktionen. Om denna måste inaktiveras kan du kontakta Commerce Support.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för kanalinställningar](channels-prerequisites.md)

[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
