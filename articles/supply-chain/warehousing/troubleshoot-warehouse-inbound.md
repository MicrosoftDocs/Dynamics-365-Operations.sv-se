---
title: Felsöka åtgärder för mottagande distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920997"
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

En ny funktion för hantering av inkommande last *Överinleverans av lastkvantiteter* åtgärdar problemet. För att aktivera denna funktion, gå till arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner (i den ordning dessa listas i):

1. Associera lagertransaktioner för inköpsorder med last
1. Överinleverans av beläggningskvantiteter

Mer information finns i [bokföra registrerade produktkvantiteter mot inköpsorder](inbound-load-handling.md#post-registered-quantities).

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>När jag registrerar inkommande order får jag följande felmeddelande: "Kvantiteten är inte giltig."

### <a name="issue-description"></a>Problembeskrivning

Om fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad* för ett mobilt enhetsmenyalternativ som används för att registrera inkommande beställningar får du ett felmeddelande ("Antalet är inte giltigt") och du kan inte slutföra registreringen.

### <a name="issue-cause"></a>Problemorsak

När *Användardefinierad* används som licens för grupperingspolicy, delar systemet upp det inkommande lagret i separat ID-nummer, enligt enhetssekvensgruppen. Om batch- eller serienummer används för att spåra artikeln som levereras måste kvantiteterna för varje batch eller serienummer anges per ID-nummer den som registreras. Om kvantiteten som har angetts för ett ID-nummer överskrider den kvantitet som fortfarande måste tas emot för de aktuella dimensionerna, visas felmeddelandet.

### <a name="issue-resolution"></a>Problemlösning

När du registrerar ett objekt med hjälp av ett mobilt enhetsmenyalternativ där fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad*, kan systemet kräva att du bekräftar eller anger ID-nummer, batch-nummer eller serienummer.

På sidan för ID-nummer bekräftelse visar systemet den kvantitet som har tilldelats för det aktuella ID-numret. På batch- eller seriebekräftelsesidorna visar systemet den kvantitet som fortfarande måste mottas på det aktuella ID-numret. Det kommer även att innehålla ett fält där du kan ange den kvantitet som ska registreras för kombinationen av ID- och batch- eller serienummer. Se då till att kvantiteten som registreras för ID-numret inte överstiger den kvantitet som fortfarande måste tas emot.

Alternativt, om för många ID-nummer genereras vid inkommande orderregistrering kan värdet på fältet **Grupperingspolicy för ID-nummer** ändras till *Gruppering av ID-nummer*, en ny enhetssekvensgrupp kan tilldelas objektet eller alternativet **Gruppering av ID-nummer** för enhetsseriegruppen kan inaktiveras.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
