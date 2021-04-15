---
title: Skapa en leasinggrupp
description: Det här ämnet innehåller information om hur du konfigurerar leasinggrupper. Leasinggrupper krävs för att skapa nya leasingar.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5d5efb02c95d9368fbc178cfd9bcd7ce088d1c66
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816062"
---
# <a name="create-a-lease-group"></a>Skapa en leasinggrupp

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om hur du konfigurerar leasinggrupper. Leasinggrupper krävs för att skapa nya leasingar. Leasingböcker associeras med varje leasinggrupp. Leasingböcker avgör vilka standardböcker som måste skapas för varje leasing. Du kan tilldela specifika konton till en leasinggrupp på sidan **Parametrar för bokföring av leasing**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Skapa en leasingbok och lägga till en leasinggrupp

1. Gå till **Leasing av tillgångar \> Konfigurera \> Leasinggrupper**.
2. I åtgärdsfönstret, välj **Ny** för att lägga till en ny leasinggrupp. En rad läggs till i rutnätet.
3. Ange ett värde i fältet **Leasingrupp** på den nya raden.
4. I fältet **Beskrivning** anger du ett värde.

Den information som du just har lagt till läggs till i fältet **Leasinggrupp** på sidan **Lägg till leasing**.

## <a name="associate-a-book-with-a-lease-group"></a>Associera en bok med en leasinggrupp

När du har skapat leasinggrupper kan du tilldela böcker till varje grupp. När du skapar en leasing och tilldelar den till en leasinggrupp, skapar systemet en uppsättning planer för varje bok som associeras med denna leasinggrupp.

> [!NOTE]
> Du måste konfigurera böcker innan de kan tilldelas till en leasinggrupp.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Leasinggrupp**.
2. Välj en leasinggrupp och välj sedan **Böcker**.
3. Välj **Ny** och i fältet **Boktyp** väljer du sedan den bok som ska tilldelas leasinggruppen. Du kan tilldela flera böcker till en leasinggrupp om en leasing måste redovisas på olika sätt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]