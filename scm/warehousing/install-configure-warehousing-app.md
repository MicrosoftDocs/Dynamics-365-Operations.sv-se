---
title: "Installera och konfigurera Microsoft Dynamics 365 för operationer & #8211, Lagerstyrning"
description: "Det här avsnittet beskrivs hur du installerar och konfigurerar Microsoft Dynamics 365 för - lagring."
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

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Installera och konfigurera Microsoft Dynamics 365 för operationer & #8211, Lagerstyrning

Det här avsnittet beskrivs hur du installerar och konfigurerar Microsoft Dynamics 365 för - lagring.

Dynamics 365 för - lagring är ett program för Google Play butiken och Windows Store. Den här appen tillhandahålls som en fristående komponent, vilket innebär att egna distribution på enheter som används för lagerstället uppgifter för den aktuella versionen av Microsoft Dynamics 365 för operationer. Hämtar appen på varje enhet du vill använda programmet i Dynamics-365 för operationer miljö, och konfigureras för anslutning till Dynamics 365 för operationer. Det här avsnittet beskrivs hur du installerar programmet på dina enheter. Här förklaras också hur du konfigurerar programmet för anslutning till Dynamics 365 för de operationer.

## <a name="prerequisites"></a>Förutsättningar
Programmet är tillgängligt på Android och operativsystemet Windows. Om du vill använda den här appen måste du ha något av följande operativsystem som stöds installerade på dina enheter. Du måste också ha någon av följande versioner av Dynamics 365 för operationer. Följ instruktionerna i följande tabell för att utvärdera om miljön maskin- och programvara är redo för att stödja installation.

| Plattform                    | version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (alla versioner)                                                                                                                                                   |
| Dynamics 365 för operationer | Uppdatera 2 med snabbkorrigering KB 3210014 plattform för Microsoft Dynamics AX och Microsoft Dynamics 365 för operationer 1611 - eller - Dynamics Microsoft Dynamics AX version 7.0/7.0.1 |

