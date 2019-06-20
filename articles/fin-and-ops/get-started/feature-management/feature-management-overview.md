---
title: Översikt över funktionshantering
description: I det här avsnittet beskrivs funktionen funktionshantering och hur du kan använda den.
author: mikefalkner
manager: AnnBe
ms.date: 06/04/2019
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
ms.openlocfilehash: b200156a623c67a562cc1a5952899e3a77517528
ms.sourcegitcommit: bbc9aa0d6b94a942e1f4d5b038601509dcc87937
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2019
ms.locfileid: "1619154"
---
# <a name="feature-management-overview"></a>Översikt över funktionshantering

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Funktioner läggs till och uppdateras i alla versioner av Microsoft Dynamics 365 for Finance and Operations. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

## <a name="the-feature-management-workspace"></a>Använd arbetsytan funktionshantering.

Du kan öppna arbetsytan **funktionshantering** genom att välja lämplig panel på instrumentpanelen. En sida visas med en lista över funktioner för alla utgåvor som stöds av funktionshanteringsupplevelsen. Med tiden kommer Microsoft att förbättra funktionerna i funktionshantering så att de omfattar ytterligare funktioner som hjälper dig att hantera funktioner.

Funktionslistan inkluderar följande information:

- **Funktionens namn** – en beskrivning av funktionen som har lagts till.
- **Aktiverad status** – en symbol anger om en funktion har aktiverats (bockmarkering), inte aktiveras (tom), har tidsplanerats för att aktiveras (klocka) eller är obligatorisk aktiverad (lås). Inställningen som visas här används för alla juridiska personer. Observera att även om en funktion har aktiverats, styrs den fortfarande av säkerhet. Funktionen är därför bara tillgänglig för användare som har åtkomst till den, baserat på deras säkerhetsroll. Det är också bara tillgängligt för juridiska personer som användaren har till gång till.
- **Aktivera datum** – det datum då funktionen aktiverades eller är tidsplanerad att aktiveras.
- **Funktionen tillagd** – det datum då funktionen lades till i din miljö. Detta datum anges automatiskt när du uppdaterar miljön under de månatliga versionscyklerna.
- **Modul** – den modul som påverkas av den nya funktionen.

När du väljer en funktion visas ytterligare information i informations fönstret till höger om funktionslistan. Längst upp i fönstret visas funktionsnamnet, det datum då funktionen lades till, den modul som påverkas av funktionen och länken **Läs mer**. Välj den här länken om du vill visa dokumentationen för funktionen. Om dokumentationen inte är tillgänglig kommer du till en tillfällig sida. Informationsfönstret innehåller också fältet **kommentarer** där du kan lägga till egna kommentarer om funktionen.

Arbetsytan **Funktionshantering** funktionshantering innehåller också flera flikar som var och en visar en lista med funktioner.

- **Ny** – denna flik visar alla funktioner som har lagts till sedan den senaste månadsuppdateringen. Om du har hoppat över några månatliga uppdateringar visas alla nya funktioner som har lagts till sedan senaste gången du uppdaterade på fliken. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner visas också på en sida högst upp på sidan.
- **Inte aktiverad** – på den här fliken visas alla funktioner som inte har aktiverats. De nyaste funktionerna visas högst upp i listan. Det totala antalet nya funktioner som inte har aktiverats visas också på en sida högst upp på sidan.
- **Tidsplanerad** - denna flik visar alla funktioner som har tidsplanerats att aktiveras för framtida datum. De funktioner som har det tidigaste tidsplanerade datumet visas överst i listan. Det totala antalet tidsplaneringar av nya funktioner visas också på en sida högst upp på sidan.
- **Alla** – på den här fliken visas alla funktioner. De nyaste funktionerna visas högst upp i listan.

## <a name="turn-on-a-feature"></a>Aktivera en funktion

