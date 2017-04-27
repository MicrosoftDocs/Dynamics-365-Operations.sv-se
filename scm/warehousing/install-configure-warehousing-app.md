---
title: 'Installera och konfigurera Microsoft Dynamics 365 for Operations & #8211; Lagerstyrning'
description: "Det här avsnittet beskriver hur du installerar och konfigurerar Microsoft Dynamics 365 for Operations - Lagerstyrning."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Installera och konfigurera Microsoft Dynamics 365 for Operations & #8211; Lagerstyrning

Det här avsnittet beskriver hur du installerar och konfigurerar Microsoft Dynamics 365 for Operations - Lagerstyrning.

Dynamics 365 for Operations - Lagerstyrning är ett program som finns att tillgå via Google Play Store och Windows Store. För den senaste versionen av Microsoft Dynamics 365 for Operations erbjuds det här programmet som en fristående komponent, vilket innebär att det kan köras för sig själv på enheter som används för lageruppgifter. För att kunna använda programmet i din Dynamics 365 for Operations-miljö måste du hämta programmet på samtliga enheter och konfigurera det att ansluta till din Dynamics 365 for Operations-miljö. Det här avsnittet beskriver hur du installerar programmet på dina enheter. Det förklaras också hur du konfigurerar programmet för anslutning till din Dynamics 365 for Operations-miljö.

## <a name="prerequisites"></a>Förutsättningar
Programmet är tillgängligt för operativsystemen Android och Windows. Om du vill använda det här programmet måste du ha något av följande operativsystem som stöds installerade på dina enheter. Du måste också ha någon av följande versioner av Dynamics 365 for Operations. Följ instruktionerna i följande tabell för att utvärdera om din maskin- och programvarumiljö är redo att stödja installationen.

| Plattform                    | version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (all versioner)                                                                                                                                                   |
| Dynamics 365 for Operations | Microsoft Dynamics 365 for Operations, version 1611 -eller- Microsoft Dynamics Dynamics AX, version 7.0/7.0.1 samt Microsoft Dynamics AX, plattformsuppdatering 2 med snabbkorrigering KB 3210014 |

