---
title: Felsöka distributionslagerkonfiguration
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646117"
---
# <a name="troubleshoot-warehouse-configuration"></a>Felsöka distributionslagerkonfiguration

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Jag får följande felmeddelande: "ID-nummer eller platsen är inte giltig."

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas när du skannar ett ID-nummer eller en plats.

### <a name="issue-resolution"></a>Problemlösning

Se till att licensens ID-nummer inte har reserverats av något annat. Det här problemet uppstår när värdet som en användare skannade i lagerstället var både en giltig plats och ett giltigt licensens ID-nummer. Det här problemet löstes emellertid i versionen 10.0.11.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>Jag får följande felmeddelande: "ID-nummer måste anges för denna för denna plats".

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas om du skapar en överföringsorder med hjälp av ett lager ställe som har aktiverats ATS för WMS (avancerad lagerstyrning) och du sedan försöker bekräfta leveransen när arbetet har slutförts.

### <a name="issue-resolution"></a>Problemlösning

Fältet **Standardinleveransplats** är tomt för transit lager av "från"-lagerstället. Du åtgärdar det här problemet genom att ange en standard inleveransplats i transitlagret. Kontrollera att den här platsen styrs av ett ID-nummer.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>Följande felmeddelande visas: "du kan inte skapa en rad för lagerstatusändring eftersom arbetstypen är ogiltig. Välj en annan arbetstyp".

### <a name="issue-description"></a>Problembeskrivning

Om det är en arbetsgrupp kan du inte markera *lagerstatusändring* i kolumnen **arbetstyp** i avsnittet **information om arbetsmallen**.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. Arbetstypen *Ändring av lagerstatus* används endast av systemprocesser. Det kan inte konfigureras. Eftersom listan med arbetstyper är fast som en uppräkning kan inte de extra posterna filtreras från den nedrullningsbara menyn **Arbetstyp**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Jag får följande felmeddelande: "Kvantiteten gäller inte för enhet 1 %".

### <a name="issue-description"></a>Problembeskrivning

Kvantiteten är inte giltig för *ea* enheten när det finns ett plockningsarbete med flera ID-nummer på en plats.

### <a name="issue-resolution"></a>Problemlösning

Kontrollera att fälten **enhetsseriegrupp-ID** och **enhetskonvertering** på den frisläppta produkten eller produktvarianten är korrekt inställda.

Observera att felmeddelandet har förbättrats i version 10.0.15 (se [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Det nya felmeddelandet är, "kvantiteten är ogiltig. Förväntat %1 %2."

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>I platsdirektiv för placeringsarbete för försäljningsorder utvärderas inte flera platsdirektivåtgärder med alternativet flera SKU:er.

### <a name="issue-description"></a>Problembeskrivning

Plats direktiv av typen arbetsorder *försäljningsorder* och arbetstypen *Placera* utvärderar inte flera lokaliseringsdirektivåtgärder när alternativet **Flera SKU-enheter** är valt. Endast den första åtgärden i platsdirektivets utvärderas.

### <a name="issue-resolution"></a>Problemlösning

En ny funktion *Utvärdera alla åtgärder för platsdirektiv med flera SKU-enheter* har lagts till i version 10.0.15 (se [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Den här funktionen utvärderar alla åtgärder för platsdirektiv med flera SKU-enheter. Om du vill ha denna funktion använd [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera den.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>Jag kan inte använda distributionslagerappen för delplockning.

### <a name="issue-description"></a>Problembeskrivning

För försäljnings- och överföringsorder kan du inte slopa artiklar och utföra delplockning.

### <a name="issue-resolution"></a>Problemlösning

På sidan **Menyalternativ på mobil enhet** för varje menyalternativ som har ställts in för att bearbeta försäljningsorder eller överföringsorder, anger du alternativet **Tillåt delning av arbete** på snabbfliken **Allmänt** till *Ja*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Hur kan jag göra en lagerstatusändring för delkvantitetsarbete?

### <a name="issue-description"></a>Problembeskrivning

Du vill utföra en lagerstatusändring för en delkvantitet av en batch.

### <a name="issue-resolution"></a>Problemlösning

Om du vill att arbetare ska kunna göra denna ändring kan du skapa ett menyalternativ för lagerstället. På sidan **Menyalternativ på mobil enhet** skapa (eller redigera) ett menyalternativ för följande inställningar:

- **Läge:** *arbete*
- **Använd befintligt arbete:** *Nej*
- **Arbetsskapandeprocess:** *Rörelse*
- **Visa lagerstatus:** *Ja*

Du kan ställa in andra fält på sidan efter behov.
