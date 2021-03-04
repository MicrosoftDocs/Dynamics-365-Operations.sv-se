---
title: Felsöka lastuppbyggnad och utleveranser
description: Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med lastuppbyggnad och leveranser i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2933bcfd2cc526e39a4e1343cd472334a5b95607
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645342"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Felsöka lastuppbyggnad och utleveranser

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du åtgärdar vanliga problem som du kan stöta på när du arbetar med lastuppbyggnad och leveranser i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Följande felmeddelande visas: "du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga..."

### <a name="issue-description"></a>Problembeskrivning

Följande felmeddelande visas när du försöker frisläppa en returförsäljningsorder till lagerstället:

> Du kan inte skapa en lastrad för den här orderraden eftersom den innehåller lagerdimensioner som är ogiltiga. Du kan inte referera lagerdimensioner som finns under platsdimensionen i den här reservationshierarkin. Ta bort de ogiltiga dimensionerna från orderraden.

### <a name="issue-resolution"></a>Problemlösning

Tyvärr har produkten inte stöd för lastbearbetning för en försäljningsreturprocess. Därför kan du inte frisläppa returförsäljningsordern till lagerstället.

På försäljningsordertransaktioner kan du inte referera till lagerdimensioner som ligger under dimensionen **Plats** i reservationshierarkin. Upplösningen är att ta bort ogiltiga dimensioner från orderraden.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Följande felmeddelande visas: "en av raderna finns redan i en last. Det gick inte att frisläppa till lagret."

### <a name="issue-description"></a>Problembeskrivning

Om du manuellt skapar beläggningar eller om du ställer in processen så att lasten redan har skapats innan försäljningsorderrad har angetts, är antagandet att den efterföljande frisläppningen utförs manuellt och att flödet och värderingen från last kommer att användas.

I ett annat scenario försöker du göra en automatisk frisläppning till lagerstället, men påfyllnadsprocessen kunde inte skapa arbete. Därför skapas fortfarande en öppen leverans eller last. Den här öppna försändelsen eller lasten spärrar sedan de efterföljande försöken att automatiskt frisläppa ordern tills du antingen tar bort den öppna försändelsen eller lasten, eller manuellt ombearbetar påfyllning.

### <a name="issue-resolution"></a>Problemlösning

Du kan frisläppa från sidan försäljningsorder, eller automatisk frisläppning kan göras från sidan Frisläpp försäljningsorder, endast om det inte finns någon last före frisläppandet till lagerstället. Lasten skapas automatiskt när påfyllnad har bearbetats.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Följande felmeddelande visas: "korrigeringen av följesedel kan inte bearbetas. Följesedeln innehåller endast artiklar som är föremål för lagerstyrningsprocesser, eftersom dessa inte stöds av korrigering av följesedel".

### <a name="issue-description"></a>Problembeskrivning

När du har bokfört en följesedel kan du inte annullera den eftersom knappen **Avbryt** inte är tillgänglig. Det går inte heller att korrigera följesedeln. Det här felmeddelandet visas om du försöker igen.

### <a name="issue-resolution"></a>Problemlösning

Om du vill korrigera bokförda följesedlar för artiklar som är aktiverade för WMS (avancerad lagerstyrning) måste du utföra bokföringen från lasten, inte direkt från ordern.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Hur kan jag skapa arbete från utgående laster i stället för påfyllningar?

### <a name="issue-description"></a>Problembeskrivning

Här finns ett sätt att reproducera problemet.

1. Skapa en utgående last med en försäljningsorder eller överföringsorder.
2. Frisläpp lasten till lagerstället.
3. Observera att inget plockningsarbete har skapats ännu.

### <a name="issue-resolution"></a>Problemlösning

Om arbete måste genereras direkt när lasten frigörs måste du konfigurera påfyllningsmallen i enlighet med detta. Ställ in följande alternativ på påfyllningsmallen *Ja*:

- Automatisera skapande av påfyllnad
- Bearbeta påfyllnaden vid släpp till lager
- Automatisera släpp av påfyllnad

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Jag kan inte släppa upp en delvis levererad last.

### <a name="issue-description"></a>Problembeskrivning

Du kan inte frisläppa en delvis levererad last till lagerstället. När du gör frisläppningen till lagerstället visas meddelandet "åtgärden är slutförd", men ingenting händer och inget arbete skapas för den återstående kvantiteten. Det här problemet uppstår när du använder funktionen för transportlast och det finns en ofullständig reservation.

### <a name="issue-resolution"></a>Problemlösning

[KB-ärende 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("delvis levererade laster kan återpåfyllas och återbearbetas") har korrigerats i [version 10.0.15](../get-started/whats-new-scm-10-0-15.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]