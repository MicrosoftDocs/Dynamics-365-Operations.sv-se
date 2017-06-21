---
title: "Inställningar för koncernintern redovisning"
description: "Det här avsnittet beskriver hur du ställer in koncernintern redovisning så att du kan använda koncerninterna journaler för redovisningsallokeringar och redovisningsjournaler, till exempel dagboksjournaler, leverantörsfakturajournaler och betalningsjournaler."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 506c7958a90bd5a891ea9859c679fcadb64a64d4
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="intercompany-accounting-setup"></a>Inställningar för koncernintern redovisning

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du ställer in koncernintern redovisning så att du kan använda koncerninterna journaler för redovisningsallokeringar och redovisningsjournaler, till exempel dagboksjournaler, leverantörsfakturajournaler och betalningsjournaler.

Koncerninterna journaler kan skapas i olika scenarier, till exempel för dagboksjournaler, leverantörsfakturajournaler, redovisningsallokeringar och centraliserade betalningar. Om du vill aktivera dessa scenarier måste du ställa in koncernintern redovisning.

## <a name="define-main-accounts"></a>Definiera huvudkonton
Först måste du skapa koncerninterna huvudkonton som ska användas för redovisningsposter för skulder och fordringar. Det är en bra idé att använda unika huvudkonton för varje företag, om du vill förenkla avstämningen och eliminering av poster för koncernintern redovisning. Om du använder en handelspartnerdimension eller motsvarighetsdimension för att identifiera den koncerninterna parten, kan du definiera denna dimension som en fast dimension på huvudkontot som definieras i koncernintern redovisning. När du ställer in huvudkonton som ska du ange fältet **Huvudkontotyp** som **Balansräkning** på sidan **Huvudkonton**.

## <a name="define-journal-names"></a>Definiera journalnamn
Sedan måste du definiera ett journalnamn. Ange fältet **Journaltyp** som **Daglig** på sidan **Journalnamn**. Det är en bra idé att använda ett specifikt journalnamn för koncernintern redovisning.

## <a name="define-intercompany-accounting-setup"></a>Ange inställningar för koncernintern redovisning
Sidan **koncernintern redovisning** används för att skapa par med juridiska personer som agera med varandra. Inställningarna för koncernintern redovisning delas, varför inställningarna visas i samtliga juridiska personer. Kontrollera att du är medveten om vilka juridisk person som definieras som ursprungsföretag kontra det ursprungliga företaget när du skapar ett nytt par juridiska personer. När du anger koncerninterna transaktioner avgör transaktionen vilken juridisk person som initierar eller utgör transaktionens ursprung. Exempelvis ställs koncernintern redovisning in för USMF (ursprung) och USSI (målet). Om användaren är aktiv i USSI och anger en koncernintern transaktion med USMF, bokförs transaktionen inte eftersom den koncerninterna redovisningen endast definieras för USMF som upphovsmann. Om endera företag kan starta en transaktion, måste du skapa en andra juridisk person för motsvarande inställningar. 

Välj **Debetkonto (förfaller den)** och **Kreditkonto (förfaller)** för både den ursprungliga och den slutliga juridiska personen. Definiera vilka **journalnamn** som ska användas när transaktionen skapas i destinationsföretaget. Journalen för det ursprungliga företaget är redan känd eftersom den markeras av användaren när du skapar en koncernintern transaktion. 

Slutligen kan du välja den juridiska person som ska få redovisningen för stödbelopp, till exempel kassarabatt eller realiserade vinster/förluster för centraliserade betalningar. 

Ett ömsesidigt förhållande kan enkelt skapas på sidan **Koncernintern redovisning** genom att använda knappen **Skapa ömsesidigt förhållande** när det första paret juridiska personer har skapats. När motsvarande par skapas, kopieras informationen för destinationsföretaget till det ursprungliga företaget och vice versa. Journalen som har definierats för destinationsföretaget blir kvar. De flesta organisationer använder samma namnkonventioner för sina journalnamn så att journalnamnet förblir densamma. Om journalnamnet skiljer sig åt, visas en varning i fältet för att påpeka att journalen inte finns, och du kan då välja en annan journal.




