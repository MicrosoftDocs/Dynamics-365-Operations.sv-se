---
title: Aktivera flera leveranssätt genom upphämtning för kundorder
description: I denna artikel beskrivs funktionerna i Microsoft Dynamics 365 Commerce som gör att du kan skapa kundorder för upphämtning i en butik.
author: hhainesms
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e4d8883b3dc1c4a0e12bcb00b6441f76d73da92e
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831595"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Aktivera flera leveranssätt genom upphämtning för kundorder

[!include [banner](includes/banner.md)]


I Microsoft Dynamics 365 Commerce kan organisationer definiera flera leveranssätt som konsumenter eller säljmedarbetare kan välja mellan när de skapar en order som ska hämtas i en butik. På så sätt kan organisationer erbjuda sina konsumenter flera upphämtningsalternativ. Numera låter många återförsäljare exempelvis sina konsumenter välja mellan upphämtning i butik eller drive in-upphämtning för sina order. Commerce stöder konfiguration av dessa olika leveranssätt genom upphämtning. Användarna kan sedan dra nytta av dem när de skapar kundorder i valfr Commerce-kanal som stöds (näthandel, kundtjänst eller butik).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Aktivera och konfigurera leveranssätt

Funktionen **Stöd för flera upphämtnings-leveranssätt** i arbetsytan **Funktionshantering** i Commerce headquarters är obligatorisk och bör aktiveras i miljön.

Om du tidigare definierat ett leveranssätt för upphämtning på sidan **Handelsparametrar** visas det läget i den aktuella konfigurationen för leveranssätt för upphämtning.

![Leveranssätt för hämtning på parametersidan för Commerce.](media/multiplepickupparameter.png)

Du kan definiera flera leveranssätt för upphämtning i rutnätet **Leveranssätt: upphämtning** på fliken **Handelsparametrar** > **Kundorders** > snabbfliken **Leveranssätt**.  

Fälten **Leveranssätt: utlämning** och **Leveranssätt: elektroniskt**, samt alternativet **Visa endast speditörslägesalternativ för leveransorder** har flyttats till denna snabbflik.

Innan du konfigurerar ytterligare lägen för upphämtning måste du definiera leveranssätten. På sidan **Leveranssätt** i Commerce headquarters lägger du till de leveranssätt som ska betraktas som leveranssätt genom upphämtning. Kontrollera att all konfiguration är slutförd. Om du till exempel erbjuder "curbside pickup" som ett leveransalternativ för dina online-shoppare för vissa butiker måste du skapa ett nytt leveransläge för detta ändamål. Du kan skapa detta leveransläget med "curbside pickup" som beskrivning. Du vill sedan se till att leveranssättet "curbside pickup" mappas till alla Commerce-kanaler som kan erbjuda detta, inklusive onlinebutiker som kan erbjuda detta alternativ och de enskilda butikskanaler som kommer att erbjuda denna distributionsmetod. Leveranssätt måste också vara kopplade till produkterna. Om det finns vissa produkter som inte kan levereras "curbside pickup" måste du i detta exempel se till att dessa artiklar exkluderas. När du är färdig med att lägga till nya leveranssätt kör du jobbet **Bearbeta leveranssätt** för att skapa relationer mellan leveranssätt, kanaler och artiklar. När jobbet är slutfört öppnar du sidan **Distributionsschema** i Commerce headquarters och kör distributionsjobbet **1120** för att säkerställa att relevanta kanaldatabaser för Commerce uppdateras med din nya leveranssättskonfiguration.

![Exempel på ett läge med leveranskonfiguration för drive in-upphämtning.](media/pickupmodes.png)

När du har definierat de ytterligare leveranssätten för upphämtning lägger du till dem i rutnätet **Upphämtningsleverans** på sidan **Commerce-parametrar**. Kör sedan lämpliga distributionsjobb för att uppdatera de relevanta kanaldatabaserna för Commerce med konfigurationsändringen.

