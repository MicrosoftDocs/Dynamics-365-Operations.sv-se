---
title: "Importera och underhålla kreditkortstransaktioner"
description: "Detta avsnitt förklarar hur du importerar och underhåller utgiftsrelaterade kreditkortstransaktioner. Dessa transaktioner kan konfigureras att importeras automatiskt enligt ett återkommande schema, eller också importeras manuellt efter behov."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e640c9e44add5599be4a2e381b4ffd81f212889c
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="import-and-maintain-credit-card-transactions"></a>Importera och underhålla kreditkortstransaktioner

[!include [banner](../includes/banner.md)]

Utgiftsrelaterade kreditkortstransaktioner kan konfigureras att importeras automatiskt enligt ett återkommande schema. Alternativt kan transaktionerna även importeras manuellt efter behov. Kreditkortstransaktionerna importeras via dataentiteten för kreditkortstransaktioner.

Mer information om dataentiteter finns i [Dataentiteter](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Importera kreditkortstransaktioner

1. På sidan **Kreditkortstransaktioner** väljer du **Importera transaktioner**. Om du öppnar datahanteringen för första gången måste systemet uppdatera listan över dataentiteter innan du kan fortsätta.
2. Ange en unik beskrivning för importjobbet i fältet **Namn**.
3. I fältet **Källdataformat** väljer du formatet på den fil som innehåller de kreditkortstransaktioner som du vill importera.
4. Välj **Ladda upp** och leta sedan upp och välj den fil du vill importera.
5. När filen har laddats upp väljer du länken **Visa karta** i panelen för att validera mappningen av filen för kreditkortstransaktionerna samt kolumnerna för kreditkortstransaktionernas dataentitet. Om mappningsfel uppstår eller du måste ändra mappningen, använder du antingen fliken **Mappningsvisualisering** eller fliken **Mappningsinformation** för att utföra mappningsändringarna.
6. Välj **Skapa återkommande datajobb** för att automatisera kreditkortstransaktionerna. Du kan sedan välja den upprepningsfrekvens som anger hur ofta kreditkortstransaktionerna ska importeras. Välj **OK** när du är klar.
7. Välj **Importera** om du vill importera vald fil nu.
8. Om något fel skulle uppstå i samband med import kan du visa körningsloggen eller underliggande data för att se de fel som du måste åtgärda i syfte att säkerställa en lyckad import.

> [!NOTE]
> Om du måste importera mer än ett filformat måste du skapa separata importjobb för respektive formattyp.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Omtilldela kreditkortstransaktioner för uppsagda medarbetare

När en medarbetarpost raderas, avaktiveras medarbetarens Active Directory Domain Services (AD DS)-konto. Det kan emellertid fortfarande finnas kreditkortstransaktioner kvar som måste betalas och ersättas. Via sidan **Kreditkortstransaktioner** kan du omtilldela medarbetaren för samtliga kreditkortstransaktioner där tillhörande medarbetare har tagits bort.

Välj en eller flera kreditkortstransaktioner och välj sedan **Omtilldela transaktioner**. Du kan sedan välja en annan medarbetare att tilldela kreditkortstransaktionerna till. När kreditkortstransaktionerna har omtilldelats kan de väljas ut till en utgiftsrapport och betalas via den sedvanliga processen för ersättning av utgiftsrapporter.

