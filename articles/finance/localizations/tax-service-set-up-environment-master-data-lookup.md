---
title: Aktivera huvuddatauppslag för momsberäkningskonfiguration
description: I den här artikeln beskrivs hur du konfigurerar och aktiverar sökfunktionen huvuddata för momsberäkning.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f9d882340171173e5e503f8b5e3aa856e8544b0
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306216"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Aktivera huvuddatauppslag för momsberäkningskonfiguration 

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du konfigurerar och aktiverar sökfunktionen huvuddata för momsberäkning. En listruta är tillgänglig för att välja värden i momsberäkningskonfigurationen för fält såsom **Juridisk person**, **Leverantörskonto**, **Artikelkod** och **Leveransvillkor**. Dessa värden kommer från den anslutna Microsoft Dynamics 365 Finance-miljön som använder Microsoft Dataverse-datakällan.

> [!NOTE] 
> Funktionen för sökning efter huvuddata för momsberäkning är valfri funktion. Du kan hoppa över följande steg om du inaktiverar funktionen **Momstjänststöd för Dataverse-datakällor** i Regulatory Configuration Service (RCS). I det fallet är dock listrutan inte tillgänglig i momsberäkningskonfigurationen.

Aktivera listrutan i funktionsversionskonfigurationen för Momsberäkning genom att utföra följande steg.

