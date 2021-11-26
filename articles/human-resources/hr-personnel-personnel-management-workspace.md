---
title: Arbetsyta för personalhantering
description: I detta ämne beskrivs de begreppsmässiga elementen i arbetsytan för personalhantering.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4332be972ab3dc81e7e4f3cc297a91cd247e721e
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771348"
---
# <a name="personnel-management-workspace"></a>Arbetsyta för personalhantering

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Arbetsytan **Personalhantering** innehåller en mängd olika innehåll. Den innehåller personalrörelser, spårar personaländringar, lediga befattningar, adressändringar, utgående poster, analyser samt länkar till specifik information. Detta ämne innehåller detaljerad information om arbetsytans respektive delar.

## <a name="activity-tab"></a>Fliken Aktivitet

Fliken **Aktivitet** innehåller avsnitt som grupperar medarbetare utifrån deras fas i anställningsprocessen:

- **Kandidater att anställa**
- **Börjar snart**
- **Tidigare anställningar**
- **Avslutar**
- **Har slutat**

När en medarbetare befinner sig i en av dessa faser finns specifika åtgärder tillgängliga som en knapp på kortet eller på menyn som visas när du väljer ellipsen (**...**) i det övre högra hörnet. Följande delavsnitt beskriver avsnitten på fliken **Aktivitet** och listar de åtgärder som är tillgängliga.

### <a name="candidates-to-hire"></a>Kandidater att anställa

Avsnittet **Kandidater att anställa** i arbetsytan fylls i från flera olika källor:

- En OData-entitet (Open Data Protocol)
- LinkedIn-integration
- Data som anges manuellt i produkten

När kandidater visas i avsnittet **Kandidater att anställa** kan du utföra följande åtgärder genom att välja ellipsen på kandidatkortet:

- **Avfärda kandidat**
- **Anställ inte**
- **Anställ**

> [!NOTE]
> Om kandidatlistan fylls i från Microsoft Dataverse kommer samma kandidater att visas för samtliga juridiska personer, detta eftersom ingen juridisk person har kopplats till kandidaten.

### <a name="starting-soon"></a>Börjar snart

I avsnittet **Börjar snart** listas medarbetare med framtida startdatum. Listan sorteras efter startdatum. Det startdatum som är närmast dagens datum anges först i listan.

Om chefen inte visas på kortet har medarbetaren inte tilldelats någon befattning.

> [!NOTE] 
> Vi rekommenderar att du tilldelar en medarbetare till en befattning innan du använder en checklista. Ibland kan registreringsuppgifter tilldelas till en nyanställd medarbetares chef. Om ingen befattning tilldelas kan emellertid den nya medarbetarens chef inte fastställas. I det här fallet tilldelas de registreringsuppgifter som är avsedda för chefen istället till checklistans ägare.

När medarbetare visas i avsnittet **Börjar snart** är följande åtgärder tillgängliga för dem:

- Tilldela position
- Verifiera anställning
- Tilldela fast kompensation
- Tilldela variabel kompensation
- Visa i Hierarki
- Använd checklista\*\*

\*\* Denna åtgärd är standardåtgärden. Den visas som en knapp på kortet.

### <a name="recent-hires"></a>Tidigare anställningar

Avsnittet **Nyanställda** visar en lista över medarbetare med startdatum nyligen. Listan sorteras efter startdatum. Det startdatum som är närmast dagens datum anges först i listan.

Som standard visar listan medarbetare som anställts de senaste sju dagarna. På sidan **Personalparametrar**, på fliken **Allmänt**, anger du en tidsram för **Nyanställda** om du vill ändra denna inställning. Datan i avsnittet **Nyanställda** kan visas under ett specifikt antal dagar, månader eller år. Om du till exempel vill visa listan med medarbetare som anställdes under de senaste 14 dagarna anger du fältet **Period** som **14** och fältet **Enhet** som **Dagar**.

> [!NOTE]
> Inställningarna på sidan **Personalparametrar** är företagsspecifika. Därför kan den tidsram som du visar nyanställningar för variera för olika företag. I till exempel företaget USMF kanske du vill se alla nyanställda från de senaste sju dagarna. I företaget USSI kanske du emellertid vill se alla nyanställda från de senaste 14 dagarna. I det här fallet måste du öppna sidan **Personalparametrar** i respektive företag och ställa in parametrarna efter behov.

Om chefen inte visas på kortet har medarbetaren inte tilldelats någon befattning.

När medarbetare visas i avsnittet **Nyanställda** blir följande åtgärder tillgängliga för dem:

- Tilldela position
- Verifiera anställning
- Fast kompensation
- Tilldela variabel kompensation
- Visa i hierarki
- Använd checklista\*\*

\*\* Denna åtgärd är standardåtgärden. Den visas som en knapp på kortet.

### <a name="exiting"></a>Avslutar

I avsnittet **Lämnar** listas medarbetare med framtida uppsägningsdatum. Listan sorteras efter uppsägningsdatum. Det uppsägningsdatum som ligger närmast dagens datum anges först i listan. 

Som standard visar listan medarbetare som har uppsägningsdatum under de nästkommande sju dagarna. På sidan **Personalparametrar**, på fliken **Allmänt**, anger du en tidsram för **Visa för tillfället anställda** om du vill ändra denna inställning. Datan i avsnittet **Lämnar** kan visas under ett specifikt antal dagar, månader eller år. Om du till exempel vill visa listan med medarbetare som kommer att lämna företaget under nästkommande 14 dagar anger du fältet **Period** som **14** och fältet **Enhet** som **Dagar**.

När medarbetare visas i avsnittet **Lämnar** är följande åtgärder tillgängliga för dem:

- Använd checklista\*\*
- Verifiera anställning
- Visa i Hierarki

