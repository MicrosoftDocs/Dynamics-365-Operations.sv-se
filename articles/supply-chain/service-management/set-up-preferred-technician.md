---
title: Ställa in en prioriterad tekniker
description: Du kan välja valfri anställd som en prioriterad tekniker för ett serviceavtal eller en serviceorder.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3175d7e604671901674975ee6fd1debd5955e8b1
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743151"
---
# <a name="set-up-a-preferred-technician"></a>Ställa in en prioriterad tekniker 

[!include [banner](../includes/banner.md)]


Du kan välja valfri anställd som en prioriterad tekniker för ett serviceavtal eller en serviceorder. Det är dock en bra idé att lägga till arbetare i en lämplig servicegrupp, så att arbetaren inkluderas på **Utförseltavla**.

## <a name="assign-employee-to-a-dispatch-team"></a>Lägga till en medarbetare i en servicegrupp

1.  Klicka på **Personal** \> **Gemensamt** \> **Arbetare** \> **Arbetare**. Dubbelklicka på en anställd för att öppna arbetaredetaljsidan. I **åtgärdsfönstret**, klickar du på **inställningar**\>**serviceteam** för att öppna formuläret **servicearbetare**.

2.  I fältet **Serviceteam**, välj teamet som ska tilldelas arbetare i fältet 

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Tilldela en prioriterad tekniker till ett serviceavtal

1.  Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**. Dubbelklicka på ett serviceavtal att öppna detaljformuläret.

2.  På fliken **Allmänt**, välj fältet **Prioriterad tekniker** välj en medlem av en lämplig servicegrupp som den tekniker som föredras för serviceavtalet genom att använda listan.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Tilldela en prioriterad tekniker till en serviceorder

1.  Klicka på **Servicehantering** \> **Periodisk** \> **Utförseltavla**.
    

    > [!NOTE]
    > <P>I formuläret <STRONG>Utförseltavla</STRONG>, ange ett datumintervall för serviceaktiviteter som du vill se. Ange dessutom om du vill se stängda aktiviteter och huruvida du vill begränsa aktivitetslistan till grupper som du tillhör eller är behörig att övervaka. Klicka på <STRONG>OK</STRONG> för att öppna <STRONG>Utförseltavla</STRONG>.</P>



2.  Markera raden för den serviceaktivitet som du vill ändra.

3.  På fliken **Relaterad**, använd listan **Arbetare** för att tilldela en medlem av en lämplig servicegrupp som den tekniker som föredras för servicetillfället.

## <a name="see-also"></a>Se även

[Serviceavtal ](service-agreements.md)

[Skapa en serviceorder manuellt](create-service-orders-manually.md)

[Serviceavtal (formulär)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  


