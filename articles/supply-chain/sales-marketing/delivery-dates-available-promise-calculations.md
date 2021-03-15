---
title: Orderlöfte
description: Detta avsnittet innehåller information om orderlöften. Orderlöften hjälper dig att ge dina kunder pålitliga löften om leveransdatum, och ger dig flexibilitet att hålla dessa datum.
author: ShylaThompson
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79f195c85df2628e54a9bf551715c193705b2694
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983076"
---
# <a name="order-promising"></a>Orderlöfte

[!include [banner](../includes/banner.md)]

Detta avsnittet innehåller information om orderlöften. Orderlöften hjälper dig att ge dina kunder pålitliga löften om leveransdatum, och ger dig flexibilitet att hålla dessa datum.

Orderlöfte beräknar de tidigaste transport- och inleveransdatumen och baseras på metoden för kontroll av leveransdatum och transportdagar. Du kan välja mellan fyra metoder för kontroll av leveransdatum:

-   **Produktionstid för försäljning** – Produktionstiden för försäljning är tiden mellan det att försäljningsordern skapas och artiklarna levereras. Beräknat för leveransdatum baseras på ett standardantal dagar och beaktar inte lagertillgänglighet, känd efterfrågan eller planerad tillgång.
-   **ATP (available-to-promise; "tillgänglig att utlova")** – ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund vid ett specifikt datum. ATP-beräkning inkluderar det obekräftade lagret, ledtider, planerade inleveranser och utleveranser.
-   **ATP + utleveransmarginal**– Leveransdatum är lika med ATP-datumet plus utleveransmarginal för artikeln. Utleveransmarginalen är den tid som krävs för att förbereda artiklar som ska levereras.
-   **CTP (CTP)**– Tillgänglighet beräknas genom nedbrytning.

> [!NOTE]
> När en försäljningsorder uppdateras information om orderlöften endast om det befintliga datumet för orderlöfte inte kan uppfyllas, vilket illustreras i följande exempel:
> 
> - **Exempel 1**: det aktuella datumet för orderlöfte är 20 juli, men på grund av en ökad kvantitet kan du inte leverera förrän den 25 juli. Eftersom det aktuella datumet inte längre kan uppfyllas utlöses orderlöfte.
> -  **Exempel 2**: det aktuella datumet för orderlöfte är 20 juli, men på grund av en minskad kvantitet är det nu möjligt att leverera den 15 juli. Eftersom det aktuella datumet kan fortfarande uppfyllas utlöses inte orderlöfte och 20 juli är datumet för orderlöftet.

## <a name="atp-calculations"></a>ATP-beräkningar
ATP-kvantiteten beräknas med metoden "ackumulerad ATP med framförhållning". Den största fördelen med ATP-beräkningsmetoden är att den förmår hantera fall där summan av utleveranser bland inleveranser överstiger den senaste inleveransen (till exempel när en kvantitet från en tidigare inleverans måste användas för att kunna uppfylla ett behov). Beräkningsmetoden "ackumulerad ATP med framförhållning" omfattar alla utleveranser tills den ackumulerade kvantiteten att inleverera är större än den ackumulerade kvantiteten att utleverera. Därför utvärderar den här ATP-beräkningsmetoden om en del av kvantiteten från en tidigare period kan användas i en senare period.  

ATP-kvantiteten är det obekräftade lagersaldot under den första perioden. Vanligtvis beräknas den för varje period som en inleverans schemaläggs. Programmet beräknar ATP-perioden i dagar och beräknar det aktuella datumet som det första datumet för ATP-kvantiteten. Under den första perioden omfattar ATP lagerbehållningen minus kundorder som har förfallit.  

ATP beräknas med följande formel:  

ATP = ATP för föregående period + inleveranser för aktuell period – utleveranser för aktuell period – nettosaldo för varje framtida period till och med den period då summan av inleveranser för alla framtida perioder (inklusive den framtida perioden) överskrider summan av inleveranserna (inklusive den framtida perioden).  

