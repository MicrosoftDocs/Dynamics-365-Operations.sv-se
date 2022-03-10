---
title: Enhetlig nummerserie för jobb-ID:n
description: Den här funktionen innehåller en enda, enhetlig nummerserie som genererar jobb-ID för modulerna Produktionskontroll, Tillverkningskörning och Tid och närvaro.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748725"
---
# <a name="unified-number-sequence-for-job-ids"></a>Enhetlig nummerserie för jobb-ID:n

[!include [banner](../includes/banner.md)]

Den här funktionen innehåller en enda, enhetlig nummerserie som genererar jobb-ID för modulerna Produktionskontroll, Tillverkningskörning och Tid och närvaro. Tidigare kunde du välja en annan nummerserie för var och en av dessa moduler, vilket skulle kunna resultera i motstridiga jobb-ID om två eller flera av dessa sekvenser använde identiskt format. En sådan konflikt kan leda till skadade data.

## <a name="turn-on-this-feature-for-your-system"></a>Aktivera funktionen i systemet

Om ditt system inte redan innehåller de funktioner som beskrivs i det här avsnittet, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera funktionen *Enhetlig nummerserie för jobb-ID*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Ställ in enhetlig nummerserie för jobb-ID

När den här funktionen har aktiverats kommer de befintliga nummerserieinställningarna för **Jobbidentifiering** som finns på parametersidorna för produktionskontroll, tillverkningskörning samt tids- och närvaromoduler att inaktiveras och ett nytt fält för **Enhetligt jobb-ID** läggs till. Värdet **Enhetligt jobb-ID** delas av alla tre modulerna, vilket säkerställer att alla moduler refererar till samma nummersekvens. Jobb-ID kommer därför att vara unika i alla tre moduler och en konflikt kommer aldrig att inträffa.

Ställ in enhetlig nummerserie för jobb-ID.

1. Aktivera funktionen enligt beskrivningen i föregående avsnitt.
1. Du kan antingen identifiera nummerserien du vill använda för dina enhetliga jobb-ID-nummer eller skapa ett nytt. Mer information finns i [Nummerserier (översikt)](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Gå till sidan **Parametrarna för produktionskontroll**, **Parametrar för tillverkningskörning** eller **Tid- och närvaroparametrar**. Det spelar ingen roll vilken du väljer eftersom när du gör den här inställningen på någon av dessa sidor uppdateras alla andra sidor automatiskt.
1. Öppna fliken **Nummerserier** på den valda parametersidan.
1. Tilldela den **nummerseriekod** som du tidigare identifierade till raden med enhetliga **enhetliga jobb-ID**.
