---
title: Felsök inköpsorder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med inköpsorder.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e55974f65577170880e60095f1ba74ea7366e592
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834428"
---
# <a name="troubleshoot-purchase-orders"></a>Felsök inköpsorder

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med inköpsorder.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>En åtgärd kan endast slutföras efter att radnumret har distribuerats fullständigt.

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>När inköpsorder importeras via datahantering följer inte inköpsordernummer det steg som definieras i systemparametrar.

### <a name="issue-description"></a>Problembeskrivning

Som standard genereras automatiskt radnummer för inköpsorderrader som importeras via dataentiteten *Inköpsorderrader V2* använder inte det systemradnummer som anges i systemparametrar. Om du skapar en inköpsorder manuellt och lägger till rader via användargränssnittet (UI), ökas radnumren korrekt. Om du använder DMF (ramverk för datahantering) ökas de emellertid inte korrekt.

Det här problemet beror på att när du importerar rader via DMF, om radnummer inte redan har tilldelats i den importerade enheten, använder systemet DMF-metoden för att tilldela dem. Den metoden ökar alltid radnummer med en.

### <a name="issue-workaround"></a>Problemlösning

Kontrollera att de önskade radnumren redan ges i fälten för radnummer för dataenhet när du importerar inköpsorderraderna. I det här fallet skrivs inte radnumren över med DMF.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>En standard momsgrupp och en standard kassarabatt fylls inte i från fakturakontot.

Om du använder ett fakturakonto som skiljer sig från kundkontot, fylls inte en standard momsgrupp och en standard kassarabatt i från fakturakontot när en inköpsorder skapas.

Detta beteende är av design. Standardvärdena för momsgrupp, kassarabatter och annan prisinformation baseras på kundkontot, inte på fakturakontot.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Jag får felmeddelandet "objektreferensen har inte angetts" vid en inköpsorderbekräftelse, eller ett undantag har utlösts av målet för ett anropsundantag uppstår under bokföringen av leverantörsfakturan.

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade.

### <a name="issue-description"></a>Problembeskrivning

Du får följande fel: "En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade."

### <a name="issue-resolution"></a>Problemlösning

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

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

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Inköpsorder avspeglar inte språkinställningarna för den juridiska personen.

### <a name="issue-description"></a>Problembeskrivning

Produktnamnet på en inköpsorder visas på systemspråket i stället för språket som är inställt för den juridiska person där inköpsordern skapades.

### <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. Ställ in system språket på *EN-US* (amerikansk engelska).
1. Kontrollera att det finns en produkt där *EN-US* och *DE* (tyska) språken finns kvar för översättningar av produktnamnet.
1. Ändra språket för en juridisk person till *DE*.
1. I den juridiska personen där *DE* har ställts in som språk skapar du en inköpsorder som innehåller produkten.
1. Observera att produktnamnet fortfarande visas i amerikansk engelska (systemspråket).

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. På inköpsorder visas produkten alltid på systemspråket. Inköpsorderns språk används när en bekräftelsejournal skapas.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>Den lista över godkända leverantörer per produktenhet tillåter inte att giltighetsdatumet ändras.

### <a name="issue-description"></a>Problembeskrivning

En produkt har en godkänd leverantör som t.ex. är ett giltighetsdatum på 11 januari 2018 (*01/11/2018*) och ett utgångsdatum för *aldrig*. Om du försöker ändra giltighetsdatum till 10 januari 2018 (*01/10/2018*) eller 12 januari 2018 (*01/12/2018*) visas följande felmeddelande:

> Det går inte att skapa en post i listan över godkända leverantörer (PdsApproveVendorList). Värdet för utgångsdatum måste vara större än eller lika med värdet effektiv.

### <a name="issue-resolution"></a>Problemlösning

Du kan bara utöka den period som leverantören är godkänd för. Följande regler gäller:

- Om du vill ändra giltighetsdatumet så att det är tidigare än någon av de befintliga posterna (perioderna) för artikelleverantören, måste utgångsdatumet för den nya perioden vara före alla utgångsdatum i de befintliga posterna.
- Om du vill ändra utgångsdatum så att det blir senare än någon av de befintliga perioderna måste giltighetsdatumet vara efter det senaste utgångsdatumet i någon befintlig post.
- Om du vill minska den totala perioden som leverantören har godkänts för måste du ta bort eller ändra befintliga poster. Alternativt kan du använda växeln **trunkera** under importen. Den här växeln tar bort alla befintliga poster i registret för godkända leverantörer per artikel.

I det här scenariot som beskrivs i ärendebeskrivningen, där en post har giltighetsdatumet *01/11/2018* och ett utgångsdatum för *aldrig*, kan du importera en ny post som har ett giltighetsdatum på *01/10/2018* och ett utgångsdatum för *aldrig*. Du kan dock inte förkorta perioden så att giltighetsdatumet uppdateras till *01/12/2018* via datahantering. Du måste göra ändringen genom användargränssnittet.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>När jag har ändrat leveransadressen i ett inköpsorderhuvud synkroniseras inte leveransnamnet.

### <a name="issue-description"></a>Problembeskrivning

Adressen i huvudet på en inköpsorder uppdateras till en adress som inte är en leveransadress. Även om adressen uppdateras på inköpsordern uppdateras inte leveransnamnet baserat på den uppdaterade adressen.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. Den valda adressen måste klassificeras som en leveransadress. Annars uppdateras inte leveransnamnet utifrån den valda adressen.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Kan jag hitta användaren som annullerade en inköpsorder?

Den här informationen spåras bara om inköpsordern är föremål för ändringshantering. Om du använder ändringshantering kan du se vem som skickade ändringen (annulleringen) och vem som godkände den.
