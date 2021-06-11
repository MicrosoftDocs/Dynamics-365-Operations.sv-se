---
title: Konfigurera avdrag
description: Använd avdrag i Microsoft Dynamics 365 Human Resources för att fastställa hur mycket, om det finns någon, dra av från en medarbetares lön för varje förmån.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fac1624ce3a88b9fb4adcf303860e82f9d9165b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055566"
---
# <a name="configure-deductions"></a>Konfigurera avdrag

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Använd avdrag i Microsoft Dynamics 365 Human Resources för att fastställa hur mycket, om det finns någon, dra av från en medarbetares lön för varje förmån. Avdrag har giltighetsdatum så att du kan spara en historisk post med avdragsinformation. 

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **avdrag**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Avdrag** | Ett unikt ID som används för att identifiera förmånsavdrag. |
   | **Beskrivning** | En beskrivning för avdraget. |
   | **Giltighet** | Startdatumet. Standardvärdet är det aktuella systemdatumet. |
   | **Förfallotid** | Slutdatumet. Standardvärdet är 12/31/2154, vilket betyder aldrig. |
   | **Rubrik** | Den rubrikkod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning. Detta används när du använder en tredje parts löneleverantör. |
   | **Referens för medarbetarens löneavdrag** | Den avdragskod från lönesystemet som det här avdraget använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning. |
   | **Beloppsrubrik** | Den rubrikkod från lönesystemet som det här avdragsbelopp använder för medarbetarens del av avdraget vid bearbetning av förmåner i samband med lönekörning. Detta används normalt när du använder en tredje parts löneleverantör. |
   | **Kan radera** | Anger om ett exporterat värde från Dynamics 365 for Finance and Operations kan orsaka att värdet raderas i lönesystemet. |
   | **Sammankopplade kolumner** | Anger om huvud- och avdragsbelopp i kopplade angränsande kolumner till lönesystemet ska exporteras. |
   | **Ändringens giltighetsdatum** | Det datum när ändringar i förmånsavdragen börjar gälla. På detta datum ändrar systemet automatiskt avdraget av förmånen och uppdaterar alla förmånsplaner som associeras med detta avdrag, förutsatt att du kör en **uppdatering av ändring av avdrag**. |
   | **Ändringen av avdrag har slutförts** | Kryssrutan **Ändring av avdrag slutförd** kommer att markeras automatiskt när ändringen av förmånsavdrag har slutförts genom Bearbetning av uppdaterade prisändringar. |
   
4. Om du vill spåra och underhålla ändringar i inställningarna för förmånsgrad **åtgärder** och välj sedan **underhåll versioner**.

5. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]