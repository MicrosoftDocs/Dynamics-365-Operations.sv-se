---
title: Vanliga frågor och svar om anskaffning
description: Det här ämnet innehåller svar på vanliga frågor (FAQ) om anskaffningsfunktionen i Supply Chain Management
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 718108447dcb5cec488b7fa626feb551808e8dd8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669360"
---
# <a name="procurement-faq"></a>Vanliga frågor och svar om anskaffning

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller svar på vanliga frågor (FAQ) om anskaffningsfunktionen i Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Kan jag bara visa inköpsorder som jag har skapat?

Den här funktionen är inte tillgänglig för närvarande.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Kan jag reservera lager och skapa transaktioner mot registrerat lager på en inköpsorder?

### <a name="issue-description"></a>Problembeskrivning

Även när artiklar är i ett *registrerat* tillstånd på en inköpsorder kan du ändå reservera lagret. Med andra ord kan du skapa transaktioner mot det registrerade lagret.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. Skapa en inköpsorder
2. Registrera inköpsorderrad.
3. Lägg märke till att du kan generera reservationer eller transaktioner mot det registrerade lagret.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. Förväntat är att registrerade artiklar har anlänt fysiskt i lagret eller lagret och att de därför är tillgängliga för reservation.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Kan jag hitta användaren som annullerade en inköpsorder?

Den här informationen spåras bara om inköpsordern är föremål för ändringshantering. Om du använder ändringshantering kan du se vem som skickade ändringen (annulleringen) och vem som godkände den.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Varför kan jag inte koppla ett inköpsavtal till en befintlig inköpsorder?

Ett inköpsavtal måste vara kopplat till en inköpsorder när inköpsordern skapas. Annars kan inte inköpsorderrader kopplas till inköpsavtalsrader.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Vilken kontroll utlöser meddelandet "uppdatera priser och rabatter som angetts manuellt eller i det externa dokumentet"?

När du ändrar leveransdatumet kan du få ett meddelande om att "uppdatera priser och rabatter som angetts manuellt eller i ett externt dokument". Det här meddelandet visas om leveransdatumet ändras, kan ett annat handels- eller försäljningsavtal utlösas och orsaka prisändringar. En ändring av leveransdatumet kan också påverka lagerplaner och annan information.

Meddelandet utlöses när något av datumen eller några andra parametrar ändras. Syftet med meddelandet är att säkerställa att du är medveten om de prisändringar som kan uppstå på grund av dessa ändringar.

Meddelandet är TAE-dialog (handelsavtalets utvärdering). En fullständig beskrivning finns i [policyer för utvärdering av handelsavtal](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Varför kan jag inte bokföra fler än en faktura för en inköpsorderrad som har kategoribaserade artiklar?

En kvantitet är obligatorisk om du vill bokföra fakturor. Om hela kvantiteten av en rad endast har fakturerats för ett delbelopp, kan du alltså inte fakturera resten av beloppet på en annan faktura.
