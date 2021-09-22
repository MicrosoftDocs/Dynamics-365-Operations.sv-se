---
title: Installera tillägget för lagersynlighet
description: I detta ämne beskrivs hur du installerar och tillägget för lagersynlighet för Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2b85f533a3318701ed08857b899cf9bdd103863
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474830"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installera och konfigurera Lagersynlighet

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

I detta ämne beskrivs hur du installerar och tillägget för lagersynlighet för Microsoft Dynamics 365 Supply Chain Management.

Du måste använda Microsoft Dynamics Lifecycle Services (LCS) för att installera tillägget för lagersynlighet. LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Finance and Operations-appar.

Mer information finns i [Lifecycle Services, resurser](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Förutsättningar för Lagersynlighet

Innan du installerar Lagersynlighet måste du slutföra följande upgifter:

- Skaffa ett LCS implementeringsprojekt där minst en miljö har distribuerats.
- Kontrollera att kraven för att ställa in tillägg har slutförts. Information om dessa förutsättningar finns i [Tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Lagersynlighet kräver inte länkning av dubbelriktad skrivning.
- Kontakta produktteamet för Lagersynlighet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få följande erforderliga filer:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (om versionen av Supply Chain Management som du kör är tidigare än version 10.0.18)

> [!NOTE]
> Bland de länder och regioner som för närvarande stöds finns Kanada (CCA, ECA), USA (WUS, EUS), Europeiska unionen (NEU, WEU), Storbritannien (SUK, WUK) och Australien (EAU, SEAU), Japan (EJP, WJP) och Brasilien (SBR, SCUS).

Om du har några frågor som rör dessa förutsättningar kontaktar du produktteamet för Lagersynlighet.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Ställ in Dataverse

Om du vill konfigurera Dataverse så att det kan användas med Lagersynlighet använder du verktyget Package Deployer för att distribuera paketet för Lagersynlighet. Följande delgrupper beskriver hur du slutför respektive uppgift.

> [!NOTE]
> För närvarande stöds endast Dataverse-miljöer som har skapats med hjälp av LCS. Om din Dataverse-miljö har skapats på något annat sätt (till exempel genom att använda administratörscentret för Power Apps), och om den är länkad till din Supply Chain Management-miljö, måste du först kontakta produktteamet för Lagersynlighet om du vill åtgärda mappningsproblemet. Du kan sedan installera Lagersynlighet.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrera från en gammal version av Dataverse-lösningen

Om du har installerat en äldre version av lösningen Lagersynlighet för Dataverse ska du använda dessa anvisningar för att uppdatera din version. Det finns två fall:

- **Fall 1:** Om du konfigurerar Dataverse genom att importera `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip`-lösningen följer du dessa steg:

    1. Hämta följande tre filer:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Importera `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` och `InventoryServiceBase_managed.cab` till Dataverse genom att följa dessa steg:

        1. Öppna URL-adressen för din Dataverse miljö.
        1. Öppna sidan **Lösningar**.
        1. Välj **Importera**.

    1. Använd verktyget Package Deployer för att distribuera `InventoryServiceApplication.PackageDeployer.zip`-paketet. Instruktioner finns i avsnittet [Använd verktyget Package Deployer för att distribuera paketet](#deploy-package) senare i det här avsnittet.

- **Fall 2:** Om du konfigurerat Dataverse genom att använda verktyget Package Deployer innan du installerat det äldre `.*PackageDeployer.zip`-paketet, hämtar du `InventoryServiceApplication.PackageDeployer.zip` och uppdaterar. Instruktioner finns i avsnittet [Använd verktyget Package Deployer för att distribuera paketet](#deploy-package).

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Använd verktyget Package Deployer för att distribuera paketet

1. Installera utvecklarverktyget enligt beskrivningen i [Hämta verktyg från NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Ta bort spärren för den `InventoryServiceApplication.PackageDeployer.zip`-fil som du hämtade från Teams-gruppen genom att följa stegen nedan:

    1. Markera och håll inne (eller högerklicka på) filen, och välj sedan **Egenskaper**.
    1. I dialogrutan **Egenskaper**, på fliken **Allmänt**, letar du upp avsnittet **Säkerhet**, väljer **Ta bort spärr** och tillämpar ändringen. Om det inte finns något **Säkerhets** avsnitt på fliken **Allmänt** är filen inte spärrad. Gå i så fall vidare till nästa steg.

    ![Ta bort spärren för den hämtade filen](media/unblock-file.png "Ta bort spärren för den hämtade filen")

1. Packa upp `InventoryServiceApplication.PackageDeployer.zip` för att hitta följande artiklar:

    - `InventoryServiceApplication`-mapp
    - `[Content_Types].xml`-fil
    - `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`-fil

1. Kopiera var och en av dessa artiklar till `.\Tools\PackageDeployment`-katalogen. (Denna katalog skapades när du installerade utvecklingsverktygen.)
1. Kör `.\Tools\PackageDeployment\PackageDeployer.exe` och följ anvisningarna på skärmen för att importera lösningarna.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installera tillägget för Lagersynlighet

Innan du installerar tillägget registrerar du ett program och lägger till en klienthemlighet i Azure Active Directory (Azure AD) under ditt Azure-abonnemang. Instruktioner finns i [Registrera ett program](/azure/active-directory/develop/quickstart-register-app) och [Lägg till en klienthemlighet](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Se till att du noterar **ID för program (klient)**, **Klienthemlighet** och **ID öfr klientorganisation**, detta eftersom du behöver dem senare.

När du har registrerat ett program och lagt till en klienthelighet i Azure AD följer du dessa steg för att installera tillägget Lagersynlighet.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index).
1. Välj det projekt där miljön har distribuerats på startsidan.
1. Välj den miljö där du vill installera tillägget på projektsidan.
1. Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform-integrering**. Där kan du hitta namnet på Dataverse-miljön.
1. I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.

    ![Sidan Miljö i LCS](media/inventory-visibility-environment.png "Sidan Miljö i LCS")

1. Välj länken **installera ett nytt tillägg**. En lista med tillgängliga tillägg visas.
1. I listan väljer du **Lagersynlighet**.
1. Ange följande fält för din nya miljö:

    - **ID för AAD-program (klient)** – Ange det ID för Azure AD-programmet som du skadade och noterade tidigare.
    - **ID för AAD-klientorganisation** –Ange det ID för klientorganisation som du antecknade tidigare.

    ![Konfigurera tilläggssida](media/inventory-visibility-setup.png "Konfigurera tilläggssida")

1. Godkänn villkoren genom att markera kryssrutan **Villkor**.
1. Välj **Installera**. Tilläggets status visas som **Installerar**. När installationen är slutförd uppdaterar du sidan. Statusvärdet ska ändras till **Installerad**.

> [!IMPORTANT]
> Om du har fler än en LCS-miljö kan du skapa olika Azure AD-program för varje miljö. Om du använder samma program-ID och klientorganisations-ID för att installera tillägget Lagersynligt för olika miljöer, uppstår ett tokenproblem för äldre miljöer. Endast det sista som installerades kommer att vara giltigt.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Avinstallera tillägget för lagersynlighet

För att avinstallera tillägget Lagersynlighet väljer du **Avinstallera** på LCS-sidan. Avinstallationen avslutar tillägget Lagersynlighet, tillägget avregistreras från LCS och eventuella tillfälliga data som lagras i datacachen för Lagersynlighet tas bort. Primära lagerdata som lagras i din Dataverse-prenumeration tas emellertid inte bort.

Om du vill avinstallera lagerdata som lagras i din Dataverse-prenumeration öppnar du [Power Apps](https://make.powerapps.com), väljer **Miljö** i navigeringsfältet och väljer sedan den Dataverse-miljö som är kopplad till din LCS-miljö. Gå sedan till **Lösningar** och ta bort följande fem lösningar:

- Ankarlösning för programmet Lagersynlighet i Dynamics 365-lösningar
- Lösningen Lagersynlighet för Dynamics 365 FNO SCM
- Konfiguration för lagertjänst
- Fristående Lagersynlighet
- Baslösningen Lagersynlighet för Dynamics 365 FNO SCM

När du har raderat dessa lösningar kommer de data som lagras i tabeller också att raderas.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Konfigurera Lagersynlighet i Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Distribuera integreringspaketet för Lagersynlighet

Om du kör Supply Chain Management version 10.0.17 eller tidigare, kontakta supportteamet för inventeringssyn på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få paketfilen. Distribuera sedan paketet i LCS.

> [!NOTE]
> Om ett versionsfel inträffar under distributionen måste du manuellt importera X++-projektet till din utvecklingsmiljö. Skapa sedan det paket som kan distribueras i din utvecklingsmiljö och distribuera det i din produktionsmiljö.
>
> Koden ingår i med Supply Chain Management version 10.0.18. Om du kör den versionen eller senare behöver du inte distribuera den.

Kontrollera att följande funktioner är aktiverat i din Supply Chain Management-miljö. (Som standard är de aktiverade.)

| Funktionsbeskrivning | Kodversion | Växla klass |
|---|---|---|
| Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Konfigurera integrering av lagersynlighet

När du har installerat tillägget kan du förbereda ditt Supply Chain Management-system så att du kan arbeta med det genom att göra följande.

1. I Supply Chain Management, öppna arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera följande funktioner:
    - *Integrering av Lagersynlighet* – obligatoriskt.
    - *Integrering av Lagersynlighet med reservationsmotbokning* – rekommenderat men valfritt. Kräver version 10.0.22 eller senare. Mer information finns i [Reservationer för Lagersynlighet](inventory-visibility-reservations.md).

1. Gå till **Lagerstyrning \> Konfigurera \> Parametrar för integrering av lagersynlighet**.
1. Öppna fliken **Allmänt** och gör följande inställningar:
    - **Slutpunkt för lagersynlighet** – ange URL för miljön där du kör Lagersynlighet. Mer information finns i [Hitta tjänsteslutpunkten](inventory-visibility-configuration.md#get-service-endpoint).
    - **Maximalt antal poster i en enskild begäran** – ställ in det maximala antalet poster som ska ingå i en enskild begäran. Du måste ange ett positivt heltal som är mindre än eller lika med 1 000. Standardvärdet är 512. Vi rekommenderar starkt att du behåller standardvärdet om du inte har fått några anvisningar från Microsofts support eller är säker på att du behöver ändra det.

1. Om du har aktiverat den valfria funktionen *Integrering av Lagersynlighet med reservationsmotbokning* öppnar du fliken **Reservationsmotbokning** och gör följande inställningar:
    - **Aktivera reservationsmotbokning** – ställ in till *Ja* om du vill aktivera den här funktionen.
    - **Modifierare för reservationsmotbokning** – välj det lagertransaktionsstatus som motbokar reservationer som gjorts i Lagersynlighet. Den här inställningen avgör vilken orderbearbetningsfas som utlöser motbokningar. Fasen spåras med hjälp av orderns lagertransaktionsstatus. Välj en av följande:
        - *För order* – För statusen *vid transaktion* skickar en order en begäran om motbokning när den skapas. Motbokningskvantiteten är kvantiteten för den skapade ordern.
        - *Reservera* – För statusen *Reservera beställd transaktion* skickar en order en begäran om motbokning när den reserveras, plockas, följesedelsbokförs eller faktureras. Denna begäran utlöses bara en gång - för det första steget när den omstämda processen inträffar. Motbokningskvantiteten är den kvantitet där lagertransaktionens status ändras från *Har beställts* till *Reserverat beställt* (eller senare status) på motsvarande orderrad.

1. Gå till **Lagerhantering \> Periodisk \> Integrering av lagerhantering** och aktivera jobbet. Alla lagerändringshändelser från Supply Chain Management bokförs nu i Lagersynlighet.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
