---
title: Omvända inställningar i journaler och på rader
description: Det här avsnittet tar upp varför en återföringspost som bokfördes i en allmän journal kanske inte inkluderas i den bokförda transaktionen.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d0659fbd814d3fb86b2f4a1ecb6162614ab8a4f125029fbb04f08cc5fb52b45c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780832"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Omvända inställningar i journaler och på rader

[!include [banner](../includes/banner.md)]

Det här avsnittet tar upp varför en återföringspost som bokfördes i en allmän journal kanske inte inkluderas i den bokförda transaktionen.  

## <a name="symptom"></a>Symptom

En allmän journal innehåller en återföringspost och ett återföringsdatum i journalen. När du bokför journalen återförs ingen av verifikationerna. Varför inträffar det här?

## <a name="resolution"></a>Lösning

När journalen bokförs tittar reverseringsprocessen bara på inställningarna för **Återföringspost** och **Återföringsdatum** i avsnittet **Rader** i verifikationen. Med den här metoden kan en journal att innehålla verifikationer markerade för återföring och andra som inte är det.

Värdena från journalen används bara som standard när *nya* rader läggs till. Att ändra värdena i journalen påverkar inte befintliga rader. I det här exemplet angavs verifikationsraderna först. När du anger radinformationen innan du anger journalen som återföring tillämpas inte beteckningen som en återföringspost och ett återföringsdatum på befintliga rader.

Om du ändrar återföringsposten eller återföringsdatumet på en befintlig rad sprids den ändringen till andra rader i samma verifikation. Optimera prestanda genom att inte uppdatera rutnätet efter att ändringar har spridits till andra rader. Det går att visa de uppdaterade värdena genom att uppdatera rutnätet.


