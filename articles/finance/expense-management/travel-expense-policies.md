---
title: Definiera utgiftspolicyer
description: Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389725"
---
# <a name="define-expense-policies"></a>Definiera utgiftspolicyer

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

## <a name="policy-tips"></a>Policytips
Här följer några förslag som kan hjälpa dig när du skapar nya policyer för utgiftshantering. 
* Principer är giltighetsdatum och börjar inte gälla om policyn skapas med ett datum efter det datum då kostnaden inträffade. Om du till exempel skapar en ny policy idag för att upprätthålla en maximal måltidskostnaden av 50 USD, kontrolleras inte alla befintliga utgifter som anges i igår mot den här policy.
* När du skapar en policy för en utgiftskategori som kan specificeras, bör du lägga till ett villkor för utgiftsradtypen. Vissa policyer t.ex. krav på inleverans, kanske inte stämmer överens med specificerade rader och ska bara användas på rubrikraden eller en rad som inte har specificerats. 
* Utgiftshanteringspolicyer utvärderas mot källentiteten som standard. I koncerninterna scenarier kan du istället ställa in policyn så att den utvärderas mot målentiteten (lånande entitet). Om du vill köra policyerna mot målentiteten aktiverar du funktionen "Utvärdera utgiftspolicy mot lånande juridisk person" i arbetsytan **Funktionshantering**.

## <a name="when-to-evaluate-policies"></a>När policyer ska utvärderas

I parametrar för utgiftshantering finns det ett alternativ som antingen utvärderar utgiftshanteringspolicyer när en rad sparas eller när en utgiftsrapport skickas. Om du väljer att utvärdera när en rad sparas ser du till att användarna har tidigare insyn i vad de behöver göra för att slutföra sina utgiftsrapporter samtidigt. Annars kan du fördröja policyutvärdering och spara tid om du har validering inträffat i slutet, under inlämning till arbetsflödet.
