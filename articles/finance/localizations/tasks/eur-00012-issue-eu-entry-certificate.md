---
title: EUR-00012 Utfärda ett EU-mottagningskvitto
description: Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41ede621fdb36d39efc79788cd2da77aacfc282895dd84d572b99f4528456643
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768243"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a>EUR-00012 Utfärda ett EU-mottagningskvitto

[!include [banner](../../includes/banner.md)]
Den här proceduren beskriver hur du aktiverar ett EU-mottagningskvitto genom att konfigurera ett kundkonto som ska använda mottagningskvitton och genom att utfärda ett certifikat. Proceduren har skapats med demodataföretaget DEMF.


## <a name="enable-entry-certificate-management"></a>Aktivera hantering av mottagningskvitton
1. Gå till Kundreskontra > Inställningar > Parametrar för kundreskontra.
2. Klicka på fliken Leveranser.
3. Expandera avsnittet Mottagningskvitto.
4. Välj Ja i fältet Aktivera hantering av mottagningskvitton.
5. Välj Ja i fältet Aktivera utfärdande av mottagningskvitton.
6. Klicka på fliken Nummersekvenser.
7. Leta upp och välj mottagningskvittoraden i listan.
8. I fältet Nummersekvenskod anger du eller väljer ett värde.

## <a name="set-up-a-customer"></a>Ställ in en kund
1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel efter fältet Konto med värdet "DE-015".
3. Öppna information om kundkontot.
4. Klicka på Redigera.
5. Expandera faktura- och leveransavsnittet.
6. Välj Ja i fältet Mottagningskvitto krävs.
7. Välj Ja i fältet Utfärda mottagningskvitto.
8. Klicka på Spara.

## <a name="create-an-eu-entry-certificate-automatically"></a>Skapa ett EU-mottagningskvitto automatiskt
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
4. Klicka på OK.
5. Ange eller välj ett värde i fältet Artikelnummer.
6. Klicka på Spara.
7. Klicka på Plocka och packa i åtgärdsfönstret.
8. Klicka på Bokför följesedel.
9. Expandera avsnittet Parametrar.
10. Välj Alla i fältet Kvantitet.
11. Avmarkera kryssrutan Utfärda mottagningskvitto.
    * Ett mottagningskvitto kan utfärdas under bokföringen av följesedeln eller under orderfaktureringen. Lämna kryssrutan Utfärda mottagningskvitto avmarkerad om du vill utfärda det senare.  
12. Klicka på OK.
13. Klicka på OK.
14. Klicka på Faktura i åtgärdsfönstret.
15. Klicka på Faktura.
    * Kontrollera att kryssrutorna Mottagningskvitto krävs och Utfärda mottagningskvitto i avsnittet Översikt är markerade.  Du kan också markera kryssrutan Skriv ut mottagningskvitto om du vill tillåta att kvittot skrivs ut.  
16. Klicka på OK.
17. Klicka på OK.
18. Klicka på Faktura i åtgärdsfönstret.
19. Klicka på Faktura.
20. Klicka på Faktura i åtgärdsfönstret.
21. Klicka på Visa utfärdade mottagningskvitton.
22. Klicka på Skriv ut.
23. Stäng sidan.
24. Klicka på Ändra status.
25. Välj ett alternativ i fältet Ny status.
26. Klicka på OK.
27. Stäng sidan.

## <a name="create-an-eu-entry-certificate-manually"></a>Skapa ett EU-mottagningskvitto manuellt
1. Klicka på Faktura i åtgärdsfönstret.
2. Klicka på Skapa mottagningskvitto.
3. Klicka på OK.
4. Klicka på Faktura i åtgärdsfönstret.
5. Klicka på Visa utfärdade mottagningskvitton.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]