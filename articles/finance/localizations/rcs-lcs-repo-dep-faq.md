---
title: Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)
description: I detta ämne finns information om den avskrivning av Microsoft Dynamics Lifecycle Services (LCS)-lagring som planerats som en del av sammanslagningen av den globala databasen för Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 68f1ed6a6d6bb0d15a81539da7f483ad71a4d696
ms.sourcegitcommit: 477efa4cb138f41d4f68bcd82552af3473bcc3d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2021
ms.locfileid: "7715240"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

Användningen av Microsoft Dynamics Lifecycle Services (LCS) som en lagringsdatabas för elektroniska rapporteringskonfigurationer (ER) håller på att avskrivas. Denna avskrivning kommer att innefatta följande ändringar:

- Microsoft-framställda konfigurationer som används i Microsoft Dynamics 365-program kommer inte längre att publiceras i biblioteket för gemensamma tillgångar i LCS. I stället kommer de endast att publiceras via den globala RCS-databasen. Konfigurationer för Dynamics AX 2012 kommer emellertid att fortsätta att publiceras i biblioteket för gemensamma tillgångar i LCS ända tills supportlivscykeln för AX 2012 avslutas.
- De funktioner som gör att du kan överföra konfigurationer till projekttillgångsbiblioteket i LCS från Finance and Operations-appar samt från RCS kommer att avskrivas. Du kommer emellertid fortfarande att kunna använda webbläsaren i LCS för att överföra konfigurationer till projekttillgångsbiblioteket. Därför kommer du fortfarande att kunna lägga till konfigurationer i LCS så att dessa kan inkluderas i lösningspaket.
- Importen av konfigurationer från LCS kommer att vara fortsatt tillgänglig och stödjas i Finance and Operations-appar samt i RCS, åtminstone under en viss tid. I slutändan kommer funktionen emellertid att avskrivas. (Det exakta datumet för avskrivning kommer att meddelas senare.)

## <a name="deprecation-notice"></a>Meddelande om avskrivning

