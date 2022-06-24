---
title: Avbryt distributionslagerarbete för undantagshantering
description: I denna artikel beskrivs funktionen Avbryt arbete som tillåter att lageransvariga hanterar spärrat arbete.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a5c0cc988141b102cf3659ab4599e025f8f4640
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907186"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Avbryt lagerarbete för undantagshantering

[!include [banner](../includes/banner.md)]

Med funktionen Avbryt arbete i Microsoft Dynamics 365 Supply Chain Management kan administratören avbryta ett specifikt lagerarbete som pågår, men som blockeras av systemet eller inte kan slutföras på grund av exceptionella omständigheter. Den här funktionen är ett attraktivt och säkert alternativ till korrigeringsskript för SQL som korrigerar inkonsekventa data. Dessa skript begärs emellertid vanligtvis av IT-proffs, men funktionen Avbryt arbete kan användas av användare i företaget som har administratörsbehörighet.

Du kan komma åt funktionen Avbryt arbete på **Lagerstyrning** \> **Periodiska uppgifter** \> **Rensa \> Avbryt arbete**. I dialogruta **Avbryt arbete** för arbetet som ska avbrytas i dialogrutan Avbryt arbete och klicka sedan på **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>Lagerställe arbete som kan annulleras

Under lagerplocknings åtgärder kan en arbetare stöta på situationer där de har registrerat kvantiteter som har registrerats som plockade från en lagringsplats till sin plats, men de kan inte registrera placeringsåtgärden. Inkonsekventa lagerdata är ofta, men inte alltid, orsaken till varför arbetet blockeras.

Till skillnad från de vanliga avbrott som går att komma åt med hjälp av knappen **Avbryt** i arbetsrubriker, kräver inte funktionen Avbryt arbete att den sista slutförda arbetsraden är en arbetsrad av typen **plats**. Med andra ord kan annulleringslogik köras även om artikelkvantiteten på en arbetsrad finns på en användarplats.

> [!NOTE]
> För arbete som måste annulleras av funktionsskäl måste lageranvändarna fortsätta att använda den vanliga funktionen Avbryt på arbetssidan.

Endast arbete av typen **Försäljning**, **Överför leverans**, **Råmaterialhämtning** eller **Lagerpåfyllnad** kan annulleras genom att använda funktionen Avbryt arbete. Annulleringslogik körs inte för plockningsarbete av fryst råmaterial eller arbete som kan avbrytas med funktionen Avbryt (se föregående notering).

För att häva blockeringen av arbetet i systemet avbryts alla återstående arbetsrader och de lagerdata som är associerade med det arbets-ID som användaren anger avbryts. Alla vanliga lagerhanteringsåtgärder som rör berörd artikelkvantitet kan sedan återupptas.

Om du vill placera den berörda artikeln på en viss plats efter att arbetet avbrutits måste användaren använda en lagerrörelse eller en kvantitetjusteringsåtgärd på en mobil enhet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]