Observera att beräkningen av ATP inte innehåller information om utgångsdatum och efter den tidsgräns för ATP som systemet förväntar sig när någon kvantitet kan utlovas.

När det inte finns några fler utleveranser eller inleveranser att ta hänsyn till är kvantiteten tillgängligt att lova för de följande datumen densamma som den senast beräknade kvantiteten tillgängligt att lova.  

Om inte alla dimensionerna som används för en artikel är givna när ATP-kontrollen slutförs, kan de fortfarande anges i utleveransen och inleveranserna. I beräkningen av tillgängligt att lova måste i så fall inleveranser och utleveranser aggregeras till de befintliga dimensionerna, för att antalet inleverans- och utleveransrader som används i beräkningen av tillgängligt att lova ska minska.  

ATP-kvantiteten som visas är alltid större än eller lika med 0 (noll). Om beräkningen returnerar en negativ ATP-kvantitet (till exempel kvantitet som lovades tidigare överskrider den tillgängliga kvantiteten) anges kvantiteten anges automatiskt till 0.

### <a name="example"></a>Exempel

Fältet **ATP-tidsgräns för omvänd efterfrågan** kontrollerar hur långt bakåt i tiden att söka efter försenade efterfrågansorder eller lagerutleveranser. Fältet **ATP-tidsgräns för omvänd leverans** kontrollerar hur långt bakåt i tiden att söka efter försenade leveransorder eller lagerinleveranser. Om till exempel order som är försenade efter bara sju dagar ska beaktas i ATP-beräkningen, måste båda fälten vara inställda på **7**.  

Fälten **ATP-förskjutningstid för fördröjd efterfrågan** och **ATP-förskjutningstid för fördröjd leverans** kontrollerar när fördröjd efterfrågan eller leverans tas med i ATP-beräkningen. Om till exempel fördröjd leverans och efterfrågan ska beaktas i ATP-beräkningen i övermorgon måste båda fälten vara inställda på **2**. Värdet **2** innebär att kvantiteten för en artikel på en fördröjd inköpsorder som ska beaktas i ATP-beräkningen ses som tillgänglig två dagar efter aktuellt datum.  

För följande exempel anges **7** i fälten **ATP-tidsgräns för omvänd efterfrågan** och **ATP-tidsgräns för omvänd leverans** och **1** anges i fälten **ATP-förskjutningstid för fördröjd efterfrågan** och **ATP-förskjutningstid för fördröjd leverans**.  

En inköpsorder för 200 enheter av en produkt som skulle ha tagits emot för tre dagar sedan har ännu inte mottagits. Därför har en försäljningsorderrad på 75 enheter av samma produkt som skulle ha levererats igår inte levererats.  

En kund ringer och vill beställa 150 enheter av samma produkt. När du kontrollerar produktens tillgänglighet upptäcker du att en annan inköpsorder på 100 enheter av produkten ska levereras 10 dagar senare.  

Du skapar en försäljningsorderrad för produkten och anger kvantitetens **150**.  

Eftersom metoden för kontroll av leveransdatum är ATP, beräknas ATP-data för att hitta tidigast möjliga transportdatum. Försenade inköpsorder och försäljningsorder beaktas baserat på inställningarna, och resulterande ATP-kvantitet för det aktuella datumet är 0. Imorgon, då den försenade inköpsordern förväntas inlevereras, beräknas ATP-kvantiteten som mer än 0 (i detta fal beräknas den som 125). 10 dagar från och med nu, när ytterligare inköpsorder för 100 enheter förväntas inlevereras, kommer ATP-kvantiteten däremot att överstiga 150.  

Därför anges transportdatum som 10 dagar från nu, baserat på beräkningen av ATP. Därför talar du om för kunden att den begärda kvantiteten kan levereras 10 dagar från och med nu.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]