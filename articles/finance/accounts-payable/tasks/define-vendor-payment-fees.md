---
title: Definiera leverantörsbetalningsavgifter
description: Ställ in avgifter för leverantörsbetalningar.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52321851a1aa588a0bbe238e366a28d503665988
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979348"
---
# <a name="define-vendor-payment-fees"></a>Definiera leverantörsbetalningsavgifter

[!include [banner](../../includes/banner.md)]

Ställ in avgifter för leverantörsbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsavgift.
2. Klicka på Ny.
3. Skriv ett värde i fältet Avgifts-ID.
    * Avgifts-ID bör beskriva när avgiften ska användas, till exempel ”EFT_Fee”.  
4. Skriv ett värde i fältet Namn.
5. I fältet Avgiftsbeskrivning, skriv ett värde.
    * Lägg till en beskrivning med mer detaljer om när avgiften åläggs.  
6. Välj antingen leverantör eller redovisning i avgiftsfältet.
    * Huvudboken används när avgift ska åläggas din organisation.  Leverantören används när avgift ska åläggas leverantören.  
7. Ange ett huvudkonto där avgiften ska konteras.
    * Det här alternativet kan bara användas när Huvudbok har valts som Tillägg.  
8. Välj den journal som avgiften kan användas för. 
    * För en leverantörsbetalningsavgift ska du välja journalen Leverantörsutbetalning.  
9. Klicka på Spara.
10. Klicka på Betalningsavgiftsinställning.
    * Fortsätt till betalningsavgiftinställningar för att definiera när kostnaden ska användas som standard till journalen du valt.  
11. Välj Register eller Grupp eller Alla.
    * Registret används för att väljer ett enskilt bankkonto, är gruppen för att väljer en bankgrupp, och alla är att använda den här ställer in avgift för alla bankkonton  
12. Välj antingen en bankgrupp eller ett bankkonto.
    * Sökningen ska visa bankgruppen, om du markerade gruppen, och visar bankkonton, om du har valt registret.  
13. Välj ett betalsätt som ska användas för åläggandet av den aktuella betalningsavgiften.
14. Välj betalningsspecifikation för aktuell betalningsmetod
    * Betalningsspecifikationen används med överföringsbetalsätt av elektronisk fond.  
15. Välj om tillägget ska vara procent, ett belopp eller ett intervall.
16. Ange procent eller belopp för avgiften.
    * Om tillägget är en procentsats, ange procentsatsen. Om tillägget är ett belopp, ange beloppet för avgiften. Om tillägget är ett intervall, ska du använda intervallfliken de definierade tiered avgifterna.  
17. Välj den valuta som avgiften ska åläggas med i avgiftvalutafältet.
    * Valutan avser avgiften. Betalningvalutan används för att ange när avgiftregeln ska vara bedömt baserat på betalningens valuta. Anta att din bank läsa in en avgift, när en betalning görs i euro, men alla andra betalningar bedömas inte en avgift.  
18. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]