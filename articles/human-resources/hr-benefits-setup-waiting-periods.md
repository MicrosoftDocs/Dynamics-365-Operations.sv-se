---
title: Konfigurera vänteperioder
description: I Microsoft Dynamics 365 Human Resources väntedagar på att få en milstolpe att använda för förmånsplaner.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0e08c0c02393506e1e292676c954bdf3850029f7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468309"
---
# <a name="configure-waiting-periods"></a>Konfigurera vänteperioder

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I Microsoft Dynamics 365 Human Resources väntedagar på att få en milstolpe att använda för förmånsplaner. Till exempel tre månader från anställningsdatum, den första av varje månad eller sex månader.   

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **vänteperioder**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Väntekod** | En identifierare för vänteperioder. |
   | **Beskrivning** | En beskrivning av vänteperioden. |
   | **Väntemetod** | Välj en lämplig väntemetod i listrutan med värden. Alternativ är netto, aktuell månad, aktuellt kvartal, aktuellt år och aktuell vecka. |
   | **Månader** | Ange antalet månader du vill lägga till i väntemetoden vid beräkning av väntedatumet. |
   | **Dagar** | Ange antalet dagar du vill lägga till i väntemetoden vid beräkning av väntedatumet. |
   | **En dags väntetid** | Välj en väntedag du vill använda vid beräkning av väntedatumet. |

4. Välj **Spara**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]