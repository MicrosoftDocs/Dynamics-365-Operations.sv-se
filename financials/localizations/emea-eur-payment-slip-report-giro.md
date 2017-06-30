---
title: "Betalningsblankettrapport för Europa"
description: "Det här avsnittet innehåller information om betalningsblankettrapporter för Europa."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e3fcef720fb38de45ed357e53c1ec6923f72fd63
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="payment-slip-report-for-europe"></a>Betalningsblankettrapport för Europa

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om betalningsblankettrapporter för Europa.

Funktionen för betalningsblankettrapporter finns tillgänglig för juridiska personer vars primära adressen finns i Danmark, Belgien, Norge, Schweiz eller Finland. Företag bifogar ofta utskrivna betalningsblanketter till fakturor för att tillhandahålla en betalningsreferens för bokföring och kvittning. Betalningsblanketten kan användas för projekt - eller tjänstfakturor, kravbrev, räntefakturor och kontoutdrag, utöver försäljningsfakturor och fritextfakturor.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Ange ett fordringshavar-ID (endast Danmark)
Följ dessa steg för att ange ID för fordringshavare för ditt företag. Detta nummer tillhandahålls av ditt finansinstitut. Det används som referens när kundbetalningar tas emot via finansinstitut.

1.  Klicka på **Organisationsadministration** &gt; **Inställningar** &gt; **Organisation** &gt; **Juridiska personer**.
2.  På snabbfliken **Bankkontoinformation**, i fältet **ID för FI-fordringshavare** anger du ditt unika åttasiffriga ID-nummer för fordringshavare.
3.  Stäng formuläret så att ändringarna sparas.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Skapa ett betalningsblankettformat för bilagor för fakturor, anteckningar, kravbrev och kontoutdrag
Följ dessa steg för att skapa ett format för en betalningsblankettbilagor som ska medfölja försäljningsfakturor, fritextfakturor, räntefakturor, kravbrev och kontoutdrag.

1.  Klicka på **Kundreskontra** &gt; **Inställningar** &gt; **Formulär** &gt; **Formulärinställningar**.
2.  På fliken **Faktura**, i fältet **Associerad betalningsbilaga för kundfaktura**, markera bilageformatet för betalningsblankett.
3.  På flikarna **Fritextfaktura**, **Räntefaktura**, **Kravbrev** och **Kontoutdrag** markerar du ett bilageformat för betalningskvitto före respektive dokumenttyp.
4.  Stäng formuläret så att ändringarna sparas.

Följ dessa steg för att ställa in ett format för en betalningsblankettbilagor som medföljer projektfakturor.

1.  Klicka på **Projekthantering och redovisning** &gt; **Inställningar** &gt; **Blanketter** &gt; **Blankettinställningar**.
2.  I fältet **Associerad betalningsbilaga** markerar du bilageformatet för betalningskvitto.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Tilldela ett bilageformat för betalningsblankett till ett kundkonto
När du har ställt in betalningsformatet för betalningsblanketter för försäljningsfakturor, fritextfakturor, räntefakturor, kravbrev, kontoutdrag och projektfakturor kan tilldela du särskilda format för en vald kund.

1.  Klicka på **Kundreskontra** &gt; **Allmänt** &gt; **Kunder** &gt; **Alla kunder**.
2.  Skapa en ny kund eller välj en befintlig.
3.  På snabbfliken **Faktura och leverans**, i fälten **På en kundfaktura**, **På en fritextfaktura**, **På en räntefaktura**, **På ett kravbrev**, **På en projektfaktura** och **På ett kontoutdrag** väljer du format för bilagor för betalningsblanketter som medföljer företagsdokument av respektive typ som skickas till den valda kunden.
4.  Stäng formuläret så att ändringarna sparas.





