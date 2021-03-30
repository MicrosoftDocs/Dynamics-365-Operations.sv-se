---
title: Konfigurera leveranssätt och avgifter för kundtjänst
description: Det här avsnittet beskriver hur du ställer in leveranssätten och avgifter för en kundtjänstorder i Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: af9ff5e613679593f59dab605ed35e0bc43dd09a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220616"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Konfigurera leveranssätt och avgifter för kundtjänst

[!INCLUDE [banner](includes/banner.md)]

När en försäljningsorder placeras i Dynamics 365 Commerce, om den person som registrerade försäljningsordern är länkad till en kundtjänstkanal används logik och regler för att validera leveranssätt och beräkna avgifter för ordern.

Du kan välja ett leveranssätt för försäljningsorderrubriken och försäljningsorderrader när du skapar en försäljningsorder. Som standard används det leveranssätt som du valde på rubriken för alla försäljningsorderrader. Du kan åsidosätta standardläge för leverans på individuella försäljningsrader enligt behov. Du kan också definiera ett leveranssätt för en kundpost. Sedan när beställningar skapas för kunden, används det leveranssätt som standard på försäljningsorderrubriken.

Commerce har funktioner som låter användarna begränsa leveranssätt som kan användas av en kanal, leveransmetoder som kan användas för en produkt och leveransmetoder som gäller för specifika leveransmål. Tillägg kan också definieras så att extra kostnad läggs till en kundorder, utifrån de leveranssätt som har valts för försäljningsordern och det totala värdet.

## <a name="define-delivery-modes"></a>Definiera leveranssätt

Du måste definiera leveransmetoder innan du anger vilken leveransadress kan användas för kundtjänst och definiera associerade tillägg och regler. Gå till **Försäljning och marknadsföring \> Inställningar \> Distribution \> Leveranssätt**. Välj **Nytt** om du vill skapa ett nytt leveranssätt. Alternativt väljer du ett befintligt leveranssätt i listan och väljer sedan **redigera** för att göra ändringar.

I fältet **leveranssätt** kan du ange en kombination av alfanumeriska tecken baserat på dina affärsbehov. Du kan använda fältet **beskrivning** och ge ytterligare kontext. Fälten **Avgiftsgrupp** och **Expediera** är valfria och förklaras i detalj längre fram i det här avsnittet.

På snabbfliken **Handelskanaler** lägg till en kanal som får användas för att skapa leveranssätt när försäljningstransaktioner skapas i den kanalen.

På snabbfliken **produkter** kan du ange vilka produkter och/eller produktkategorier som leveranssättet kan och inte kan användas för. Till exempel om en produkt inte kan levereras med flyg på grund av begränsningar för farligt material (hazmat), se till att kontroll av produkt eller produktkategori utesluts från alla de leveranssätt som rör flygtransport.

På snabbfliken **Adresser** kan du ange vilka länder eller regioner eller stater som leveranssättet kan och inte kan användas för. Till exempel order som levereras till Hawaii eller Alaska är inte berättigade till markleverans. Dessa lägen bör därför undantas från varje leveranssätt som associeras med en markleveranstjänst men ingå i varje leveranssätt som är kopplat till en lufttrafikleverans.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Validera leveranssätt för en kundtjänst

När leveranssätt definieras måste du köra batchjobbet **bearbeta leveranssätt**. Det här jobbet gör leveransmetoder tillgänglig så att de kan användas i försäljningsorderprocesser för kanaler. För att köra jobbet **bearbeta leveranssätt**, gå till **Butik och handel \> Butik och handel-IT \> Bearbeta leveranssätt**. Det här jobbet bör köras när nya leveranssätt läggs till en kanal eller befintliga relationer för leveranssätt/kanal ändras.

När du har kört batchjobbet **bearbeta leveranssätt** kan du gå till **Butik och handel \> Kanaler \> Kundtjänst \> Alla kundtjänster**. På sidan **alla kundtjänster** i åtgärdsfönstret, på fliken **Ställ in**, välj **leveranssätt**. Sidan **leveranssätt** visar alla giltiga leveransmetoder för valda kundtjänster. För att redigera befintliga leveranssätt eller lägga till nya leveranssätt **hantera leveranssätt**. Observera att jobbet **bearbeta leveranssätt** måste köras när ändringar har gjorts.