Om en funktion inte har aktiverats visas knappen **Aktivera nu** i informationsfönstret. Du kan använda den här knappen om du vill aktivera funktionen.

- Välj den funktion som du vill aktivera och välj sedan **aktivera nu** i informationsfönstret. Funktionen är aktiverad.

Vissa funktioner kan inte inaktiveras när du har aktiverat dem. Om funktionen som du försöker aktivera inte kan inaktiveras får du en varning. I det här läget kan du välja **Avbryt** om du vill avbryta åtgärden och lämna funktionen inaktiverad. Om du däremot väljer **aktivera** och aktiverar funktionen kommer du inte att kunna inaktivera den senare.

När funktionen är aktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Det här meddelandet anger att funktionen har aktiverats eller anger det framtida datum när funktionen är tidsplanerad att aktiveras. Det visas varje gång du väljer funktionen i funktionslistan.

Funktioner som är schemalagda att aktiveras i framtiden visas på fliken **Schemalagd**. En batchprocess aktiverar dem vid midnatt det angivna datumet, baserat på tidszonen som representeras av systemdatumet.

## <a name="reschedule-a-feature"></a>Tidsplanera om en funktion

Om en funktion har tidsplanerats att aktiverats i framtiden visas knappen **tidsplanera** i informationsfönstret. Du kan använda den här knappen om du vill ändra värdet **aktivera datum** till ett annat datum.

1. Välj en tidsplanerad funktion som du vill tidsplanera om och välj sedan **Tidsplanera** i informationsfönstret.
2. I dialogrutan som visas i fältet **aktivera datum** anger du det nya datum då funktionen ska aktiveras.
3. Välj **aktivera** om du vill tidsplanera om funktionen eller **inaktivera** om du vill avbryta schemat.

## <a name="turn-off-a-feature"></a>Inaktivera en funktion

Om en funktion redan har aktiverats visas knappen **Inaktivera** i informationsfönstret. Du kan använda den här knappen om du vill inaktivera funktionen. Knappen **inaktivera** är inte tillgänglig om funktionen inte kan inaktiveras när den har aktiverats.

- Välj den funktion som du vill stänga av och välj sedan **inaktivera** i informationsfönstret. Funktionen är inaktiverad och fältet **aktivera datum** avmarkeras.

När funktionen är inaktiverad visas ett meddelande under länken **Mer information** i informationsfönstret. Meddelandet anger att funktionen inte har aktiverats ännu. Det visas varje gång du väljer funktionen i funktionslistan. Funktioner som int hr aktiverats visas på fliken **Inte aktiverad**.

## <a name="features-that-must-be-turned-on"></a>Funktioner som måste aktiveras

Ibland levereras en kritisk funktion som måste aktiveras automatiskt när du gör en uppdatering. De här funktionerna aktiveras automatiskt på det datum som anges i fältet **aktivera datum**. För dessa funktioner visas ett meddelande under länken **Mer information** i informationsfönstret. Det här meddelandet anger att funktionen har aktiverats eller anger det framtida datum när funktionen kommer att aktiveras. Det visas varje gång du väljer funktionen i funktionslistan.

## <a name="turn-on-all-features-automatically"></a>Aktivera alla funktioner automatiskt

Som standard är alla funktioner som läggs till i miljön inaktiverade, såvida de inte är obligatoriska funktioner. Om du vill aktivera alla nya funktioner automatiskt kan du dock ändra vad som händer när nya funktioner läggs till genom att använda listrutan under arbetsytans rubrik.

- Markera **alla nya funktioner aktiveras som standard** för att automatiskt aktivera alla nya funktioner när de läggs till i miljön.
- Markera **alla nya funktioner inaktiveras som standard** för att automatiskt inaktivera alla nya funktioner när de läggs till i miljön.

## <a name="assigning-roles"></a>Tilldela roller

