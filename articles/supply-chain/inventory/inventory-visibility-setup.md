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
ms.openlocfilehash: a49f35211f30cdb76104cc5be78f5b114320a228
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062660"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installera och konfigurera Lagersynlighet

[!include [banner](../includes/banner.md)]


I detta ämne beskrivs hur du installerar och tillägget för lagersynlighet för Microsoft Dynamics 365 Supply Chain Management.

Du måste använda Microsoft Dynamics Lifecycle Services (LCS) för att installera tillägget för lagersynlighet. LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Finance and Operations-appar.

Mer information finns i [Lifecycle Services, resurser](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Förutsättningar för Lagersynlighet

Innan du installerar Lagersynlighet måste du slutföra följande upgifter:

- Skaffa ett LCS implementeringsprojekt där minst en miljö har distribuerats.
- Kontrollera att kraven för att ställa in tillägg har slutförts. Information om dessa förutsättningar finns i [Tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Lagersynlighet kräver inte länkning av dubbelriktad skrivning.

> [!NOTE]
> Bland de länder och regioner som för närvarande stöds finns Kanada (CCA, ECA), USA (WUS, EUS), Europeiska unionen (NEU, WEU), Storbritannien (SUK, WUK) och Australien (EAU, SEAU), Japan (EJP, WJP) och Brasilien (SBR, SCUS).

Om du har några frågeställningar om dessa förutsättningar kontaktar du produktteamet för lagersynlighet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installera tillägget för Lagersynlighet

Innan du installerar tillägget registrerar du ett program och lägger till en klienthemlighet i Azure Active Directory (Azure AD) under ditt Azure-abonnemang. Instruktioner finns i [Registrera ett program](/azure/active-directory/develop/quickstart-register-app) och [Lägg till en klienthemlighet](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Se till att du noterar **ID för program (klient)**, **Klienthemlighet** och **ID öfr klientorganisation**, detta eftersom du behöver dem senare.

När du har registrerat ett program och lagt till en klienthelighet i Azure AD följer du dessa steg för att installera tillägget Lagersynlighet.

1. Logga in på [LCS](https://lcs.dynamics.com/Logon/Index).
1. Välj det projekt där miljön har distribuerats på startsidan.
1. Välj den miljö där du vill installera tillägget på projektsidan.
1. Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform-integrering**. Där kan du hitta namnet på Dataverse-miljön. Bekräfta att Dataverse miljönamnet är det som du vill använda för lagersynlighet.

    > [!NOTE]
    > För närvarande stöds endast Dataverse-miljöer som har skapats med hjälp av LCS. Om din Dataverse-miljö har skapats på något annat sätt (till exempel genom att använda Power Apps administratörscentret), och om den är länkad till din Supply Chain Management-miljö, måste du först kontakta produktteamet för Lagersynlighet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) om du vill åtgärda mappningsproblemet. Du kan sedan installera Lagersynlighet.

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
1. I avsnittet Dataverse, välj **Appar** i den vänstra navigeringen och kontrollera att **lagrets synlighet** Power Apps har installerats. Om avsnittet **Appar** inte finns kontaktar du produktteamet för Lagersynlighet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!TIP]
> Vi rekommenderar att du deltar i användargruppen Lagersynlighet information, där du kan hitta användbara guider, få tillgång till de senaste uppdateringarna och besvara eventuella frågor som du kan ha om hur du använder lagersynlighet. För att gå med, skicka e-post till produktteamet för lagersynlighet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) och inkludera Supply Chain Management miljö-ID.

> [!IMPORTANT]
> Om du har fler än en LCS-miljö kan du skapa olika Azure AD-program för varje miljö. Om du använder samma program-ID och klientorganisations-ID för att installera tillägget Lagersynligt för olika miljöer, uppstår ett tokenproblem för äldre miljöer. Endast det sista som installerades kommer att vara giltigt.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Avinstallera tillägget för lagersynlighet

För att avinstallera tillägget Lagersynlighet väljer du **Avinstallera** på LCS-sidan. Avinstallationen avslutar tillägget Lagersynlighet, tillägget avregistreras från LCS och eventuella tillfälliga data som lagras i datacachen för Lagersynlighet tas bort. Primära lagerdata som lagras i din Dataverse-prenumeration tas emellertid inte bort.

Om du vill avinstallera lagerdata som lagras i din Dataverse-prenumeration öppnar du [Power Apps](https://make.powerapps.com), väljer **Miljö** i navigeringsfältet och väljer sedan den Dataverse-miljö som är kopplad till din LCS-miljö. Gå sedan till **Lösningar** och ta bort följande fem lösningar i denna order:

1. Ankarlösning för programmet Lagersynlighet i Dynamics 365-lösningar
1. Lösningen Lagersynlighet för Dynamics 365 FNO SCM
1. Konfiguration för lagertjänst
1. Fristående Lagersynlighet
1. Baslösningen Lagersynlighet för Dynamics 365 FNO SCM

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