1. [Aktivera Microsoft Power Platform-integrering och öppna Dataverse-miljön.](#enable)
2. [Installer virtuella entiteter för ekonomi och drift.](#install)
3. [Registrera ett Azure Active Directory (Azure AD)-program.](#register)
4. [Bevilja appbehörigheter i appar för ekonomi och drift.](#grant)
5. [Konfigurera den virtuella datakällan för entiteten.](#configure)
6. [Aktivera virtuella Dataverse-entiteter.](#virtual)
7. [Konfigurera det kopplade programmet för momsberäkning.](#set-up)
8. [Importera och konfigurera konfigurationen för Dataverse-modellmappning.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Aktivera Microsoft Power Platform-integrering och öppna Dataverse-miljön

Integreringen av appar för ekonomi och drift Microsoft Power Platform kan aktiveras när du skapar en ny miljö för appar för ekonomi och drift Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Microsoft Power Platform-integrering – tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). När du är färdig visas namnet på en Microsoft Power Platform-miljö i avsnittet **Power Platform-integrering**.

1. I din miljö för ekonomi och drift i LCS, i avsnittet **Power Platform-integrering**, letar du reda på samt noterar värdet för **Miljönamn** för den länkade miljön.

    [![Värde för Miljönamn.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. I [administrationscentret för Power Platform](https://admin.powerplatform.microsoft.com/environments), på fliken **Miljöer**, väljer du den miljö som matchar värdet för **Miljönamn** som du noterat.
3. På sidan **Information** letar du reda på värdet för **Miljö-URL** för Dataverse-miljön. Notera det här värdet eftersom du behöver det i [Steg 7. Konfigurera det anslutna programmet för momsberäkning](#set-up).
4. Kontrollera att du kan öppna Dataverse-miljön i webbläsaren genom att välja URL-värdet för **Miljö**.

    [![Sidan Dataverse-miljö.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Låt Dataverse-miljön vara öppen i webbläsaren. Du behöver den i [Steg 5. Konfigurera datakälla för virtuell entitet](#configure).

Mer information finns i avsnittet [Aktivera Microsoft Power Platform-integrering](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Installer virtuella entiteter för ekonomi och drift

Dataverse-lösningen för virtuella entiteter för ekonomi och drift måste installeras från Microsoft AppSource-lösningen för virtuella entiteter.

1. I AppSource finns den [virtuella entiteten för ekonomi och drift](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Välj **Hämta nu**.
3. I fältet **Välj en miljö** anger du det **Miljönamn** som du tidigare noterade.
4. Markera kryssrutorna och markera sedan **Installera**.

När installationen är klar hittar du programmet **Virtuell entitet för ekonomi och drift** i [administrationscentret för Power Platform](https://admin.powerplatform.microsoft.com/), under **Resurser** \> **Dynamics 365-program**.

Mer information finns i [Hämta lösningen för virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Registrera ett Azure AD-program

Du måste registrera ett Azure AD-program i samma klientorganisation som apparna för ekonomi och drift så att de kan anropas av Dataverse.

1. I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory \> Appregistreringar**.
2. Välj **Ny registrering** och ange sedan följande information:

    - **Namn** – Ange ett unikt namn.
    - **Kontotyp** – Ange **Valfri Azure AD-katalog** (med en eller flera klientorganisationer).
    - **Omdirigera URI** – Lämna detta fält tomt.

3. Välj **Registrera**.
4. Anteckna värdet för **Program-ID (klient)** eftersom du kommer att behöva detta senare.

    [![ID för Azure AD-program (klient)](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Skapa en symmetrisk nyckel för programmet.
6. I det nya programmet väljer du **Certifikat och hemligheter**.
7. Välj **Ny klienthemlighet**.
8. Ange en beskrivning, välj ett utgångsdatum och välj sedan **Spara**. En nyckel skapas och visas. Kopiera värdet för senare användning.

Mer information finns i [Registrera Azure AD-program](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Bevilja appbehörigheter i appar för ekonomi och drift

Dataverse använder det Azure AD-program du skapat för att anropa appar för ekonomi och drift. Därför måste programmet vara betrodda av programmen för ekonomi och drift och associeras med ett användarkonto som har rätt behörighet. I programmen för ekonomi och drift måste du skapa en särskild tjänsteanvändare som **bara** har behörighet för funktionerna för virtuell entitet. Denna tjänsteanvändare får inte ha några andra behörigheter. När du har slutfört det här steget kommer alla program som innehar hemligheten för det Azure AD-program som du skapat att kunna anropa miljön för ekonomi- och driftprogram och få åtkomst till funktionerna för virtuell entitet.

1. I din miljö går du till **Systemadministration** \> **Användare** \> **Användare**.
2. Om du vill lägga till en post, välj **Ny** och ange följande information:

    - **Användar-ID** – Ange **dataverseintegration** eller något annat värde.
    - **Användarnamn** – Ange **dataverse integration** eller något annat värde.
    - **Leverantör** – Ange det här fältet som **NonAAD**.
    - **E-post** – Ange **dataverseintegration** eller något annat värde. (Värdet behöver inte vara ett giltigt e-postkonto.)

3. Tilldela användaren säkerhetsrollen **Dataverse app för integrering av virtuell enhet**.
4. Ta bort alla andra roller, inklusive **Systemanvändare**.
5. Gå till **Systemadministrering** \> **Inställningar** \> **Azure Active Directory-program** för att registrera Dataverse. 
6. Lägg till en rad och ange sedan, i fältet **Klient-ID**, det **Program-ID (klient)** som du tidigare gjorde en notering om.
7. Ange sedan ett namn i fältet **Namn**. Ange till exempel **Dataverse-integrering**.
8. I fältet **Användar-ID** anger du det användar-ID som du tidigare skapat.

Mer information finns i [Bevilja programbehörigheter i appar för ekonomi och drift](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Konfigurera den virtuella datakällan för entiteten

Till Dataverse måste du tillhandahålla den app-instans för ekonomi och drift som du vill ansluta till.

1. Din Dataverse-miljö bör fortfarande vara öppen i webbläsaren från [Steg 1. Aktivera Microsoft Power Platform-integrering och öppna Dataverse-miljön](#enable). Välj knappen Inställningar (kugghjulssymbol) i det övre högra hörnet, och välj sedan **Avancerade inställningar**.

    [![Öppna avancerade inställningar i Dataverse-miljön.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. I listrutan **Inställningar** väljer du **Administration**.

    [![Administration.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Välj **Datakällor för virtuell entitet**.

    [![Datakällor för virtuell entitet.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Välj datakällan kallad **Ekonomi och drift**.

    [![Datakällan Ekonomi och drift](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Ange följande information från tidigare steg:

    - **Mål-URL** – Ange den URL där du kan komma åt appar för ekonomi och drift.
    - **OAuth-URL** – Ange `https://login.windows.net/`.
    - **Klientorganisations-ID** – Ange din klientorganisation. Det här värdet kan vara domännamnet för företagets e-postadress (till exempel contoso.com).
    - **ID för AAD-program** – Ange värdet för **Program-ID (klient)** som skapades tidigare.
    - **AAD-programhemlighet** – Ange hemligheten som skapades tidigare.
    - **AAD-resurs** – Ange **00000015-0000-0000-c000-000000000000**. Detta värde är det Azure AD-program som representerar appar för ekonomi och drift. Detta ska alltid vara samma värde.

6. Spara ändringarna.
7. Stäng sidan för att gå tillbaka till sidan **Administration**, där du påbörjar [Steg 6. Aktivera virtuella Dataverse-entiteter](#virtual).

    [![Avsluta entiteten för redigering.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Mer information finns i [Konfigurera datakällan för virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Aktivera virtuella Dataverse-entiteter

Synligheten för de virtuella entiteterna från appar för ekonomi och drift måste anges som **Ja** innan de kan förbrukas av konfigurationen för Momsberäkning.

> [!NOTE]
> Du kan hoppa över det här steget genom att aktivera de momsberäkningsrelaterade virtuella entiteterna med ett enda klick i [Steg 8. Ställ in det anslutna programmet för momsberäkning](#import). Vi rekommenderar emellertid att du manuellt aktiverar minst en virtuell entitet, detta för att visa att kopplingen mellan appar för ekonomi och drift och Dataverse är väletablerad.

1. I din Dataverse-miljö, på sidan **Administration**, väljer du filterknappen (med trattsymbol) i det övre högra hörnet.

    [![Filterknapp.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. I fönstret **Avancerad sökning**, i fältet **Sök efter**, väljer du **Tillgängliga entiteter för Ekonomi och drift**.
3. Lägg till följande regel: **Namn** – **Innehåller** – **CompanyInfoEntity**. Välj sedan **Resultat**.

    [![Fönstret Avancerad sökning.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Välj **CompanyInfoEntity** i sökresultaten, markera kryssrutan **Synlig** och välj sedan **Spara**.

    [![Ange entitetens synlighet.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Upprepa de föregående stegen för följande entiteter som refereras till i konfigurationen Momsberäkning:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCode-enhet
    - InventWarehouseEntity

    > [!NOTE]
    > Endast de första 5 000 posterna för en entitet kan hämtas av Dataverse och göras tillgängliga i listrutan för konfigurationen för momsberäkning.

Mer information finns i [Aktivera Microsoft Dataverse virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Konfigurera det anslutna programmet för momsberäkning

1. Gå till **Elektronisk rapportering** och välj sedan, i avsnittet **Relaterade länkar**, **Anslutna program**.

    [![Anslutna program.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

2. Om du vill lägga till en post, välj **Ny** och ange följande fältinformation.

    - **Namn** – Ange ett namn.
    - **Typ** – Välj **Dataverse**.
    - **Program** – Ange din Dataverse-miljös **URL-värde** som du noterade i [Steg 1. Aktivera Microsoft Power Platform-integrering och öppna din Dataverse-miljö](#enable).
    - **Klientorganisation** – Ange din klientorganisation.
    - **Anpassad URL** – Ange din Dataverse-URL och lägg till **/api/data/v9.1** i denna.

3. Välj **Kontrollera anslutning** och välj sedan **Klicka här för att ansluta till valt fjärrprogram** i dialogrutan.

    [![Kontrollera anslutningen.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
4. Se till att du får ett "Slutfördes!" -meddelande som anger att anslutningen har upprättats.

    [![Meddelande vid slutfört.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)
    
5. Öppna arbetsytan **Funktionshantering** i RCS och aktivera följande funktioner:

    - Globaliseringsfunktioner
    - Dataverse-datakällor för elektronisk rapportering
    - Stöd för Dataverse-datakällor för skattetjänst

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Importera och konfigurera konfigurationen för Dataverse-modellmappning

Microsoft tillhandahåller standardkonfigurationer för modellmappning för entiteter från appar för ekonomi och drift till Momsberäkning.

1. I RCS går du till **Elektronisk rapportering**.
2. I avsnittet **Konfigurationsleverantörer**, på panelen för leverantören **Microsoft**, väljer du **Databaser**.

    [![Databaser.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Välj posten **Global konfigurationsdatabas** och sedan **Öppna**.
4. Under **Momsdatamodell** \> **Datamodell för momsberäkning** väljer du konfigurationen **Dataverse-modellmappning**.
5. På snabbfliken **Version** väljer du en version som matchar din version av appar för ekonomi och drift, och välj sedan **Importera**.

    [![Importera konfigurationen för Dataverse-modellmappning.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > Konfigurationen för **Dataverse-modellmappning** gäller endast för den högsta importerade versionen. Därför ska du inte importera en version av konfigurationen för **Dataverse-modellmappning** som är högre än den version av momsberäkningskonfigurationen som du avser att implementera. Om du till exempel avser att implementera version 40.50.225 av konfigurationen för Momsberäkning bör du endast importera version 40.50.13 av konfigurationen för **Dataverse-modellmappning**. Du ska inte importera version 40.54.14. I annat fall kommer datamodeller i konfigurationen inte att matcha.

6. Gå tillbaka till **Elektronisk rapportering** och välj sedan panelen **Momskonfigurationer**.
7. Markera den importerade konfigurationen för **Dataverse-modellmappning** och välj sedan **Redigera**.
8. Ange alternativet **standard för modellmappning** till **Ja**.
9. I fältet **Kopplat program** väljer du det kopplade program som du konfigurerat i [Steg 7. Konfigurera kopplat program för Momsberäkning](#set-up).
10. Ställ in alternativet **Ange synlighet för virtuell tabell** som **Ja** om du vill att alla momsberäkningsrelaterade virtuella entiteter ska visas.

Du har nu slutfört inställningarna för sökfunktionen för huvuddata. En listruta för fält som till exempel **Juridisk person**, **Leverantörskonto**, **Artikelkod** och **Leveransvillkor** från Dynamics 365 Finance aktiveras nu i inställningarna för **Funktionsversion för Momsberäkning**.

[![Listrutan Juridisk person.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