\*\* Denna åtgärd är standardåtgärden. Den visas som en knapp på kortet.

### <a name="exited"></a>Har slutat

Avsnittet **Lämnat** visar en lista över medarbetare med uppsägningsdatum nyligen. Listan sorteras efter uppsägningsdatum. Det uppsägningsdatum som ligger närmast dagens datum anges först i listan.

Som standard visar listan medarbetare som har uppsägningsdatum under de senaste sju dagarna. Om du vill ändra denna inställning går du till sidan **Personalparametrar** > fliken **Allmänt** och anger en tidsram för **Visa medarbetare som har lämnat**. Datan i avsnittet **Lämnat** kan visas under ett specifikt antal dagar, månader eller år. Om du till exempel vill visa listan med medarbetare som lämnat under de senaste 14 dagarna anger du fältet **Period** som **14** och fältet **Enhet** som **Dagar**.

När medarbetare visas i avsnittet **Lämnat** är följande åtgärder tillgängliga för dem:

- Använd checklista\*\*
- Verifiera anställning
- Visa i hierarki

\*\* Denna åtgärd är standardåtgärden. Den visas som en knapp på kortet.

## <a name="employee-changes-tab"></a>Fliken Medarbetarförändringar

Fliken **Medarbetarförändringar** innehåller en lista över samtliga personalåtgärder för medarbetare. Denna lista är inte tillgänglig som standard. Om du vill aktivera funktionen går du till sidan **Delade personalparametrar** > fliken **Personalåtgärder** och anger alternativet **Aktivera medarbetaråtgärder** som **Ja**.

## <a name="position-changes-tab"></a>Fliken Befattningsändringar

Fliken **Befattningsförändringar** innehåller en lista över samtliga personalåtgärder för befattningar. Denna lista är inte tillgänglig som standard. Om du vill aktivera funktionen går du till sidan **Delade personalparametrar** > fliken **Personalåtgärder** och anger alternativet **Aktivera befattningsåtgärder** som **Ja**.

## <a name="open-positions-tab"></a>Fliken Lediga befattningar

Fliken **Lediga befattningar** listar alla öppna befattningar. För att kunna visas i listan måste befattningar ha ett aktiveringsdatum idag eller tidigare, samt får inte ha någon medarbetartilldelning för tillfället.

> [!NOTE]
> Listan tar hänsyn till medarbetartilldelningen från och med idag. Alla befattningar som har medarbetartilldelning i framtiden fortsätter att visas i listan. När giltighetsdatumet för medarbetartilldelningen har nåtts tas befattningen emellertid bort från listan.

## <a name="expiring-records-tab"></a>Fliken Utgående poster

Fliken **Utgående poster** listar alla artiklar som har förfallit eller kommer att förfalla för medarbetarna i det företag som användaren är inloggad i. Följande artiklar visas i listan:

- **Intyg**
- **Identifiering**
- **Under prövning**
- **Kontroller**
- **Tester**

Om du vill ange om listan ska visa utgångna poster eller utgångna poster ska du på fliken **Personalparametrar** > fliken **Allmänt** ange en tidsram för antingen **Utgående poster** eller **Utgångna poster**. Datan på fliken **Utgående poster** kan visas för ett specifikt antal dagar. Om du till exempel vill visa listan med poster som går ut om 14 dagar ställer du in fältet **Antal dagar** som **14**.

> [!NOTE] 
> Om du ställer in tidsramen för **Utgångna poster** eller **Utgående poster** som **0** på sidan **Personalparametrar** visar listan inga av dessa poster.

## <a name="employees-tile"></a>Medarbetarpanel

I panelen **Medarbetare** visas en uppräkning av alla medarbetare som är anställda i det företag som användaren för tillfället är inloggad i. När du väljer panelen **Medarbetare** visas information om medarbetarna på en ny sida.

## <a name="contractors-tile"></a>Leverantörspanel

I panelen **Leverantörer** visas en uppräkning av alla leverantörer som är anställda i det företag som användaren för tillfället är inloggad i. När du väljer panelen **Leverantörer** visas information om leverantörerna på en ny sida.

## <a name="open-positions-tile"></a>Panelen Lediga befattningar

Panelen **Lediga befattningar** innehåller en sammanräkning av alla lediga befattningar. När du väljer panelen **Lediga befattningar** visas information om lediga befattningar. För att inkluderas i sammanställningen måste befattningar ha ett aktiveringsdatum idag eller tidigare, samt får inte ha någon medarbetartilldelning för tillfället.

> [!NOTE]
> Panelen tar hänsyn till medarbetartilldelningen från och med idag. Alla befattningar som har medarbetartilldelning i framtiden fortsätter att inkluderas i sammanställningen. När giltighetsdatumet för medarbetartilldelningen har nåtts tas befattningen emellertid bort från sammanställningen.

## <a name="approvals-tile"></a>Godkännandepanel

Panelen **Godkännanden** innehåller en antal arbetsflödesobjekt som väntar på godkännande från den aktuella användaren. När du väljer panelen **Godkännanden** visas en ny sida med information om arbetsflödesobjekten som kräver ditt godkännande.

## <a name="address-changes-tile"></a>Panel för adressändringar

Panelen **Adressändringar** innehåller en sammanställning av alla adressändringar som gjorts under det antal dagar som angetts på sidan **Personalparametrar**. När du väljer panelen **Adressändringar** visas informationen om adressändringar på en ny sida. I sidans övre högra hörn kan du också välja att **Inkludera framtida adressändringar** för att visa adressändringar som har ett framtida datum.

Mer information om hur du visar och hanterar adressändringar finns i [Visa och hantera adressändringar](hr-personnel-view-address-changes.md).
