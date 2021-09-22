---
title: Kvantitet som inte är giltig för plockningsarbete med flera IP-adresser
description: När det finns plockningsarbete med flera ID-nummer på en plats är kvantiteten inte giltig för enheten st. Kontrollera att följande fält är korrekta.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477591"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>Kvantiteten är inte giltig när det finns plockningsarbete med flera ID-nummer på en plats

## <a name="symptoms"></a>Symtom

När det finns plockningsarbete med flera ID-nummer på en plats är kvantiteten inte giltig för enheten *st* och du får följande felmeddelande:

> Kvantiteten är ogiltig för enheten 1%.

## <a name="resolution"></a>Lösning

Kontrollera att fälten **enhetsseriegrupp-ID** och **enhetskonvertering** på den frisläppta produkten eller produktvarianten är korrekt inställda.

Observera att felmeddelandet har förbättrats i version 10.0.15 så att det visar den förväntade kvantiteten (se [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Det nya felmeddelandet är:

> Kvantiteten är ogiltig. Förväntat %1 %2.
