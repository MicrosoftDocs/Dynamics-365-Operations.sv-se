---
title: Betalningskontrollöversikt
description: Den här artikeln innehåller information om betalningskontroll, som används för att generera en elektronisk lista med checkar som kan skickas till en bank.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 51603df2847f4c21910a718186accca27e30ca67
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512348"
---
# <a name="positive-pay-overview"></a>Betalningskontrollöversikt

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om betalningskontroll, som används för att generera en elektronisk lista med checkar som kan skickas till en bank. 

Du kan använda betalningskontroll för att generera en elektronisk lista med checkar som kan skickas till en bank. Betalningskontrollfiler kan hjälpa bankerna att förhindra checkbedrägerier. Du ställer in betalningskontroll för att generera en elektronisk lista med checkar varje gång checkarna skrivs ut. När en check sedan visas för banken, jämför banken checken med listan med checkar som tidigare har skickats in. Om checken matchar en check i listan behandlar banken checken. Om checken inte matchar en check in listan kvarhåller banken checken för granskning.

Betalningskontrollfil kallas också SafePay. 

Betalningskontrollfiler kan innehålla känslig information om betalningsmottagare och checkbelopp. Se därför till att du använder lämpliga säkerhetsåtgärder från det att filerna skapas tills det att de tas emot av banken. Betalningskontrollfiler hämtas enligt hämtningsinstruktionerna för webbläsaren. 

Betalningskontrollfiler skapas genom att använda dataentiteter. Innan du skapar en betalningskontrollfil, måste du ställa in transformeringsformaten för den XML som översätter data till ett format som banken kan förbruka. 

För varje bankkonto som du vill skapa information om betalningskontroll för måste du tilldela betalningskontrollformatet. När du har genererat betalningarna kan du generera en betalningskontrollfil för en enda juridisk person och ett enskilt bankkonto. Du kan även generera betalningskontrollfiler för flera juridiska personer och bankkonton samtidigt. 

När checkarna som anges i en betalningskontrollfil har betalats får du ett bekräftelsenummer från banken. Sedan kan du bekräfta betalningskontrollfilen i Microsoft Dynamics 365 for Finance and Operations. 

Om du måste ändra en betalningskontrollfil kan du sedan återkalla den. Sedan, för varje check i betalningskontrollfilen återställs fältet som anger om denna check har inkluderats i en betalningskontrollfil.

Mer information finns i [Ställa in och generera betalningskontrollfiler](set-up-generate-positive-pay-files.md).



