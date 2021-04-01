---
title: Tidsplansalternativ för åtgärder
description: I det här avsnittet beskrivs alternativen för grovplanering. Du kan använda grovplaneringen för att ange en allmän uppskattning av produktionsprocessen över en viss tid.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c95e23b070cd0234917ba14ecd6d8f37cfc8c40
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260489"
---
# <a name="operations-scheduling-options"></a>Tidsplansalternativ för åtgärder

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs alternativen för grovplanering. Du kan använda grovplaneringen för att ange en allmän uppskattning av produktionsprocessen över en viss tid.

Åtgärdstidsplaneringen beräknar följande information för en produktionsorder:

-   Start- och slutdatum anges för produktionsordern och respektive åtgärd.
-   Resurser tilldelas till verksamheter.

Flera inställningar anger hur produktionens tidsplaner beräknas. Du definierar dessa inställningar på sidan **Grovplanering**. Nedan följer information som beskriver planeringsalternativen.

## <a name="operations-scheduling"></a>Grovplanering
### <a name="scheduling-direction"></a>Planeringsriktning

Planeringsriktningen är avgörande för planeringsprocessen. Produktion kan planeras framåt eller bakåt från alla datum, beroende på tids- och planeringskrav.

-   **Framåtplanering**– Du kan tidsplanera en produktion så att denna startar så tidigt som möjligt. Produktionen kan påbörjas idag, imorgon eller på ett angivet datum i framtiden. Produktionen är planerad att inledas vid ett så tidigt datum som möjligt och planeras framåt i tiden till det tidigast möjliga slutdatumet.
-   **Bakåtplanering**– Du kan tidsplanera en produktion så att denna startar så sent som möjligt. Tidsplanen baseras på det datum då produktionen måste vara slutförd, och räknar bakåt till senast möjliga datum då produktionen kan inledas utan att missa deadline.

Följande alternativ är tillgängliga:

-   **Framåt från idag** – Planering framåt från aktuellt datum. (Aktuellt datum är systemdatum.)
-   **Framåt från planerad start** – Planering framåt från ett tidigare startdatum. Om det inte finns någon föregående tidsplanering, kommer tidsplaneringsriktningen att vara framåt från aktuellt datum.
-   **Framåt från tidsplaneringsdatum** – Tidsplanering framåt från det datum som anges i fältet **Planeringsdatum**. Om du inte anger något tidsplaneringsdatum, kommer tidsplaneringsriktningen att vara framåt från aktuellt datum.
-   **Bakåt från leveransdatum** – Tidsplanering bakåt från det leveransdatum som har angetts för produktionsordern. Om du väljer det här tidsplaneringsalternativet men inget leveransdatum finns angivet, kommer leveransdatum att ställas in till aktuellt datum.
-   **Bakåt från planerat slut** – Tidsplanering bakåt från ett tidigare beräknat slutdatum. Om det inte finns någon tidsplanering blir slutdatumet detsamma som det aktuella datumet.
-   **Bakåt från tidsplaneringsdatum** – Tidsplanering bakåt från det datum som anges i fältet **Planeringsdatum**. Om du inte anger något tidsplaneringsdatum, kommer aktuellt datum att användas. Bakåt från tidsplaneringsdatum beräknas för produktionsordern senast ett behov beräknades. Om inget datum anges för produktionsordern, ställs detta in på aktuellt datum.
-   **Bakåt från leveransplansdatum** – Tidsplanering bakåt från det framtida datum som beräknats för produktionsordern senast ett behov beräknades. Om inget framtida datum anges för produktionsordern, ställs detta in på aktuellt datum.
-   **Som vid senaste tidsplanering** – I samband med grovplanering och finplanering sparas den valda planeringsriktningen och det valda datumet. Du kan därför välja detta alternativet för efterföljande tidsplanering. Om det inte finns någon föregående tidsplanering för tillverkningsordern sker tidsplaneringen bakåt från det aktuella systemdatumet.
-   **Framåt från i morgon** – Tidsplanering framåt från aktuellt datum plus en dag.
-   **Framåt från tidigare jobb** – Detta alternativ är endast relevant vid finplanering. Om du väljer denna planeringsriktning för grovplanering, tidsplaneras produktionsordern framåt från aktuellt datum. Vid finplanering upprättas tidsplanering för ett jobb, och alla andra jobb för produktionen tidsplaneras baserat på detta.
-   **Bakåt från tidigare jobb** – Detta alternativ är endast relevant vid finplanering. Om du väljer denna planeringsriktning för grovplanering, tidsplaneras order bakåt från det aktuella datumet. Vid finplanering upprättas tidsplanering för ett jobb, och alla andra jobb för produktionen tidsplaneras baserat på detta.

### <a name="scheduling-date"></a>Planeringsdatum

Detta datum används för tidsplaneringsriktningarna **Framåt från tidsplaneringsdatum** och **Bakåt från tidsplaneringsdatum**. Tidsplaneringen görs sedan bakåt eller framåt från det datumet. Mer information finns i föregående avsnitt "Tidsplaneringsriktning."

### <a name="recalculate-bom-levels"></a>Räkna om strukturlistenivåer

När du väljer **Omberäkna strukturlistenivåer**, kommer de valda strukturlistenivåerna att beräknas om i syfte att garantera rätt planeringsordning.

## <a name="limitations"></a>Begränsningar
### <a name="finite-capacity"></a>Begränsad kapacitet

