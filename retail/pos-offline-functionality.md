---
title: "Offlinefunktioner för kassa"
description: "Det här avsnittet innehåller information om offline-läget för Retail Modern POS, i vilket kassaenheter växlar automatiskt från kanaldatabasen till offline-databasen om butiksservern inte är tillgänglig. Det här avsnittet innehåller även information om allmänna inställningar för offline-läget och en beskrivning av datasynkroniseringen mellan offline-databasen och kanaldatabasen."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Offlinefunktioner för kassa

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om offline-läget för Retail Modern POS, i vilket kassaenheter växlar automatiskt från kanaldatabasen till offline-databasen om butiksservern inte är tillgänglig. Det här avsnittet innehåller även information om allmänna inställningar för offline-läget och en beskrivning av datasynkroniseringen mellan offline-databasen och kanaldatabasen.

<a name="overview"></a>Översikt
--------

I Retail Modern POS sätts en kassaenhet i offlineläge när butiksservern inte är tillgänglig. Om anslutningen till butiksservern bryts växlar Modern Retail POS därför automatiskt till offlinedatabasen. Om dataförfrågan inte lyckas inom tidsgränsintervallet konfigurerad i offlineprofilen under en försäljningstransaktion växlar Retail Modern POS automatiskt till offlinedatabasen och fortsätter försäljningstransaktionen. Retail Modern POS försöker att ansluta till butiksservern när kassaenheten är i offlineläge efter intervallet för återanslutningsförsök som konfigureras i offlineprofilen. Detta återanslutningsförsök sker bara i början av en transaktion.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Bestämma anslutningsläget för Retail Modern POS

Statushuvudet i Retail Modern POS anger den aktuella anslutningsstatusen och fönstret **Anslutningsstatus** visar status för det senaste försöket att synkronisera med offlinedatabasen. [![Anslutningsstatus](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Skapa en knapp för att växla manuellt mellan online- och offlineläge

Du kan lägga till en knapp i Retail Modern POS för att växla manuellt mellan online- och offlineläge. Skapa en knapp för kassaoperation **917 – Status för databasanslutning**. Namnet på den här knappen är **Koppla från** när Retail Modern POS är ansluten till butiksservern och **Anslut** när den är frånkopplad. Du kan använda den här knappen när du vill visa anslutningen och för att koppla från butiksservern eller för att ansluta till den. [![Knappen Koppla från i Retail Modern POS](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>Inställningar
För att aktivera offlinestöd för en kassaenhet (kassaregister), ställ in alternativet **Stöd offline** till **Ja** på sidan **Register**. En ny kanaldatabasenhet skapas och läggs till i butikens kanaldatagruppen. Kör sedan alla nödvändiga distributionsplaner för att generera datapaketen för offlinedatabasen. Installera sedan offlineversionen av Retail Modern POS. Installationen skapar offlinedatabasen. Installera också Microsoft SQL Server 2014 Express om det behövs. Datasynkronisering offline startar efter den första inloggningen på Retail Modern POS.

## <a name="data-synchronization"></a>Datasynkronisering
Butiksschemaläggaren används för att skicka huvuddata till offlinedatabasen. Som standard när en distributionstidsplan körs, skickas dataändringar till både kanaldatabasen och offlinedatabasen. Retail Modern POS inkluderar synkroniseringsbiblioteket Async som hämtar alla tillgängliga datapaket och infogar dem i offlinedatabasen. Om transaktioner skapas offline överför Retail Modern POS dem till butiksservern så att de kan infogas i kanaldatabasen. Datasynkronisering offline sker endast om Retail Modern POS körs. [![Offline-synkronisering](./media/offline-sync-1024x521.png)](./media/offline-sync.png)




