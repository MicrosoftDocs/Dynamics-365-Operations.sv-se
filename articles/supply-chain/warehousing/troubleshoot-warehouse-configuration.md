---
title: Felsöka distributionslagerkonfiguration
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 1dbd947f0740d22e0f79e6d5c272beb64715c8a5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814402"
---
# <a name="troubleshoot-warehouse-configuration"></a>Felsöka distributionslagerkonfiguration

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du konfigurerar i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>Jag får följande felmeddelande: "ID-nummer eller platsen är inte giltig."

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas när du skannar ett ID-nummer eller en plats.

### <a name="issue-resolution"></a>Problemlösning

Se till att licensens ID-nummer inte har reserverats av något annat. Det här problemet uppstår när värdet som en användare skannade i mobilappen för distributionslagerhantering var både en giltig plats och ett giltigt licensens ID-nummer. Det här problemet löstes emellertid i versionen 10.0.11.

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

## <a name="i-cant-use-the-warehouse-management-mobile-app-to-do-partial-picking"></a>Jag kan inte använda mobilappen för distributionslagerhantering för delplockning.

### <a name="issue-description"></a>Problembeskrivning

För försäljnings- och överföringsorder kan du inte slopa artiklar och utföra delplockning.

### <a name="issue-resolution"></a>Problemlösning

På sidan **Menyalternativ på mobil enhet** för varje menyalternativ som har ställts in för att bearbeta försäljningsorder eller överföringsorder, anger du alternativet **Tillåt delning av arbete** på snabbfliken **Allmänt** till *Ja*.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Hur kan jag göra en lagerstatusändring för delkvantitetsarbete?

### <a name="issue-description"></a>Problembeskrivning

Du vill utföra en lagerstatusändring för en delkvantitet av en batch.

### <a name="issue-resolution"></a>Problemlösning

Om du vill att arbetare ska kunna göra denna ändring kan du skapa ett menyalternativ för mobilappen för distributionslagerhantering. På sidan **Menyalternativ på mobil enhet** skapa (eller redigera) ett menyalternativ för följande inställningar:

- **Läge:** *arbete*
- **Använd befintligt arbete:** *Nej*
- **Arbetsskapandeprocess:** *Rörelse*
- **Visa lagerstatus:** *Ja*

Du kan ställa in andra fält på sidan efter behov.

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a>Dockhanteringsprofilen för en platsprofil förhindrar inte att lagertyper blandas.

### <a name="issue-description"></a>Problembeskrivning

Om du använder *policyer för leveranskonsolidering*. Du har ställt in en *dockningshanteringsprofil* för en *platsprofil*, men när arbete skapas blandas lagertyperna på den slutliga platsen.

### <a name="issue-resolution"></a>Problemlösning

Dockhanteringsprofiler kräver att arbetet delas upp i förväg. Med andra ord förväntar sig dockhanteringsprofilen att en arbetsrubrik inte har flera platser.

För att dockhanteringsprofilen ska fungera effektivt måste en arbetsrubriksbrytning ställas in.

I det här exemplet konfigureras vår dockningshanteringsprofil så att **lagertyper som inte ska blandas** ställs in på *Leverans-ID* och vi ställer in en arbetsrubriksbrytning för det:

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Välj vilken **arbetsordertyp** du vill redigera (t.ex. *inköpsorder*).
1. Välj arbetsmallen som du vill redigera.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. Öppna fliken **Sortering** och lägg till en rad med följande inställningar:
    - **Tabell** - *Tillfälliga arbetstransaktioner*
    - **Härlett register** - *Tillfälliga arbetstransaktioner*
    - **Fält** - *leverans-ID*
1. Välj **OK**.
1. Du går tillbaka till sidan **Arbetsmallar**. Klicka på **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Markera kryssrutan som är kopplad till **fältnamnet** *leverans-ID*.
1. Klicka på **Spara** i åtgärdsfönstret.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
