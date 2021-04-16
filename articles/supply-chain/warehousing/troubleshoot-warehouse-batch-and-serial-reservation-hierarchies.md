---
title: Felsök hierarkier för lagerställebatch och serie reservation
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med reservationshierarkier som använder batch- eller seriedimensioner.
author: perlynne
ms.date: 3/12/2021
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
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: a1abb6f8657484d43d434076e5ee38d1c63fe2ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838188"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Felsök hierarkier för lagerställebatch och serie reservation

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med reservationshierarkier som använder batch- eller seriedimensioner.

För mer information [Flexibel reservationspolicy för dimension på distributionslagernivå](flexible-warehouse-level-dimension-reservation.md).

Reservationshierarkin för en artikel anger behovet av lagringsdimensioner som måste uppfyllas för att tilldela en plats till en efterfrågeorder. Dessa dimensioner kan beskrivas som *mått över plats* för alla dimensioner som måste uppfyllas innan en plats tilldelas, och *mått under plats*, för dimensioner som kan tilldelas efter att en plats har tilldelats efterfrågan. Dessa bokningshierarkier är också kända som *batch ovan* och *batch under* reservationhierarkier eller *serie ovan* och *serie under* reservationshierarkier.

Lagret kan bara allokeras om det inte finns några luckor i dimensionerna ovanför platsen. Till exempel *batch-ovan* reservationshierarki, förvänta **Webbplats**, **Lagerställe** och **Batch-nummer** mått som ska specificeras på beställningen. Om någon av dessa dimensioner saknas misslyckas allokeringsprocessen. Däremot, i en bokningshierarki *batch under* eller *serie under*, ett batch- eller serienummer kan anges i begäran, men allokeringsprocessen kräver det inte.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Följande felmeddelande visas: "För att tilldelas en cykel måste lastlinjer ange dimensionerna ovanför platsen. För att tilldela dessa dimensioner, reservera och återskapa lastraden".

### <a name="issue-description"></a>Problembeskrivning

När du använder ett objekt som har en *batch ovan* bokningshierarki, kommer kommandot **Släppa till distributionslager** på sidan **Workbench för lastplanering** inte att fungera om du försäker släppa en last för en delkvantitet. Det här felmeddelandet visas och inget arbete skapas för delkvantiteten.

Men när du använder ett objekt som har ett *batch under* bokningshierarki, kan du frisläppa en last för en delkvantitet från sidan **Workbench för lastplanering**.

### <a name="issue-cause"></a>Problemorsak

När en dimension ovanför dimensionen **Plats** i reservationshierarkin måste den anges innan den kan frisläppas till lagerstället. Delkvantiteter kan inte frisläppas om en eller flera dimensioner ovanför **plats** inte har angetts.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>Prompten för automatisk reservation av ett batchnummer utlöses även om det finns tillgängligt lager.

### <a name="issue-description"></a>Problembeskrivning

När du använder ett objekt som har ett *batch ovan* bokningshierarki i ett lager som inte har aktiverat lagerprocesser och automatisk bokning är aktiverad visas snabbokningsprompten för ett batchnummer även om bara en batch är tillgänglig för plockning.

Om du använder samma artikel på ett lagerställe där lagerställeprocesser har aktiverats visas dock inte prompten för automatisk reservation.

### <a name="issue-cause"></a>Problemorsak

Om en reservationshierarki definieras som *batch ovan* eller *serie ovan*, måste referensdimensionen (**batchnummer** eller **serienummer**) måste alltid anges på beställning. Lagerställeprocesser kan eventuellt fylla i informationen om ett enda batch- eller serienummer finns tillgängligt. Eftersom lagerstället inte är aktiverat för lagerställeprocesser måste användaren alltid specificera alla dimensioner ovan **Plats**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Artikelplaceringsmallar som har kriteriet om platsbehållning beaktas inte aktuell lagerbehållning för batchaktiverade artiklar.

Mer information finns i [Artikelplacering för distributionslager](warehouse-slotting.md).

### <a name="issue-description"></a>Problembeskrivning

Artikelplaceringsmallar som har kriteriet om *platsbehållning* beaktas inte aktuell lagerbehållning för *batch ovan* artiklar. De överväger det bara om batchnumret anges på försäljningsorderraden.

När du använder *batch under*, den aktuella lagerinventeringen betraktas som förväntat.

### <a name="issue-cause"></a>Problemorsak

Spårmallens rubrik kan definieras för *Beställt*, *Reserverat* eller *Frisläppt* efterfrågestrategi. För strategin *Beställt* efterfrågestrategi, gäller samma reservationshierarki krav som gäller för reservation eller släppning till lagerprocesser. Därför för föremål som har *batch ovan* och *serie under* reservationshierarkier måste batchen eller serienumret anges på efterfrågeordern (försäljning eller överföring). Alternativt kan strategin *Reserverad* efterfrågestrategi kan användas för att välja batch- eller serienummer innan efterfrågan på lagerlocket genereras.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
