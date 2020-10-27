---
title: Konfigurera virtuella Common Data Service-enheter
description: I det här avsnittet beskrivs hur du konfigurerar virtuella entiteter för Dynamics 365 Human Resources. Generera och uppdatera befintliga virtuella entiteter samt analysera genererade och tillgängliga entiteter.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959585"
---
# <a name="configure-common-data-service-virtual-entities"></a>Konfigurera virtuella Common Data Service-enheter

[!include [banner](includes/preview-feature.md)]

Dynamics 365 Human Resources är en virtuell datakälla i Common Data Service. Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Common Data Service och Microsoft Power Platform. Data för virtuella entiteter lagras inte i Common Data Service, men i appdatabasen. 

Om du vill aktivera CRUD åtgärder från personalenheter från Common Data Service måste du göra enheterna tillgängliga som virtuella entiteter i Common Data Service. På så sätt kan du utföra CRUD operationer från Common Data Service och Microsoft Power Platform på data i personal. Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.

## <a name="available-virtual-entities-for-human-resources"></a>Tillgängliga virtuella enheter för personal

Alla OData-entiteter (Open Data Protocol) i personal är tillgängliga som virtuella entiteter i Common Data Service. De är också tillgängliga i Power Platform. Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Common Data Service. Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.

Du kan visa listan med virtuella entiteter som är aktiverade i miljön och börja arbeta med entiteterna i [Power Apps](https://make.powerapps.com) i lösningen **virtuella Dynamics 365 personalenheter**.

![Virtuella Dynamics 365 personalenheter i Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Virtuella enheter jämfört med fysiska enheter

Virtuella enheter för personal är inte samma sak som de fysiska Common Data Service-enheter som har skapats för personal. De naturliga enheterna för personal genereras separat och underhålls i den HCM gemensamma lösningen i Common Data Service. Med fysiska enheter lagras data i Common Data Service och måste synkroniseras med appdatabasen för personal.

> [!NOTE]
> En lista över de naturliga Common Data Service-enheterna för personal finns i [Common Data Service-entiteter](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Ställ in

Följ dessa installationssteg för att aktivera virtuella enheter i miljön. 

### <a name="register-the-app-in-microsoft-azure"></a>Registrera appen i Microsoft Azure

Först måste du registrera programmet på Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna. Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Öppna [Microsoft Azure-portal](https://portal.azure.com).

2. I listan Azure-tjänster, välj **App-registreringar**.

3. Välj **Ny registrering**.

4. I fältet **Namn** ange ett beskrivande namn för appen. Till exempel **Dynamics 365 Human Resources virtuella enheter**.

5. I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.

6. Välj **Registrera**.

7. När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**. Anteckna **App-ID (klient)** för tillfället. Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.

9. I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.

10. Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.

11. Registrera hemlighetens värde. Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > Se till att du noterar hemlighetens värde just nu. Hemligheten visas aldrig igen när du har lämnat den här sidan.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>Installera appen Dynamics 365 HR Virtual Entity

Installera appen Dynamics 365 HR Virtual Entity i din Power Apps-miljö för att distribuera lösningspaketet för virtuell enhet till Common Data Service.

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.

3. I avsnittet **resurser** på sidan väljer du **Dynamics 365-appar**.

4. Välj åtgärden **Installera app**.

5. Välj **Dynamics 365 HR Virtual Entity**och välj **Nästa**.

6. Granska och markera det här alternativet om du vill godkänna tjänstvillkoren.

7. Välj **Installera**.

Installationen tar några minuter. När den är klar fortsätter du till nästa steg.

![Installera appen Dynamics 365 HR Virtual Entity från Power Platform administrationscentret](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>Konfigurera den virtuella datakällan för entiteten 

Nästa steg är att konfigurera datakällan för den virtuella enheten i Power Apps-miljön. 

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.

3. Välj **miljö-URL** i avsnittet **information** på sidan.

4. I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på appsidan.

5. På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Finance and Operations**.

6. Välj **resultat**.

7. Markera posten **Microsoft HR datakälla**.

8. Ange den information som krävs för konfigurationen av datakällan.

   - **Mål-URL**: en URL till din personal namnrymd.
   - **Klientorganisations-ID**: Azure Active Directory (Azure AD) klientorganisations-ID.
   - **AAD app-ID**: det app-ID (klient) som skapades för den app som är registrerat i Microsoft Azure-portalen. Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).
   - **Hemlighet för AAD app-ID**: klienthemligheten som skapades för den app som är registrerat i Microsoft Azure-portalen. Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

9. Välj **Spara och stäng**.

   ![Microsoft HR-datakälla](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a>Ge appbehörighet i Human Resources

Bevilja behörigheter för de två Azure AD-apparna i Human Resources:

- Appen som har skapats för din innehavare på Microsoft Azure-portalen
- Appen Dynamics 365 HR Virtual Entity installeras Power Apps-miljön 

1. I Human Resources, öppna sidan **Azure Active Directory-appar**.

2. Välj **Nytt** för att skapa en ny appost:

    - I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.
    - I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.
    - I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.

3. Välj **Nytt** för att skapa en andra appost:

    - **Klient-ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Namn**: Dynamics 365 HR Virtual Entity
    - I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.

## <a name="generate-virtual-entities"></a>Generera virtuella enheter

När installationsprogrammet är klart kan du välja vilka virtuella entiteter du vill generera och aktivera i din Common Data Service-instans.

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.

3. Välj **miljö-URL** i avsnittet **information** på sidan.

4. I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på sidan.

5. På sidan **Avancerad sökning** i listrutan **Sök efte** välj **Tillgängliga HR-enheter**.

6. Använd filteralternativen för att söka efter den eller de entiteter som du vill aktivera.

7. Välj en enhet i listan.

8. På sidan entitet ändrar du egenskapen **har genererats** till **Ja** för entiteten.

9. Spara och stäng enhetssidan.

> [!NOTE]
> Du kan generera flera virtuella entiteter samtidigt genom att använda sidan **ändra flera poster**. Markera flera poster på sidan och välj **Redigera** i menyfliksområdet. Du kan sedan ändra egenskapen **har genererats** för alla valda poster.

![Tillgängliga HR-entiteter](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> För att effektivisera processen med att generera virtuella enheter i framtida versioner sker processen på en sida i Human Resources.

## <a name="see-also"></a>Se även

[Vad är Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Enhetsöversikt](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Översikt över entitetsrelationer](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Skapa och redigera virtuella entiteter som innehåller data från en extern datakälla](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Vad är Power Apps-portaler?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Översikt över att skapa appar i Power Apps](https://docs.microsoft.com/powerapps/maker/)
