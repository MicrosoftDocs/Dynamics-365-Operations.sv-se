---
title: Förpackningsarbete för att packa utgående behållare och bearbeta försändelser
description: Den här artikeln beskriver arbetsordertypen "Förpackning" som hanterar arbete för förpackningsbehållare och stöder delvisa försändelser av packade behållare som är relaterade till lastning där lagerartiklar förblir packade.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220596"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Förpackningsarbete för att packa utgående behållare och bearbeta försändelser

[!include [banner](../../includes/banner.md)]

Den här artikeln beskriver arbetsordertypen *Förpackning* som hanterar arbete för förpackningsbehållare och stöder delvisa försändelser av packade behållare som är relaterade till lastning där lagerartiklar förblir packade. Med förpackningsarbete kan du använda funktionen [Bekräfta och överför](confirm-and-transfer.md) för att bekräfta utgående försändelser som är associerade med behållare.

Förpackningsarbete skapas automatiskt när lager som är relaterat till källdokumentarbete sätts till platser av typen *Förpackningsplats*. Arbetet består av två rader, en för *Plocka* och en för *Placera* och underhålls automatiskt som en del av en process för att stänga/öppna en behållare igen.

Mer information om hur du ställer in och använder förpackningsprocessen för behållare finns i [Packa behållare för leverans](packing-containers.md).

## <a name="turn-on-the-feature"></a>Aktivera en funktion

Om systemet inte redan har de funktioner som beskrivs i denna artikel går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar följande funktioner i följande ordning. Båda funktionerna ingår i modulen **Lagerstyrning**.

1. *Bekräfta och överföra*
1. *Förpackningsstationer för packningsarbete*

## <a name="set-up-a-location-for-packing-work"></a>Sätt upp en plats för packningsarbete

Använd följande procedur för att konfigurera packningsplatser. För varje plats kan du välja om förpackningsarbete ska skapas automatiskt i systemet.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Inställning av förpackningsstation**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en post för inställning av förpackningsstation.
1. I den nya posten anger du följande fält:

    - **Distributionslager** – Välj eller ange det distributionslager där förpackningsplatsen finns.
    - **Plats** – Välj eller ange packningsplatsen. Denna plats måste tilldelas en platsprofil som använder den platstyp som är konfigurerad som förpackningsplatstyp för ditt företag på sidan **Parametrar för lagerstyrning**. Mer information finns i [Packa behållare för leverans](packing-containers.md).
    - **Skapa förpackningsarbete** – Markera den här kryssrutan om du vill skapa förpackningsarbete varje gång artiklar levereras till förpackningsplatsen. Arbetet kommer att innehålla länkar till relaterade beläggningsrader, så att delbelastning kan packas och skeppas.

## <a name="example-scenario"></a>Exempelscenario

I det här exempelscenariot visas hur du bearbetar ett utgående försäljningsorderflöde genom att packa en behållare och leverera en delbelastning.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda dessa scenarier som vägledning för funktionen när du använder ett produktionssystem. I så fall måste du dock ersätta dina egna värden för varje inställning som beskrivs här.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Konfigurera förpackningsarbete för förpackningsplats för lagerställe

Du måste konfigurera arbetsprocessen för *Packa* en viss lagerställe och plats för att kunna komma igång.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Inställning av förpackningsstation**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till en inställningspost.
1. I den nya posten anger du följande värden:

    - **Lagerställe:** *62*
    - **Plats:** *Packa*
    - **Skapa packningsarbete:** *Ja*

1. Stäng sidan **Inställning av förpackningsstation**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Skapa en lastmall som tillåter delleverans

Om du vill aktivera en belastning som ska levereras över flera försändelser måste du koppla den till en beläggningsmall som tillåter delförsändelser. Följ dessa steg om du vill skapa önskad mall.

1. Gå till **Lagerstyrning \> Inställningar \> Last \> Lastmallar**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till en inställningspost.
1. I den nya posten anger du följande värden:

    - **Lastmall-ID:** *Delvis*
    - **Tillåt lastdelning vid bekräftelse av transport:** *Ja*

1. Stäng sidan **Lastmallar**.

Mer information finns i [Bekräfta och överför](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Bearbeta en försäljningsorder

Följ dessa steg när du vill bearbeta en försäljningsorder och delvis leverera den.

1. Slutför [exempelscenariot](packing-containers.md#scenario) som anges i [Förpackningsbehållare för leverans](packing-containers.md). I det scenariot skapar du en försäljningsorder för två delar av en artikel. Därefter packas bara en av delarna i en behållare och stängs behållaren. Du bör göra en notering av det försändelse-ID som du skapar, enligt instruktionerna i scenariot.
1. Gå till **Lagerstyrning \> Arbete\> Allt arbete**.
1. Markera kryssrutan **Visa stängt arbete** i filterområdet. Ange sedan leverans-ID i fältet **Filter** och välj om du vill filtrera efter värde för **Leverans-ID**. Nu ska du se tre arbetsrubriker. Ett är för plockningsarbetet för försäljningsordern och har statusen *Stängd*. Två gäller för förpackningsprocessen: en är relaterad till den stängda behållaren och har statusen *Stängd* och den andra är relaterad till den oförpackade kvarvarande artikeln och har statusen *Öppen*.
1. Välj värdet för **Last-ID** för någon av arbetsrubrikerna om du vill öppna sidan **Lastinformation** för lasten.
1. Växla till vyn **Rubrik**.
1. På snabbfliken **Allmänt**, välj knappen **Redigera** för fältet **Lastmall-ID**. Välj sedan mallen för delfraktlast som du skapade för detta scenario (*delvis*).
1. I Åtgärdsfönster, på fliken **Leverera och ta emot** i gruppen **Bekräfta**, välj **Utgående leverans**.
1. I dialogrutan **Bekräfta transport**, välj alternativet **Dela kvantitet till ny last**.
1. Välj **OK**.

Du har nu skeppat en behållare som är relaterad till den ursprungliga lasten och systemet har skapat en ny last för de återstående artiklar som fortfarande måste packas i behållare.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
