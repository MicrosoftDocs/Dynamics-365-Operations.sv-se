---
title: Lagermedveten produktlistor
description: I den här artikeln beskrivs hur organisationer kan konfigurera sidor med produktlistor på deras Microsoft Dynamics 365 Commerce e-handelswebbplats så att de känner till lagret.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: 2a65dedf2da62fcd92169077d75a0f3b7832a86d
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473751"
---
# <a name="inventory-aware-product-listing"></a>Lagermedveten produktlistor

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur organisationer kan konfigurera sidor med produktlistor på deras Microsoft Dynamics 365 Commerce e-handelswebbplats så att de känner till lagret. Produktlistesidor omfattar landningssidor för kategorier och sökresultatsidor.

Köpare förväntar sig i allmänhet att produktupptäckten på en e-handelswebbplats är lagermedveten, så att de kan bestämma vad de ska göra om en produkt är slut i lager. Kategorin [Commerce modulbibliotek](starter-kit-overview.md) och sökresultatmoduler kan konfigureras för att inkludera lagerdata. På så sätt kan de ge följande upplevelser:

- Visa lagernivåetiketter som använder produkter.
- Dölj produkter som inte finns i lager från produktlistan.
- Flytta produkter som inte finns i lager till botten av produktlistans sidor.
- Stödja lagerbaserad produktfiltrering.

Om du vill aktivera dessa erfarenheter måste du först aktivera funktionen **Utökad identifiering av näthandelsprodukt att bli lagermedveten** i Commerce headquarters.

> [!NOTE]
> I Commerce version 10.0.29 och senare funktionen **utökad identifiering av näthandelsprodukt att bli lagermedveten** aktiveras som standard.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Ställa in produktattribut för lagertillgänglighet

Lagernotering av produkt använder ramverket för produktattribut. En förutsättning är att ett dedicerat produktattribut skapas för att kunna samla in data för lagertillgänglighet.

För att ställa in produktattribut för lagertillgänglighet i Commerce headquarters.

1. Gå till **Butik och handel \> Butik och handel IT \> Produkter och lager \> Fyll i produktattribut med lagernivå**.
1. I dialogrutan **Fyll i produktattribut med lagernivå** i fältet **Produktattribut och typnamn** anger du ett anpassat namn för det dedikerade produktattributet som kommer att skapas för att fånga in lagerdata.
1. I fältet **Lagertillgänglighet grundad på** den kvantitetstyp som lagernivåberäkningen ska baseras på t.ex.: **Fysiskt disponibelt** eller **Totalt disponibelt**.
1. Ange alternativet **Batchbearbetning** till **Ja**.
1. Välj **OK**.

> [!NOTE]
> För konsekvent beräkning av lagernivå över sidorna på din e-handelswebbplats, se till att du väljer samma kvantitetstyp i både fältet **Lagertillgänglighet grundad på** för jobbet **Fyll i produktattribut med lagernivå** och inställningen **Lagernivå grundad på** i Commerce webbplatsskaparen.

När det dedikerade produktattributet har skapats är nästa steg att konfigurera attributet för online-kanalen.

Följ dessa steg för att konfigurera attributet för onlinekanalen i Commerce headquarters.

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj onlinekanalen för att aktivera den lagermedvetna produktlistningsupplevelsen för.
1. Markera och öppna en associerad attributgrupp, lägg till det nya produktattributet.
1. Gå till **Butik och handel \> Butik och handel IT \> Distributionsschema** och kör jobbet **1150** (**Katalog**). Vi rekommenderar att du schemalägger det här jobbet som en batchprocess som körs med samma frekvens som jobbet **Fyll i produktattribut med lagernivå**.

> [!NOTE]
> I Commerce version 10.0.26 och tidigare efter att du har lagt till produktattributet lagertillgänglighet i en attributgrupp måste du också välja **Ange attributmetadata** och aktivera sedan alternativen **Visa attribut på kanal**, **Hämtningsbart**, **Kan förfinas** och **Kan frågas** för det nya produktattributet.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Konfigurera visningssättet för produkter som inte finns i lager på produktlistesidor

När alla föregående konfigurationssteg har slutförts har anvisningarna på kategori- och sökresultatsidorna ett lagerbaserat filteralternativ. En lagernivåetikett visas för varje produktpanel som visas på sidan.

Kategori- och sökresultatsidan visar produkter på huvudnivå, inte produktvariantnivå. Den lagernivå som visas för varje produkt är en aggregerad lagernivå som bestäms av lagernivån för alla varianter av en produkt. Lagernivån för en variant beräknas utifrån lagerbehållningen för den varianten i standardlagerstället på onlinekanal i Commerce headquarters. Lagernivån för en huvudprodukt har två möjliga värden som representerar stater i lager och utanför lagret. En huvudprodukt anses endast vara i lager när alla varianter av den inte finns i lager. Annars anses produkten vara i lager. Etiketten för värdet hämtas från definitionen [lagernivå](inventory-buffers-levels.md). Om ingen lagernivå är definierad är standardetiketterna (på engelska) **Tillgängliga** och **Slut på lagret**.

Du kan konfigurera **lagerinställningarna för produktlistesidor** i Commerce webbplatsskaparen för att styra hur kategorin och sökresultatsidan visar produkter som inte finns i lager. Mer information om [Använd lagerinställningar](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
