---
title: Produktjämförelsemoduler
description: I den här artikeln beskrivs moduler för produktjämförelse och hur du implementerar dem så att kunder kan göra produktjämförelser på Microsoft Dynamics 365 Commerce e-handelswebbplatser.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 6fd851ce6b32d0772c3fe23c4d7bd4dae2616fdc
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474137"
---
# <a name="product-comparison-modules"></a>Produktjämförelsemoduler

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs moduler för produktjämförelse och hur du implementerar dem så att kunder kan göra produktjämförelser på Microsoft Dynamics 365 Commerce e-handelswebbplatser.

> [!NOTE]
> Modulerna för produktjämförelse och produktjämförelse är tillgängliga från Dynamics 365 Commerce i version 10.0.29. De kan användas för både webbplatser för B2C och BSB.

Med funktionen för produktjämförelse kan du jämföra produktinformation på en sida för produktjämförelse för att hjälpa dem att fatta bättre inköpsbeslut. Den här funktionen konfigureras i Commerce-webbplatsbyggaren med hjälp av modulen för produktjämförelse. På produktlistsidor (PLP), som kategoriresultat, sökresultat och produktsamlingssidor, kan du konfigurera en knapp för produktjämförelse som låter köpare lägga till produkter i en jämförelseplats. Den här funktionen konfigureras i webbplatsbyggaren genom att använda knappmodulen för produktjämförelse, som fungerar som [snabbvymodulen](quick-view-module.md).

När webbplatsanvändare lägger till produkter för jämförelse genom att välja dem på produktpanelerna visas en jämförelsebricka längst ned på sidan. Jämförelsebrickan visar de produkter som jämförelsen för närvarande jämförs med korta förhandsgranskningar av produkterna. Siteanvändare kan också lägga till produkter från produktinformationssidor och de kan lägga till specifika produktvarianter som jämförs med produkt magisterexamen.

När kunderna har lagt till några produkter i jämförelsen kan de välja **Jämför** för att omdirigeras till en produktjämförelsesida. På sidan för produktjämförelse visas produktinformation för varje vald produkt så att kunderna kan jämföra bilder, priser, produktdimensioner (storlek, stil och färg), samlad värderingar och andra produktattribut.

Följande illustration visar exempel på knappen Jämför produkt, ta bort från jämförelseknappen, jämförelsebrickan och produktjämförelsesidan.