## <a name="define-charges-for-delivery-services"></a>Definiera avgifter för leveranstjänsterna

När försäljningsorder skapas för kunder kanske ett företag vill lägga till avgifter som beräknas automatiskt baserat på de leveranssätt som valts för ordern. Dessa kostnader kan konfigureras så att de är identiska för alla kunder och leveranssätt. Alternativt kan avgifterna variera beroende på kunden och/eller de leveranssätt som har valts för försäljningsordern.

Definiera avgifterna genom att gå till **Butik och handel \> Kanalinställning \> Avgifter \> Automatiska avgifter**. Välj **Ny** för att lägga till nya avgifter. Du kan också markera en befintlig post och välj sedan **redigera**.

Avgifter kan definieras så att de beräknas på nivån av antingen orderrubriken eller orderraderna. Använd fältet **nivå** om du vill ange önskad nivå.

Avgifter kan definieras för en specifik kund, en grupp med kunder eller alla kunder. På fältet **Kontokod** väljer du **Tabell** för att definiera avgifter som endast används för en viss kund. Välj **grupp** för att definiera en specifik kundgrupp. Välj **Alla** för att tillämpa avgifter på kunder som placerar en försäljningsorder med relaterade leveranssätt. Om du har valt **tabell** eller **grupp** i fältet **Kontokod** väljer kund eller kundgrupp i fältet **kontorelation**.

Avgifter kan konfigureras så att de tillämpas för ett visst leveranssätt, en leveranssättgrupp eller alla leveranssätt. Om du väljer **Tabell** i fältet **kod för leveranssätt** måste du välja ett visst leveranssätt i fältet **relation för leveranssätt**. Om du väljer **grupp**, måste du välja en grupp med leveranssätt i fältet **relation för leveranssätt**. Leveransättgrupperna definieras vid **Butik och handel \> kanalinställning \> tillägg \> leveransavgiftsgrupp**. De kan sedan länkas till en eller flera leveranssätt på sidan **leveranssätt**. Om du väljer en grupp när du definierar avgifter använder varje leveranssätt som är kopplad till vald grupp dessa avgifter. Slutligen, om du väljer **alla** i fältet **kod för leveranssätt** använder alla leveranssätt avgifterna. Därför ska du inte välja ett värde i fältet **relation för leveranssätt**.

I avsnittet **rader** kan du definiera en eller flera avgifter med valuta, enligt behov. Avgifter måste kopplas till en avgiftskod som definierar ekonomiska bokföringsreglerna för avgiften. Fältet **kategori** används för att definiera hur kostnader ska beräknas. Till exempel om kunder ska debiteras ett schablonbelopp på 9,95 $ för att ha en order som levererats från ett visst leveranssätt, använda kategorin **fast**. Om företaget beslutar att debitera kunder procent av orderns totala summa för att täcka leveransavgifterna, använd kategorin **Procent**. Den verkliga avgiften till kunder som har definierats i fältet **Avgiftsvärde**.

Företag konfigurerar ofta skiftindelade avgifter. I detta fall baseras det belopp som kunden ska betala för leveransen på ordervärdet. Om du vill konfigurera skiftindelade avgifter fyller du i fältet **Från belopp** och **Till belopp** förutom att definiera själva avgiften i fältet **Avgiftsvärde**. Exempelvis för order som har ett värde som är mindre än 50 $ debiterar en återförsäljare avgifter på 5,95 $ för markleverans. Order som har ett värde som är lika med eller större än 50 $, men mindre än 100 $, återförsäljaren debiterar 7,95 $. Order som har ett värde som är lika med eller större än 100 $, ger återförsäljaren gratis leverans. Följande bild visar konfigurationen av dessa avgifter.

![Exempel på fasta skiftindelade avgifter](media/fixedtieredcharges.png)