## <a name="get-the-app"></a>Hämta programmet
-   Windows (UWP) – [Dynamics 365 för - lagring på Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android - [Dynamics 365 för verksamhet – på Google Play butik lagerhantering](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Skapa ett webbprogram tjänst i Active Directory
Om du vill att programmet ska samverka med en viss Dynamics 365 för operationer servern måste du registrera ett webbtjänstprogrammet i en Active Directory Azure för Dynamics 365 för innehavare av operationer. Av säkerhetsskäl rekommenderar vi att du skapar en webbtjänstprogrammet för varje enhet som du använder. Gör följande om du vill skapa en webbtjänstprogrammet i Azure Active Directory (AD Azure):

1.  I en webbläsare går du till <https://manage.windowsazure.com>.
2.  Ange namn och lösenord för den användare som har tillgång till Azure abonnemanget.
3.  Klicka på Azure Portal i det vänstra navigeringsfönstret **Active Directory**. [](./media/wh-01-active-directory-example.png)[![vad 01-active-directory-exempel](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  Välj den Active Directory-instans som används av Dynamics 365 för operationer i rutnätet.
5.  Klicka på det översta verktygsfältet **program**. [![Vad 02-active-directory-program](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Längst ned i fönstret, klickar du på **Lägg till**. Den **lägga till application** startas automatiskt.
7.  Ange ett namn för programmet och markera **webbprogram och/eller web API**. [![Wh-03-Active-Directory-Add-Application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Ange den inloggning URL, vilket är programmets URL i hyresgästen roten operationer URL. Tecken i URL: en aktivt används inte i appen verifieringen, men det är ett obligatoriskt fält. Ange samma URL i fältet program-ID-URI. [![st-04-ad-Lägg till-egenskaper](./media/wh-04-ad-add-properties.png)](./media/wh-04-ad-add-properties.png)
9.  Gå till den **konfigurera** fliken. [![St-05-ad-konfigurera-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Bläddra nedåt tills du ser den **behörigheter till andra program** avsnitt. Klicka på **program lägger du till**. [![Wh-06-AD-App-Add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Välj **Microsoft Dynamics ERP** i listan. Klicka på den **kryssrutan Slutför** i högra hörnet på sidan. [![Vad 07-ad-select-behörighet](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. I den **behörigheter för ombud** väljer du de relevanta kryssrutorna. Click **Save**. [![St-08-ad--behörigheter för ombud](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Anteckna följande uppgifter:
    -   **Klient-ID** - när du rullar upp sidan visas **klient-ID** visas.
    -   **Nyckeln** - i den **nycklar** avsnitt, skapar du en nyckel genom att välja varaktighet och kopiera nyckeln. Den här nyckeln senare betecknas som den **klienten hemlighet**.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Skapa och konfigurera ett användarkonto i Dynamics 365 för operationer
Om du vill aktivera Dynamics 365 för operationer som använder programmet AD Azure måste du utföra följande konfigurationssteg:

1.  Skapa ett nytt användarkonto i Active Directory i Azure för Dynamics 365 för innehavare av operationer. Kontot syftar till specifika kundtjänst för appen datalagring som visar Dynamics 365 för servern operationer. När du har slutfört det här steget får WMDP användarreferenser, som består av en WMDP e-postadress och WMDP lösenord. Mer information om de grundläggande stegen för att lägga till användare i AD Azure och Dynamics 365 för operationer finns i kursen: [anmäla dig till en Microsoft Dynamics 365 för operationer abonnemang](/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Skapa en Dynamics 365 för användare med operationer som motsvarar datalagring app användarreferenser.
    1.  I Dynamics 365 för operationer, gå till **systemadministration**&gt;**gemensamma**&gt;**användare**.
    2.  Skapa en ny användare.
    3.  Tilldela användaren lagerställe mobiltelefon, vilket visas i följande skärmbild. [![Wh-09-Add-User-Security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Koppla programmet Azure Active Directory till användaren app datalagring.
    1.  I Dynamics 365 för operationer, gå till **systemadministration**&gt;**inställningar**&gt;**program Azure Active Directory**.
    2.  Skapa en ny rad.
    3.  Ange den **klient-ID** (hämtat i installationens sista avsnitt), ge den ett namn och välja vilken användare som har skapats tidigare. Vi rekommenderar att du lägger till märkord i alla enheter så att du kan enkelt ta bort åtkomsten till Dynamics 365 för operationer på denna sida om försvinner de. [![Vad 10-ad-program-formulär](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Konfigurera programmet
Du måste konfigurera programmet ska ansluta till Dynamics 365 för operationer servern via AD Azure-program. Det gör du genom att utföra följande steg.

1.  I programmet, går du till **anslutningsinställningar**.
2.  Ta bort den **demoläge** fält. [![Wh-11-App-Connection-Settings-demo-Mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Ange följande information:- **Azure Active directory-klient-ID** -ID får du i steg 13 i "Skapa ett webbprogram tjänst i Active Directory" klienten. - **Azure Active directory client hemlighet** -hemligheten klienten uppnås i steg 13 i "Skapa ett webbprogram tjänst i Active Directory". - **Azure Active directory-resursen** -resursen Azure Active directory visar Dynamics 365 för operationer rot-URL. **Observera**: inte avslutas med ett snedstreck (/). - **Innehavare azure Active directory** -hyresgäster Azure Active directory används med Dynamics 365 för operationer server: https://login.windows.net/&lt;your-AD-innehavare-ID&gt;. Exempel: https://login.windows.net/contosooperations.onmicrosoft.com. 
**Observera**: inte avslutas med ett snedstreck (/). - **Företag** -ange den juridiska personen i Dynamics 365 för operationer som du vill ansluta. [![St-12-app--inställningar](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Välj den **tillbaka** knappen i det övre vänstra hörnet av programmet. Programmet kommer nu att ansluta till Dynamics 365 för operationer servern och för lagerarbetaren inloggningsskärmen visas. [![st-13--inloggningsskärmen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Ta bort åtkomsten för en enhet
När det gäller en förlorad eller avslöjade enhet måste du ta bort åtkomsten till Dynamics 365 för operationer för enheten. Följande steg beskriver den rekommenderade processen när du tar bort åtkomst.

1.  I Dynamics 365 för operationer, gå till **systemadministration**&gt;**inställningar**&gt;**program Azure Active Directory**.
2.  Ta bort den rad som motsvarar den enhet som du vill ta bort åtkomsten. Anteckna den **klient-ID** för enheten tas bort.
3.  Logga in på Azure klassisk portalen <https://manage.windowsazure.com>.
4.  Klicka på den **Active Directory** ikon på den vänstra menyn och klickar på önskad katalog.
5.  På huvudmenyn klickar du på **program**, och klicka sedan på programmet du vill konfigurera. Den **Snabbstart** visas med enkel inloggning och annan konfigurationsinformation.
6.  Klicka på den **konfigurera** genom att rulla nedåt och se till att den **klient-ID** i programmet är samma som i steg 2 i det här avsnittet.
7.  Klicka på den **bort** knappen i kommandofältet.
8.  Klicka på **Ja** i bekräftelsemeddelandet.



