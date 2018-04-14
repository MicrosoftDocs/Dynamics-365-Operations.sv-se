---
title: Utgiftsrapporter och flera granskare
description: "Det här avsnittet innehåller information om utgiftsrapporter som kräver godkännande av flera personer."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 0f7592c580a21040c8b630885939ceaab3855c2c
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a>Utgiftsrapporter och flera granskare

[!INCLUDE [banner](../includes/banner.md)]

Beroende på företagets policy för godkännande av projektutgifter kanske mer än en person måste godkänna utgiftsrapporter som har skickats av en medarbetare. När du anger arbetsflödesprocessen för godkännande av utgiftsrapport kan du lägga till arbetsflödeselement som inkluderar uppgifter eller steg för en eller flera godkännare av utgiftsrapporter. Du kan till exempel kräva att alla utgiftsrapporter först godkänns av chefen för medarbetaren som skickade rapporten och av sedan leverantörsreskontrakoordinatorn.

Om du bestämmer dig för att kräva flera godkännare av utgiftsrapporter kan du lägga till olika arbetsflödeselement på något av följande sätt:

- Lägg till ett godkännandeelement som har ett steg. Steget kan till exempel kräva att en utgiftsrapport tilldelas en användargrupp och att den godkänns av 50 procent av medlemmarna i användargruppen.
- Lägg till ett godkännandeelement som har flera steg. Godkännandeelementet kan till exempel ha följande steg:

    1. Chefen för medarbetarens som skickade utgiftsrapporten godkänner den.
    2. Leverantörsreskontraansvarig verifierar kvitton och rapportens utgiftsposter.
    3. Budgetägaren godkänner utgiftsrapporten.

- Lägg till flera godkännandeelement, var och en har ett steg. Till exempel kan du lägga till ett separat godkännandeelement för var och ett av följande steg:

    1. Medarbetarens chef godkänner utgiftsrapporten.
    2. Budgetägaren godkänner utgiftsrapporten.

