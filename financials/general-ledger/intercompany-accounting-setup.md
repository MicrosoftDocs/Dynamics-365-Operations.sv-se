---
title: "Koncerninterna redovisningsinställningarna"
description: "Det här avsnittet beskrivs hur du ställer in koncernintern redovisning så att du kan använda koncerninterna journaler för redovisningallokeringar och redovisningsjournaler som dagboksjournaler, leverantörsfakturajournaler och betalningsjournaler."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Koncerninterna redovisningsinställningarna

Det här avsnittet beskrivs hur du ställer in koncernintern redovisning så att du kan använda koncerninterna journaler för redovisningallokeringar och redovisningsjournaler som dagboksjournaler, leverantörsfakturajournaler och betalningsjournaler.

Koncerninterna journaler kan skapas under olika förhållanden som för dagboksjournaler fakturajournaler för leverantören, och redovisningallokeringar centraliserade betalningar. Om du vill aktivera dessa scenarier måste du ställa in koncernintern redovisning.

## <a name="define-main-accounts"></a>Definiera huvudkonton
Först måste du skapa koncerninterna huvudkonton som ska användas för redovisningsposter för skulder och fordringar. Det är en bra idé att använda unika huvudkonton för varje företag, om du vill förenkla avstämningen och eliminering av poster för koncernintern redovisning. Om du använder en handelspartner eller motsvarande dimension för identifiering av den koncerninterna parten, definierar du dimensionen som en fast dimension för kontot definieras i koncernintern redovisning. När du ställer in huvudkonton som ska du ange den **huvud kontotyp** till **balansräkningen** på den **huvud konton** sida.

## <a name="define-journal-names"></a>Definiera journalnamn
Sedan måste du definiera ett journalnamn. Ange den **journaltyp** till **dagliga** på de **journalnamn** sida. Det är en bra idé att använda ett specifikt journalnamn för koncernintern redovisning.

## <a name="define-intercompany-accounting-setup"></a>Definiera koncerninterna redovisningsinställningarna
Den **koncernintern redovisning** sidan används för att skapa par med juridiska personer kan möjligheten till varandra. Koncernintern redovisning inställningar delas så att inställningarna visas från alla juridiska personer. Kontrollera att du är medveten om vilka juridisk person definieras som destinationsföretag jämfört med det ursprungliga företaget när du skapar ett par med ny juridisk person. När du anger koncerninterna transaktioner avgör transaktionen vilken juridisk person initiering eller transaktionens ursprung. Exempelvis ställs koncernintern redovisning in för USMF (ursprung) och USSI (målet). Om användaren är aktiv i USSI och anger en koncernintern transaktion med USMF, bokföras transaktionen inte eftersom koncernintern redovisning definieras bara på USMF som upphovsmannen. Om antingen företaget måste starta en transaktion, måste principsökning andra juridisk person för motsvarande inställningar. 

Välj den **debiteras kontot (förfallna)** och **Kreditkonto (beror på)** för både den ursprungliga och det slutliga juridisk person. Definiera vilka **journalnamn** ska användas när transaktionen skapas i destinationsföretaget. Journal för det ursprungliga företaget då redan är känd eftersom det har markerats av användaren när du skapar en koncernintern transaktion. 

Slutligen kan du välja vilken juridisk person får redovisning för att stödja belopp, till exempel kassarabatt eller vinster/förluster för centraliserade betalningar. 

Ett ömsesidigt förhållande enkelt ställas in på de **koncernintern redovisning** genom att använda de **skapa ömsesidigt förhållande** knappen efter två första juridisk person skapas. När motsvarande par skapas kopieras informationen för destinationsföretaget till det ursprungliga företaget och vice versa. Journalen som har definierats för destinationsföretaget kvar. De flesta organisationer använder samma namnkonventionen för deras journalnamn så att journalnamnet är densamma. Om journalnamnet skiljer sig, visas en varning i fältet för att visa att journalen finns inte och du kan välja en annan journal.


