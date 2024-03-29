---
title: Inleverans av blandat ID-nummer
description: Denna artikel beskriver hur du använder blandade registreringsskyltar för att registrera och skapa arbetsuppgifter för flera artiklar med en mobil enhet.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ba316a5ed55902aed35acb4ef21623c7676b38
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907070"
---
# <a name="mixed-license-plate-receiving"></a>Inleverans av blandad registreringsskylt

[!include [banner](../includes/banner.md)]

Mottagning av blandade registreringsskyltar låter dig skapa en registreringsskylt som består av flera artiklar innan du registrerar och skapar arbetsuppgifter med plats. 

En registreringsskylt som består av flera artiklar behöver inte delas vid mottagningsplatsen för att du ka kunna registrera varje artikel. 

Du kan skanna streckkoder via artikelstyrningen för att identifiera källdokumentrader när du använder ett artikelrelaterat flöde. Om streckkoden omfattar en konfigurerad kvantitet och en måttenhet (UOM), kommer artikeln och kvantiteten automatiskt att läggas tillför den blandade registreringsskylten, och du återförs till vyn för att skanna en annan artikel. På så sätt kan du snabbt scanna alla artiklar utan att behöva göra en bekräftelse i varje steg. 

I flödet för mottagande av blandade registreringsskyltar kan du visa listan med artiklar som du redan hr scannat för registreringsskylten, och härifrån kan du även ändra eller korrigera kvantiteten av en artikel.

## <a name="where-it-applies"></a>Tillämpning

Mottagning av blandade registreringsskyltar är ett mottagningsflöde för mobila enheter med syfte att registrera och skapa arbetsuppgifter för flera rader/artiklar samtidigt. Detta är användbart om du tar emot inkommande registreringsskyltar med flera objekt. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Konfigurera mottagning av blandade registreringsskyltar
Mottagning av blandade registreringsskyltar ställs in som ett menyobjekt på mobila enheter.

Du måste skapa ett nytt menyalternativ med läge för arbetsuppgifter som inte använder befintliga arbetsuppgifter och använda någon av följande metoder:

- Inleverans av blandad registreringsskylt
- Inleverans och inlagring för blandad registreringsskylt

Alternativen för att identifiera källdokumentraderna är inköpsorderartikel, inköpsorderrad, returorder, överföring av orderartikel och överföringsorderrad. Dessa alternativ kan ändra mottagningsordningen på en enda registreringsskylt. Det sista alternativet är per beläggningsartikel. Du kan lägga till flera artiklar på en registreringsskylt, men du kan inte växla mellan flera olika beläggningar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]