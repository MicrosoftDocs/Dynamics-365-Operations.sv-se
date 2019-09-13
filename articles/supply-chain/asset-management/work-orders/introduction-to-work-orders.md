---
title: Introduktion till arbetsorder
description: Det här avsnittet innehåller en översikt över arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875911"
---
# <a name="introduction-to-work-orders"></a>Introduktion till arbetsorder

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Arbetsorder används för att hantera, ange nödvändig information för och registrera förbrukning för underhållsjobb. En arbetsorder kan innehålla ett eller flera arbetsorderjobb, och en eller flera till gångar kan kopplas till en arbetsorder. Varje arbetsorderrad definierar ett underhållsjobb som har tidsplanerats för till gången.

Arbetsorder kan skapas automatiskt eller manuellt:

- Automatiskt med hjälp av formuläret **Schemalägg underhållsplaner**, för kalenderbaserade underhållsplaner inställda på "Autoskapa".  

- Automatiskt med hjälp av formuläret **Schemalägg underhållsomgångar**, för underhållsomgångar inställda på "Autoskapa".  

- Skapa från underhållsschema, som kan vara förebyggande underhållsjobb eller underhållsbegäranden.  

- Skapa en arbetsorder manuellt.  

- Skapa en arbetsorder från **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**.

>[!NOTE]
>Arbetsorderjobb relaterade till samma tillgång är relaterade till samma projekt-ID.

## <a name="all-work-orders"></a>Alla arbetsorder

Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** för att öppna listan. **Alla arbetsorder** innehåller en lista över alla arbetsorder och visar en del av informationen som hör till en arbetsorder.

![Figur 1](media/01-work-orders.png)

- Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Aktiva arbetsorder** för att visa en lista med aktiva arbetsorder.

- Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Mina underhållsjobb för arbetsorder för funktionsplats** om du vill visa en lista med arbetsorderjobb som innehåller tillgångar som är installerade på funktionsplatser du är relaterad till som en arbetare (ställs in i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md)).

- I listan **Alla arbetsorder** (rutnätsvy) klickar du på en länk i kolumnen **Arbetsorder** för att visa informationsvyn för den valda posten. Klicka på knappen **Redigera** om du vill öppna för redigering.  

- I informationsvyn visas detaljerad information som är relaterad till arbetsordern.  

- I informationsvyn väljer du länken **Rader** om du vill se jobb information om arbetsorder eller välj länken **Sidhuvud** om du vill visa information om arbetsorder.  

- Det lodräta fönstret **Relaterad information** till höger på skärmen innehåller ytterligare information som är relaterad till arbetsordern. Expandera fönstret om du vill visa relaterad information för den valda arbetsordern.  


![Figur 2](media/02-work-orders.png)


Knapparna i åtgärdsfönstret är ordnade på flikar i åtgärdsfönstret. Här följer en kort beskrivning av knapparna för hantering av företagstillgångar:



