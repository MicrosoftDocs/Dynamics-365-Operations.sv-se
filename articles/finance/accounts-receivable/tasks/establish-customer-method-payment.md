---
title: Upprätta ett betalsätt för kund
description: Det här avsnittet förklarar hur du skapar en metod för betalning av kundbetalningar.
author: ShivamPandey-msft
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0dd9fb37c733730360c78b702c62adadfdc6bd476ba4c436da08c86a9ad7ff55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762149"
---
# <a name="establish-customer-method-of-payment"></a>Upprätta ett betalsätt för kund

[!include [banner](../../includes/banner.md)]

Det här avsnittet förklarar hur du skapar en metod för betalning av kundbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. I navigeringsfönstret, gå till **Moduler > Kundreskontra > Betalningsinställning > Betalsätt**.
2. Välj **Ny**.
3. I fältet  **Betalningsmetod** infogas ett ID för betalsättet. Betalningsmetod-ID visas på fakturor och betalningar, vilket gör ett beskrivande nog för att förstå vilken typ av betalning registreras, och för vilket bankkonto.  
4. Ange en beskrivning i fältet **beskrivning**.
5. Välj vilken betalningsstatus krävs för att betalningar som ska bokföras. När du skapar en kundbetalning, den bara kan bokföras, när betalningsstatusen matchar betalningsstatusen, anger du här.  
6. Välj hur kundbetalningar ska skapas för fakturor. Den här väljare, används bara när du kör ett betalningsförslag. En betalningsförslag kan användas för kundbetalningar, när du har gjort direkta debetar och drog ut medel från kundernas bankkonton.  
7. Välj betalningstyp. Betalningstypen gör det enklare att bestämma om någon validering ska ske eller inte för betalningen.  
8. Välj vilka kontotypbetalningar ska bokföras i. Vanligtvis ska du välja Bank för det här alternativet.  
9. Välj bankkontot som den här betalningen ska registreras till.
10. Ange vilken typ av banktransaktion som identifierar den typ av betalning som används av banken. Banktransaktionstypen används under bankavstämningprocessen och kan göra en avstämning enklare.  
11. Välj om den här betalningen tillfälligt bokförs på ett interimskonto. Om du vill försöka flyttaltiden för att en betalning kommer att rensa banken, använder du den överbrygga funktionen. Betalningen tillfälligt bokförs på ett redovisningskonto, tills den rensar banken, då betalningen ska flyttas till bankkontot, som du definierade här.  
12. Ange som huvudkontot som används för interimsbokningen. Detta är huvudkontot som betalningen ska bokföras i, om tillfälligt med hjälp av överbrygga.  
13. Använd fliken **Filformat** för att definiera inställningen för elektroniska betalningar.
14. Använd fliken **Betalningskontroll** för att definiera fält som är obligatoriska. Om du till exempel kräver att alla betalningar med denna betalningsmetod som ska infogas, kan du välja den väljare på den här fliken.  
15. Använd fliken **Betalningsattribut** för att definiera betalningsattribut som du vill använda för den här betalsättet.
16. Välj **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]