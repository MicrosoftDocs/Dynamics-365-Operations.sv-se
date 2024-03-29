---
title: Bekräftelse av batch och ID-nummer
description: Denna artikel beskriver hur du konfigurerar och använder bekräftelse av batch och registreringsskylt från en mobil enhet.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef0d528d23c1ee9424e35e29d39121d42ba548e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903736"
---
# <a name="batch-and-license-plate-confirmation"></a>Bekräftelse av batch och ID-nummer

[!include [banner](../includes/banner.md)]

Batch-bekräftelse låter dig bekräfta att korrekt batch hämtas från den mobila enheten. På den första plockningen för *batch ovan*\[plats\]-objekt, anger batch ovan att om batch-ovan överskrider placering i sökningshierarkin måste du kontrollera att den batch som plockas matchar batchen på arbetsraden.

Bekräftelse för registreringsskylt låter dig bekräfta att korrekt registreringsskylt hämtas från den mobila enheten. När du plockar arbete från en fasplats måste du kontrollera att registreringsskylten som plockas matchar registreringsskylten som associeras med arbetet. Om arbetet har påbörjats genom att skanna en registreringsskylt, kommer detta bekräftelsesteg att hoppas över.

## <a name="where-it-applies"></a>När det gäller

Bekräftelse tillämpas detta i följande fall:

- Batch-bekräftelse gäller första plockningen för arbete för batch ovan-objekt.
- Bekräftelse för registreringsskylt gäller för plockning från fasplatser.

> [!IMPORTANT]
> Påfyllning stöds inte för bekräftelse av ID-nummer. När påfyllningsarbetet körs skapas inget bekräftelsesteg för ID-nummer.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Ange bekräftelse av batch och registreringsskylt

Du kan konfigurera bekräftelse av batch och registreringsskylt från mobila enhetens menyalternativ.

1. Ange inställning av arbetsbekräftelse från mobila enhetens menyalternativ.  
1. Välj alternativ för bekräftelse av batch eller registreringsskylt. Båda alternativen är tillgängliga för arbetstypen plockning som inte har automatisk bekräftelse aktiverad.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
