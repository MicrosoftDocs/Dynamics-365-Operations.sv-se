---
title: Kuponger
description: Denna artikel innehåller en översikt över kupongrelaterade funktioner i Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 2594848948b141015adfaa4ec27e2c2b4cc4dcd2
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410780"
---
# <a name="coupons"></a>Kuponger

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Denna artikel innehåller en översikt över kupongrelaterade funktioner i Microsoft Dynamics 365 Commerce.

Kuponger är koder och streckkoder som används för att lägga till rabatter till transaktioner. Detaljhandlare distribuerar kuponger till potentiella eller befintliga kunder för att förbättra deras märkesigenkänning, köra konvertering, behålla kundbasen, sälja försäljning och slutligen öka intäkterna. Kuponger har blivit ett av de mest använda marknadsföringsverktygen och är en ny norm i e-handelsförsäljningen.

I Dynamics 365 Commerce är kuponger kopplade till rabatter och betraktas som ytterligare validering ovanpå rabatter. Varje kupong är relaterad till en rabatt och den kopplade rabatten definierar vilken uppsättning produkter som kupongen gäller för.

Prisgrupper som är kopplade till en rabatt definierar de berättigade villkoren för att en kupong ska kunna användas. Dessa villkor omfattar kundgrupper och försäljningskanaler. Kuponger ger också **Användargräns** och **Krävs av kund** egenskaper som kan användas för att konfigurera valfria användarbegränsningar.

Varje kupong kan ha flera kupongkoder och kupongstreckkoder, och varje kod kan ha sitt eget giltiga datumintervall och status. Om status för en kod är **Inaktiv** kan koden inte användas i någon kanal.

## <a name="set-up-a-coupon"></a>Ställ in en kupong

Innan du kan skapa en kupong måste du konfigurera kupongens streckkod och två kupongnummerserier.

Så här ställer du in en kupong i Commerce headquarters.

1. Gå till **Butik och handel \> Lagerhantering \> Streckkoder och etiketter \> Masktecken**.
1. Välj **Lägg till** för att skapa ett masktecken av typen **Kupongkod**. I fältet **Tecken** kan du välja oanvända tecken.
1. Gå till **Butik och handel \> Lagerhantering \> Streckkoder och etiketter \> Inställning av streckkodsmask**.
1. Välj **Ny** för att skapa en streckkodsmask av typen **Kupong**.
1. Gå till **Butik och handel \> Lagerhantering \> Streckkoder och etiketter \> Inställning av streckkod**.
1. Välj **Ny** för att skapa en streckkod som använder streckkodsmasken som du skapade.
1. Gå till **Organisationsadministration \> Nummerserier**.
1. Skapa två nummerserier:

    1. En sekvens för referensen **Kupongnummer**. I den här serien definieras den unika identifieraren av kupongen.
    1. En sekvens för referensen **Kupongkod-ID**. Denna sekvens definierar är den unika identifieraren för varje kupongkod för en kupong.

    För de båda nummerserierna måste du konfigurera fältet **Omfattning** på **Företag**. I de flesta fall ska du skapa båda nummerserienumren automatiskt.

1. Gå till **Handelsparametrar \> Priser och rabatter \> Kuponger**.
1. Ställ in fältet **Streckkodsmask för kupong** till den streckkod som du skapade tidigare.
1. Gå till **Handelsparametrar \> Nummerserier**.
1. Välj de nummerserier som du skapade tidigare för referenser till **kupongnummer** och **kupongkod-ID**.

Om du vill ställa in en kupong måste du skapa rabatten och kupongen separat, och sedan koppla dem genom att välja rabatten i fältet **Rabatt** i kupongkonfigurationen. Efter att en kupong är kopplad till en rabatt, fälten **Status**, **Giltighetsdatum** och **Utgångsdatum** i den länkade rabatten blir skrivskyddade, eftersom värdena bestäms av kupongens status och giltighetstid. När status för en kupong är **Aktiv** uppdateras statusen för den kopplade rabatten automatiskt till **Aktiverad**. Likaså när en kupongs status är inställd på **Inaktiv**, status för den länkade rabattstatusen uppdateras automatiskt till **Inaktiverad**.

## <a name="use-a-coupon"></a>Använd en kupong

För att lägga till en kupong till en försäljningstransaktion i kassan (POS) kan du använda en kupongkod eller en kupongstreckkod. Om du vill använda en kupongkod väljer du operationen **Lägg till kupongkod** och anger koden. För att använda en kupongstreckkod kan du antingen skanna streckkoden med hjälp av en skannerenhet eller ange den genom att använda den numeriska knappsatsen på skärmen **Transaktion**.

Detaljhandlare vill ibland att kassörerna ska kunna ge kunder fastbeloppsrabatter på grund av exempelvis produktfel, men de vill inte skriva ut kupongkoder och distribuera dem till kassörerna. I detta fall kan du ställa in alternativet **Använd utan kupongkod** för kupongen till **Ja**. Kassörerna kan sedan använda funktionen **Använd kupong** inne i åtgärden **Visa tillgängliga rabatter** för att lägga till en kupong till en transaktion utan att manuellt ange koden. Om det finns flera kupongkoder för en kupong väljer systemet automatiskt den första aktiva koden och tillämpar den för transaktionen.

Om du vill lägga till en kupong till en kundtjänstförsäljningsorder måste en kundtjänstanvändare välja **Kuponger** på fliken **Hantera** i åtgärdsfönstret på försäljningsordersidan.

Om du vill lägga till en kupong till en e-handelsorder kan han eller hon ange rabattkoden i fältet för **kampanjkod** i shoppingvagnen.

När en kupong har lagts till en försäljningsorder, utlöser prissättningsmotorn omedelbart omberäkningen av hela ordern, oavsett om en försenad beräkning är aktiverad eller inte.

> [!NOTE]
> I Commerce version 10.0.30 och tidigare, efter att kundtjänstanvändare har lagt till en kupong på en kundtjänstförsäljningsorder måste de välja **Omberäkna** i gruppen **Beräkna** på fliken **Sälja** i åtgärdsfönstret för att tillämpa rabatten som är kopplad till den kupongen.

## <a name="coupon-usage-limit"></a>Gräns för kupongförbrukning

Du kan konfigurera kuponger för begränsad användning. Användningsgränsen kan definieras per kund, per kanal, eller som en globalt. Användningsgränsen tillämpas per kupongkod på en kupong. Exempelvis kan en kupong med två kupongkoder användas två gånger: en gång för varje kupongkod.

Kuponger kan användas i alla försäljningskanaler. För kundtjänst kan dock kuponger som är begränsade användas endast när inställningen **Aktivera slutförande av order** för kundtjänstkanal har aktiverats. Om inställningen **Aktivera slutförande av order** är inaktiverad kan endast ej begränsade användningskoder användas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
