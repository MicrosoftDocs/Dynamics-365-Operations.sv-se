---
title: Definiera leverantörsbetalningsavgifter
description: Ställ in avgifter för leverantörsbetalningar.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109841"
---
# <a name="define-vendor-payment-fees"></a>Definiera leverantörsbetalningsavgifter

[!include [banner](../../includes/banner.md)]

Ställ in avgifter för leverantörsbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till **Leverantörsreskontra > Betalningsinställning > Betalningsavgift**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Avgifts-ID**.
    * **Avgifts-ID** bör beskriva när avgiften ska användas, till exempel ”EFT_Fee”.  
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Avgiftsbeskrivning**, skriv ett värde.
    * Lägg till en beskrivning med mer detaljer om när avgiften åläggs.  
6. I fältet **Avgift** välj antingen **leverantör** eller **redovisning**.
    * **Huvudboken** används när avgift ska åläggas din organisation. **Leverantören** används när avgift ska åläggas leverantören.  
7. Ange ett huvudkonto där avgiften ska konteras.
    * Det här alternativet kan bara användas när **Huvudbok** har valts som **Tillägg**.  
8. Välj den journal som avgiften kan användas för. 
    * För en leverantörsbetalningsavgift ska du välja journalen Leverantörsutbetalning.  
9. Klicka på **Spara**.
10. Klicka på **Betalningsavgiftsinställning**.
    * Fortsätt till **betalningsavgiftinställningar** för att definiera när kostnaden ska användas som standard till journalen du valt.  
11. Välj **Register** eller **Grupp** eller **Alla**.
    * **Registret** används för att väljer ett enskilt bankkonto, är **gruppen** för att väljer en bankgrupp, och **alla** är att använda den här ställer in avgift för alla bankkonton.  
12. Välj antingen en bankgrupp eller ett bankkonto.
    * Sökningen ska visa bankgruppen, om du markerade **gruppen**, och visar bankkonton, om du har valt **registret**.  
13. Välj ett betalsätt som ska användas för åläggandet av den aktuella betalningsavgiften.
14. Välj **betalningsspecifikation** för aktuell betalningsmetod.
    * **Betalningsspecifikationen** används med överföringsbetalsätt av elektronisk fond.  
15. Välj om tillägget ska vara procent, ett belopp eller ett intervall.
16. Ange procent eller belopp för avgiften.
    * Om **avgift** är en procentsats, ange procentsatsen. Om **avgift** är ett belopp, ange beloppet för avgiften. Om **avgift** är ett intervall, ska du använda fliken **intervall** de definierade blandade avgifterna.  
17. Välj den valuta som avgiften ska åläggas med i **avgiftsvaluta** fältet.
    * Valutan avser avgiften. Betalningvalutan används för att ange när avgiftregeln ska vara bedömt baserat på betalningens valuta. Anta att din bank läsa in en avgift, när en betalning görs i euro, men alla andra betalningar bedömas inte en avgift.  
18. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
