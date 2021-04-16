---
title: Felsök anskaffnings- och källarbetsflöden
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med anskaffnings- och källarbetsflöden.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 100adef4dfd257ba86dd394b401766d2cb00394c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832044"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Felsök anskaffnings- och källarbetsflöden

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med anskaffnings- och källarbetsflöden.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Ett fel uppstod när en inköpsorder skickas igen till arbetsflödet efter en ändring: "ändringar av inköpsordern X tillåts endast i utkastläge när ändringshanteringen aktiveras"

Det här problemet uppstår endast om inköpsordern har statusen *bekräftat* innan du begärde ändringar. Om du begär ändringar medan inköpsordern är i ett tillstånd *godkänt* kan arbetsflödet bearbetas.

### <a name="error-description"></a>Felbeskrivning

Följande fel uppstår i arbetsflödet när en inköpsorder skickas igen efter en ändring:

> Stoppat (fel): X ++, undantag: ändringar av inköpsordern PO0000569 tillåts endast i utkast när ändringshantering aktiveras på<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Problemlösning

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Problemet kommer att åtgärdas genom [den här artikeln i Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade.

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Om en leveranspåminnelse annulleras på en inköpsorder där ändringshantering har aktiverats, skickas inköpsordern till ett bekräftat tillstånd.

### <a name="issue-description"></a>Problembeskrivning

För en inköpsorder som är föremål för ändringshantering, om den enda ändringen som begärs är annulleringen av en leverans som rest på en eller flera av raderna, skickas inköpsordern direkt till ett tillstånd *bekräftat* när den godkänns och ingen journal skapas.

### <a name="issue-resolution"></a>Problemlösning

Annullering av en leveranspåminnelse påverkar inte innehållet i bekräftelsejournalen. Den här funktionen ska användas när raden har inlevererats delvis och den resterande kvaliteten ska annulleras i processteg efter det att inköpsordern har bekräftats med leverantören.

Om detta ska avspeglas på inköpsorderbekräftelsen ska kvantiteten justeras på inköpsorderraden så att bekräftelsen blir nödvändig. Om inget har mottagits på raden kan du ta bort kvantiteten. I det här fallet krävs en ombekräftelse.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>Annullerade inköpsorder visas i utkast listan på arbetsytan för förberedelse av inköpsorder.

### <a name="issue-description"></a>Problembeskrivning

När du har avbrutit inköpsorder som *bekräftat* visas de inställda inköpsorder fortfarande i listan över utkast till inköpsorder i arbetsordern **Inköpsorderförberedelse**.

### <a name="issue-resolution"></a>Problemlösning

Det här problemet uppstår endast för inköpsorder som är föremål för ändringshantering. Det beror på att annulleringen betraktas som en ändring som måste godkännas. Godkännandet kan utföras automatiskt av systemet. Därför är processen att skicka den annullerade inköpsordern till arbetsflödet för godkännande så att den kan gå till ett *godkänt* tillstånd. Vid den tidpunkten visas inköpsordern inte längre i listan med utkast till inköpsorder i arbetsytan **Inköpsorder förberedelse**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]