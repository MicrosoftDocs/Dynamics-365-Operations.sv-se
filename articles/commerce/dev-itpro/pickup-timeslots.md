---
title: Skapa och uppdatera tidpunkt för kundupphämtning
description: I det här avsnittet beskrivs hur du skapar, konfigurerar och uppdaterar tidpunkt för kundupphämtning i Commerce-administrationen.
author: anupamar-ms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: e2369b17244525023541cdbd0a0da3f2a2a09b30
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355462"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Skapa och uppdatera tidpunkt för kundupphämtning

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar, konfigurerar och uppdaterar tidpunkt för kundupphämtning i Commerce-administrationen.

Funktionen för tidpunkt ger återförsäljarna ett sätt att definiera en tidpunkt för artiklar som läget för kundupphämtning är aktiverat för. Tidpunkter låter återförsäljare definiera de dagar och tider då order kan hämtas från en butik. Återförsäljare kan även definiera antalet order som kan hämtas under en viss period. På så sätt kan återförsäljare begränsa antalet order som kan hämtas en viss dag och vid en given tidpunkt. Resultatet blir en bättre upplevelse för kunderna.

> [!NOTE]
> Funktionen för tidpunkt tillgänglig i Microsoft Dynamics 365 Commerce version 10.0.15 och senare.

I bilden nedan visas ett exempel på valet av tidpunkt ser ut vid näthandelskassan.