Du kan använda en blandning av kategorier för avgifter, beroende på företagets behov. Exempelvis för alla order som har ett värde som är mindre än 100 $ finns en fast avgift på 9,95 $ för leverans. För order som har ett värde som är lika med eller överstiger 100 $ beräknas leveransavgifter till 5 procent av värdet för ordern. Följande bild visar konfigurationen av dessa avgifter.

![Exempel på blandade skiftindelade avgifter](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Använd leveranssätt under orderregistreringen i en kundtjänst

När en ny försäljningsorder skapas måste ett värde anges i fältet **leveranssätt** på snabbfliken **leverans** i försäljningsorderrubriken. Fältet kan fyllas i automatiskt, baserat på standardvärden från kundposten.

Leveranssätt som definieras i orderrubriken kopieras automatiskt till försäljningsorderraderna som har skapats. Du kan ändra leveranssättinstallation för en viss artikel på fliken **leverans** i avsnittet **radinformation** på startsidan för försäljningsorder.

Om det valda leveranssättet inte är giltigt för produkten eller leveransadressen som definieras för ordern eller orderraden, visas ett felmeddelande. Du måste ange ett leveranssätt som har definierats för denna produkt- eller adresskonfiguration.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Beräkning av leveransavgifter under registreringen av order

Om inställningen är **Aktivera slutförande av order** aktiveras för din kundtjänstkanal kommer leveransavgifter beräknas automatiskt för försäljningsorder när användarna väljer **komplett**. Följande meddelande visas längst upp på sidan **Sammanfattning av försäljningsorder**: ”Skiftindelade avgifter beräknas. Avgifterna som beräknas läggs till värdet i fältet **Total försäljning**. På snabbfliken **Belopp** visar fältet **Avgifter** det totala beloppet för alla avgifter som har beräknats för ordern och raderna. Om du vill visa en mer detaljerad uppdelning av avgifterna, välj **Order** på sidan **Sammanfattning av försäljningsorder** och välj sedan alternativet **Avgifter** för att visa, lägga till eller redigera avgifterna. Observera att beräkningen av leveransavgifter på orderrubriken baseras på leveranssätt som är kopplat till rubriken. Radnivå leverans kostnader beräknas baserat på leveranssätt som har konfigurerats för försäljningsraden. Om flera leveranssätt används på olika rader, kan flera avgifter tillämpas och läggas ihop. Därefter visas det totala beloppet i den **tillägg** på de **försäljning ordersammandrag** sida.

Om inställningen **aktivera slutförande av order** är inaktiverad, måste användare manuellt initiera beräkningen av avgifter. På sidan **försäljningsorder** i åtgärdsfönstret, på fliken **sälja** i gruppen **beräkna** markerar du **Skiftindelade avgifter**. Meddelandet ”Skiftindelade avgifter beräknas” visas. Du kan välja alternativet **Avgifter** på fliken **Sälja** om du vill visa, redigera eller ta bort beräknade avgifter.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Använd expedierad leveranssätt på kundtjänstorder

Du kan även länka en expedieringskod till varje leveranssätt som du konfigurerar. Den här koden används som en prioriteringssorterings- och rapporteringsverktyg. Det orsakar för närvarande inte extra avgifter som tillämpas på ordern. För att ställa in expedieringskod, gå till **försäljning och marknadsföring \>inställningar \>fördelning \>expedieringskoder**.

Exempelvis för order som ska levereras med flyg, nästa dag måste plockning göras på ett lagerställe kl 13 varje dag. I det här fallet kan du skapa en expedieringskod och koden kan länkas till leverans nästa arbetsdagsläge som har konfigurerats i systemet. När lagerstället skapar dess påfyllnadsplockning och lämplig expedieringskod i fältet **expediering** kan användas som ett filter så att plockning utförs endast för order som har de leveranssätt som är kopplade till koden.

Dessutom när en kundtjänstorder anges kan en expedieringskod användas manuellt till försäljningsorderrubriken eller till enskilda försäljningsorderraden. Igen kan koden användas för sorterings- eller rapporteringsändamål. Ibland kan måste en order hanteras försiktigt på grund av ett problem med kundtjänst. Då kan en viss expedieringskod tillämpas på orderrubriken eller rader för att identifiera och prioritera ordern under utförandeprocessen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]