Arbetsytan för **Funktionshantering** kan öppnas av systemadministratörer och även av användare som har tilldelats rollen Funktionshanterare eller Funktionsvisare. Dessa två roller skapades för att ge stöd till upplevelsen för funktionshantering. Användare med funktionshanterarens roll kan aktivera och inaktivera alla funktioner. De kan också uppdatera avsnittet **kommentarer** för funktionen. Användare med funktionsrollen kan endast visa arbetsytan **Funktionshantering**. De kan inte aktivera eller inaktivera funktioner.

Rollen Funktionshanterare och rollen Funktionsvisare åsidosätter inte den befintliga säkerhet som en användare har. De styr bara om användaren kan aktivera och inaktivera funktioner. De ger inte tillgång till själva funktionerna.

## <a name="features-that-use-configuration-keys"></a>Funktioner som använder konfigurationsnycklar

Om en funktion använder en konfigurationsnyckel men konfigurationsnyckeln inte är aktiverad visar arbetsytan **Funktionshantering** inte funktionen i listan över tillgängliga funktioner. När du har aktiverat konfigurationsnyckeln måste du uppdatera funktionslistan genom att använda menyalternativet **Kontrollera updatering**. Funktionen visas sedan i funktionslistan.

Om du inaktiverar konfigurationsnyckeln tas funktionen inte bort från funktionslistan.

## <a name="data-entities"></a>Datatabeller

Med hjälp av en dataenhet som kallas **funktionshantering** kan du exportera funktionshanteringsinställningarna från en miljö och sedan importera dem till en annan miljö. Den här enheten uppdaterar endast befintliga funktioner. Affärslogiken i entiteten garanterar också att samma regler som används på arbetsytan **funktionshantering** används när importen görs. Du kan till exempel inte åsidosätta en obligatorisk funktionsinställning genom att ta bort datumet under importen.

I följande exempel beskrivs vad som händer när du använder entiteten **funktionshantering** för att importera data.

- Om **du ändrar värdet i det aktiverade** fältet till **ja**, aktive ras funktionen, och fältet **aktiverings datum** sätts till aktuellt datum.
- Om du ändrar värdet **Aktiverad** till **Nej** eller lämnar fältet **EnableDate** tomt inaktiveras funktionen och fältet **Aktivera datum**. Du kan inte inaktivera en obligatorisk funktion eller en funktion som inte kan inaktiveras när den är aktiverad.
- Om du ändrar värdet i fältet **EnableDate** till ett framtida datum, tidsplaneras funktionen för det datumet.
- Om du ändrar värdet i fältet **Aktiverad** till **Ja** och ändrar värdet i fältet **EnableDate** till ett framtida datum tidsplaneras funktionen för det datumet. 
- Om du ändrar värdet i fältet **Aktiverad** till **Nej** och ändrar också värdet i fältet **EnableDate** till ett framtida datum tidsplaneras funktionen för det datumet.
- Om en funktion är aktiverad och du lägger till fältet **EnableDate** som är inställt på ett framtida datum, förblir funktionen aktiverad. Om du vill tidsplanera om funktionen måste du ändra fältet **aktiv** till **Nej**.

## <a name="feature-management-and-flighting"></a>Funktionshantering och flygning

Med funktionshantering kan du styra de funktioner som levereras i varje utgåva. Förhandsversioner låter Microsoft Teams frisläppa funktioner till ett begränsat antal kunder så att funktionerna kan testas och valideras utan att alla kunder påverkas. Funktionshanteringen styr inte förhandsversioner av funktioner.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Använda funktionshantering för att aktivera ISV-funktioner eller anpassade funktioner

Funktionshantering är för närvarande inte tillgängligt för funktioner från oberoende programvaruleverantörer (ISV) och anpassade funktioner. Microsoft lägger dock till fler funktioner för att förbättra funktionshanteringen. När dessa förbättringar har genomförts gör Microsoft funktionshantering tillgängligt för alla funktioner och innehåller instruktioner för hur du uppdaterar funktionerna.