Planeringen vilar på resurstillgängligheten som krävs för att slutföra produktionen. Om det inte finns tillräckligt med kapacitet kan produktionsorder komma att senareläggas eller till och med stoppas. Om begränsad kapacitet används för grovplanering, beaktas befintliga kapacitetsreservationer för resurserna, och denna kapacitet ses som icke tillgänglig. Produktionsordern planeras baserat på tillgängligheten för de resurskapaciteter som krävs. Verksamhetsplanering använder angiven verksamhetsordning för att bestämma ordningsföljden för verksamheterna i produktionsflödet. Verksamhetsplanering reserverar kapacitet i resursgrupperna baserat på de verksamhetstider som anges i produktionsflödet. Resursgruppernas kapacitet är summan av den tillgängliga kapaciteten för alla resurser i resursgrupperna.

### <a name="finite-material"></a>Begränsat material

Planeringen vilar dessutom på tillgängligheten för de material som krävs för produktionen. Otillräcklig komponenttillgänglighet kan även orsaka produktionsförseningar. Tidsplanering kan också baseras på materialanvändning. Ange bara de material som måste vara tillgängliga för produktion i stället för de materialet som inte är avgörande. Denna typ av planering kallas för att tidsplanera med begränsat material. När du anger begränsade material, planeras produktionen baserat på om materialet finns tillgängligt. **Obs!** När optimeringen sker både på kapacitet och material, beräknas produktionen för att uppfylla båda restriktioner. Tillgängligheten på kapacitet och material beaktas, och produktionsorderns verksamheter kan inte är planeras att inledas förrän kapacitet och material är tillgängliga samtidigt och i begärda kvantiteter. Markera den här kryssrutan om materialet ska betraktas som begränsat under planering. Om materialet är begränsat tas det hänsyn till materialets disponering. Det innebär alltså att hänsyn tas till de leveransplansdatum som har beräknats för artiklarna vid tidsplaneringen. Råmaterial reserveras vid tidsplaneringen och den aktuella produktionen bryts ned. Om planering sker flera gånger, genomför endast den första planeringen en nedbrytning och utför reservationer. Om du gör ändringar i produktionsstrukturlistan eller produktionsflödet, genomför nästa tidsplanering en nedbrytning. Nedbrytningen förutsätter att materialet behövs samma dag. Eftersom produktionen inte är tidsplanerad vid tidpunkten för nedbrytning av huvudplanen, används aktuellt datum som ungefärlig uppskattning av när artiklarna beräknas bli tillgängliga. Nedbrytningen kontrollerar sedan om artiklarna är tillgängliga. Om artiklarna är tillgängliga är det möjligt att uppfylla produktionskravet. Om artiklarna inte är tillgängliga det aktuella datumet skapas en planerad order, och ett motval för den planerade ordern skapas. Om en automatisk bekräftelse har angetts för den planerade ordern, bekräftas den planerade ordern automatiskt för inköp eller produktion. Produktionens status ändras automatiskt till det som anges i fältet **Begärd produktionsstatus** i dialogrutan **Disponeringsgrupper**. Om kryssrutan avmarkeras betraktas materialet alltid som tillgängligt. Därför tar tidsplaneringen inte hänsyn till om materialet är tillgängligt vid tiden för behovet.

### <a name="finite-property"></a>Begränsad egenskap

Markera den här kryssrutan om finplaneringen ska inkludera egenskapskrav.

### <a name="keep-production-unit"></a>Behåll produktionsenhet

Välj om planeringsmotorn endast ska schemalägga resurser som redan har registrerats på produktionsenheten.

### <a name="keep-warehouse-from-resource"></a>Behåll lager från resurs

Välj om får planeringsmotorn endast ska schemalägga resurser som är kopplade till det inleveranslagerställe som anges i resursen.

## <a name="references"></a>Referenser
### <a name="schedule-references"></a>Tidsplanera referenser

När referenser vilar på tillverkningsorder kallas de också för delproduktioner. Delproduktioner kan planeras som en del av planeringen för en produktionsorder. Markera den här kryssrutan om tidsplaneringen för delproduktioner ska baseras på planeringen för huvudproduktionen. I relation till huvudproduktionen tidsplaneras överliggande produktioner framåt och underliggande produktioner bakåt. Produktionsorderreferenser finns i fältet **Referensnivå** på sidan **Produktionsorder**.

### <a name="synchronize-references"></a>Synkronisera referenser

Du kan synkronisera referenser med produktionsordern. Om det här alternativet väljs flyttas och justeras datumen för delproduktionerna när ändringar görs i produktionsorderns tidsplanering. Om en tillverkningsorder har en eller flera delproduktioner, kan du överväga att planera delproduktionerna tillsammans med huvudproduktionen. I så fall kan huvudproduktionen inte startas förrän de relaterade delproduktionerna har slutförts. Markera därför den här kryssrutan om tidsplaneringen för delproduktioner ska baseras på start- och sluttid för vald produktion. Du kan markera den här kryssrutan om även kryssrutan **Tidsplanera referenser** markeras.

## <a name="cancellation"></a>Annullera
### <a name="cancel-queue-time"></a>Annullera kötid

Markera den här kryssrutan om du vill exkludera kötiden från tidsplaneringen.

### <a name="cancel-setup"></a>Annullera inställningar

Markera den här kryssrutan om du vill exkludera inställningstiden från tidsplaneringen.

### <a name="cancel-process"></a>Annullera process

Markera den här kryssrutan om du vill exkludera körningstiden från tidsplaneringen.

### <a name="cancel-overlap"></a>Annullera överlappning

Markera den här kryssrutan om du vill exkludera överlappningstiden från tidsplaneringen.

### <a name="cancel-transport"></a>Annullera transport

Markera den här kryssrutan om du vill exkludera transporttiden från tidsplaneringen.

## <a name="set-default"></a>Ställ in standard
Du kan spara aktuella värden som förvalda värden. Det finns två alternativ:

-   Ange som min standard
-   Ange som standard för alla


<a name="additional-resources"></a>Ytterligare resurser
--------

[Grovplanering](operations-scheduling.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]