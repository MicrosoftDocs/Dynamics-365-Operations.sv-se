---
title: Definiera utgiftspolicyer
description: "Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a>Utgiftspolicy

[!include[banner](../includes/banner.md)]

Du kan definiera policyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner. Om du använder utgiftsprinciper kan det hjälpa dig att hantera dina utgifter på ett effektivt sätt. 

Du kan till exempel ange en policy för hotellutgifter i New York, som anger att utgiften per natt inte får överstiga 250 USD. Om en medarbetare skickar in en utgiftsrapport eller en reserekvisition där rumstaxan överstiger detta belopp, kommer systemet att meddela medarbetaren att policybeloppet för utgiften har överskridits. Du kan konfigurera det meddelande som medarbetaren får i samband med att du definierar policyn. 

Du kan definiera tre olika typer av policy: 

 - Varnings – Tillåter medarbetaren att skicka in en utgiftsrapport eller en reserekvisition, men utgiften markeras för samtliga godkännare samt  
 för senare rapportering. 
 - Fel – Kräver att medarbetaren reviderar utgiften så att denna uppfyller policykraven innan utgiftsrapporten eller reserekvisitionen lämnas in. 
 - Motivering – Kräver att medarbetaren eller en chef anger en motivering för att policybeloppet har överskridits innan utgiftsrapporten eller reserekvisitionen lämnas in. 

Du kan också ange ett datumintervall för när utgiftspolicyerna är giltiga. Exempelvis kan flygpriserna mellan Sverige och New York vara höga under semestertider. Du kan definiera en regel för flygutgifter som begränsar flygkostnaderna till New York till 5 000 DKK, och du kan även ange att denna regel ska vara giltig mellan den 15 mars och den 15 september. 