![Produktjämförelse översikt visar exempel på knappen Jämför produkt, ta bort från jämförelseknappen, jämförelsepanelen och produktjämförelsesidan.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - På produktjämförelsesidan jämförs en standarduppsättning produktegenskaper och alla attribut som kan visas på en PDP för en viss produkt.
> - Egenskaper som leveransläge, lagerbehållning och måttenhet kan inte visas på en sida för produktjämförelse.
> - Kunder kan lägga till produkter från olika kategorier till jämförelsen, förutsatt att produkterna kommer från samma katalog.
> - Produktjämförelsefunktionen är för närvarande begränsad för att jämföra produkter i en enskild katalog. Webbplatsanvändare kan inte göra jämförelser av kataloger mellan kataloger.
> - Du måste kontrollera att egenskapen på **klientsidan för återgivningsmodulen** är avmarkerad för alla moduler för produktjämförelse.
> - Du bör kontrollera att cachelagring på sidnivå är inaktiverad för alla sidor där produktjämförelsemodulen används. På dessa sidor finns PDP och produktjämförelsesidor. Mer information finns i [Konfigurera sidcachelagring](e-commerce-extensibility/page-caching.md).

Illustrationen nedan visar ett exempel på sidan produktjämförelse.

![Sidan Produktjämförelse.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Lägga till modulen för produktjämförelse på en ny produktjämförelsesida

Du kan skapa en dedikerad produktjämförelsesida genom att lägga till en produktjämförelsemodul till sidans brödtext. Förutom att aktivera kunder för att jämföra produktinformation om olika produkter, kan du konfigurera modulen för produktjämförelse så att kunderna snabbt kan slutföra sina inköp efter att de har jämfört produkter. Produktjämförelsemodulen innehåller en **tom jämförelse** plats där du kan lägga till en innehållsblockmodul som beskriver det tomma tillståndet (till exempel "Din produktjämförelse är tom").

För att lägga till en produktjämförelsemodul på en ny produktjämförelsesida, följ dessa steg.

1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida** under **Sidnamn**, ange ett lämpligt sidnamn och välj sedan (till exempel **Produktjämförelse**) och välj **Nästa**.
1. Under **Välj en mall**, välj lämplig mall (till exempel mallen som används av din standardkategorisida) och välj sedan **Nästa**.
1. Under **Välj en layout** väljer du en sidlayout (till exempel **Flexibel layout**) och väljer sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du måste redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**.
1. På **Huvudplatsen** väljer du ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **produktjämförelse** och sedan **OK**.
1. På platsen **Snabbvyknapp** väljer du ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Snabbvy över produkt** och sedan **OK**.
1. I fönstret för egenskaper till höger, konfigurera modulegenskaperna **Snabbvy över produkt**.
1. I platsen **tom jämförelse** välj ellips (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Innehållsblock** och klicka sedan på **OK**.
1. I fönstret för egenskaper till höger, konfigurera modulegenskaperna **Innehållsblock**. 
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

Följande illustration visar ett exempel på en tom jämförelsesida i webbplatsbyggaren.

![Produktjämförelsemodul.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Lägg till en knapp för produktjämförelse för produkt som du använder på sök- och kategoriresultatsidor

Med knappen för produktjämförelse kan användarna snabbt lägga till en produkt för jämförelsen när de bläddrar i produkter på en listsida. De kan lägga till en eller flera produkter till jämförelsen från en listsida utan att behöva gå till en PDP.

Produktjämförelseknappen stöds av produktsamlingen, sökresultaten och PDP-moduler för inköpsruta.

Lägg till en knapp för produktjämförelse för produkt som du använder på sök- och kategoriresultatsidor med följande steg.

1. I webbplatsbyggaren, gå till **Sidor** och öppna kategorisidan som du vill lägga till en produktjämförelseknapp till.
1. På **Huvudplatsen** väljer du ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Sökresultat** och sedan **OK**.
1. I platsen **knapp för produktjämförelse** för modulen **Sökresultat** välj ellipsen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **produktjämförelseknapp** och sedan **OK**.
1. I fönstret för egenskaper till höger , konfigurera modulegenskaperna **produktjämförelseknapp**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Ange det maximala antalet produkter som ska visas under jämförelsen

Du kan ange högsta antal produkter som ska visas i jämförelsen genom att gå till **Webbplatsinställningar \>Tillägg** i webbplatsskaparen. Du kan konfigurera separata maxgränser för vyer för datorer och mobiler/surfplatta. Som standard används ingen gräns om ingen maxgräns har definierats.

> [!NOTE]
> För en optimal surfupplevelse rekommenderar vi att du ställer in det maximala antalet produkter i jämförelsefacket till **2** för det mobila visningsområdet och **4** för dator visningsområdet för att minska mängden horisontell rullning som krävs.

Ange det maximala antalet produkter som ska visas under jämförelsen med följande steg.

1. I webbplatsskaparen går du till **Webbplatsinställningar \> Tillägg**.
1. För egenskapen **Produkter i jämförelsegränsen – stationära enheter** ange det maximala antalet produkter som ska visas i jämförelsefältet för visningsportar för dator.
1. För egenskapen **Produkter i jämförelsegränsen – mobila och surfplatteenheter** ange det maximala antalet produkter som ska visas i jämförelsefältet för visningsportar för mobil och surfplatta.
1. Klicka på **Spara och publicera** i kommandofältet.

![Webbplatsinställningar som begränsar produkter under jämförelsen.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
