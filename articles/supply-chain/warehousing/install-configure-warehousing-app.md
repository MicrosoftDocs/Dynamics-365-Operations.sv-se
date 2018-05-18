---
title: Installera och konfigurera Microsoft Dynamics 365 for Finance and Operations &#8211; Lagerstyrning
description: "Det här avsnittet beskriver hur du installerar och konfigurerar Microsoft Dynamics 365 for Finance and Operations - Lagerstyrning."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 608543c9cfd93c4772e93089e1d174312d8b23a6
ms.openlocfilehash: 411bb28668f5aa9d07774211814da4e9757ac43c
ms.contentlocale: sv-se
ms.lasthandoff: 03/06/2018

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Installera och konfigurera Microsoft Dynamics 365 for Finance and Operations &#8211; Lagerstyrning

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Det här ämnet beskriver hur man konfigurerar lagerstyrning för molndistribution. Om du letar efter hur du konfigurerar lagerstyrning för lokal distribution kan du läsa på denna länk om [lokal distribution](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Det här avsnittet beskriver hur du installerar och konfigurerar Microsoft Dynamics 365 for Finance and Operations - Lagerstyrning.

Finance and Operations - Lagerstyrning är ett program som finns att tillgå via Google Play Store och Windows Store. För den senaste versionen av Finance and Operations erbjuds det här programmet som en fristående komponent, vilket innebär att det kan köras separat på enheter som används för lageruppgifter. För att kunna använda programmet i din Finance and Operation-miljö måste du hämta programmet på samtliga enheter och konfigurera det att ansluta till din Finance and Operation-miljö. Det här avsnittet beskriver hur du installerar programmet på dina enheter. Det förklarar också hur du konfigurerar programmet för anslutning till din Finance and Operations-miljö.

## <a name="prerequisites"></a>Förutsättningar
Programmet är tillgängligt för operativsystemen Android och Windows. Om du vill använda det här programmet måste du ha något av följande operativsystem som stöds installerade på dina enheter. Du måste också ha någon av följande versioner av Finance and Operation. Följ instruktionerna i följande tabell för att utvärdera om din maskin- och programvarumiljö är redo att stödja installationen.

| Plattform                    | Version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (all versioner)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, version 1611 <br>- eller - <br>Microsoft Dynamics AX version 7.0/7.0.1 och Microsoft Dynamics AX, plattformsuppdatering 2 med snabbkorrigering KB 3210014 |

## <a name="get-the-app"></a>Hämta programmet
-   Windows (UWP)
     - [Finance and Operations - Warehousing](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations - Lagerstyrning i Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations - Lagerstyrning i Zebra App Gallery](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Skapa ett webbtjänstprogram i Azure Active Directory
Om du vill att programmet ska interagera med en viss Finance and Operations-server, måste du registrera ett webbtjänstprogram i en Azure Active-katalog för Finance and Operations-innehavaren. Av säkerhetsskäl rekommenderar vi att du skapar ett webbtjänstprogram för varje enhet som du använder. Gör följande om du vill skapa ett webbtjänstprogram i Azure Active Directory (Azure AD):

1.  I en webbläsare går du till <https://portal.azure.com>.
2.  Ange namn och lösenord för den användare som har tillgång till Azure-abonnemanget.
3.  Klicka på **Azure Active Directory**.[](./media/WMA-01-active-directory-example.png)[![WMA-01-exempel-aktiv-katalog](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png) i Azure-portalen.
4.  Säkerställ att instansen för Active Directory är den som används av Finance and Operations.
5.  I listan klickar du på **App registreringar**. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  I det övre fönstret klickar du på **ny programregistrering**. Guiden **Lägg till program** startar.
7.  Ange ett namn för programmet och markera **Webbprogram / webb-API**. Ange inloggnings-URL, d.v.s. din URL för webbappen. Denna URL-adress är densamma som din distributions-URL, men oauth läggs till i slutet. Klicka på **Skapa**. [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Välj den nya appen i listan. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Kom ihåg **Application ID** du kommer att behöva det senare. **Application ID** kommer senare att kallas **Client ID**.
10. Klick **Keys** i fönstret **Settings pane**. Skapa en nyckel genom att ange en nyckelbeskrivning och en varaktighet i avsnittet **lösenord**. 
11. Klicka på **spara** och kopiera nyckeln. Den här nyckeln kommer senare att betecknas som **Klienthemlighet**. [![WMA-05-Active-Directory-Create-Key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Skapa och konfigurera ett användarkonto i Finance and Operations
Om du vill aktivera Finance and Operations för ditt Azure AD-program, måste du slutföra följande konfigurationssteg:

1.  Skapa ett nytt användarkonto i Azure Active Directory för Finance and Operations-innehavaren. Detta användarkonto syftar till att få åtkomst till den specifika kundtjänsten för lagerstyrningsprogrammet som Finance and Operations-servern visar. När du har slutfört det här steget får du WMDP-autentiseringsuppgifter, som består av en WMDP-e-postadress och ett WMDP-lösenord. Mer information om de grundläggande stegen för att lägga till användare i Azure AD och Finance and Operations finns i kursen: [Registrera dig för ett Finance and Operations-abonnemang](../../dev-itpro/dev-tools/sign-up-preview-subscription.md).
2.  Skapa en Finance and Operations-användare som motsvarar autentiseringsuppgifterna för lagerstyrningsprogrammet.
    1.  I Finance and Operations, navigera till **Systemadministration** &gt; **Allmänt** &gt; **Användare**.
    2.  Skapa en ny användare.
    3.  Tilldela den mobila enhetsanvändaren på lagret enligt följande skärmbild. [![wh-09-lägg-till-säkerhetsroll-för-användare](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Koppla ditt Azure Active Directory-program till användaren av lagerstyrningsprogrammet.
    1.  I Finance and Operations, navigera till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-program**.
    2.  Skapa en ny rad.
    3.  Ange det **Klient-ID** (som erhölls i det senaste avsnittet), namnge det och välj den användare som skapades tidigare. Vi rekommenderar att du märker samtliga dina enheter, så att du kan enkelt ta bort deras åtkomst till Finance and Operations från denna sida om de skulle gå förlorade. [![wh-10-ad-programformulär](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurera programmet
Du måste konfigurera programmet på enheten för att ansluta till Finance and Operations-servern via Azure AD-programmet. Det gör du genom att utföra följande steg:

1.  I programmet går du till **Anslutningsinställningar**.
2.  Rensa fältet **Demoläge**. <br>[![Wh-11-Inställningar för programanslutning-demoläge](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Ange följande information: 
    + **Klient-ID för Azure Active-katalog** - Klient-ID erhålls i steg 9 i "Skapa ett webbtjänstprogram i Active Directory". 
    + **Klienthemlighet för Azure Active-katalog** - Klienthemligheten erhålls i steg 11 i "Skapa ett webbtjänstprogram i Active Directory". 
    + **Azure Active-katalogresurs** - Azure AD-katalogresursen beskriver rot-webbadressen (URL) för Finance and Operations. **Obs!** Avsluta inte detta fält med ett snedstreck (/). 
    + **Azure Active-kataloginnehavare** - Den Azure AD-kataloginnehavare som används med Finance and Operations-servern: `https://login.windows.net/your-AD-tenant-ID`. Exempel: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Obs!** Avsluta inte detta fält med ett snedstreck (/). 
    + **Företag** - Ange den juridiska person i Finance and Operations som du vill att programmet ansluter till. <br>[![wh-12-inställningar-för-programanslutningar](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Välj knappen **Tillbaka** i programmets övre vänstra hörn. Programmet kommer nu att ansluta till din Finance and Operations-server, och inloggningsskärmen för lagermedarbetaren visas. <br>[![wh-13-inloggningsskärm](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Mer information om hur du ställer in Dynamics 365 for Finance and Operations – Warehousing för att skanna streckkoder på en mobil enhet med hjälp av en kamera finns i [Skanna streckkoder med en kamera i Dynamics 365 for Finance and Operations – Warehousing](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Ta bort åtkomsten för en enhet
Om en enhet går förlorad eller drabbas av fel, måste du ta bort åtkomsten till Finance and Operations för enheten. Följande steg beskriver den rekommenderade processen när du tar bort åtkomst.

1.  I Finance and Operations, navigera till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-program**.
2.  Ta bort den rad som motsvarar den enhet för vilken du vill ta bort åtkomsten. Kom ihåg det **klient-ID** som används för den borttagna enheten, du behöver det senare.
3.  Logga in på Azure portal på <https://portal.azure.com>.
4.  Klicka på ikonen **Active Directory** i den vänstra menyn och se till att du befinner dig i rätt katalog.
5.  I listan klickar du på **App registreringar** och sedan på det program som du vill konfigurera. Sidan **Settings** visas och innehåller konfigurationsinformation.
6.  Se till att **klient-ID** för programmet är detsamma här som i steg 2 i det här avsnittet.
7.  Klicka på knappen **Radera** i det översta fönstret.
8.  Klicka på **Ja** i bekräftelsemeddelandet.