| Namn på knapp                     | Beskrivning                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redigera                            | Redigera den valda arbetsordern.                                                                                                                                                                                                                                           |
| Nytt                             | Skapa ny arbetsorder.                                                                                                                                                                                                                                                  |
| Radera                          | Radera den valda arbetsordern.                                                                                                                                                                                                                                         |
| Arbetsorderpool                 | Lägg till den markerade arbetsordern i en arbetsorderpool eller ta bort från en arbetsorderpool.                                                                                                                                                                                           |
| Justera                          | Justera information om förväntad start och slut, servicenivå, ansvarig underhållsarbetare eller ansvarig underhållsarbetargrupp på valda arbetsorder.                                                                                                                                     |
| Relaterad arbetsorder              | Skapa en ny arbetsorder relaterad till det valda arbetsorderjobbet. Detta är användbart om du vill registrera primära och sekundära arbetsorder.                                                                                                                              |
| Kopiera arbetsorder                 | Skapa en ny arbetsorder utifrån en befintlig arbetsorder.                                                                                                                                                                                                                |
| Händelsehistorik                   | Se registreringshistorik för arbetsordern.                                                                                                                                                                                                                |
| Anteckningar om underhållsjobb på arbetsorder                           | Skapa en beskrivning, eller infoga anteckningar eller kommentarer, på en arbetsorder. Börja med att klicka på knappen **Lägg till tidsstämpel** om du vill lägga till ditt användarnamn och en tidstämpel i anteckningen. Anteckningar visas i formuläret **Arbetsorder** > snabbfliken **Radinformation** > fliken **Beskrivning**. |
| Verktyg                           | Skapa en lista med verktyg som krävs för en arbetsorder. Verktyg är inställda som resurser i **Organisationsadministration** > **Allmänt** > **Resurser** > **Resurser**.                                                                                                      |
| Underhållschecklista           | Visa checklista för den till gång som är kopplad till arbetsordern.                                                                                                                                                                                                              |
| Tillgångsfel                     | Visa eller registrera felinformation om en tillgång som ska användas för felhantering.                                                                                                                                                                                        |
| Underhållsstopp            | Ange underhållsstopp för en arbetsorder.                                                                                                                                                                                                                               |
| Villkorsutvärdering            | Registrera tillståndsbedömningsmått på en arbetsorder.                                                                                                                                                                                                             |
| Tillgångsräknare                 | Skapa eller visa räknarregistreringar för tillgången.                                                                                                                                                                                                                     |
| Prognos                        | Visa eller skapa prognoser för en arbetsorder.                                                                                                                                                                                                                               |
| Journaler                        | Visa eller skapa arbetsorderjournaler. Journalrader kan kopieras från prognoser.                                                                                                                                                                                         |
| Projekttransaktioner            | Visa alla bokförda transaktioner som är relaterade till arbetsorder som skapats för tillgången.                                                                                                                                                                                             |
| Uppdatera arbetsorderns tillstånd                | Uppdatera livscykeltillstånd för arbetsorder.                                                                                                                                                                                                                                                |
| Logg för livscykeltillstånd                       | Logg som visar livscykeltillstånden för den valda arbetsordern.                                                                                                                                                                                                                   |
| Tillgångsdokument                | Visa en lista över dokument som är kopplade till tillgångar relaterade till en arbetsorder. Dessa dokument ställs in i **Tillgångshantering** > **Inställningar** > **Tillgångsdokument**.                                                                                                 |
| Tidsplanera                        | Tidsplanera valda arbetsorder.                                                                                                                                                                                                                                      |
| Skicka ut            | Tidsplanera den valda arbetsordern för en arbetare.                                                                                                                                                                                                                        |
| Ta bort tidsplan                 | Ta bort tidsplanering för den valda arbetaren.                                                                                                                                                                                                                          |
| Schemalagda underhållsjobb för arbetsorder             | Öppna listsidan **Schemalagda arbetsorder för underhållsjobb**.                                                                                                                                                                                                                             |
| Inköpsrekvisition för arbetsorder | Öppna listsidan **Inköpsrekvisition för arbetsorder**.                                                                                                                                                                                                                 |
| Inköp för arbetsorder             | Öppna listsidan **Arbetsorderinköp**.                                                                                                                                                                                                                             |
| Kostnadskontroll                    | Jämför budgetkostnader och faktiska kostnader för arbetsordern.                                                                                                                                                                                                                |
| Timkontroll                    | Jämför prognosticerade timmar och faktiska timmar för arbetsordern.                                                                                                                                                                                                                |
| Arbetsorderrapport               | Skriv ut arbetsorderrapport.                                                                                                                                                                                                                                                |
| Arbetsorderförbrukning          | Skriv ut förbrukningsrapport.                                                                                                                                                                                                                                               |


Knapparna på fliken **Arbetsorder** > gruppen **Projekt** relaterar till funktionerna i modulen **Projekthantering och redovisning** beträffande prognoser, journaler och fakturering.

>[!NOTE]
>Prognoser som har skapats för en arbetsorder kan inkluderas när du kör huvudplaneringen genom att använda den prognosmodell som valts i formuläret **Parametrar för tillgångshantering**.

