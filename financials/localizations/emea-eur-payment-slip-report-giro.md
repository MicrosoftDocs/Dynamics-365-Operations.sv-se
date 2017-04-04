---
title: "Slip-betalningsrapport för Europa"
description: "Det här avsnittet innehåller information om följesedeln betalning rapporter för Europa."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264604
ms.assetid: 551e047b-4581-4a77-b470-c4f8d395c375
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: c795466753ca1515790b7961b989aac6e7d63c2c
ms.lasthandoff: 03/31/2017


---

# <a name="payment-slip-report-for-europe"></a>Slip-betalningsrapport för Europa

Det här avsnittet innehåller information om följesedeln betalning rapporter för Europa.

Funktionen betalning för insättningskvitto är tillgänglig för juridiska personer vars primära adressen i Danmark, Belgien, Schweiz, Norge eller Finland. Företag koppla ofta utskrivna betalningsdokument till fakturor en betalningsreferens för att bokföring och kvittningen. Betalningsblanketten kan användas för projekt - eller tjänstfakturor, kravbrev, räntefakturor och kontoutdrag, utöver försäljningsfakturor och fritextfakturor.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Ställ in en fordringshavare ID-nummer (Danmark)
Följ anvisningarna, verifikationsnummer företagets kreditgivare identifiering (ID). Din finansinstitut innehåller detta nummer. Den används som referens när kundbetalningar som tas emot via finansinstitut.

1.  Klicka på **Organisationsadministration**&gt;**inställningar**&gt;**organisationen**&gt;**juridiska personer som**.
2.  I den **bankkontoinformation** snabbfliken i den **ID för FI-kreditgivare** anger du ditt unika åttasiffriga fordringshavare ID-nummer.
3.  Stäng formuläret så att ändringarna sparas.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Ställa in en följesedel bilagan betalningsformat för fakturor, räntefakturor, kravbrev och kontoutdrag
Följ dessa steg för att ställa in ett format för betalningen följesedeln bifogade filer som bifogas försäljningsfakturor, fritextfakturor, räntefakturor, kravbrev och kontoutdrag.

1.  Klicka på **kundreskontra**&gt;**inställningar**&gt;**formulär**&gt;**inställningar**.
2.  På den **fakturan** fliken den **Associerad betalningsbilaga för kundfaktura**, markera betalningsformat följesedeln bilagan.
3.  I den **fritextfaktura**, **räntefakturan**, **kravbrevet**, och **konto utdraget** flikar, markera en följesedel bilagan betalningsformat för varje dokumenttyp.
4.  Stäng formuläret så att ändringarna sparas.

Följ dessa steg för att ställa in ett format för betalningen följesedeln bifogade filer som bifogas projektfakturor.

1.  Klicka på **projekthantering och redovisning**&gt;**inställningar**&gt;**formulär**&gt;**inställningar**.
2.  I den **Associerad betalningsbilaga**, markera betalningsformat följesedeln bilagan.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Tilldela en betalningsformat följesedeln bilagan till ett kundkonto
När du har ställt in betalningsformat för följesedeln bilagan för försäljningsfakturor, fritextfakturor, räntefakturor, kravbrev, kontoutdrag och projektfakturor kan tilldela du särskilda format för en vald kund.

1.  Klicka på **kundreskontra**&gt;**gemensamma**&gt;**kunder**&gt;**alla kunder**.
2.  Skapa en ny kund eller välj en befintlig kund.
3.  I den **faktura- och** på snabbfliken i den **på en kundfaktura**, **på en fritextfaktura**, **på en räntefaktura**, **på ett kravbrev**, **på en projektfaktura**, och **på ett kontoutdrag** väljer du format för betalningen följesedeln bifogade filer som kommer att medfölja varje dokument som skickas till den valda kunden.
4.  Stäng formuläret så att ändringarna sparas.



