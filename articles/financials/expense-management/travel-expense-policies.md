---
title: Definiera utgiftspolicyer
description: Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04eaff110fea021ddee32be650be540894eb703b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "342441"
---
# <a name="expense-policies"></a>Utgiftspolicy

[!include [banner](../includes/banner.md)]

Du kan definiera policyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner.         
Om du använder utgiftsprinciper kan det hjälpa dig att hantera dina utgifter på ett effektivt sätt.         

Du kan till exempel ange en policy för hotellutgifter i New York, som anger att utgiften per natt inte får överstiga 250 USD.       
Om en anställd skickar utgiftsrapporter eller en reserekvisition där rumspriset överstiger detta belopp kommer systemet att meddela        
medarbetaren att policybeloppet för utgiften har överskridits. Du kan konfigurera det meddelande som medarbetaren får i samband med att du        
definierar policyn.      
        
Du kan definiera tre olika typer av policy:         
        
- Varnings – Tillåter medarbetaren att skicka in en utgiftsrapport eller en reserekvisition, men utgiften markeras för samtliga godkännare samt        
  för senare rapportering.        

- Fel – Kräver att medarbetaren reviderar utgiften så att denna uppfyller policykraven innan utgiftsrapporten eller reserekvisitionen lämnas in.       
 
  - Motivering – Kräver att medarbetaren eller en chef anger en motivering för att policybeloppet har överskridits innan utgiftsrapporten eller reserekvisitionen lämnas in.        
 
  Du kan också ange ett datumintervall för när utgiftspolicyerna är giltiga. Exempelvis flygpriserna mellan Danmark      
  och New York kan vara höga under semestertider. Du kan definiera en regel för flygpriser som begränsar      
  kostnaden för flygbiljetter till New York till 5000 DKK och du kan ange att regeln ska gälla mellan 15 mars och      
  15 september.
