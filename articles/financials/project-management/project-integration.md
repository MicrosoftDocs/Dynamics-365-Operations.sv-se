---
title: Integrering av Microsoft Project-klient
description: Att planera och underhålla en projekttidsplan kan vara komplext, därför behöver projektledare verktyg som hjälper dem att hantera uppgiften. Integration med Microsoft Project-klienten ger stöd för att öppna och hantera en uppdelad arbetsstruktur för projekt.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 48feb0182c623714b2acffafc42016c0471ba6c1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "317486"
---
# <a name="microsoft-project-client-integration"></a>Integrering av Microsoft Project-klient

[!include [banner](../includes/banner.md)]

Att planera och underhålla en projekttidsplan kan vara komplext, därför behöver projektledare verktyg som hjälper dem att hantera uppgiften. Integration med Microsoft Project-klienten ger stöd för att öppna och hantera en uppdelad arbetsstruktur för projekt. Projektledaren kan publicera alla ändringar tillbaka till den uppdelade arbetsstrukturen för projekt i Finance and Operations.

> [!NOTE]
> Om du använder Microsoft Dynamics 365 for Finance and Operations, uppdateringen från juli, måste du installera KB 4054797 och 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Konfigurera tillägget för Microsoft Project-klienten
Om du vill aktivera integrationen med Microsoft Project-klienten behöver Microsoft Dynamics 365-tillägget installeras på användarens klient i Microsoft Project-programmet. Detta görs genom att öppna arbetsytan för **projekthantering**.

• Klicka på **konfigurera tillägg för projekt-klient** från arbetsytans **länkar** > **inställningar**.

• Klicka på **öppna** och välj **kör** när du blir tillfrågad.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Öppna och redigera ett befintligt utkast till uppdelad arbetsstruktur i Microsoft Project-klienten
Om ett projekt i Finance and Operations redan har en uppdelad arbetsstruktur kan den uppdelade arbetsstrukturen öppnas i Microsoft Project klientprogrammet, om strukturen har statusen utkast. För att öppna från sidan **Projekt** klicka på länken **Öppna i Microsoft Project** från fliken **Planera**. Den här sidan kan även öppnas från Microsoft Project-klientprogrammet genom att klicka på **Öppna** på fliken **Microsoft Dynamics 365**. Välj **Juridisk person** och **Projekt**.

> [!NOTE]
> Om du använder Internet Explorer som webbläsare kan du behöva klicka på **spara** för att manuellt öppna från den plats filen är nedladdad till. Eller klicka på **spara och öppna** för att öppna filen i Microsoft Project-klienten. Byt inte namn på filen när du sparar.

Innan du gör redigeringar i filen med hjälp av Microsoft Project-klienten måste du checka ut den. Klicka på **utcheckning** på fliken **Microsoft Dynamics 365**. Detta förhindrar att andra användare redigerar den uppdelade arbetsstrukturen i Finance and Operations samtidigt. Om du vill publicera den uppdelade arbetsstrukturen efter att du slutfört redigeringarna klickar du på **Incheckning** på fliken **Microsoft Dynamics 365**.

Om en projektgrupp redan har lagts till projektet i Finance and Operations fylls resurslistan med gruppmedlemmar. Om en projektgrupp inte har lagts till i projektet kan du välja resurser och skapa ett team i Microsoft Project-klienten genom att klicka på knappen **Resurser** på fliken **Microsoft Dynamics 365**. 

Följande data synkroniseras tillbaka till Finance and Operations som en del av incheckningsprocessen:

•   Uppgiftsnamn

•   Startdatum

•   Slutdatum

•   Företrädare

•   Resursnamn

•   Kategori

•   Resurskategori

•   Arbetstimmar

•   Noteringar

•   Prioritet

> [!NOTE]
> Om du lägger till andra kolumner i filen i Microsoft Project-klienten sparas inte kolumnerna och visas inte när filen öppnas igen.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Skapa den uppdelade arbetsstrukturen för ett befintligt projekt med hjälp av Microsoft Project-klienten
För att skapa en ny uppdelad arbetsstruktur för ett befintligt projekt med hjälp av Microsoft Project-klienten gör du så här:


1.  Öppna Microsoft Project-klienten.

2.  På fliken **Microsoft Dynamics 365**, klicka på **Öppna**.

3.  Välj **juridisk person** för projektet.

4.  Välj lämpligt **projekt**.

5.  Klicka på **Utcheckning** på fliken **Microsoft Dynamics 365**.

6.  När du är klar att publicera till Finance and Operations klickar du på **Incheckning** på fliken **Microsoft Dynamics 365**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Ersätt en befintlig uppdelad arbetsstruktur för ett befintligt projekt med hjälp av Microsoft Project-klienten
Om du vill skapa en ny uppdelad arbetsstruktur med hjälp av Microsoft Project-klienten och ersätta en befintlig struktur för ett befintligt projekt gör så här:

1.  Öppna Microsoft Project-klienten.

2.  Skapa tidsplanen i Microsoft Project-klienten.

3.  På fliken **Microsoft Dynamics 365**, klicka på **Spara ändringar** > **Ersätt befintligt projekt**.

4.  Välj **juridisk person** för projektet.

5.  Välj lämpligt **projekt**.

6.  Klicka på **OK**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Skapa ett nytt projekt från Microsoft Project-klienten


1.  Öppna Microsoft Project-klienten.

2.  Skapa tidsplanen i Microsoft Project-klienten.

3.  På fliken **Microsoft Dynamics 365**, klicka på **Spara ändringar** > **Spara till nytt projekt**.

4.  Välj **juridisk person** för projektet.

5.  Ange **projekt-ID** om det behövs.

6.  Ange det **projektnamnet**.

7.  Välj **projekttyp**, **projektgrupp** och **projektkontrakt-ID**. Du kan också skapa ett nytt projektkontrakt genom att klicka på **New**.

8.  Välj vilken **kalender** som ska användas för resurshantering.

11. Klicka på **OK**.