![Exempel på val av tidpunkt vid näthandelskassan.](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Egenskaper för tidpunkt

En tidpunkt är ett specifikt intervall när en kund kan välja att hämta en order från en specifik butik eller plats. Funktionen för tidpunktshantering är endast tillgänglig när leveranssättet för kundupphämtning har konfigurerats i Dynamics 365 Commerce.

En tidpunkt definieras med hjälp av följande egenskaper:

- **Leveranssätt** – Ange det upphämtningsläge som tidpunkten gäller för.
- **Lägsta antal dagar** och **Maximalt antal dagar** – Ange det tidigaste och senaste datum som kan väljas för upphämtning i förhållande till det datum då ordern placeras. 

    Egenskapen för **Lägsta antal dagar** garanterar att det finns tillräckligt med tid för återförsäljaren att bearbeta ordern innan den är klar för upphämtning. Egenskapen **Maximalt antal dagar** garanterar att användaren inte kan välja ett datum som ligger för långt fram i tiden. Om t. ex. minimivärdet är inställt på **1** och en order ställs in den 20 september blir den tidigaste dagen för upphämtningen nästa valbara dag (21 september). På samma sätt kan du, genom att ange ett maxvärde, definiera det maximala antalet dagar som en order kan hämtas upp. När lägsta och högsta värden har definierats kan webbplatsanvändarna bara se och välja en viss uppsättning dagar i POS.

    Du kan ange det lägsta värdet till ett decimalvärde som är mindre än 1. Om upphämtning till exempel är tillgängligt fyra timmar efter det att en order har lagts, ställer du in det lägsta värdet på **0,17** (= 4 ÷ 24, avrundat till två decimaler). Om du däremot anger det lägsta värdet som ett decimalvärde som är större än 1, avrundas det alltid upp till närmaste heltal. Värdet **1,2** avrundas exempelvis till **2**. Om du på liknande sätt anger maxvärdet som ett decimalvärde, avrundas det alltid upp till närmaste heltal. 

- **Startdatum** och **Slutdatum** – Ange start- och slutdatum för tidpunkten. Varje tidpunktspost har ett startdatum och ett slutdatum. Därför har du flexibilitet att lägga till olika tidpunkter under året (t. ex. upphämtningar under semestertid). Om tidsangivelserna för en tidpunkt ändras efter det att en order har lagts tillämpas inte ändringarna på den ordern. När du definierar start- och slutdatum måste du ta hänsyn till stängningsdatum för butiker (t. ex. juldagen) och kontrollera att inga tidpunkter har definierats för dessa dagar.
- **Aktiva timmar för upphämtning** – Ange den period då upphämtning är tillåten. Upphämtningstiderna kan till exempel vara mellan kl. 14 och kl. 17 varje dag. Den här egenskapen gör att upphämtningstiderna kan vara oberoende av butikens öppettider. Därför kan återförsäljaren konfigurera upphämtningstider som uppfyller specifika affärskrav. När du definierar aktiva tider för upphämtning måste du ta hänsyn till öppettider och kontrollera att upphämtningstiderna inte är definierade för tillfällen när butiken är stängd.

    > [!NOTE]
    > Antalet timmar för butiksupphämtningen måste definieras i tidszonen för den aktuella butiken.

- **Tidpunktsintervall** – Ange den varaktighet som kan tilldelas respektive tidpunkt. Varaktigheten för respektive tidpunkt kan t. ex. vara i steg om 15 minuter, 30 minuter eller en timme. Om värdet för en tidpunkt är 0 är tidpunkten tillgänglig under hela tiden mellan start- och sluttid.
- **Tidpunkter per intervall** – Ange antalet kunder eller order som kan hanteras för upphämtning under respektive tidpunktsintervall. Ange till exempel **1**, **2**, **3** eller något annat heltal.
- **Aktiva dagar** – Ange de veckodagar som ska vara aktiva när upphämtningstiden är aktiv. Med den här egenskapen kan återförsäljaren definiera de dagar då man vill ha stöd för upphämtningsorder.
- **Butikskanaler** – Ange butikskanalerna. Varje tidpunkt kan associeras med en eller flera butiker. Beroende på respektive butiks öppettider kan en eller flera tidpunkt skapas och associeras med en kanal. 

<!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Endast en tidpunkt kan konfigureras per kanal. Dessa kanaler är bland annat fysiska butiker, kundtjänster, mobila enheter och näthandelssajter.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Konfigurera funktionen för tidpunkt i Commerce-administrationen

Tidpunkter måste anges för respektive upphämtningsläge i Commerce-administrationen så att kassa- (POS) och näthandelskanaler kan referera till dem.

- Endast en tidpunktsmall kan associeras med respektive butik eller kanal.
- Varje tidpunkt som skapas ska vara unikt för respektive leveranssätt i respektive mall.
- När du har konfigurerat funktionen för tidpunkt blir tidpunktskalendern tillgänglig för de valda butikerna eller butiksgrupperna. Den kommer också att vara synlig i POS, som referens.

Följ dessa steg för att konfigurera funktionen för tidpunkt i Commerce-administrationen.

1. Gå till **Commerce** \> **Kanalkonfiguration** \> **Tidpunkter för butiksupphämtning**.
1. Välj **Nytt** för att skapa en ny mall för tidpunkt. Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret.
1. Ange värden i fälten **ID för tidpunkt** och **Beskrivning**.
1. På snabbflicken **Orderupphämtning – Tidsinställningar** väljer du **Lägg till**.
1. I dialogrutan **Orderupphämtning – Tidsinställningar** anger du datumintervall, leveranssätt, aktiva leveranstimmar, aktiva dagar, tidpunktsintervall, tidpunkt per intervall och andra inställningar.

    Ange fältet **Slutdatum** som **Aldrig** om du vill att tidpunkterna ska vara statiska under överskådlig framtid.

    > [!NOTE]
    > Du kan skapa flera mallar, men endast en mall kan associeras med en enda kanal eller butik.

    ![Orderupphämtning – Dialogruta för tidsinställningar.](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Välj **OK** när du är klar.
1. Om tidpunkterna varierar under en dag skapar du ytterligare poster på snabbfliken **Orderupphämtning – Tidsinställningar** för att se till att datum och tider inte överlappar varandra.
1. På snabbfliken **Butikskanaler** väljer du **Lägg till** för att associera mallen för tidpunkt med de butiker eller kanaler där den ska användas.
1. I dialogrutan **Välj organisationsnoder** använder du pilknapparna för att välja (eller rensa urvalet av) de butiker, regioner och organisationer som mallen ska associeras med.

    <!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Välj **OK** när du är klar.
1. På sidan **Distributionsschema** kör du jobben **1070** och **1135** för att synkronisera data till kanalerna.

## <a name="time-slot-selection-for-pos-orders"></a>Urval av tidpunkt för kassaorder

När en order eller orderrad identifieras för upphämtning i POS kan kassören välja butik eller plats för upphämtning, samt datum och tidpunkt. Om en kund har en upphämtningsorder för en annan butik, kan kassören välja datum när upphämtningen blir tillgänglig i den butiken. Butikssökningen ger en referens till datumen och öppettiderna.

I bilden nedan visas ett exempel på val av tidpunkt för en kassaorder.

![Ett exempel på tidpunktsval för en kassaorder.](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Tidpunktsval för näthandelsorder

Mer information om hur du gör tidpunktsvalet tillgängligt för näthandelsorder finns i [Informationsmodul för upphämtning](../pickup-info-module.md).

> [!NOTE]
> Användarna kan bara visa och redigera tidpunkt för upphämtning på kassasidan för en Commerce-webbplats om modulen för upphämtningsinformation har lagts till på sidan. Om det inte finns någon modul för upphämtningsinformation på kassasidan placeras order utan att användarna kan ange eller visa information om tidpunkt.

Följande illustration visar ett exempel på en näthandelsorder där en tidpunkt har valts.

![Exempel på en näthandelsorder där en tidpunkt för upphämtning har valts.](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Tidpunktsval för kundtjänstorder

I kundtjänstprogrammet kan kundtjänstmedarbetare välja upphämtningsbutik eller -plats, samt datum och tidpunkt, enligt illustrationen nedan.

![Exempel på en kundtjänstorder där en tidpunkt för upphämtning har valts.](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Modul för upphämtningsinformation](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]