> [!NOTE]
> Förutom det befintliga leveranssättet för upphämtning som kopieras till rutnätet **Leveranssätt: upphämtning** när du aktiverar funktionen **Stöd för flera leveranssätt genom upphämtning** bör du konfigurera nya leveranssätt för varje ytterligare leveranssätt genom upphämtning som du skapar. När du lägger till leveranssätt i rutnätet **Leveranssätt: upphämtning** validerar Commerce huruvida någon aktiv och öppen försäljningsrad redan använder dem. Om någon öppen försäljningsrad hittas visas ett felmeddelande. Leveranssätt betraktas inte som leveranssätt genom upphämtning förrän alla öppna försäljningsrader där de används har stängts (antingen fakturerats eller annullerats).


### <a name="e-commerce-site-configurations"></a>Konfigurationer för näthandelssajt

När funktionen **Stöd för flera leveranssätt genom upphämtning** har aktiverats visar följande moduler på näthandelssidor de nya leveranssätta för upphämtning enligt konfigurationen:

- Inköpsruta
- Butiksväljare
- Kundvagn
- Upphämtningsinformation
- Orderbekräftelse
- Orderdetaljer

Inga ytterligare steg krävs på näthandelssidorna för att göra leveranssätten genom upphämtning tillgängliga.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Arbeta med flera leveranssätt genom upphämtning

När flera leveranssätt genom upphämtning är tillgängliga för en kanal ges kunderna en förbättrad upplevelse när de köper produkter som ska hämtas. 

- I näthandelskanaler kan konsumenterna välja valfritt leveranssätt som är tillgängligt för upphämtning. En återförsäljare definierar t. ex. två leveranssätt genom upphämtning (i butik och via drive-in), båda konfigureras i rutnätet **Leveranssätt: upphämtning** och båda gäller för den kanal för orderuppfyllelse kanalen och den produkt som en konsument för närvarande köper. I det här fallet kan konsumenten välja önskat leveranssätt genom upphämtning. Det valda leveranssättet för upphämtning blir då det leveranssätt som är kopplat till försäljningsorderraden när ordern skapas i Commerce headquarters.

    ![Välja ett upphämtningsalternativ inom näthandel.](media/pickupecommerce.png)

- Om en kundorder för upphämtning skapas via kassaprogrammet (POS) i butikskanaler, uppmanas säljaren att välja bland de tillgängliga leveranssätten för upphämtning (om sådana har konfigurerats). Om bara ett giltigt leveranssätt genom upphämtning är tillgängligt för kanalen och artikeln, uppmanas inte säljaren att markera det. I stället tillämpas det tillgängliga leveranssättet för upphämtning automatiskt på orderraderna.

    ![Välja ett upphämtningsalternativ kassaprogrammet.](media/pickuppos.png)

- När användarna skapar upphämtningsorder i kundtjänstkanaler kan de manuellt välja ett definierat leveranssätt genom upphämtning som är länkat till kundtjänstkanalen. Systemet kontrollerar sedan att det valda leveranssättet för upphämtning kan användas när artikeln som länkas till den beställs. När ett leveranssätt genom upphämtning väljs i kundcenterkanaler måste försäljningsorderraderna länkas till ett giltigt butikslagerställe. Om ett lager utanför butiken har definierats på en försäljningsrad för kundtjänst kan ett leveranssätt genom upphämtning inte anges på den försäljningsraden.
- Säljare kan använda åtgärden **Orderåterkallning** eller **Orderuppfyllelse** i kassaprogrammet för att hämta en lista med order eller orderrader för upphämtning. Om en säljare använder ett fördefinierat sökfilter för att visa alla order som kommer att hämtas i den aktuella butiken ändras frågorna för att se till att sökresultaten innehåller alla berättigade order som använder något slags leveranssätt genom upphämtning. Kassaanvändare kan också använda befintliga filter för att begränsa listan med order till ett visst leveransläge för upphämtning. De kan till exempel visa enbart order för drive in-upphämtning.

    ![Filter för leveranssätt genom upphämtning tillämpat på en lista över återkallningsorder.](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Beaktanden för fördelad orderhantering

Funktionerna för [fördelad orderhantering (DOM)](./dom.md) i Commerce ignorerar alla försäljningsrader som har markerats för hämtning i butik. Dessa funktioner har uppdaterats i syfte att se till att försäljningsrader som är länkade till konfigurerade leveranssätt för upphämtning åsidosätter DOM-logiken och inte allokeras om till ett nytt lagerställe för uppfyllande.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
