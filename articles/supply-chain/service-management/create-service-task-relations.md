---
title: Skapa serviceuppgiftsrelationer
description: Du kan koppla serviceuppgifter till serviceavtal eller serviceorder för att beskriva serviceuppgiften som ska slutföras för avtalet eller serviceordern.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80980d83248612037999c665b6058c4d0bbf6a7c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678246"
---
# <a name="create-service-task-relations"></a>Skapa serviceuppgiftsrelationer    

[!include [banner](../includes/banner.md)]

Du kan koppla serviceuppgifter till serviceavtal eller serviceorder för att beskriva serviceuppgiften som ska slutföras för avtalet eller serviceordern. Den här informationen är tillgänglig för servicetekniker och kunder.

## <a name="create-a-relation-with-a-service-agreement"></a>Skapa en relation med ett serviceavtal

1.  Gå till **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.

2.  Välj ett befintligt serviceavtal eller skapa ett nytt serviceavtal.

3.  Klicka på knappen **Serviceuppgifter**.

4.  I formuläret **serviceuppgifter** tryck på **Ny** för att skapa en ny rad och välj sedan en serviceuppgift i listan **serviceuppgift** för att koppla serviceuppgiften till serviceavtalet.

5.  På fliken **Beskrivning** anger du eventuella interna eller externa anteckningar i fritextfälten.

6.  Stäng formuläret om du vill spara posten.

Upprepa proceduren tills du har skapat alla nödvändiga serviceuppgiftsrelationer för serviceavtalet. Nu kan du specificera vilka serviceuppgifter som ska höra till vilka kopplade avtalsrader.

En serviceuppgiftsrelation som skapas i ett serviceavtal är tillgänligt från alla serviceorder som är kopplade till serviceavtalet.

## <a name="create-a-relation-with-a-service-order"></a>Skapa en relation med en serviceorder

1.  Klicka på **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Välj en befintlig serviceorder eller skapa en ny serviceorder.

3.  Klicka på knappen **Serviceuppgifter**.

4.  I formuläret **serviceuppgifter** tryck på **Ny** för att skapa en ny rad och välj sedan en serviceuppgift i listan **serviceuppgift** för att koppla serviceuppgiften till serviceorder.

5.  På fliken **Beskrivning** anger du eventuella interna eller externa anteckningar i fritextfälten.

6.  Stäng formuläret om du vill spara posten.

Upprepa proceduren tills du har skapat alla nödvändiga serviceuppgiftsrelationer för serviceordern. När du skapar serviceorderrader kan du välja den serviceuppgift för vilken du skapade relationen.

Serviceuppgiftsrelationer som skapas i en serviceorder är tillgängliga i den specifika serviceordern.

## <a name="see-also"></a>Se även

[Serviceuppgifter – översikt](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]