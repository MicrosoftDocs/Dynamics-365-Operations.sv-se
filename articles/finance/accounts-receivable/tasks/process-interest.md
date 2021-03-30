---
title: Beräkna ränta
description: I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4f1ed6d0199235e946d55dfa904246c109acba42
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220141"
---
# <a name="process-interest"></a>Beräkna ränta

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor. I den här uppgiften används demonstrationsföretaget USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Ställ in ränta i bokföringsprofilen
1. I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.
2. Klicka på **Redigera**.
3. På **snabbfliken Inställningar**, i fältet **Räntekod**, välj en räntekod i den nedrullningsbara listan. Om du inte vill skapa beräkna ränta för transaktioner med denna bokföringsprofil, lämna fältet tomt. Snabbfliken **Registerbegränsning** gör det möjligt att ändra hur ränta bearbetas. Om detta fält har satts till Ja, beräknas ränta för denna bokföringsprofil.  

## <a name="calculate-interest"></a>Beräkna ränta
1. I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Ränta > Skapa räntefakturor**.
2. Du måste välja transaktionstyperna för att beräkna ränta. Alla öppna transaktioner för dessa typer inkluderas i beräkningen.  
3. Om du ställer in **Ränta** till Ja beräknas ränta på ränta. Du kanske du vill kontrollera lagar som styr beräkningen av ränta på ränta som inkluderar för dessa transaktioner.  
4. I fältet **Från datum** anger du ett datum från vilket ränta ska beräknas. Om du inte anger ett **Från datum** annulleras alla ej bokförda räntefakturor och ränta beräknas på nytt från transaktionsdatum.
5. I fältet **Till datum** anger du ett datum till vilket ränta ska beräknas.
6. Välj ett alternativ i fältet **Använd bokföringsprofil från**. Det finns tre alternativ för bokföringsprofil:
    - Konto – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura. 
    - Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.
    - Transaktion – Använd bokföringsprofilen från den transaktioner där ränta beräknas för varje räntefaktura. Transaktioner som inte har en tilldelad bokföringsprofil kommer använda bokföringsprofilen som angetts i området Redovisning och moms i formuläret Parametrar för kundreskontra.  
7. Expandera snabbfliken **Poster som ska ingå**.
8. Klicka på **Filter**.
9. I fältet **Kriterier**, ange ett kund-ID. Till exempel "US-001".
6. Klicka på **OK**.
7. Klicka på **OK**.

## <a name="print-interest-notes"></a>Skriv ut räntefakturor
1. I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Ränta > Granska och beräkna räntefakturor**.
2. Välj Skapad i fältet **Status**.
3. Välj Ej utskrivet i fältet **Utskriven.**
4. Klicka på **Skriv ut**.
5. Expandera snabbfliken **Poster som ska ingå**.
6. Klicka på **OK**.
7. Stäng sidan.

## <a name="post-the-interest-note"></a>Bokför räntefakturan
1. Välj en räntefakktura som är klar att bokföra (status skapas).
2. Klicka på **Bokför**.
3. Ange bokföringsdatumet för räntefakturan. Välj Ja för att skapa en redovisningstransaktion för varje räntefaktura. Om du inte mväljer Ja ackumuleras räntan på alla räntefakturor till kunden och bokförs i redovisningen i en enda transaktion.  
4. Expandera snabbfliken **Poster som ska ingå**.
5. Klicka på **OK**.
6. Välj Bokförd i fältet **Status.**



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]