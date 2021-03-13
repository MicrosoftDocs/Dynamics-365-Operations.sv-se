---
title: Använd mobil arbetsyta för tillgångshantering
description: Det här ämnet innehåller information om arbetsyta för tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: afda807714f14efb1cbab4ecfdd273aac52f4558
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033162"
---
# <a name="use-the-asset-management-mobile-workspace"></a>Använd mobil arbetsyta för tillgångshantering

[!include [banner](../../includes/banner.md)]

Det här ämnet innehåller information om mobil arbetsyta för **tillgångshantering**. På den här arbetsytan kan användare visa och skapa underhållsbegäran och arbetsorder. Användarna kan också visa de tilldelade arbetsorderjobben i en kalender eller listvy. Tillgångar och funktionella platser kan också visas och sökas efter.

## <a name="overview"></a>Översikt

Tillgångshantering är en avancerad modul för hantering av tillgångar och arbetsorderjobb i Dynamics 365 Supply Chain Management. Den mobila arbetsytan **Tillgångshantering** låter användarna snabbt visa tilldelade arbetsorderjobb på den mobila enhet som de väljer. Användare kan också skapa och hantera underhållsbegäran, uppdatera livscykeltillstånd och visa information om tillgångar och funktionella placeringar genom att använda deras mobila enheter.

Särskilt den mobila arbetsytan **Tillgångshantering** låter användarna utföra följande uppgifter:

- Skapa, visa och redigera underhållsbegäran, ta ett foto eller bifoga en befintlig bild till underhållsbegäran, ändra livscykeltillståndet för underhållsbegäran. 
- Skapa, visa och redigera arbetsorder, ta ett foto eller bifoga en befintlig bild till arbetsorder, ändra livscykeltillståndet för arbetsorder, visa arbetsorderjobb.
- Visa tilldelade arbetsorderjobb i en kalendervy.
- Skapa, visa och redigera arbetsorderjobb, uppdatera tillgångsräknare, visa underhållschecklista, visa och redigera arbetsordernoteringar , visa de verktyg som krävs för arbetsorderjobbet.
- Visa eller sök efter en viss tillgång eller en funktionsplats.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan använda den mobila arbetsytan för **Tillgångshantering** måste din administratör ställa in nödvändiga användar- och arbetarkonton och publicera arbetsytan. Mer information finns i [Ställa in mobila arbetsytan för Tillgångshantering](set-up-asset-management-mobile.md).

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Hämta och installera mobilappen Dynamics 365 for Unified Operations:

- [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
- [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen

1. Starta appen i din mobila enhet.

1. Ange din webbadress för Dynamics 365.

1. Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.

1. När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.

    ![Välj en arbetsyta](media/am-mobile-01.png "Välj en arbetsyta")

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Visa tilldelade arbetsorderjobb i en kalendervy.

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **Min kalender för arbetsorderjobb**.

1. Välj det datum som du vill visa arbetsorderjobb för. I listan visas resurs-ID och funktionsplats-ID för varje arbetsorderjobb.

1. Välj ett arbetsorderjobb i listan om du vill se jobbinformation: information om tillgång och funktionsplats samt andra navigeringslänkar för att visa **bifogade filer**, **checklistor**, **verktyg**, **tillgångsräknare**, **noteringar**, **journaler**.

    ![Visa tilldelade arbetsorderjobb i en kalendervy.](media/am-mobile-02.png "Visa tilldelade arbetsorderjobb i en kalendervy.")

## <a name="create-a-work-order-job"></a>Skapa en arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder som du vill skapa ett nytt arbetsorderjobb för.

1. Klicka på knappen **Lägg till rad**.

1. Välj den **tillgång** som du vill skapa ett nytt arbetsorderjobb för.

1. Välj **underhållsjobbtyp**, **underhållsjobbtypvariant** och **handel**.

1. Välj **Klar**.

    ![Lägg till radskärmen](media/am-mobile-03.png "Lägg till radskärmen")


## <a name="add-attachment-to-a-work-order-job"></a>Lägga till en bilaga till ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder > arbetsorderjobb du vill lägga till en bifogad fil till.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

1. Välj **bilagor** på sidan **information om arbetsorderjobb**.

1. Befintliga bilagor visas i arbetsorderjobbet. Välj **lägg till bilagor**.

1. Ange **namn** och **noteringar** för den bifogade filen.

1. Välj **Välj bild** om du vill välja ett foto i det mobila galleriet eller **ta en bild** för att ta en bild.

1. Välj **Klar**.

    ![Visa och lägga till bilagor för ett arbetsorderjobb](media/am-mobile-04.png "Visa och lägga till bilagor för ett arbetsorderjobb")

## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Visa underhållschecklista för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder > arbetsorderjobb som du vill visa en checklista för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

1. Välj **checklistor** på sidan **information om arbetsorderjobb**.

1. En lista över checklistrader som hör till arbetsorderjobbet visas. Markera en checklistarad om du vill visa **instruktioner** och lägga till **anteckningar**.

1. Klicka på knappen Tillbaka (**<**) för att gå tillbaka till föregående sida.

    ![Underhållschecklista och raddetaljer](media/am-mobile-05.png "Underhållschecklista och raddetaljer")

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Visa och uppdatera tillgångsräknare för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder > arbetsorderjobb som du vill visa en tillgångsräknare för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

1. Välj **tillgångsräknare** på sidan **information om arbetsorderjobb**.

1. En lista över tillgångsräknare som hör till arbetsorderjobbet visas. Välj penn-ikonen på en tillgångsräknarrad för att uppdatera räknarvärdet.

1. Ange ett nytt räknarvärde och välj sedan **klar**.

    ![Visa och uppdatera tillgångsräknare](media/am-mobile-06.png "Visa och uppdatera tillgångsräknare")

## <a name="register-consumption-on-a-work-order-job"></a>Registrera förbrukning för ett arbetsorderjobb

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder > arbetsorderjobb som du vill lägga till förbrukningsregistreringar för.
    - Alternativt kan du även välja **Min kalender för arbetsorderjobb** eller **Min arbetsorderjobblista** på hemsidan för att navigera till sidan **information om arbetsorderjobb**.

1. Välj **journaler** på sidan **information om arbetsorderjobb**.

1. Välj **Lägg till timmar** för att skapa registreringar av arbetstid.
    1. Välj **kategorin** från uppslaget
    1. I fältet **timmar** anger du antalet timmar som ägnats åt arbetsorderjobbet.
    1. Välj lämplig **radegenskap**.
    1. Välj **Klar**.

1. Välj **Lägg till artiklar** om du vill skapa artikelregistreringar.
    1. Välj **Artikelnummer** från sökningen
    1. Välj kategorin från **Plats**.
    1. Ange **kvantitet** av artiklar som ska förbrukas.
    1. Välj **Klar**.

1. Välj **Lägg till utgift** för att skapa registreringar av utgifter.
    1. Välj **kategorin** från uppslaget
    1. Ange kvantitet för utgiftsregistrering.
    1. Välj **Försäljningsvaluta** från uppslaget.
    1. Ange **Självkostnad** för utgiftsregistrering.
    1. Välj **Klar**.

    ![Uppdatera en arbetsorderjournal](media/am-mobile-07.png "Uppdatera en arbetsorderjournal")

## <a name="update-lifecycle-state-on-a-work-order"></a>Uppdatera livscykeltillstånd för en arbetsorder.

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **alla underhållsarbetsorder**.

1. Välj den arbetsorder som du vill uppdatera livscykeltillstånd för.

1. Klicka på knappen **uppdateringstillstånd** längst ned på skärmen.

1. Välj ett nytt livscykeltillstånd i listan.

1. Välj **Klar**.

    ![Uppdatera livscykeltillstånd för en arbetsorder.](media/am-mobile-08.png "Uppdatera livscykeltillstånd för en arbetsorder.")

## <a name="create-a-maintenance-request"></a>Skapa en underhållsbegäran

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **Alla underhållsbegäran**.

1. Välj **åtgärder** längst ned på skärmen och välj **skapa underhållsbegäran**.

1. Om nummerserien är aktiverad för underhållsbegäran i **tillgångshantering** är fältet **underhållsbegäran** dolt, eftersom det fylls i automatiskt. Om fältet **underhållskostnader** visas, ange ett ID för underhållbegäran.

1. Välj en **underhållbegärantyp**.

1. Ange en **beskrivning** för underhållsbegäran.

1. Välj det **tillgång** som du vill skapa begäran för.

1. Välj **Servicenivå** för underhållsbegäran.

1. Välj **Klar**.

    ![Skapa en underhållsbegäran](media/am-mobile-09.png "Skapa en underhållsbegäran")

## <a name="add-attachment-to-a-maintenance-request"></a>Lägg till en bilaga till en underhållsbegäran

1. På din mobila enhet öppnar du arbetsytan **Tillgångshantering**.

1. Välj **Alla underhållsbegäran**.

1. Välj den underhållsbegäran som du vill lägga till en bilaga till.

1. Välj **bifogade filer** längst ned på skärmen.

1. Välj **lägg till bilagor**.

1. Ange **namn** och **noteringar** för den bifogade filen.

1. Välj **Välj bild** om du vill välja ett foto i det mobila galleriet eller **ta en bild** för att ta en bild.

1. Välj **Klar**.

    ![Lägg till en bilaga till en underhållsbegäran](media/am-mobile-10.png "Lägg till en bilaga till en underhållsbegäran")
