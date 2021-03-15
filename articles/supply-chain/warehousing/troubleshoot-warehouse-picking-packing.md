---
title: Felsöka plockning och packning
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du ställer in plockning och packning i Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2cce1038ed393fc8a7bb489a37fc0921b0ac755e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993948"
---
# <a name="troubleshoot-picking-and-packing"></a>Felsöka plockning och packning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du ställer in plockning och packning i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Följande felmeddelande visas: "dimensionsplats kan inte lämnas tom om serienummer för dimension har angetts."

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas om du skapar en överföringsorder för varor med serienummer med hjälp av ett lagerställe som har aktiveratstas för WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts.

### <a name="issue-resolution"></a>Problemlösning

Fältet **Standardinleveransplats** är tomt för transit lager av "från"-lagerstället. Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret. Kontrollera att den här platsen styrs av ett ID-nummer.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Följande felmeddelande visas: "Ogiltigt ID-nummer".

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet i distributionslagerappen visas när du skannar ett ID-nummer.

### <a name="issue-resolution"></a>Problemlösning

Kontrol lera att det finns ett ID-nummer i registret med ID-nummer och att artiklarna och kvantiteterna på ID-numret är tillgängliga (dvs. de spärras inte).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Jag får följande felmeddelande: "fältet Lastvikt (=-%1) kan bara innehålla positiva tal. Uppdateringen har avbrutits".

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas om det är öppet när du bearbetar arbete från förpackningsplatser till mellan platser, eller från mellanlagringsplatser till dockningsplatser.

### <a name="issue-resolution"></a>Problemlösning

Du löser det här problemet genom att gå till **Systemadministration \> Periodiska uppgifter \> Databas \> Konsekvenskontroll** och köra processen för **Konsekvenskontroll för lagerplatsstatus**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Jag får följande felmeddelande: "Kvantiteten gäller inte för enhet %1."

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas när du försöker göra en *delad plockning* i flera batchar.

### <a name="issue-resolution"></a>Problemlösning

Lagerarbetaren måste använda en process *kort plockning* i distributionslagerappen. Om du försöker att plocka flera batchar från samma plats kan du även använda alternativet **fullständig** i distributionslagerappen.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Jag kan inte flytta lagret till en plats som är kontrollerad av ID-nummer.

### <a name="issue-description"></a>Problembeskrivning

Du kan inte minska plockade kvantiteter på en last.

### <a name="issue-resolution"></a>Problemlösning

I tidigare versioner kunde du inte minska plockade kvantiteter på en last. Du kan dock nu välja bort till en plats som kontrolleras av ID-nummer. Du måste ange både ett värde för **plats** och ett värde för **ID-nummer** för lastraden **Minska plockad kvantitet**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>Kan jag skriva ut en följesedel eller förpackningsinnehåll per lagerställe?

### <a name="issue-description"></a>Problembeskrivning

Du vill skriva ut en följesedel eller ett förpackningsinnehåll per lagerställe eller plats på sidan **raduppdatering av arbetsgranskningsmall**.

### <a name="issue-resolution"></a>Problemlösning

När du skriver ut ett dokument med inställningar för utskriftshantering, begränsar du omfattningen (webbplats/lager) genom utskriftshantering istället för genom att välja **Redigera utskriftsinställningar** på sidan **Raduppdatering av arbetsgranskningsmall**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Jag kan inte annullera en följesedel efter att den har bokförts från en försäljningsorder.

### <a name="issue-description"></a>Problembeskrivning

När plocknings- och leveransprocesser är aktiverade för WMS kan du inte annullera en följesedel efter att den har bokförts från en försäljningsorder.

### <a name="issue-resolution"></a>Problemlösning

För att korrigera bokförda paket för artiklar som är aktiverade för WMS måste bokningen ske från lasten, inte från beställningen. Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. I allmänhet kan en försäljningsorder som har plockats och levererats via lagerstyrningsprocesser följesedel – uppdateras från beläggningen eller utleveransen och själva försäljningsorderdokumentet. Om du packar upp försäljningsordern från försäljningsorderdokumentet kan det dock fortfarande inte göras någon återföring av följesedeln från försäljningsordern. Därför rekommenderar vi att du använder följesedels bokföringen från lasten. I det här fallet kommer den återföring som måste göras från lasten att aktiveras.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Jag får följande felmeddelande: "det går inte att hitta tillräckligt med arbete för klustret."

### <a name="issue-description"></a>Problembeskrivning

När du använder processen *Systemdirigerad klusterplockning* om du konfigurerar en klusterprofil där till exempel 10 positioner kan väljas, fungerar processen som planerat när det finns tillräckligt med arbete för att välja till 10 positioner. Om det bara finns åtta positioner att plocka får du det här felmeddelandet, eftersom det inte finns tillräckligt med arbete för ett kluster.

### <a name="issue-resolution"></a>Problemlösning

Åtgärda problemet genom att redigera klusterprofilen och ställa in alternativet **Aktivera positioner** på *Nej*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]