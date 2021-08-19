---
title: Upphöra konfigurationer i den globala RCS-databasen
description: I det här avsnittet beskrivs hur du upphör att konfigurerar i globala RCS-databasen.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 340fc96e7dfe56da9ee8d4831a5980e3e96ec3ee0f2f5a8fb2ab72f713de9737
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712180"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Upphöra konfigurationer i den globala RCS-databasen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du upphör att konfigurerar i globala RCS-databasen. Tidigare var det bara möjligt att ta bort konfigurationer som inte längre behövs. Men nu kan du markera en släppt konfiguration som **Upphörd** i globala RCS-databasen. Med den här funktionen kan du också göra följande: 
 
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


