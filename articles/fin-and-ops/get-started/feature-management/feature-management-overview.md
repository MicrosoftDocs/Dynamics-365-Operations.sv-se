---
title: Översikt över funktionshantering
description: I det här avsnittet beskrivs funktionen funktionshantering och hur du kan använda den.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538711"
---
# <a name="feature-management-overview"></a>Översikt över funktionshantering

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Funktioner läggs till och uppdateras i alla versioner av Microsoft Dynamics 365 for Finance and Operations. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

## <a name="the-feature-management-workspace"></a>Använd arbetsytan funktionshantering.

Du kan öppna arbetsytan **funktionshantering** genom att välja lämplig panel på instrumentpanelen. En sida visas med en lista över funktioner för alla utgåvor som stöds av funktionshanteringsupplevelsen. Med tiden kommer Microsoft att förbättra funktionerna i funktionshantering så att de omfattar ytterligare funktioner som hjälper dig att hantera funktioner.

Funktionslistan inkluderar följande information:

- **Funktionens namn** – en beskrivning av funktionen som har lagts till.
- **Aktiverad status** – en symbol anger om en funktion har aktiverats (bockmarkering), inte aktiveras (tom), har schemalagts för att aktiveras (klocka) eller är obligatorisk aktiverad (lås). Inställningen som visas här används för alla juridiska personer. Observera att även om en funktion har aktiverats, styrs den fortfarande av säkerhet. Funktionen är därför bara tillgänglig för användare som har åtkomst till den, baserat på deras säkerhetsroll. Det är också bara tillgängligt för juridiska personer som användaren har till gång till.
- **Aktivera datum** – datumet då funktionen aktiverades eller kommer att aktiveras om datumet är ett framtida datum.
- **Funktionen tillagd** – det datum då funktionen lades till i din miljö. Detta datum anges automatiskt när du uppdaterar miljön under de månatliga versionscyklerna.
- **Modul** – den modul som påverkas av den nya funktionen.

När du väljer en funktion visas ytterligare information i informations fönstret till höger om funktionslistan. Längst upp i fönstret visas funktionsnamnet, det datum då funktionen lades till, den modul som påverkas av funktionen och länken **Läs mer**. Välj den här länken om du vill visa dokumentationen för funktionen. Om dokumentationen inte är tillgänglig kommer du till en tillfällig sida. Informationsfönstret innehåller också fältet **kommentarer** där du kan lägga till egna kommentarer om funktionen.

Arbetsytan **Funktionshantering** funktionshantering innehåller också flera flikar med en lista med funktioner. 
- **Ny** – visar alla funktioner som har lagts till sedan den senaste månadsuppdateringen. Om du har hoppat över några månatliga uppdateringar kommer de att innehålla alla nya funktioner sedan du senast uppdaterade. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner visas också på en sida högst upp på sidan.
- **Inte aktiverad** - visar alla funktioner som inte har aktiverats. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner visas också på en sida högst upp på sidan.
- **Schemalagda** - visar alla funktioner som har tidsplanerats för framtida datum. De funktioner som har det tidigaste schemalagda datumet visas överst i listan. Det totala antalet nya funktioner visas också på en sida högst upp på sidan.
- **Alla** - visar alla funktioner. De nyaste funktionerna visas högst upp i listan.


## <a name="enable-a-feature"></a>Aktivera en funktion

Om en funktion inte har aktiverats visas knappen **Aktivera** i informationsfönstret. Du kan använda den här knappen om du vill aktivera funktionen.

1. Välj den funktion som du vill aktivera och välj sedan **aktivera** i informationsfönstret.
2. Ett skjutreglage visas där du kan ange det datum då funktionen ska aktiveras. Som standard är det här datumet inställt på det aktuella datumet.
3. Välj **Aktivera** för att aktivera funktionen.

Vissa funktioner kan inte inaktiveras när du har aktiverat dem. Om funktionen som du försöker aktivera inte kan inaktiveras får du en varning. I det här läget kan du välja **Avbryt** om du vill avbryta åtgärden och lämna funktionen inaktiverad. Om du däremot väljer **aktivera** och aktiverar funktionen kommer du inte att kunna inaktivera den senare.

