---
title: Kopiera en instans
description: Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6cb8050980b9b54480d09a59379430cd229ff141
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801105"
---
# <a name="copy-an-instance"></a>Kopiera en instans

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Du kan använda Microsoft Dynamics Lifecycle Services (LCS) för att kopiera en Microsoft Dynamics 365 Human Resources-databas till en miljö i begränsat läge. Om du har en annan miljö med begränsat läge kan du även kopiera databasen från den miljön till en miljö med begränsat läge.

Om du vill kopiera en instans bör du tänka på följande:

- Den personalinstans som du vill skriva över måste vara en miljö i begränsat läge.

- De miljöer som du kopierar från och till måste finnas i samma region. Du kan inte kopiera mellan regioner.

- Du måste vara administratör i målmiljön för att du ska kunna logga in på den efter att du har kopierat instansen.

- När du kopierar databasen för Personal kopierar du inte de element (appar eller data) som finns i en Microsoft Power Apps-miljö. Information om hur du kopierar element i en Power Apps-miljö finns i [kopiera en miljö](https://docs.microsoft.com/power-platform/admin/copy-environment). Den Power Apps-miljö som du vill skriva över måste vara en miljö i begränsat läge. Du måste vara global innehavaradministratör om du vill ändra en Power Apps-produktionsmiljö till en miljö i begränsat läge. Mer information om hur du ändrar Power Apps-miljö finns i [Växla en instans](https://docs.microsoft.com/dynamics365/admin/switch-instance).

- Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Dataverse, måste du återställa anpassade fält till Dataverse-register. Se [tillämpa anpassade fält på Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>Effekter av att kopiera personaldatabasen

Följande händelser inträffar när du kopierar en personaldatabas:

- När du kopierar processen raderas den befintliga databasen i målmiljön. När kopieringsprocessen är klar kan du inte återställa den befintliga databasen.

- Målmiljön kommer inte att vara tillgänglig förrän kopieringsprocessen har slutförts.

- Dokument i Microsoft Azure Blob-lagring kopieras inte från en miljö till en annan. Därför kopieras inte de kopplade dokumenten och mallarna och de blir kvar i källmiljön.

- Alla användare förutom administratören och andra interna användarkonton kommer inte att vara tillgängliga.​ Administratörsanvändaren kan ta bort eller dölja data innan andra användare tillåts tillbaka till systemet.

- Administratörsanvändaren måste göra obligatoriska konfigurationsändringar, t.ex. återansluta integreringsslutpunkter för specifika tjänster eller URL:er.

## <a name="copy-the-human-resources-database"></a>Kopiera databasen för personal

Om du vill slutföra den här uppgiften kopierar du först en instans och loggar sedan in på Microsoft Power Platform administrationscenter för att kopiera Power Apps-miljön.

> [!WARNING]
> När du kopierar en instans raderas databasen i målinstansen. Målinstansen är inte tillgänglig under denna process.

1. Logga in på LCS och välj det LCS-projekt som innehåller den instans som du vill kopiera.

2. I LCS-projektet väljer du fliken **-hantering for Personal**.

3. Markera den instans du vill kopiera och välj sedan **kopiera**.

4. I åtgärdsfönstret **Kopiera en instans** välj instansen som ska skrivas över och välj sedan **Kopiera**. Vänta tills värdet på fältet **Kopieringsstatus** uppdateras till **Slutförd**.

   ![[Välj instans som ska skrivas över](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Välj **Power Platform** och logga in på administrationscenter för Microsoft Power Platform.

   ![[Välj Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Markera den Power Apps-miljö du vill kopiera och välj sedan **kopiera**.

7. När kopieringsprocessen har slutförts loggar du in på målinstansen och aktiverar Dataverse-integreringen. Mer information och anvisningar finns i [Konfigurera Dataverse-integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Dataelement och status

Följande dataelement kopieras inte när du kopierar en personalinstans:

- E-postadresser i **LogisticsElectronicAddress**-registret

- Historiken för batchjobb i tabellerna **BatchJobHistory**, **BatchHistory** och **BatchConstraintHistory**

- SMTP-lösenordet (Simple Mail Transfer Protocol) i **SysEmailSMTPPassword**-registret

- SMTP-relayservern i **SysEmailParameters**-registret

- Utskriftshanteringsinställningar i registren **PrintMgmtSettings** och **PrintMgmtDocInstance**

- Miljöspecifika poster i registren **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** och **BatchServerGroup**

- Dokumentbilagor i DocuValue-registret. Dessa bifogade filer innehåller alla Microsoft Office-mallar som har skrivits över i källmiljön

- Anslutningssträngen i registret **PersonnelIntegrationConfiguration**

Vissa av elementen kopieras inte eftersom de är miljöspecifika. Exempel innehåller posterna **BatchServerConfig** och **SysCorpNetPrinters**. Andra element kopieras inte på grund av supportärendens volym. Exempel:

- Dubbla e-postmeddelanden kan skickas eftersom SMTP fortfarande är aktiverat i den begränsade miljön för användar godkännande.

- Ogiltiga integrationsmeddelanden kan skickas eftersom batch-jobb fortfarande är aktiverade.

- Användare kan aktiveras innan administratörer kan utföra rensningsåtgärder efter uppdatering.

Dessutom ändras följande statusvärden när du kopierar en instans:

- Alla användare utom administratören har **inaktiverats**.

- Alla batchjobb, förutom vissa systemjobb, ställs in på **undanhålla**.

## <a name="environment-admin"></a>Miljöadministration

Alla användare i målmiljön i begränsat läge, inklusive administratörer, ersätts av användarna i källmiljön. Kontrollera att du är administratör i källmiljön innan du kopierar en instans. Om du inte är det kan du inte logga in till målmiljön efter att kopieringen har slutförts.

Alla användare som inte är administratörer i målmiljön i begränsat läge är inaktiverade för att förhindra oönskade inloggningar i miljön i begränsat läge. Administratörer kan återaktivera användare om det behövs.

## <a name="apply-custom-fields-to-dataverse"></a>Tillämpa anpassade fält på Dataverse

Om du kopierar en instans till sandbox-miljön och vill integrera sandbox-miljön med Dataverse, måste du återställa anpassade fält till Dataverse-register.

Utför följande steg för varje anpassat fält som visas i Dataverse-register:

1. Gå till det anpassade fältet och välj **Redigera**.

2. Avmarkera fältet **aktiverad** för varje cdm_*-entitet som det anpassade fältet är aktiverat på.

3. Välj **Verkställ ändringar**.

4. Välj **Redigera** igen.

5. Markera fältet **aktiverad** för varje cdm_*-entitet som det anpassade fältet är aktiverat på.

6. Välj **Verkställ ändringar**.

Avmarkerar, tillämpar ändringar, markerar om och återanvänder ändringar gör att schemat uppdateras i Dataverse för att inkludera de anpassade fälten.

Mer information om anpassade fält finns i [Skapa och arbeta med anpassade fält](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).

## <a name="see-also"></a>Se även

[Reservera Personal](hr-admin-setup-provision.md)</br>
[Ta bort en instans](hr-admin-setup-remove-instance.md)</br>
[Uppdatera process](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]