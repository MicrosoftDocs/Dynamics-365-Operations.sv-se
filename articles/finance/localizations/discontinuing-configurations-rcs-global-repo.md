---
title: Upphöra konfigurationer i den globala RCS-databasen
description: I den här artikeln beskrivs hur du upphör att konfigurerar i globala RCS-databasen.
author: gionoder
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace
ms.openlocfilehash: b0605f56058e3c93ea088ee8386ba26c4ce2b65a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272349"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Upphöra konfigurationer i den globala RCS-databasen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du upphör att konfigurerar i globala RCS-databasen. Tidigare var det bara möjligt att ta bort konfigurationer som inte längre behövs. Men nu kan du markera en släppt konfiguration som **Upphörd** i globala RCS-databasen. Med den här funktionen kan du också göra följande: 
 
 - Ange i förväg meddelanden när en konfiguration har planerats att upphöra.
 - Inkludera tillämpliga uppgifter om ersättningskonfigurationen.
 - Ange ett datum för **Stöds till** för att den specifika konfigurationen ska informera användaren när den kommer att avbrytas.

När du upphör att använda en konfigurationsversion kan du ange följande valfria information:

  - **Ersättningskonfiguration**
  - **Konfigurationsversion för ersättning**
  - **Fritextnotering**: Använd det här fältet för att tillhandahålla dokumentationslänkar eller referenser
  - **Stöds tills**: Det här fältet innehåller det föreslagna datum fram till vilket aktuell konfiguration/version kommer att stödjas. Datumet måste uppdateras manuellt.
  
Om du vill avbryta konfigurationen utför du följande steg. 

1. Välj om du vill upphöra att använda en enda version eller alla versioner med samma inställningar i en operation genom att ange **Alla versioner** till **Ja**. 
2. Ange parametern **Upphör** till **Ja**.
3. Välj **OK** om du vill upphöra konfigurationerna. Fältet **Utgångsdatum** fylls då i när du sparar ändringarna.

![Upphöra med konfigurationsinformation.](media/Discontinue-details-2.png)
  
Du kan när som helst återställa konfigurationen till **Delad** eller justera annulleringsinformation. Om du delar en konfiguration anger du datumet **Stöds till** och all annan information relaterad till avvecklingen för att ange dina planer för framtida avveckling.

Om du vill dela information om en planerad avbrytning, innan konfigurationen faktiskt avbryts, kan användaren fylla i alla fält som är relaterade till ersättning men lämna parametern **Upphör** anges till **Nej**.

> [!NOTE]
> När någon av dem avbryts begränsas inte operationer med konfigurationer. De här fälten är information om du kan fortsätta att importera, köra eller härleda konfigurationerna.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Finance stöder visning av denna information från version 10.0.14

Startar i version 10.0.14, Dynamics 365 Finance stöder visa annulleringsinformation. På sidan **globala databas** kan du visa aktuell information som är relaterad till annullering. Som standard filtreras konfigurationer som upphör att vara utfilterade.
  
Sidan **Importerade konfigurationer** (ERSolutionTable) visar konfigurationer som redan upphörde när det importerades. För de konfigurationer som upphör att köras efter importen kan information om förkonteringen synkroniseras genom att jobbet **Importkonfigurationer uppdatera**.


