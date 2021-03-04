---
title: Mobil arbetsyta för tillgångshantering
description: Det här ämnet innehåller information om arbetsyta för tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 525f21d076027f1bf339e59fd0e346706044839c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437496"
---
# <a name="asset-management-mobile-workspace"></a>Mobil arbetsyta för tillgångshantering

[!include [banner](../../includes/banner.md)]


Det här ämnet innehåller information om arbetsyta för tillgångshantering. På den här arbetsytan kan användare visa och skapa underhållsbegäran och arbetsorder. Användarna kan också visa de tilldelade arbetsorderjobben i en kalender eller listvy. Tillgångar och funktionella platser kan också visas och sökas efter.


## <a name="overview"></a>Översikt

Tillgångshantering är en avancerad modul för hantering av tillgångar och arbetsorderjobb i Dynamics 365 Supply Chain Management. Den mobila arbetsytan **Tillgångshantering** låter användarna snabbt visa tilldelade arbetsorderjobb på den mobila enhet som de väljer. Användare kan också skapa och hantera underhållsbegäran, uppdatera livscykeltillstånd och visa information om tillgångar och funktionella placeringar genom att använda deras mobila enheter.

Särskilt den mobila arbetsytan **Tillgångshantering** låter användarna utföra följande uppgifter:

- Skapa, visa och redigera underhållsbegäran, ta ett foto eller bifoga en befintlig bild till underhållsbegäran, ändra livscykeltillståndet för underhållsbegäran. 
- Skapa, visa och redigera arbetsorder, ta ett foto eller bifoga en befintlig bild till arbetsorder, ändra livscykeltillståndet för arbetsorder, visa arbetsorderjobb.
- Visa tilldelade arbetsorderjobb i en kalendervy.
- Skapa, visa och redigera arbetsorderjobb, uppdatera tillgångsräknare, visa underhållschecklista, visa och redigera arbetsordernoteringar , visa de verktyg som krävs för arbetsorderjobbet.
- Visa eller sök efter en viss tillgång eller en funktionsplats.


## <a name="prerequisites"></a>Förutsättningar

Kraven varierar baserat på versionen av Dynamics 365 Supply Chain Management som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Förutsättningar om du använder Microsoft Dynamics 365 Supply Chain Management 
Om Microsoft Dynamics 365 Supply Chain Management används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Tillgångshantering**. Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen
Hämta och installera mobilappen Dynamics 365 for Unified Operations:

- [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
- [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen
1. Starta appen i din mobila enhet.

2. Ange din webbadress för Dynamics 365.

3. Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.

4. När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

![Figur 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Visa tilldelade arbetsorderjobb i en kalendervy.

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **Min kalender för arbetsorderjobb**.

3. Välj det datum som du vill visa arbetsorderjobb för. I listan visas resurs-ID och funktionsplats-ID för varje arbetsorderjobb.

4. Välj ett arbetsorderjobb i listan om du vill se jobbinformation: information om tillgång och funktionsplats samt andra navigeringslänkar för att visa **bifogade filer**, **checklistor**, **verktyg**, **tillgångsräknare**, **noteringar**, **journaler**.

![Figur 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Skapa en arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder som du vill skapa ett nytt arbetsorderjobb för.

4. Klicka på knappen **Lägg till rad**.

5. Välj den **tillgång** som du vill skapa ett nytt arbetsorderjobb för.

6. Välj **underhållsjobbtyp**, **underhållsjobbtypvariant** och **handel**.

7. Välj **Klar**.

![Figur 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Lägga till en bilaga till ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder > arbetsorderjobb du vill lägga till en bifogad fil till.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

4. Välj **bilagor** på sidan **information om arbetsorderjobb**.

5. Befintliga bilagor visas i arbetsorderjobbet. Välj **lägg till bilagor**.

6. Ange **namn** och **noteringar** för den bifogade filen.

7. Välj **Välj bild** om du vill välja ett foto i det mobila galleriet eller **ta en bild** för att ta en bild.

8. Välj **Klar**.

![Figur 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Visa underhållschecklista för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder > arbetsorderjobb som du vill visa en checklista för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

4. Välj **checklistor** på sidan **information om arbetsorderjobb**.

5. En lista över checklistrader som hör till arbetsorderjobbet visas. Markera en checklistarad om du vill visa **instruktioner** och lägga till **anteckningar**.

6. Klicka på knappen Tillbaka (**<**) för att gå tillbaka till föregående sida.

![Figur 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Visa och uppdatera tillgångsräknare för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder > arbetsorderjobb som du vill visa en tillgångsräknare för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

4. Välj **tillgångsräknare** på sidan **information om arbetsorderjobb**.

5. En lista över tillgångsräknare som hör till arbetsorderjobbet visas. Välj penn-ikonen på en tillgångsräknarrad för att uppdatera räknarvärdet.

6. Ange ett nytt räknarvärde och välj sedan **klar**.

![Figur 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Registrera förbrukning för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder > arbetsorderjobb som du vill lägga till förbrukningsregistreringar för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

4. Välj **journaler** på sidan **information om arbetsorderjobb**.

5. Välj **Lägg till timmar** för att skapa registreringar av arbetstid.
    1. Välj **kategorin** från uppslaget
    2. I fältet **timmar** anger du antalet timmar som ägnats åt arbetsorderjobbet.
    3. Välj lämplig **radegenskap**.
    4. Välj **Klar**.

6. Välj **Lägg till artiklar** om du vill skapa artikelregistreringar.
    1. Välj **Artikelnummer** från sökningen
    2. Välj kategorin från **Plats**.
    3. Ange **kvantitet** av artiklar som ska förbrukas.
    4. Välj **Klar**.

7. Välj **Lägg till utgift** för att skapa registreringar av utgifter.
    1. Välj **kategorin** från uppslaget
    2. Ange kvantitet för utgiftsregistrering.
    3. Välj **Försäljningsvaluta** från uppslaget.
    4. Ange **Självkostnad** för utgiftsregistrering.
    5. Välj **Klar**.

![Figur 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Uppdatera livscykeltillstånd för en arbetsorder.

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **alla underhållsarbetsorder**.

3. Välj den arbetsorder som du vill uppdatera livscykeltillstånd för.

4. Klicka på knappen **uppdateringstillstånd** längst ned på skärmen.

5. Välj ett nytt livscykeltillstånd i listan.

6. Välj **Klar**.

![Figur 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Skapa en underhållsbegäran

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **Alla underhållsbegäran**.

3. Välj **åtgärder** längst ned på skärmen och välj **skapa underhållsbegäran**.

4. Om nummerserien är aktiverad för underhållsbegäran i **tillgångshantering** är fältet **underhållsbegäran** dolt, eftersom det fylls i automatiskt. Om fältet **underhållskostnader** visas, ange ett ID för underhållbegäran.

5. Välj en **underhållbegärantyp**.

6. Ange en **beskrivning** för underhållsbegäran.

7. Välj det **tillgång** som du vill skapa begäran för.

8. Välj **Servicenivå** för underhållsbegäran.

9. Välj **Klar**.

![Figur 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Lägg till en bilaga till en underhållsbegäran

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

2. Välj **Alla underhållsbegäran**.

3. Välj den underhållsbegäran som du vill lägga till en bilaga till.

4. Välj **bifogade filer** längst ned på skärmen.

5. Välj **lägg till bilagor**.

6. Ange **namn** och **noteringar** för den bifogade filen.

7. Välj **Välj bild** om du vill välja ett foto i det mobila galleriet eller **ta en bild** för att ta en bild.

8. Välj **Klar**.

![Figur 10](media/am-mobile-10.png)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]