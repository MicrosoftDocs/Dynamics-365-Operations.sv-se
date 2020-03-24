---
title: Kopiera en instans
description: Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bb363369994d99f358be0c23cdaf1dbc80b644e5
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092302"
---
# <a name="copy-an-instance"></a>Kopiera en instans

Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge. Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.

Om du vill kopiera en instans måste du säkerställa följande:

- Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.

- De miljöer som du kopierar från och till måste finnas i samma region. Du kan inte kopiera mellan regioner.

- Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.

- När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft PowerApps-miljö. Information om hur du kopierar element i en PowerApps-miljö finns i [kopiera en miljö](https://docs.microsoft.com/power-platform/admin/copy-environment). Den PowerApps-miljö som du vill skriva över måste vara en miljö i begränsat läge. Du måste vara global innehavaradministratör om du vill ändra en PowerApps-produktionsmiljö till en miljö i begränsat läge. Mer information om hur du ändrar PowerApps-miljö finns i [Växla en instans](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Effekter av att kopiera personaldatabasen

Följande händelser inträffar när du kopierar en personaldatabas:

- När du kopierar processen raderas den befintliga databasen i målmiljön. När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.

- Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.

- Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan. Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.

- Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​ Därför kan administratörsanvändaren ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.

- Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.

## <a name="copy-the-human-resources-database"></a>Kopiera databasen för personal

Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera PowerApps-miljön.

> [!WARNING]
> När du kopierar en instans raderas databasen i målinstansen. Målinstansen är inte tillgänglig under denna process.

1. Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.

2. I LCS-projektet väljer du fliken **-hantering for Personal**.

3. Markera den instans du vill kopiera och välj sedan **kopiera**.

4. I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**. Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.

   ![[Markera instansen som ska skrivas över](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.

   ![[Välj Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Markera den PowerApps-miljö du vill kopiera och välj sedan **kopiera**.

7. När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Common Data Service-integreringen. Mer information och anvisningar finns i [Konfigurera Common Data Service-integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Dataelement och status

Följande dataelement kopieras inte när du kopierar en personalinstans:

- E-postadresser i **LogisticsElectronicAddress**-registret

- Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory**och **BatchConstraintHistory**

- SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret

- SMTP-relayservern i **SysEmailParameters**-registret

- Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**

- Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**

- Dokumentbilagor i DocuValue-registret. Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön

- Anslutningssträngen i registret **PersonnelIntegrationConfiguration**

Vissa av elementen kopieras inte eftersom de är miljöspecifika. Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**. Andra element kopieras inte på grund av supportärendens volym. Dubbletter av e-postmeddelanden kan t.ex. skickas eftersom SMTP fortfarande är aktiverat i miljön i begränsat läge för användargodkännande kan ogiltiga integrationsmeddelanden skickas eftersom batch-jobb fortfarande är aktiverade och användarna kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.

Dessutom ändras följande statusvärden när du kopierar en instans:

- Alla användare utom administratören har **inaktiverats**.

- Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.

## <a name="environment-admin"></a>Miljöadministration

Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön. Kontrollera att du är administratör i målmiljön innan du kopierar en instans. Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.

Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge. Administratörer kan återaktivera användare om det behövs.
