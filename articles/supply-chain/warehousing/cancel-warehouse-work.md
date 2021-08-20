---
title: Avbryt lagerarbete för undantagshantering
description: I det här avsnittet beskrivs funktionen Avbryt arbete som tillåter att jobbet för kontroll av lagerstyrning hanterar spärrat arbete.
author: omulvad
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3cab74b1961213567d0caa49035048cb84cffddeb13b63bfc699f4f130f08c77
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775493"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Avbryt lagerarbete för undantagshantering

[!include [banner](../includes/banner.md)]

Med funktionen Avbryt arbete i Microsoft Dynamics 365 Supply Chain Management kan administratören avbryta ett specifikt lagerarbete som pågår, men som blockeras av systemet eller inte kan slutföras på grund av exceptionella omständigheter. Den här funktionen är ett attraktivt och säkert alternativ till korrigeringsskript för SQL som korrigerar inkonsekventa data. Dessa skript begärs emellertid vanligtvis av IT-proffs, men funktionen Avbryt arbete kan användas av användare i företaget som har administratörsbehörighet.

Du kan komma åt funktionen Avbryt arbete på **Lagerstyrning** \> **Periodiska uppgifter** \> **Rensa \> Avbryt arbete**. I dialogruta **Avbryt arbete** för arbetet som ska avbrytas i dialogrutan Avbryt arbete och klicka sedan på **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>Lagerställe arbete som kan annulleras

Under lagerplocknings operationer kan en arbetare stöta på situationer där de har registrerat kvantiteter som har registrerats som plockade från en lagringsplats till sin plats, men de kan inte registrera placeringsoperationen. Inkonsekventa lagerdata är ofta, men inte alltid, orsaken till varför arbetet blockeras.

Till skillnad från de vanliga avbrott som går att komma åt med hjälp av knappen **Avbryt** i arbetsrubriker, kräver inte funktionen Avbryt arbete att den sista slutförda arbetsraden är en arbetsrad av typen **plats**. Med andra ord kan annulleringslogik köras även om artikelkvantiteten på en arbetsrad finns på en användarplats.

> [!NOTE]
> För arbete som måste annulleras av funktionsskäl måste lageranvändarna fortsätta att använda den vanliga funktionen Avbryt på arbetssidan.

Endast arbete av typen **Försäljning**, **Överför leverans**, **Råmaterialhämtning** eller **Lagerpåfyllnad** kan annulleras genom att använda funktionen Avbryt arbete. Annulleringslogik körs inte för plockningsarbete av fryst råmaterial eller arbete som kan avbrytas med funktionen Avbryt (se föregående notering).

För att häva blockeringen av arbetet i systemet avbryts alla återstående arbetsrader och de lagerdata som är associerade med det arbets-ID som användaren anger avbryts. Alla vanliga lagerhanteringsoperationer som rör berörd artikelkvantitet kan sedan återupptas.

Om du vill placera den berörda artikeln på en viss plats efter att arbetet avbrutits måste användaren använda en lagerrörelse eller en kvantitetjusteringsåtgärd på en mobil enhet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]