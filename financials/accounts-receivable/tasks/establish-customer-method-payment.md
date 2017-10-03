--- 
title: "Upprätta en betalningsmetod för kund"
description: "Skapa en betalningsmetod för kundbetalningar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bfafcccb12112ca7cceefb65be3f942bfc307751
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-method-of-payment"></a>Upprätta en betalningsmetod för kund

[!include[task guide banner](../../includes/task-guide-banner.md)]

Skapa en betalningsmetod för kundbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder.
2. Klicka på Ny.
3. I betalningsmetodfältet infogas ett ID för betalningsmetoden.
    * Betalningsmetod-ID visas på fakturor och betalningar, vilket gör ett beskrivande nog för att förstå vilken typ av betalning registreras, och för vilket bankkonto.  
4. Ange en beskrivning i beskrivningsfältet.
5. Välj vilken betalningsstatus krävs för att betalningar som ska bokföras.
    * När du skapar en kundbetalning, den bara kan bokföras, när betalningsstatusen matchar betalningsstatusen, anger du här.  
6. Välj hur kundbetalningar ska skapas för fakturor.
    * Den här väljare, används bara när du kör ett betalningsförslag. En betalningsförslag kan användas för kundbetalningar, när du har gjort direkta debetar och drog ut medel från kundernas bankkonton.  
7. Välj betalningstyp.
    * Betalningstypen gör det enklare att bestämma om någon validering ska ske eller inte för betalningen.  
8. Välj vilka kontotypbetalningar ska bokföras i.
    * Vanligtvis ska du välja Bank för det här alternativet.  
9. Välj bankkontot som den här betalningen ska registreras till.
10. Ange vilken typ av banktransaktion som identifierar den typ av betalning som används av banken.
    * Banktransaktionstypen används under bankavstämningprocessen och kan göra en avstämning enklare.  
11. Välj om den här betalningen tillfälligt bokförs på ett interimskonto.
    * Om du vill försöka flyttaltiden för att en betalning kommer att rensa banken, använder du den överbrygga funktionen. Betalningen tillfälligt bokförs på ett redovisningskonto, tills den rensar banken, då betalningen ska flyttas till bankkontot, som du definierade här.  
12. Ange som huvudkontot som används för interimsbokningen.
    * Detta är huvudkontot som betalningen ska bokföras i, om tillfälligt med hjälp av överbrygga.  
13. Använd filformatfliken för att definiera inställningen för elektroniska betalningar.
14. Använd betalningkontrollfliken för att definiera fält som är obligatoriska.
    * Om du till exempel kräver att alla betalningar med denna betalningsmetod som ska infogas, kan du välja den väljare på den här fliken.  
15. Använd betalningatrributesfliken för att definiera betalningsattribut som du vill använda för betalningsmetoden.
16. Klicka på Spara.


