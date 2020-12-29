---
title: Föra returnerade artiklar genom inspektionen
description: Föra returnerade artiklar genom inspektionen
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bdc42f9c5ece8e2c2570cadf623f52648b7b174e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437829"
---
# <a name="take-returned-items-through-inspection"></a>Föra returnerade artiklar genom inspektionen 

[!include [banner](../includes/banner.md)]


1.  Klicka på **Lagerhantering** \> **Periodisk** \> **Kvalitetshantering** \> **Karantänorder**.

2.  Leta upp den orderrad som motsvarar den returnerade artikel som du inspekterar.

    > [!NOTE]
    > <P>En karantänorder kan bara associeras med ett enda artikelnummer. Om 10 artiklar med olika artikelnummer returneras i en enda leverans och skickas till karantän skapas 10 enskilda karantänorder.</P>

3.  Gör ett val i fältet **Dispositionskod** om du vill ange vad som ska göras med artikeln och hur du hanterar den relaterade ekonomiska transaktionen när du har undersökt artikeln. Du kan till exempel välja att returnera artikeln till lagret och återbetala kunden, kassera artikeln och skicka ett byte till kunden eller returnera artikeln till kunden utan kredit.
    
    > [!NOTE]
    > <P>Om samma dispositionskod inte kan anges för flera returnerade artiklar från en batch med artiklar som har samma artikelnummer, måste du dela karantänordern (<STRONG>Funktioner</STRONG> &gt; <STRONG>Dela</STRONG>) för att kunna tilldela olika dispositionskoder till varje delbatch.</P>


4.  När du är klar med inspektionen klickar du på **Rapportera som färdigt** för att släppa de returnerade artiklarna och skapa en post i en artikelinförseljournal. Den person eller avdelning som tar emot artiklarna bearbetar sedan journalen för att artiklarna ska kunna returneras till lagret.
    
    –eller–
    
    Avsluta karantänordern och flytta tillbaka artiklarna till lagret direkt med någon av knappfunktionerna för **Lager**.

5.  Stäng formuläret så att ändringarna sparas.

## <a name="see-also"></a>Se även

[Ange hur returnerade artiklar ska avyttras](specify-how-to-dispose-of-returned-items.md)

  