## <a name="get-the-app"></a>Hämta programmet
-   Windows (UWP) – [Dynamics 365 for Operations - Lagerstyrning i Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android - [Dynamics 365 for Operations – Lagerstyrning i Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Skapa ett webbtjänstprogram i Active Directory
Om du vill att programmet ska samverka med en viss Dynamics 365 for Operations-server, måste du registrera ett webbtjänstprogram i en Azure Active-katalog för Dynamics 365 for Operations-innehavaren. Av säkerhetsskäl rekommenderar vi att du skapar ett webbtjänstprogram för varje enhet som du använder. Gör följande om du vill skapa ett webbtjänstprogram i Azure Active Directory (Azure AD):

1.  Navigera till <https://manage.windowsazure.com> i webbläsaren.
2.  Ange namn och lösenord för den användare som har tillgång till Azure-abonnemanget.
3.  Klicka på **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-exempel-aktiv-katalog](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png) i Azure-portalen.
4.  Välj den Active Directory-instans som används av Dynamics 365 for Operations i rutnätet.
5.  Klicka på **Program** i det översta verktygsfältet. [![wh-02-active-directory-program](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Klicka på **Lägg till** i det nedre fönstret. Guiden **Lägg till program** startar.
7.  Ange ett namn för programmet och markera **Webbprogram och/eller webb-API**. [![wh-03-active-directory-lägg-till-program](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Ange webbadressen (URL) för inloggning, som är programmets URL i din innehavare, URL för rotåtgärder. Webbadressen (URL) för inloggning används för tillfället inte aktivt för att verifiera programmet, men är ändå ett obligatoriskt fält. Ange samma URL i programmets ID URI-fält. [![wh-04-ad-lägg-till-egenskaper](./media/wh-04-ad-add-properties.png)](./media/wh-04-ad-add-properties.png)
9.  Navigera till fliken **Konfigurera**. [![wh-05-ad-konfigurera-program](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Bläddra nedåt tills du ser avsnittet **Behörigheter till andra program**. Klicka på **Lägg till program**. [![wh-06-ad-program-lägg-till-behörighet](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Välj **Microsoft Dynamics ERP** i listan. Klicka på knappen **Fullständig kontroll** i sidans nedre högra hörn. [![wh-07-ad-välj-behörigheter](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. I listan **Delegera behörighet** markerar du alla kryssrutor. Klicka på **Spara**. [![wh-08-ad-delegera-behörighet](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Anteckna följande uppgifter:
    -   **Klient-ID** - När du rullar uppför sidan visas **Klient-ID**.
    -   **Nyckel** - I avsnittet **Nycklar** skapar du en nyckel genom att välja varaktighet och kopiera nyckeln. Den här nyckeln kommer senare att betecknas som **Klienthemlighet**.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Skapa och konfigurera ett användarkonto i Dynamics 365 for Operations
Om du vill aktivera Dynamics 365 for Operations för ditt Azure AD-program, måste du slutföra följande konfigurationssteg:

1.  Skapa ett nytt användarkonto i Azure Active Directory för Dynamics 365 for Operations-innehavaren. Detta användarkonto syftar till att få åtkomst till den specifika kundtjänsten för lagerstyrningsprogrammet som Dynamics 365 for Operations-servern visar. När du har slutfört det här steget får du WMDP-autentiseringsuppgifter, som består av en WMDP-e-postadress och ett WMDP-lösenord. Mer information om de grundläggande stegen för att lägga till användare i Azure AD och Dynamics 365 for Operations finns i kursen: [Registrera dig för ett Microsoft Dynamics 365 for Operations-abonnemang](/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Skapa en Dynamics 365 for Operations-användare som motsvarar autentiseringsuppgifterna för lagerstyrningsprogrammet.
    1.  I Dynamics 365 for Operations, navigera till **Systemadministration** &gt; **Allmänt** &gt; **Användare**.
    2.  Skapa en ny användare.
    3.  Tilldela den mobila enhetsanvändaren på lagret enligt följande skärmbild. [![wh-09-lägg-till-säkerhetsroll-för-användare](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Koppla ditt Azure Active Directory-program till användaren av lagerstyrningsprogrammet.
    1.  I Dynamics 365 for Operations, navigera till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-program**.
    2.  Skapa en ny rad.
    3.  Ange det **Klient-ID** (som erhölls i det senaste avsnittet), namnge det och välj den användare som skapades tidigare. Vi rekommenderar att du märker samtliga dina enheter, så att du kan enkelt ta bort deras åtkomst till Dynamics 365 for Operations från denna sida om de skulle försvinna. [![wh-10-ad-programformulär](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurera programmet
Du måste konfigurera programmet på enheten för att ansluta till Dynamics 365 for Operations-servern via Azure AD-programmet. Det gör du genom att utföra följande steg:

1.  I programmet går du till **Anslutningsinställningar**.
2.  Rensa fältet **Demoläge**. [![Wh-11-Inställningar för programanslutning-demoläge](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Ange följande information:- **Klient-ID för Azure Active directory** - Klient-ID får du i steg 13 i "Skapa ett webbtjänstprogram Active Directory". - **Klienthemlighet för Azure Active Directory** - Klienthemligheten erhålls i steg 13 i "Skapa ett webbtjänstprogram i Active Directory". - **Azure Active directory-resurs** - Azure Active Directory-resurser beskriver rot-webbadressen (URL) för Dynamics 365 for Operations. **Obs!** Avsluta inte detta fält med ett snedstreck (/). - **Innehavare av Azure Active Directory** - Den Azure Active Directoryinnehavare som används med Dynamics 365 for Operations-servern: https://login.windows.net/&lt;ditt-AD-innehavar-ID&gt;. Till exempel: https://login.windows.net/contosooperations.onmicrosoft.com. 
**Obs!** Avsluta inte detta fält med ett snedstreck (/). - **Företag** - Ange den juridiska person i Dynamics 365 for Operations som du vill att programmet ansluter. [![wh-12-inställningar-för-programanslutningar](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Välj knappen **Tillbaka** i programmets övre vänstra hörn. Programmet kommer nu att ansluta till din Dynamics 365 for Operations-server, och inloggningsskärmen för lagermedarbetaren visas. [![wh-13-inloggningsskärm](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Ta bort åtkomsten för en enhet
Vid en förlorad eller komprometterad enhet måste du ta bort åtkomsten till Dynamics 365 for Operations för enheten. Följande steg beskriver den rekommenderade processen när du tar bort åtkomst.

1.  I Dynamics 365 for Operations, navigera till **Systemadministration** &gt; **Inställningar** &gt; **Azure Active Directory-program**.
2.  Ta bort den rad som motsvarar den enhet för vilken du vill ta bort åtkomsten. Anteckna det **Klient-ID** som används för den borttagna enheten.
3.  Logga in på Azures klassiska portal på <https://manage.windowsazure.com>.
4.  Klicka på ikonen **Active Directory** i den vänstra menyn, och klicka sedan på önskad katalog.
5.  På huvudmenyn klickar du på **Program** och sedan på det program som du vill konfigurera. Sidan **Snabbstart** visas med enkel inloggning och annan konfigurationsinformation.
6.  Klicka på fliken **Konfigurera**, rulla nedåt och se till att programmet **Klient-ID** är detsamma som i steg 2 i det här avsnittet.
7.  Klicka på knappen **Radera** i kommandofältet.
8.  Klicka på **Ja** i bekräftelsemeddelandet.



