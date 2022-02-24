---
title: Introduktion till tillgångar
description: Det här avsnittet innehåller en översikt över tillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f629ebdf7423ca75fe215b0a3223478685fe95c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018581"
---
# <a name="introduction-to-assets"></a>Introduktion till tillgångar

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet innehåller en översikt över tillgångar i tillgångshantering. En *tillgång* är någon typ av utrustning, till exempel en maskin eller en maskindel, som kräver underhåll, service eller reparation.

En tillgång uppdateras automatiskt med relaterad information. Den här relaterade informationen kan till exempel vara om nya eller uppdaterade arbetsorder. Du kan skapa tillgångar genom att använda antingen menyartikeln **alla tillgångar** eller menyartikeln **väntande tillgångar**. I det här avsnittet beskrivs hur du skapar tillgångar med hjälp av menyalternativet **Alla tillgångar**. Information om hur du skapar tillgångar med hjälp av menyalternativet **väntande tillgångar** finns i [skapa tillgångar baserat på inköpsorder](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Alla tillgångar

Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** Listsidan **Alla tillgångar** visar alla tillgångar och en del av den information som är relaterad till dem. Om du endast vill visa aktiva tillgångar du **Aktiva tillgångar**. Om du endast vill visa tillgångar som är installerade på de funktionsplatser som du är relaterad till som underhållsarbetare, välj **, Mina aktiva tillgångar**. (Den här relationen har ställts in på sidan **arbetare**. Mer information finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).)

I rutnätsvyn **Alla tillgångar** väljer du en länk i kolumnen **tillgång** för att visa information om den valda posten. Om du vill redigera posten väljer du knappen **redigera**. Detaljvyn visar detaljerad information som är relaterad till tillgången. En ruta för **relaterad informations** till höger innehåller ytterligare tillgångsrelaterad information. Expandera fönstret om du vill visa relaterad information för den valda tillgången.

Knapparna i åtgärdsfönstret är ordnade på flikar. I följande tabell beskrivs kortfattat knappar som är relaterade till tillgångshantering.

| Namn på knapp          | Beskrivning                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redigera                 | Redigera den valda tillgången.                                                                                                                                         |
| Nytt                  | Skapa en ny tillgång.                                                                                                                                                |
| Radera               | Ta bort den valda tillgången.                                                                                                                                       |
| Flytta tillgång           | Flytta tillgångar till en annan tillgångsstruktur eller till en annan plats i samma tillgångsstruktur.                                                                                         |
| Ersätt tillgång        | Ersätt en underordnad tillgång i en tillgångshierarki med en annan tillgång.                                                                                                  |
| Installera tillgång        | Installera en tillgång på en funktionsplats.                                                                                                                          |
| Kopiera tillgång           | Kopiera en tillgångshierarki till en annan tillgång.                                                                                                                          |
| Förfrågningar             | Öppna listsidan **Aktiva begäran** där du kan visa underhållsbegäran som har skapats för den valda tillgången.                                                                         |
| Händelsehistorik        | Visa en översikt över de olika registreringar som har gjorts på tillgången.                                                                                                         |
| Tillgångsstruktur            | Visa en lista över alla artiklar (reservdelar och andra artiklar) som används på en tillgång.                                                                                  |
| Arbetsorder          | Öppna listsidan **aktiva arbetsorder** där du kan visa arbetsorder för tillgången.                                                                                        |
| Kontrollista            | Visa en översikt över underhållschecklistor och mätningar som har registrerats på tillgången.                                                                                                 |
| Underhållsstopp | Skapa eller visa registreringar för underhållsstopp på tillgången.                                                                                                       |
| Projekttransaktioner | Visa alla bokförda transaktioner som är relaterade till arbetsorder som har skapats för tillgången.                                                                                       |
| Tillgångsmått       | Skapa eller visa tillgångsmått på tillgången.                                                                                                               |
| Underhållsschema | Öppna listsidan **öppna underhållsschema** där du kan visa underhållsplaner, underhållsbegäranden och underhållsomgångar som är associerade med tillgången och som har statusen **skapad**. |
| Uppdatera tillgångens tillstånd   | Uppdatera tillgångens livscykeltillstånd. Du kan välja flera tillgångar på listsidan **alla tillgångar** och sedan uppdatera tillgångens livscykeltillstånd för dem alla på samma gång.              |
| Logg för livscykeltillstånd  | Öppna en logg som visar livscykeltillstånden för den valda tillgången.                                                                                                                 |
| Tillgångsdokument      | Visa listan över dokument som är bifogade med en tillgång. Dessa dokument ställs in på **tillgångshantering** \> **inställningar** \> **tillgångsdokument**.                 |
| Attribut           | Skapa eller visa tillgångsattribut.                                                                                                                             |
| Bild                | Välj en bild för tillgången.                                                                                                                                   |
| Överordnade tillgångar        | Visa överordnad tillgångshistorik för den valda tillgången.                                                                                                                |
| Funktionsplatser | Visa historik för funktionsplatser för den valda tillgången.                                                                                                          |
| Villkorsutvärdering | Registrera tillståndsbedömningsmätningar på tillgången.                                                                                                         |
| Fel               | Öppna listsidan **Tillgångsfel** där du kan visa fel som har registrerats på tillgången.                                                                                             |
| Kostnadskontroll         | Jämför budgetkostnader och faktiska kostnader på tillgången.                                                                                                              |
| Timkontroll         | Jämför prognostimmar och faktiska timmar på tillgången.                                                                                                              |
| KPI:er för tillgång           | Beräkna och visa prestationsindikatorer (KPI:er) för tillgången.                                                                                              |
| Jobbtyper            | Visa en översikt över de aktuella standardjobbtyperna för tillgången.                                                                                                            |
| Typer av allvarlighetsgrad    | Visa eller uppdatera allvarlighetsgradtyper för tillgång.                                                                                                                              |
| Reservdelar          | Visa en lista över godkända och alternativa reservdelar som kan användas på tillgången.                                                                               |
| Tillgångsförbrukning    | Skriv ut en rapport som visar förbrukningsregistreringar på tillgången.                                                                                                |
| Tillgångsfel          | Skriv ut en rapport som visar felregistreringar på tillgången.                                                                                                      |