När funktionen är aktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Det här meddelandet anger att funktionen har aktiverats eller anger när funktionen ska aktiveras i framtiden. Om du använder ett framtida datum visas funktionen i listan **schemalagda**. Det här meddelandet visas varje gång du väljer funktionen i funktionslistan. Funktioner som är schemalagda i framtiden kommer att aktiveras vid midnatt med en batchprocess baserat på tidszonen som representeras av systemdatumet. 

## <a name="reschedule-a-feature"></a>Tidsplanera om en funktion

Om en funktion har aktiverats i framtiden visas knappen **Tidsplanera om** i informationsfönstret. Du kan använda den här knappen om du vill **aktivera datum** till ett annat datum.

1. Välj en tidsplanerad funktion som du vill tidsplanera om och välj sedan **tidsplanera om** i informationsfönstret.
2. Ett skjutreglage visas där du kan ange det datum då funktionen ska aktiveras. 
3. Välj **aktivera** om du vill tidsplanera om funktionen eller **inaktivera** om du vill avbryta schemat.

## <a name="disable-a-feature"></a>Inaktivera en funktion

Om en funktion redan har aktiverats visas knappen **Inaktivera** i informationsfönstret. Du kan använda den här knappen om du vill inaktivera funktionen. Knappen **inaktivera** är inte tillgänglig om funktionen inte kan inaktiveras när den har aktiverats.

- Välj den funktion som du vill stänga av och välj sedan **inaktivera** i informationsfönstret.

- Funktionen inaktiveras och datumet avmarkeras.

När funktionen är inaktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Detta meddelande anger att funktionen ännu inte har aktiverats och att den visas i listan **ej aktiverad**. Det här meddelandet visas varje gång du väljer funktionen i funktionslistan.

## <a name="features-that-must-be-enabled"></a>Funktioner som måste aktiveras

En kritisk funktion kan levereras som måste aktiveras automatiskt när du gör en uppdatering. Den aktiveras automatiskt på **aktivera datum**. Ett meddelande visas under **Mer information** i informationsfönstret. I det här meddelandet anges att funktionen har aktiverats automatiskt eller aktiveras **aktivera datum**. Detvisas varje gång du väljer funktionen i funktionslistan.

## <a name="assigning-roles"></a>Tilldela roller

Arbetsytan för **Funktionshantering** kan öppnas av systemadministratörer och användare som har tilldelats rollhanteraren eller funktionsvisarna som har skapats för funktionshanteringsupplevelsen. Användare med funktionshanterarens roll kan aktivera och inaktivera alla funktioner. De kan också uppdatera avsnittet kommentarer för funktionen. Användare med funktionsrollen kan endast visa arbetsytan **Funktionshantering**. De kan inte aktivera eller inaktivera funktioner.

Rollen Funktionshanterare och rollen Funktionsvisare åsidosätter inte den befintliga säkerhet som en användare har. Rollerna styr bara åtkomst till funktioner för att aktivera funktioner. Den ger inte tillgång till själva funktionerna.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Använda funktionshantering för att aktivera ISV-funktioner eller anpassade funktioner

Funktionshanteringsprocessen är för närvarande inte tillgänglig för ISV-funktioner eller anpassade funktioner. Vi lägger till ytterligare funktioner för att förbättra funktionshanteringen och, när dessa förbättringar är klara, öppnar vi funktionshantering för alla funktioner och ger specifika instruktioner för hur du uppdaterar funktionen för att använda den.

## <a name="feature-management-and-flighting"></a>Funktionshantering och flygning

Med funktionshantering kan du styra de funktioner som levereras i varje utgåva. Förhandsversioner låter Microsoft Teams frisläppa funktioner till ett begränsat antal kunder så att funktionerna kan testas och valideras utan att alla kunder påverkas. Funktionshanteringen styr inte förhandsversioner av funktioner.
