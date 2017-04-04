---
title: "Orderlöfte"
description: "Denna artikel innehåller information om orderlöften. Orderlöften hjälper dig att ge dina kunder pålitliga löften om leveransdatum, och ger dig flexibilitet att hålla dessa datum."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8aa0a58b03ee18e42ca7770ea3e22311c1ddba67
ms.lasthandoff: 03/31/2017


---

# <a name="order-promising"></a>Orderlöfte

Denna artikel innehåller information om orderlöften. Orderlöften hjälper dig att ge dina kunder pålitliga löften om leveransdatum, och ger dig flexibilitet att hålla dessa datum.

Orderlöfte beräknar de tidigaste transport- och inleveransdatumen och baseras på metoden för kontroll av leveransdatum och transportdagar. Du kan välja mellan fyra metoder för kontroll av leveransdatum:

-   **Produktionstid för försäljning** – försäljning produktionstiden är tiden mellan försäljningsorder skapas och leverans av artiklarna. Beräkning för leveransdatum utifrån en standardantalet dagar och anser inte lagertillgänglighet kända efterfrågan eller planerade leveransen.
-   **Tillgängligt att LOVA (tillgängligt att lova)** – tillgängligt att LOVA är antal artiklar som är tillgängliga och kan utlovas till en kund vid ett visst datum. ATP-beräkning inkluderar det obekräftade lagret, ledtider, planerade inleveranser och utleveranser.
-   **ATP + utleveransmarginal **– Leveransdatum är lika med ATP-datumet plus utleveransmarginal för artikeln. Utleveransmarginalen är den tid som krävs för att förbereda artiklar som ska levereras.
-   **CTP (CTP) **– Tillgänglighet beräknas genom nedbrytning.

## <a name="atp-calculations"></a>ATP-beräkningar
Kvantiteten tillgängligt att LOVA beräknas med hjälp av metoden "Ackumulerat tillgängligt att LOVA med framförhållning". Den största fördelen med DAL-beräkningsmetoden är att den kan hantera fall där summan av utleveranser mellan inleveranser är större än den senaste inleveransen (t.ex, när en kvantitet från en tidigare inleverans måste användas för att uppfylla ett krav). Metoden "Ackumulerat tillgängligt att LOVA med framförhållning" beräkningen omfattar alla utleveranser tills den ackumulerade kvantiteten att inleverera är större än den ackumulerade kvantiteten att utleverera. Därför utvärderar den här ATP-beräkningsmetoden om en del av kvantiteten från en tidigare period kan användas i en senare period.  

ATP-kvantiteten är det obekräftade lagersaldot under den första perioden. Vanligtvis beräknas den för varje period som en inleverans schemaläggs. Programmet beräknar ATP-perioden i dagar och beräknar det aktuella datumet som det första datumet för ATP-kvantiteten. Under den första perioden omfattar ATP lagerbehållningen minus kundorder som har förfallit.  

ATP beräknas med följande formel:  

Tillgängligt att LOVA = tillgängligt att LOVA för föregående period + inleveranser för aktuell period – utleveranser för den aktuella perioden-nettosaldot för varje framtida period tills den period då summan av inleveranser för alla framtida perioder fram till och med den framtida perioden överstiger summan av utleveranser upp till och med den framtida perioden.  

När det inte finns några fler utleveranser eller inleveranser att ta hänsyn till är kvantiteten tillgängligt att lova för de följande datumen densamma som den senast beräknade kvantiteten tillgängligt att lova.  

Om inte alla dimensionerna som används för en artikel är givna när ATP-kontrollen slutförs, kan de fortfarande anges i utleveransen och inleveranserna. I beräkningen av tillgängligt att lova måste i så fall inleveranser och utleveranser aggregeras till de befintliga dimensionerna, för att antalet inleverans- och utleveransrader som används i beräkningen av tillgängligt att lova ska minska.  

ATP-kvantiteten som visas är alltid större än eller lika med 0 (noll). Om beräkningen returnerar en negativ ATP-kvantitet (till exempel kvantitet som lovades tidigare överskrider den tillgängliga kvantiteten) anges kvantiteten automatiskt till **0**.

### <a name="example"></a>Exempel

Fältet **ATP-tidsgräns för omvänd efterfrågan** kontrollerar hur långt bakåt i tiden att söka efter försenade efterfrågansorder eller lagerutleveranser. Fältet **ATP-tidsgräns för omvänd leverans** kontrollerar hur långt bakåt i tiden att söka efter försenade leveransorder eller lagerinleveranser. Om till exempel order som är försenade efter bara sju dagar ska beaktas i ATP-beräkningen, måste båda fälten vara inställda på **7**.  

Fälten **ATP-förskjutningstid för fördröjd efterfrågan** och **ATP-förskjutningstid för fördröjd leverans** kontrollerar när fördröjd efterfrågan eller leverans tas med i ATP-beräkningen. Om till exempel fördröjd leverans och efterfrågan ska beaktas i ATP-beräkningen i övermorgon måste båda fälten vara inställda på **2**. Värdet **2** innebär att kvantiteten för en artikel på en fördröjd inköpsorder som ska beaktas i ATP-beräkningen ses som tillgänglig två dagar efter aktuellt datum.  

För följande exempel anges **7** i fälten **ATP-tidsgräns för omvänd efterfrågan** och **ATP-tidsgräns för omvänd leverans** och **1** anges i fälten **ATP-förskjutningstid för fördröjd efterfrågan** och **ATP-förskjutningstid för fördröjd leverans**.  

En inköpsorder för 200 enheter av en produkt som skulle ha tagits emot för tre dagar sedan har ännu inte mottagits. Därför har en försäljningsorderrad på 75 enheter av samma produkt som skulle ha levererats igår inte levererats.  

En kund ringer och vill beställa 150 enheter av samma produkt. När du kontrollerar produktens tillgänglighet upptäcker du att en annan inköpsorder på 100 enheter av produkten ska levereras 10 dagar senare.  

Du skapar en försäljningsorderrad för produkten och anger kvantitetens **150**.  

Eftersom metoden för kontroll av leveransdatum är ATP, beräknas ATP-data för att hitta tidigast möjliga transportdatum. Utifrån inställningarna vara försenade inköpsorder och försäljningsorder och resulterande kvantiteten tillgängligt att LOVA för det aktuella datumet är 0. Imorgon om försenade inköpsorder ska tas emot kvantiteten tillgängligt att LOVA beräknas som överstiger 0 (då det beräknas som 125). 10 dagar från och med nu när ytterligare inköpsorder för 100 enheter förväntas ta emot blir kvantiteten tillgängligt att LOVA emellertid mer än 150.  

Därför transportdatum är inställt på 10 dagar från nu, baserat på beräkningen av ATP. Därför talar du om för kunden att den begärda kvantiteten kan levereras 10 dagar från och med nu.


