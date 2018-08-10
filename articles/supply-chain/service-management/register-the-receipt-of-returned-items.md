---
title: Registrera inleverans av returnerade artiklar
description: "Du kan registrera inleverans av returnerade artiklar med formuläret Införselöversikt eller Registration."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 550b59a64fb0e81a56d6fea921e1b1df20c5f6e6
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="register-the-receipt-of-returned-items"></a>Registrera inleverans av returnerade artiklar 

[!include [banner](../includes/banner.md)]


Du kan registrera inleverans av returnerade artiklar på två sätt. Den första metoden är en lagerinleveransprocess som använder formuläret **Införselöversikt**. Andra använder formuläret **Registrering**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Registrera inleverans av returnerade artiklar i formuläret Införselöversikt

Du kan använda formuläret **Införselöversikt**för att identifiera en returleverans genom dess RMA-numret (Return Material Authorization). Om ett journalnamn definieras på fliken **Inställning**och journalrader som motsvarar de rader som väljs i formuläret **Införselöversikt** finns, skapas en ny journalrubrik när du klickar på **Starta införsel**.

1.  Klicka på **Lagerhantering** \> **Periodisk** \> **Införselöversikt**.

2.  I fältet **inställningsnamn** väljer du **returorder**, och klickar sedan på **uppdatering**.
    

    > [!TIP]
    > <P>Du kan använda fälten <STRONG>Intervall</STRONG> för att begränsa sökresultatet. Du kan ange eller välja RMA-numret i fältet <STRONG>RMA-nummer</STRONG> för ett visst resultat. Du kan ange och spara en uppsättning filter som ska begränsa vilka inkommande införsel som visas klickar du på fliken <STRONG>inställningar</STRONG>. Tillgängliga filtren är typer, lagerställen och dockningsstationer.</P>

    

    > [!WARNING]
    > <P>Returneraordrar kan inte blandas med andra inleveranstyper i formuläret <STRONG>Införselöversikt</STRONG>. Därför kommer referensen alltid att vara försäljningsorder, men inga försäljningsorder-ID ska anges i journalrubriken.</P>



3.  I rutnätet **Inleveranser**, leta upp den rad som matchar den returnerade artikeln och markera rutan i kolumnen **Välj för införsel**.

4.  Om du vill undanta vissa rader från returinleveransen, t.ex. artiklar från den ursprungliga ordern som inte har inkluderats i returen, avmarkerar du motsvarande kryssrutor **Välj för införsel** i tabellen **Rader** i den nedre delen av formuläret.

5.  Klicka på **Start införsel** om du vill skapa en införseljournal.
    

    > [!NOTE]
    > <P>Du kan markera flera returorder och inkludera dem alla i en enda inleveransprocess. Varje returorderrad kopieras till motsvarande journalrad för artikelinleverans.</P>

    

    > [!NOTE]
    > <P>Du kan också manuellt skapa en införseljournal med hjälp av formuläret <STRONG>Artikelinförsel</STRONG>. 



6.  Klicka på **Lagerhantering** \> **Journaler** \> **Artikelinförsel** \> **Artikelinförsel**.

7.  Välj införseljournalen som du just skapat, och klicka sedan på **Rader** för att öppna formuläret **Journalrader, platser**.

8.  På fliken**Allmänt**, justera antalet i fältet **Kvantitet** om det behövs, och sedan tilldela en dispositionskod i fältet **Dispositionskod**.
    
    Alternativt kan du välja kryssrutan **Karantänhantering** om du vill att de returnerade artiklarna som skickas via en inspektionprocess i samband med en karantänorder.
    

    > [!NOTE]
    > <P>Om du skickar de returnerade artiklarna genom karantän, kan du inte ange en dispositionskod.</P>



9.  Klicka på knappen **Validera**.

10. Om det inte finns några fel i valideringsprocessen klickar du på **Bokföra**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Registrera inleverans av returnerade artiklar i formuläret Registrering

Ett alternativ till att använda formuläret **Införselöversikt** kan du använda formuläret **Registrering** om du vill registrera inleverans av returnerade artiklar.

1.  Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**. Skapa en ny returorder eller öppna returordern från listan. På snabbfliken **Rader**, välj returorderrad. Klicka på **uppdatera**, och klicka sedan på **registrering**.

2.  Tilldela en dispositionskod i fältet **Dispositionskod** och klicka sedan på **OK**.
    

    > [!NOTE]
    > <P>Det går inte att skicka artikeln för inspektion som en karantänorder med hjälp av formuläret <STRONG>Registrering</STRONG>.</P>



3.  I rutnätet **transaktioner**, välj den transaktion som ska registreras.

4.  I rutnätet **registrera nu** klickar du på **Lägg till**. Upprepa de tidigare två stegen tills alla returnerade artiklar visas i **Registrera nu**.

5.  Klicka på **Bokför alla**

## <a name="see-also"></a>Se även

[Införselöversikt (formulär)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))

  



