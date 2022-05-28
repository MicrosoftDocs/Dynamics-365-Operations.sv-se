---
title: Överplockning för försäljningsorder och överföringsorder
description: I avsnittet beskrivs hur du aktiverar överplockning för försäljningsorder och överföringsorder.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 52a4225efa88a7b9303dd611d5652f59da1612a4
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678420"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Överplockning för försäljningsorder och överföringsorder

[!include [banner](../includes/banner.md)]

Avsnittet innehåller ett scenario som visar hur du aktiverar antingen en viss arbetare eller alla arbetare för överplockning. Överplockningsprocessen ger möjlighet till kontrollerad överplockning under plockningsarbetet.

Lagerställes överplockning är ett enkelt koncept. Systemet låter arbetare att plocka fler artiklar än vad som har angetts för en order. Processen beaktar dock den gräns för överleverans som har ställts in på radnivå för överföringsordern eller försäljningsordern. Om denna gräns överskrids informerar appen Warehouse Management arbetarna om att de överskrider gränsen för överleverans.

Funktionen för överplockning minimerar underhåll och hjälper även dina inställningar att vara flexibla. Du kan definiera en eller flera menyalternativ för mobila enheter och aktivera överplockning enbart för vissa av dem. Du kan också förhindra att utvalda arbetare överplockar försäljningsorder och/eller överföringsorder utan att ändra menyalternativ. Du kan i stället stänga av en eller båda av dessa funktioner i relevanta inställningar för arbetare.

Överplockningsfunktionen kan hjälpa arbetarna att spara tid och kraft när de plockar och levererar artiklar. Funktionen gör exempelvis att arbetare kan utföra följande uppgifter:

- Kompensera för minskning under plockning eller leverans.
- Undvika att behöva packa upp förpackningsmaterial under plockningsprocessen.
- Kompensera för artikelskador under transport.
- Leverera avvikande kvantitet eller måttenhet.
- Minimera att bryta upp kvantiteter för ID-nummer.
- Undvika materialslöseri och brist på dyrbara material.
- Mäta plockad kvantitet efter plockning (t.ex. genom lastvikt).

> [!IMPORTANT]
> Funktionen för överplockning gäller endast för plockning och bearbetning av försäljningsorder och överföringsorder. Lagerpåfyllnad har inte stöd för överplockning. När lagerpåfyllnadsarbete körs tillåter systemet inte att användarna plockar för mycket.

Scenariot i avsnittet visar hur du ställer in och använder överplockningsfunktionen.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Scenario: Göra demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på *USMF* innan du börjar.

## <a name="scenario-setup"></a>Scenarioinställningar

Innan du arbetar dig genom exempelscenariot måste du aktivera överplockning för både relevant arbetare och relevant menyalternativ.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Ställa in en arbetare för överplockning

Detta är en allmän procedur för att konfigurera en arbetare för överplockning för försäljningsorder och överföringsorder separat. Denna konfiguration kontrollerar vilken plockningsarbetare som kan göra överplockningen, och om den arbetaren kan göra överplockning för både överföringsorder och försäljningsorder.

1. Gå till **Warehouse management \> Inställningar \> Arbetare**.
1. Välj i listfönstret **Julia Funderburk**.
1. På snabbflikarna **Användare** välj raden som har följande värden. Om det inte finns någon befintlig rad med de här värdena skapar du den.

    - **Användar-ID:** *24*
    - **Användarnamn:** *WH 24*
    - **Standardlagerställe:** *24*
    - **Menynamn:** *huvud*

1. På snabbflikarna **Arbete**, ange följande värde för användare *24* ställts in:

    - **Tillåt överplockning för försäljning:** *Ja*
    - **Tillåt överplockning för överföring:** *Ja*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Ställa in ett menyalternativ för mobila enheter för att tillåta överplockning

Här är den allmänna proceduren för att konfigurera ett menyalternativ för mobil enhet för att aktivera överplockning. Beroende på företagets krav på behörighetsnivå för den arbetare som ska använda menyn för den mobila enheten, kan vissa parametrar slås på eller stängas av.

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Markera posten med namnet *Försäljningsplockning* i listrutan. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta eller ställ in följande värden för posten:

    - **Menyalternativnamn:** *Försäljningsplockning*
    - **Titel:** *Försäljningsplockning*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*
    - **Styrs av:** *Användarstyrd*
    - **Åsidosätt målets ID-nummer:** *Ja*
    - **Åsidosätt ID-nummer vid plockning:** *Ja*
    - **Håll arbetet låst av användare:** *Ja*
    - **Tillåt överplockning:** *Ja*

