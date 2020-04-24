---
title: Installera och konfigurera lagerstyrningsappen - översikt
description: Det här avsnittet beskriver hur du installerar och konfigurerar Dynamics 365 for Finance and Operations - appen Lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 52882ef7542bfedebdae4a08de8404cddd01ed55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205608"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>Installera och konfigurera lagerstyrningsappen - översikt

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Det här ämnet beskriver hur man konfigurerar lagerstyrning för molndistribution. Om du letar efter hur du konfigurerar lagerstyrning för lokal distribution kan du läsa på denna länk om [lokal distribution](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Det här avsnittet beskriver hur du installerar och konfigurerar Dynamics 365 for Finance and Operations - appen Lagerställe.

Appen Lagerställe finns i Google Play och i Windows Store. För den senaste versionen av Dynamics 365 Supply Chain Management erbjuds det här programmet som en fristående komponent, vilket innebär att det kan köras separat på enheter som används för lageruppgifter. För att kunna använda programmet måste du hämta programmet på samtliga enheter och konfigurera det att ansluta till din Supply Chain Management-miljö. Det här avsnittet beskriver hur du installerar programmet på dina enheter. Det förklarar också hur du konfigurerar programmet för anslutning till din Supply Chain Management-miljö.

## <a name="prerequisites"></a>Förutsättningar
Programmet är tillgängligt för operativsystemen Android och Windows. Om du vill använda det här programmet måste du ha något av följande operativsystem som stöds installerade på dina enheter. Du måste också ha någon av följande versioner som stöds: Följ instruktionerna i följande tabell för att utvärdera om din maskin- och programvarumiljö är redo att stödja installationen.

| Plattform                    | Version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0, 9.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (all versioner)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, version 1611 <br>- eller - <br>Microsoft Dynamics AX version 7.0/7.0.1 och Microsoft Dynamics AX plattformsuppdatering 2 med snabbkorrigering KB 3210014 |

## <a name="get-the-app"></a>Hämta programmet
-   Windows (UWP)
     - [Finance and Operations - Lagerhållning i Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations- Lagerhållning i Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> Zebra App Gallery har tagits bort, vilket innebär att appen Lagerställe inte längre är tillgängligt för hämtning på denna plats.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Skapa ett webbtjänstprogram i Azure Active Directory
Om du vill att programmet ska interagera med en viss Supply Chain Management-server, måste du registrera ett webbtjänstprogram i en Azure Active Directory-katalog för Supply Chain Management-innehavaren. Av säkerhetsskäl rekommenderar vi att du skapar ett webbtjänstprogram för varje enhet som du använder. För att skapa du ett webbtjänstprogram i Azure Active Directory (Azure AD), gör du följande:

1.  I en webbläsare går du till <https://portal.azure.com>.
2.  Ange namn och lösenord för den användare som har tillgång till Azure-abonnemanget.
3.  I Azure Portal, i vänstra navigeringsfönstret, klicka på **Azure Active Directory**.

    [![WMA-01-active-directory-exempel](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)

4.  Säkerställ att instansen för Active Directory är den som används av Supply Chain Management.
5.  I listan klickar du på **App registreringar**. 

    [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)

6.  I det övre fönstret klickar du på **ny registrering**. Guiden **Registrera en programguide** startar.
7.  Ange ett namn på programmet och välj **endast konton i denna organisationskatalog**. Klicka på **Registrera**.  

    [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)

8.  Din nya programregistrering kommer att öppnas. 

    [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)

9.  Kom ihåg **Application ID** du kommer att behöva det senare. **Application ID** kommer senare att kallas **Client ID**.
10. Klicka på **certifikat och hemligheter** i fönstret **hantera**. Klicka på **ny klienthemlighet**. 

    [![WMA-05-Active-Directory-Create-Key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

11. Skapa en nyckel genom att ange en nyckelbeskrivning och en varaktighet i avsnittet **lösenord**. Klicka på **lägg till** och kopiera nyckeln. Den här nyckeln kommer senare att betecknas som **Klienthemlighet**. 

    [![WMA-06-active-directory-save-key](./media/WMA-06-active-directory-save-key.png)](./media/WMA-06-active-directory-save-key.png)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Skapa och konfigurera ett användarkonto i Supply Chain Management
Om du vill aktivera Supply Chain Management för ditt Azure AD-program, måste du slutföra följande konfigurationssteg:

1.  Skapa en användare som motsvarar autentiseringsuppgifterna för lagerstyrningsprogrammet.
    1.  Gå till **Systemadministration** &gt; **Vanlig** &gt; **Användare**.
    2.  Skapa en ny användare.
    3.  Tilldela den mobila enhetsanvändaren på lagret enligt följande skärmbild. 
    
        [![wh-09-lägg-till-säkerhetsroll-för-användare](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Koppla ditt Azure Active Directory-program till användaren av lagerstyrningsprogrammet.
    1.  I Supply Chain Management, navigera till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-program**.
    2.  Skapa en ny rad.
    3.  Ange det **Klient-ID** (som erhölls i det senaste avsnittet), namnge det och välj den användare som skapades tidigare. Vi rekommenderar att du märker samtliga dina enheter, så att du kan enkelt ta bort deras åtkomst till Supply Chain Management från denna sida om de skulle gå förlorade. 
    
        [![wh-10-ad-programformulär](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurera programmet
Du måste konfigurera programmet på enheten för att ansluta till Supply Chain Management-servern via Azure AD-programmet. Det gör du genom att utföra följande steg:

1.  I programmet går du till **Anslutningsinställningar**.
2.  Rensa fältet **Demoläge**. <br>

    [![Wh-11-Inställningar för programanslutning-demoläge](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)

3.  Ange följande information: 
    + **Klient-ID för Azure Active-katalog** - Klient-ID erhålls i steg 9 i "Skapa ett webbtjänstprogram i Active Directory". 
    + **Klienthemlighet för Azure Active-katalog** - Klienthemligheten erhålls i steg 11 i "Skapa ett webbtjänstprogram i Active Directory". 
    + **Azure Active directory resource** - Azure AD Directory-resurs beskriver rot-webbadressen (URL) för Supply Chain Management. 
    
        > [!NOTE]
        > Avsluta inte detta fält med ett snedstreck (/). 

    + **Azure Active-kataloginnehavare** - Azure AD-kataloginnehavare som används med Supply Chain Management-servern: `https://login.windows.net/your-AD-tenant-ID`. Till exempel: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    
        > [!NOTE]
        > Avsluta inte detta fält med ett snedstreck (/). 
    
    + **Företag** - Ange den juridiska person i Supply Chain Management som du vill att programmet ansluter till. <br>
    
    [![wh-12-inställningar-för-programanslutningar](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)

4.  Välj knappen **Tillbaka** i programmets övre vänstra hörn. Programmet kommer nu att ansluta till din Supply Chain Management-server, och inloggningsskärmen för lagermedarbetaren visas.

    [![wh-13-inloggningsskärm](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Mer information om hur du ställer in  aååen Lagerhållning till att skanna streckkoder på en mobil enhet med hjälp av en kamera finns i [skanna streckkoder med hjälp av en kamera i  Dynamics 365 for Finance and Operations – Lagerhållning-app](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Ta bort åtkomsten för en enhet
Om en enhet går förlorad eller drabbas av fel, måste du ta bort åtkomsten till Supply Chain Management för enheten. Följande steg beskriver den rekommenderade processen när du tar bort åtkomst.

1.  Gå till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-appar**.
2.  Ta bort den rad som motsvarar den enhet för vilken du vill ta bort åtkomsten. Kom ihåg det **klient-ID** som används för den borttagna enheten, du behöver det senare.
3.  Logga in på Azure portal på <https://portal.azure.com>.
4.  Klicka på ikonen **Active Directory** i den vänstra menyn och se till att du befinner dig i rätt katalog.
5.  I listan klickar du på **App registreringar** och sedan på det program som du vill konfigurera. Sidan **Settings** visas och innehåller konfigurationsinformation.
6.  Se till att **klient-ID** för programmet är detsamma här som i steg 2 i det här avsnittet.
7.  Klicka på knappen **Radera** i det översta fönstret.
8.  Klicka på **Ja** i bekräftelsemeddelandet.
