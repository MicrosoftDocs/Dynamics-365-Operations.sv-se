---
title: Introduktion till arbetsorder
description: Det här avsnittet innehåller en översikt över arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9890057ab852a7fb0d60056bb102ce15ac124e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263744"
---
# <a name="introduction-to-work-orders"></a>Introduktion till arbetsorder

[!include [banner](../../includes/banner.md)]



Arbetsorder används för att hantera underhållsjobb, ange nödvändig information för dem och registrera förbrukning. Varje arbetsorder kan innehålla ett eller flera arbetsorderjobb, och en eller flera till gångar kan kopplas till varje en arbetsorder. Varje arbetsorderjobb definierar ett underhållsjobb som har tidsplanerats för till gången.

Arbetsorder kan skapas på följande sätt:

- För kalenderbaserade underhållsplaner där inställningen "Autoskapa" är aktiverad automatiskt med [Schemalägg underhållsplaner](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- För underhållsomgångar där inställningen "Autoskapa" är aktiverad automatiskt med [Schemalägg underhållsomgångar](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- För förebyggande underhållsjobb eller underhållsbegäranden, från [underhållsschema](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Manuellt

- Från sidan **Alla underhållsbegäranden**, **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**.

>[!NOTE]
>Arbetsorderjobb relaterade till samma tillgång är relaterade till samma projekt-ID.

## <a name="all-work-orders"></a>Alla arbetsorder

Välj **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** för att öppna listsidan **Alla arbetsorder**. Den här sidan visar alla arbetsorder och en del av den information som är relaterad till varje.

I bilden nedan visas ett exempel på listsidan **Alla arbetsorder**.

![Figur 1](media/01-work-orders.png)

Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Aktiva arbetsorder** för att visa en lista med aktiva arbetsorder. 

Om du vill visa en lista med arbetsorderjobb som innehåller tillgångar som är installerade på funktionella platser som du är relaterad till som arbetare väljer du **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Mina underhållsjobb för arbetsorder för funktionsplats**. Relationen mellan arbetare och funktionella platser ställs in på sidan **arbetare**. Mer information finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).)

Här följer några exempel på hur du kan använd sidan **Alla arbetsorder**:

- I rutnätsvyn, välj en länk i kolumnen **Arbetsorder** för att visa informationsvyn för den valda posten. Du kan sedan välja **redigera** om du vill öppna posten för redigering.

- I informationsvyn visas detaljerad information som är relaterad till arbetsordern.  

- I informationsvyn väljer du fliken **Rader** om du vill visa information om arbetsorderjobb eller välj fliken **Huvud** om du vill visa information om arbetsorder.  

- Expandera fönstret **relaterad information** till höger på sidan om du vill visa mer information som är relaterad till den valda arbetsordern.

I bilden nedan visas ett exempel på informationsvyn **Alla arbetsorder**.

![Figur 2](media/02-work-orders.png)


Knapparna i åtgärdsfönstret är ordnade på flikar. I följande tabell beskrivs kortfattat knappar som är relaterade till tillgångshantering:



| Namn på knapp                     | Beskrivning                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redigera                            | Redigera den valda arbetsordern.                                                                                                                                                                                                                                           |
| Nytt                             | Skapa ny arbetsorder.                                                                                                                                                                                                                                                  |
| Radera                          | Radera den valda arbetsordern.                                                                                                                                                                                                                                         |
| Arbetsorderpool                 | Lägg till den markerade arbetsordern i en arbetsorderpool eller ta bort från en arbetsorderpool.                                                                                                                                                                                           |
| Justera                          | Justera information om förväntad start och slut, servicenivå, ansvarig underhållsarbetare eller ansvarig underhållsarbetargrupp på valda arbetsorder.                                                                                                                                     |
| Relaterad arbetsorder              | Skapa en ny arbetsorder relaterad till det valda arbetsorderjobbet. Detta är användbart om du vill registrera primära och sekundära arbetsorder.                                                                                                                              |
| Kopiera arbetsorder                 | Skapa en ny arbetsorder utifrån en befintlig arbetsorder.                                                                                                                                                                                                               |
| Händelsehistorik                   | Visa registreringshistoriken för arbetsordern.                                                                                                                                                                                                                |
| Anteckningar om underhållsjobb på arbetsorder                           | Skapa en beskrivning för en arbetsorder eller infoga anteckningar eller kommentarer om den. Välj först **Lägg till tidsstämpel** om du vill lägga till ditt användarnamn och en tidstämpel i anteckningen. Noteringar visas på fliken **Beskrivning** på snabbfliken **radinformation** på sidan **arbetsorder**.         |
| Verktyg                           | Skapa en lista med verktyg som krävs för en arbetsorder. Verktyg är inställda som resurser i **Organisationsadministration** > **Resurser** > **Resurser**.                                                                                                      |
| Underhållschecklista           | Visa checklista för den till gång som är kopplad till arbetsordern.                                                                                                                                                                                                              |
| Tillgångsfel                     | Visa eller registrera felinformation för en tillgång. Denna information används för felhantering.                                                                                                                                                                                      |
| Underhållsstopp            | Ange underhållsstopp för en arbetsorder.                                                                                                                                                                                                                               |
| Villkorsutvärdering            | Registrera tillståndsbedömningsmått på en arbetsorder.                                                                                                                                                                                                             |
| Tillgångsräknare                 | Skapa eller visa räknarregistreringar för tillgången.                                                                                                                                                                                                                     |
| Prognos                        | Visa eller skapa prognoser för en arbetsorder.                                                                                                                                                                                                                               |
| Journaler                        | Visa eller skapa arbetsorderjournaler. Journalrader kan kopieras från prognoser.                                                                                                                                                                                         |
| Projekttransaktioner            | Visa alla bokförda transaktioner som är relaterade till arbetsorder som skapats för tillgången.                                                                                                                                                                                             |
| Uppdatera arbetsorderns tillstånd           | Uppdatera livscykeltillstånd för arbetsorder.                                                                                                                                                                                                                                                |
| Logg för livscykeltillstånd                      | Visa en logg som visar livscykeltillstånden för den valda arbetsorder.                                                                                                                                                                                                                   |
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


Knapparna på fliken **Projekt** på fliken **Arbetsorder** i åtgärdsfönstret är relaterat till funktionaliteten för prognoser, tidskrifter och fakturering i modulen **Projekthantering och redovisning**.

>[!NOTE]
>Om du vill inkludera prognoser som har skapats i en arbetsordning när du kör huvudplanering använder du den prognosmodell som är vald på sidan **Parametrar för tillgångshantering**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]