Avskrivning av användning av LCS som lagring har kommunicerats i [Borttagna eller inaktuella funktioner i Dynamics 365 Finance - LCS-avskrivningsmeddelande](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Det planerade slutdatumet är 1 april 2022.

## <a name="key-features"></a>Nyckelfunktioner

- Använd RCS om du vill skapa och redigera ER-konfigurationer och globaliseringsfunktioner.
- Push-konfigurationer direkt från RCS-designern till ett anslutet program, t.ex. en Dynamics 365 Finance miljö, så att du snabbt kan göra och testa ändringar i dina konfigurationer.
- Centraliserad lagring, delning och hantering av livscykeln för både ER-konfigurationer och globaliseringsfunktioner via den globala databasens centraliserade lagring.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Riktlinjer för engångs- och pågående åtgärder

I det här avsnittet beskrivs en uppsättning steg som måste utföras en gång. Det beskriver även steg som måste utföras regelbundet efteråt.

### <a name="one-time-action"></a>Åtgärd vid ett enstaka tillfälle

Importera alla erforderliga konfigurationer från LCS till RCS och publicera dem sedan från RCS till den globala databasen. Om du använder projektspecifika tillgångsbibliotek för att lagra härledda konfigurationer i LCS måste följande steg genomföras när LCS fortfarande är tillgängligt.

1. Om ingen RCS-instans redan finns tillgänglig kan du tillhandahålla en. Mer information finns i [RCS-översikten](rcs-overview.md).
2. I den tillhandahållna RCS-instansen registrerar du lämplig LCS-databas för alla LCS-projekt i tillgångsbiblioteket som innehåller härledda ER-konfigurationer.
3. Importera ER-konfigurationerna från LCS-databaserna till RCS. Mer information finns i [Importera konfigurationer från LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Om den globala databasen inte tillhandahålls automatiskt registrerar du den i RCS.
5. Överför alla härledda konfigurationer från den aktuella RCS-instansen till den globala databasen. Använd funktionen **Konfigurationspaket** som hjälp vid överföringen. Mer information finns i [global lagringsplattsuppladdning för RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>Framöver

Använd de visuella designersna i RCS i följande syften:

- Utöka mallarna som tillhandahålls av Microsoft.
- Skapa nya konfigurationer som din organisation behöver.
- Anpassa globaliseringsfunktioner för elektronisk fakturering och beräkningstjänsten för moms.

Använd globaliseringsdatabasen i följande syften:

- Få åtkomst till Microsoft-producerade konfigurationer och globaliseringsfunktioner.
- Överför konfigurationer som du har skapat eller utvidgat till den globala lagringsdatabasen, och dela dem i hela organisationens Dynamics 365-programmiljöer eller med externa organisationer. Mer information finns i [Skapa ER-konfiguration i RCS och ladda upp till global lagringsplats](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Innebär den här ändringen att LCS inte kan användas som central lagring för konfigurationer?

Ja. De funktioner som gör att du kan ladda upp konfigurationer till projekttillgångsbiblioteket i LCS från Finance and Operations-appar kommer att avskrivas. Du kommer emellertid fortfarande att kunna använda webbläsaren i LCS för att överföra konfigurationer till projekttillgångsbiblioteket efter behov.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Jag trodde att RCS var en ersättningsdatabas för import av globala mallfiler. Jag tror inte att det används för att lagra konfigurationer. Vilket är korrekt?

RCS är en designtjänst som används för att skapa och redigera ER-konfigurationer. RCS har sin egen databas som kallas för den globala databasen. Denna databas används för att lagra konfigurationer som skapas i RCS. När LCS har avskrivits som lagring kommer den globala databasen att vara den enda källan för Microsoft-konfigurationer. Du måste utföra en viss åtgärd vid ett enda tillfälle för att importera alla konfigurationer som du behöver från LCS till RCS och sedan publicera dem från RCS till den globala databasen.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Utan LCS, vad är det föreslagna sättet att lagra konfigurationer så att konfigurationerna "testa" och "produktion" enkelt kan hanteras och överföras?

RCS använder ett koncept med ett *anslutet program*. Ett anslutet program bildar en anslutning mellan RCS och alla instanser av Finance and Operations-program. Eftersom RCS kan användas för redigering av konfigurationer kan det anslutna programmet användas för att flytta konfigurationerna direkt från designern till Finance and Operations-programmiljöer. Du kan därför snabbt ändra och testa dina konfigurationer istället för att behöva gå igenom LCS-lagring på projektnivå.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Finns det några exempel som visar inställningar och hantering?

Det finns inga exempel, men du kan utföra stegen tidigare i det här avsnittet i syfte att flytta dina konfigurationer till den globala RCS-databasen.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>Är RCS en förutsättning för att konfigurera elektronisk rapportering?

Ja. RCS innehåller funktioner som stöder installationen av globaliseringsfunktioner som används av globaliseringstjänster som elektronisk fakturering och skatteberäkningstjänsten. Tjänsten har dock samma visuella designerfunktion som låter dig utöka eller skapa nya ER-konfigurationer. RCS innehåller även livscykelhantering för både ER-konfigurationer och globaliseringsfunktioner.

### <a name="which-regions-can-rcs-be-deployed-in"></a>Vilka regioner kan RCS distribueras i?

RCS är tillgängligt i följande Azure-regioner:

- USA
- Indien
- Frankrike
- Europa

Mer information om produktsupport finns i [översikten över Globaliseringstjänster för Dynamics](globalization-services-overview.md). För information om geografiskt stöd, se [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/rcs/D365Productavailabilityguide).

### <a name="whats-the-cost-of-using-rcs"></a>Vad är kostnaden för att använda RCS?

RCS och globaliseringsdatabasen tillhandahålls gratis som en del av befintliga Finance and Operations applicenser. Inga separata kostnader är förknippade med att använda RCS-designtjänsten eller att lagra konfigurationer i det globala arkivet. Det finns för närvarande ingen gräns för antalet konfigurationer eller anslutna program.
