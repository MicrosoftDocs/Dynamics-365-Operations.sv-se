---
title: Felsöka reservationer i distributionslagerhantering
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828116"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Felsöka reservationer i distributionslagerhantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.

Avsnitt som är relaterade till batch- och serienummerregistreringar finns i [Felsöka batch- och seriereservationhierarkier för lagerställen](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Jag får följande felmeddelande: "reservationer kan inte tas bort eftersom det finns ett arbete skapat som använder reservationerna".

### <a name="issue-description"></a>Problembeskrivning

Du kan inte icke-reserverade på en försäljningsrad, eftersom det är öppet arbete på raden.

### <a name="issue-resolution"></a>Problemlösning

Undersök om öppna förpackningsgrupparbete finns för att hämta artikeln från en förpackningsstation till en annan plats (t.ex. *Baydoor*). Granska posterna på sidorna för **Loggen över arbetsskapande** och **Arbetsinformation** för att avgöra vad som fysiskt reserverar inventeringen och sedan slutföra eller ta bort arbetet för att frigöra reservationen.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Följande felmeddelande visas: "lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikel %2...".

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna. Här är hela texten till hela felmeddelandet:

> Lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikeln %2 med dimensioner Storlek=%3, Färg=%4, Tillägg=%5, Webbplats=%6, Lagerställe=%7, Plats=%8, Lagerstatus=tillgänglig, ID-nummer=%9, Batchnummer=%10 för referens-ID %11 på parti-Lot ID %12.

### <a name="issue-resolution"></a>Problemlösning

Se till att inga lagertransaktioner fysiskt reserverar kvantiteten. Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Jag får följande felmeddelande: "fysisk behållning... Det går inte att reservera eftersom bara 0,00 är tillgängligt i lagret".

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna. Här är hela texten till hela felmeddelandet:

> Fysisk behållning Webbplats=%1, Lagerställe=%2, Lagerstatus=tillgänglig, batchnummer=%3, Ägare=%4: %5 kan inte reserveras eftersom endast 0,00 är tillgängligt i lagret.

### <a name="issue-resolution"></a>Problemlösning

Det här problemet orsakas troligen av öppet arbete. Antingen slutför du arbetet eller tar emot det utan att arbetet skapas. Se till att inga lagertransaktioner fysiskt reserverar kvantiteten. Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