> [!IMPORTANT]
> När relevanta parametrar för både arbetare och menyalternativ för mobil enhet har aktiverats kan överplockning endast bearbetas via den mobila enheten.

## <a name="example-scenario"></a>Exempelscenario

När förutsättningarna, arbetarinställningarna och inställning av menyalternativ är klara kan du börja arbeta med funktionen.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Skapa en försäljningsorder som tillåter överleverans

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Välj **Ny** för att skapa en ny försäljningsorder.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *24*

1. Välj **OK**.
1. Den nya försäljningsordern öppnas. På snabbfliken **försäljningsorderrader** lägger du till en rad som har följande inställningar:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *10*

1. På snabbfliken **Raddetaljer** på fliken **leverans**, ange fältet **Överleverans** till *10*.
1. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
1. Stäng sidan **Reservation**.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

När släppningen är klar får du informationsmeddelanden som visar påfyllnads- och last-ID som skapades.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Hämta arbets-ID och ID-nummer för den nya ordern

När du släppt försäljningsordern till lagerstället ska systemet ha skapat ett nytt arbets-ID med en plockrad. Följ dessa steg för att hitta arbets-ID och tilldelning av ID-nummer.

1. Gå till **Warehouse management \> Arbete \> Arbetsdetaljer**.
1. I rutnätet **Översikt** söker du i kolumnen **Ordernummer** efter de två försäljningsorder som du precis har skapat. Notera motsvarande arbets-ID för den försäljningsordern.
1. Markera raden för den nya försäljningsordern för att visa relaterad information i rutnätet **Rader**. Notera platsen som respektive artikel ska plockas från.
1. Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.
1. I åtgärdsfönstret, välj **Dimensioner**.
1. Kontrollera i dialogrutan **Dimensionsvisning** att kryssrutorna **ID-nummer**, **Lagerställe** och **Artikelnummer** är markerade och välj sedan **OK**.
1. I rutan **Filter** ange följande filter:

    - **Artikelnummer** – **är ett av** – *A0001*
    - **Lagerställe** – **börjar med** – *24*

1. Välj **Tillämpa**.
1. Anteckna vilket värde **ID-numret** visar.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Överplockning av ordern med mobilappen Warehouse Management

1. Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *24*.
1. Gå till **Utgående \> Försäljningsplockning**.
1. I fältet **Skanna arbets-ID eller ID-nummer** anger du det arbets-ID som har skapats för försäljningsordern.
1. Välj **OK** (kryssmarkeringssymbol).
1. Välj **Överplockning**.
1. Ange fältet **Plockkvant** till *14*.
1. Välj **OK** (kryssmarkeringssymbol).

    På sidan **Överplockning** visas följande meddelande: "Överleverans för raden är 40,00 procent, men den tillåtna överleveransen är bara 10,00 procent". Meddelandet indikerar att den plockkvantitet som du har angett överskrider gränsen för överleverans. Gränsen för överleverans för försäljningsorderraden är 10 procent. För en angiven kvantitet på 10 kan du alltså bara överplocka 1 för total plockkvantitet på 11.

1. Ange fältet **Plockkvant** till *11*.
1. Välj **OK** (kryssmarkeringssymbol).
1. I fältet **ID-nummer** anger du ID-numret som du noterade i föregående avsnitt.
1. I fältet **Målets ID-nummer** anger du ID-nummer för ett mål. Observera att plockplats (*FLOOR-001*), artikel (*A0001*) och kvantitet (*11 stycken*) visas.
1. Välj **OK** (kryssmarkeringssymbol).
1. Granska informationen på sidan **Inköpsorder – placera**. Fältet **Loc** ska visa att de plockade artiklarna ska till platsen *BAYDOOR*.
1. Välj **OK** (kryssmarkeringssymbol).

På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete". Meddelandet indikerar att arbets-ID för försäljningsordern har slutförts och att den överplockade kvantiteten inte överskrider gränsen för överleverans på 10 procent.
