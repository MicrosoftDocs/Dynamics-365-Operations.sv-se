---
title: Konfigurera virtuella Dataverse-register
description: I det här avsnittet visas hur du konfigurerar, genererar och uppdaterar befintliga virtuella tabeller samt analyserar genererade och tillgängliga tabeller för Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7f4d3770c754d2a7974d17fc7c40462ac8fc642
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691426"
---
# <a name="configure-dataverse-virtual-tables"></a>Konfigurera virtuella Dataverse-register


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources är en virtuell datakälla i Microsoft Dataverse. Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Dataverse och Microsoft Power Platform. Data för virtuella register lagras inte i Dataverse utan i programdatabasen.

Om du vill aktivera CRUD-åtgärder i Personal-entiteter från Dataverse måste du göra entiteterna tillgängliga som virtuella register i Dataverse. På så sätt kan du utföra CRUD operationer från Dataverse och Microsoft Power Platform på data i personal. Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.

> [!NOTE]
> Personal-entiteter motsvarar Dataverse-register. Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Tillgängliga virtuella register för Personal

Alla OData-entiteter (Open Data Protocol) i Personal är tillgängliga som virtuella register i Dataverse. De är också tillgängliga i Power Platform. Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Dataverse. Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.

Du kan visa listan med virtuella register som är aktiverade i miljön och börja arbeta med registren i [Power Apps](https://make.powerapps.com), i lösningen **Virtuella personalregister för Dynamics 365**.

![Virtuella personalregister för Dynamics 365 i Power Apps.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Virtuella register kontra inbyggda register

Virtuella register Personal är inte samma sak som de inbyggda Dataverse-register som har skapats för Personal. 

De inbyggda registren för Personal genereras separat och underhålls i den gemensamma HCM-lösningen i Dataverse. Med inbyggda register lagras data i Dataverse och måste synkroniseras med programdatabasen för Personal.

> [!NOTE]
> En lista över de inbyggda Dataverse-registren för Personal finns i [Dataverse-register](./hr-developer-entities.md).

## <a name="setup"></a>Ställ in

Följ dessa installationssteg för att aktivera virtuella register i din miljö.

### <a name="enable-virtual-tables-in-human-resources"></a>Aktivera virtuella register i Personal

Först måste du aktivera virtuella register i arbetsytan **Funktionshantering**.

1. I Personal, välj **Systemadministration**.

2. Välj panelen **funktionshantering**.

3. Välj **Stöd för virtuella register för Personal i Dataverse** och sedan **Aktivera**.

Mer information om att aktivera och inaktivera funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrera appen i Microsoft Azure

Du måste registrera din Human Resource-instans i Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna. Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](/azure/active-directory/develop/quickstart-register-app).

1. Öppna [Microsoft Azure-portal](https://portal.azure.com).

2. I listan Azure-tjänster, välj **App-registreringar**.

3. Välj **Ny registrering**.

4. I fältet **Namn** ange ett beskrivande namn för appen. Till exempel **Virtuella register för Dynamics 365 Human Resources**.

5. I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.

6. Välj **Registrera**.

7. När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**. Anteckna **App-ID (klient)** för tillfället. Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.

9. I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.

10. Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.

11. Registrera hemlighetens värde från egenskapen **Värde** för registret. Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Se till att du noterar hemlighetens värde just nu. Hemligheten visas aldrig igen när du har lämnat den här sidan.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Installera appen Dynamics 365 HR Virtual Table

Installera appen Dynamics 365 HR Virtual Table i din Power Apps-miljö för att distribuera lösningspaketet för virtuellt register till Dataverse.

1. I Personal öppnar du sidan **Microsoft Dataverse-integrering**.

2. Välj fliken **Virtuella register**.

3. Välj **Installera program för virtuellt register**.

### <a name="configure-the-virtual-table-data-source"></a>Konfigurera den virtuella datakällan för register

Nästa steg är att konfigurera datakällan för det virtuella registret i Power Apps-miljön.

1. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2. I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.

3. Välj **miljö-URL** i avsnittet **information** på sidan.

4. I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på appsidan.

5. På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Ekonomi och Drift**.

   > [!NOTE]
   > Installationen av det virtuella registerprogrammet från föregående inställningssteg kan ta några minuter. Om **Konfiguration av virtuella enhetens datakälla i Ekonomi och Drift** inte är tillgängligt i listan ska du vänta en minut och sedan uppdatera listan.

6. Välj **resultat**.

7. Markera posten **Microsoft HR datakälla**.

8. Ange den information som krävs för konfigurationen av datakällan:

   - **Mål-URL**: en URL till din personal namnrymd. Formatet för mål-URL:en är:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Exempel:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Se till att du tar med "**/**"-tecknet i slutet av URL:en för att undvika att få ett fel.

     >[!NOTE]
     >URL-måladressen avgör vilken personalmiljö som virtuella tabeller refererar till för data. Om du skapar en sandbox-miljö genom att skapa en kopia av din produktionsmiljö ska du uppdatera detta värde till namnrymdens URL för den nya sandbox-miljön. På så sätt ser du till att de virtuella registren är anslutna till data i sandbox-miljön istället för att fortsätta referera till produktionsmiljön.

   - **Klientorganisations-ID**: Azure Active Directory (Azure AD) klientorganisations-ID.

   - **AAD app-ID**: det app-ID (klient) som skapades för dett programsom är registrerat i Microsoft Azure-portalen. Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Hemlighet för AAD app-ID**: klienthemligheten som skapades för dett programsom är registrerat i Microsoft Azure-portalen. Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Microsoft HR-datakälla.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Välj **Spara och stäng**.

### <a name="grant-app-permissions-in-human-resources"></a>Ge appbehörighet i Personal

Bevilja behörigheter för de två Azure AD-apparna i Personal:

- Appen som har skapats för din innehavare på Microsoft Azure-portalen
- Appen Dynamics 365 HR Virtual Table installeras i Power Apps-miljön 

1. I Personal, öppna sidan **Azure Active Directory-appar**.

2. Välj **Nytt** för att skapa en ny appost:

    - I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.
    - I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.
    - I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.

3. Välj **Nytt** för att skapa en andra appost:

    - **Klient-ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Namn**: Dynamics 365 HR Virtual Table
    - I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.

## <a name="generate-virtual-tables"></a>Generera virtuella register

När installationsprogrammet är slutfört kan du välja vilka virtuella register du vill generera och aktivera i din Dataverse-instans.

1. I Personal öppnar du sidan **Microsoft Dataverse-integrering**.

2. Välj fliken **Virtuella register**.

> [!NOTE]
> Växlingsknappen **Aktivera virtuella register** anges automatiskt som **Ja** när alla erforderliga inställningar har gjorts. Om växlingsknappen är inställd på **Nej** bör du granska stegen i de tidigare avsnitten i det här dokumentet så att alla nödvändiga inställningar är slutförda.

3. Välj det eller de register du vill generera i Dataverse.

4. Välj **generera/uppdatera**.

![Dataverse-integrering.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Kontrollera registrets genereringsstatus

Virtuella register genereras i Dataverse genom en asynkron bakgrundsprocess. Uppdateringar av processvisningen i åtgärdscentret. Information om processen, inklusive felloggar, visas på sidan **Processautomatiseringar**.

1. I Personal, öppna listsidan **Processautomatiseringar**.

2. Välj fliken **Bakgrundsprocesser**.

3. Välj **Bakgrundsprocess för virtuell registersökning av asynkron åtgärd**.

4. Välj **Visa senaste resultat**.

I det utfällbara fönstret visas de senaste körningsresultaten för processen. Du kan visa loggen för processen, inklusive eventuella fel som returnerats från Dataverse.

## <a name="see-also"></a>Se även

[Vad är Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Register i Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Översikt över registerrelationer](/powerapps/maker/common-data-service/relationships-overview)<br>
[Skapa och redigera virtuella register som innehåller data från en extern datakälla](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Vad är Power Apps-portaler?](/powerapps/maker/portals/overview)<br>
[Översikt över att skapa appar i Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
