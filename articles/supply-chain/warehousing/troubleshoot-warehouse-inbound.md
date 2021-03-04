---
title: Felsöka åtgärder för mottagande distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 60b6e37ec9d716f635c2d25374ac25a82286660e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645982"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Felsöka åtgärder för mottagande distributionslager

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Jag får följande felmeddelande: "kvalitetsordern %1 har genererats. Det gick inte att hitta klusterprofilen. Kontrollera konfigurationen."

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet är relaterat till en mottagningsprocess där kvalitetshantering (QMS) aktiveras. Beroende på konfigurationerna i din miljö kan ytterligare information om transaktionen som genererar felmeddelandet hjälpa till att åtgärda problemet.

### <a name="issue-resolution"></a>Problemlösning

Granska först inställningar för [klusterplockning](set-up-cluster-picking.md) och kontrollera att dina klusterprofiler är korrekt inställda. Du kan inte använda en menyartikel för mobila enheter för klusterplockning om inte klusterprofiler har ställts in. Beroende på din miljö kan du också behöva granska andra relaterade konfigurationer.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>Inleverans av blandat ID-nummer fungerar inte för dispositionskod utom kredit.

### <a name="issue-description"></a>Problembeskrivning

När fältet **Åtgärd** för en dispositionskod är inställd på *Kredit* eller *Kassation* kan du bara använda emnyartikeln [Inleverans av blandat ID-nummer](mixed-license-plate-receiving.md) för att behandla returnerade artiklar.

### <a name="issue-resolution"></a>Problemlösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande kan endast [dispositionskoder](../service-management/set-up-disposition-codes.md) där fältet **Åtgärd** anges till *Kredit* eller *Kassation* stöds för mottagning av blandade registreringsskyltar.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>När jag kör uppdatera produktinleveranser för en periodisk uppgift bekräftas obekräftade inköpsorder.

### <a name="issue-description"></a>Problembeskrivning

När du har kört den periodiska uppgiften *Uppdatera produktinleveranser* bekräftar systemet automatiskt obekräftade inköpsorder som har statusen för lagertransaktion *Registrerad*.

### <a name="issue-resolution"></a>Problemlösning

En ny funktion för hantering av inkommande last *Överinleverans av lastkvantiteter* åtgärdar problemet. För att aktivera denna funktion, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner (i den ordning de är listade i):

1. Associera lagertransaktioner för inköpsorder med last
1. Överinleverans av beläggningskvantiteter

Mer information finns i [bokföra registrerade produktkvantiteter mot inköpsorder](inbound-load-handling.md#post-registered-quantities).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]