---
title: Konfigurera visning av äldre batcher inom lagerstället på en mobil enhet
description: Det här avsnittet beskriver hur du ställer in en mobil enhet för att visa en lista över platser med batchar som är äldre än den aktuella platsen för en arbetsrad.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5156b17b9eddc2c3127b6d91fd8cd7d519d240e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838308"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>Konfigurera visning av äldre batcher inom lagerstället på en mobil enhet

[!include [banner](../includes/banner.md)]

Konfigurationen **visning av äldre batcher inom lagerstället på en mobil enhet** låter dig visa en lista över platser med batchar som är äldre än den aktuella platsen för arbetsraden. Listan över platser som visas innehåller information om äldre batchar på platsen med utgångsdatum och inventering av varje batch. Du kan välja från en ny plats eller att fortsätta plocka från den aktuella platsen. 
- Plocka från en ny plats - om du väljer en ny plats att plocka från, kommer den aktuella arbetsraden att uppdateras för att använda den nya platsen och arbete fortsätter som vanligt med den nya platsen. Det måste ha tillräckligt med tillgänglig kvantitet för hela arbetsraden för att den nya platsen ska gälla. Om den begärda kvantiteten inte är tillgänglig kommer arbetsraden inte att uppdateras och listan visas. 
- Fortsätt plocka från den aktuella platsen – om du fortsätter med den aktuella arbetsradplatsen, fortsätter kvantiteterna för arbetsraden att plockas från ursprungsplatsen.

## <a name="where-it-applies"></a>Tillämpning
Visning av äldre batcher inom lagerstället konfigureras på en mobil enhets menyalternativ och påverkar plockningen av batchen under artiklar.

## <a name="set-up-display-older-batches-within-warehouse"></a>Ställ in visning av äldre batchar i lager
Konfigurationen **visning av äldre batcher inom lagerstället på en mobil enhet** finns på mobilenhetens menyalternativ när alternativet **plocka äldsta batch** är inställt på **Varna**.

- Under **lagerstyrning** > **inställningar** > **mobiltelefon** > **Menyalternativ på mobil enhet**, ange **använd befintligt arbete** till **Ja** för menyobjekt och välj **Varna** i fältet **plocka äldsta batch**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]