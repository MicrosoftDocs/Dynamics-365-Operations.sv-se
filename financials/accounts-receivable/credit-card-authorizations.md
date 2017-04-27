---
title: "Kreditkortinställning, auktorisering och registrering"
description: "Den här artikeln ger en översikt över kreditkortskontroll i Microsoft Dynamics AX. Här finns information om hur du ställer in en betalningstjänst, lägger till ett kreditkort till en försäljningsorder och annullerar en auktorisering."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40d950b04511e85d05106c274d1580a3daac7af7
ms.lasthandoff: 03/31/2017


---

# <a name="credit-card-setup-authorization-and-capture"></a>Kreditkortinställning, auktorisering och registrering

[!include[banner](../includes/banner.md)]


Den här artikeln ger en översikt över kreditkortskontroll i Microsoft Dynamics AX. Här finns information om hur du ställer in en betalningstjänst, lägger till ett kreditkort till en försäljningsorder och annullerar en auktorisering.

<a name="setting-up-the-credit-card-payment-service"></a>Ställa in kreditkortbetalningtjänsten
------------------------------------------

Om du vill använda kreditkort måste du ställa in och aktivera en betalning på sidan Betalningtjänst. En betalningstjänst fungerar som en brygga mellan din juridiska person och banken som bearbetar en kunds kreditkortavgifter. Du måste arbeta med en kreditkortleverantör, som anges i fältet Betalningkoppling och ställer in ett konto med den leverantören. Du måste sedan ställa in andra alternativ på sidan Betalningtjänst, ställa in kreditkorttyper för American Express Discover och MasterCard på sian Kreditkorttyp och aktivera leverantören som standardleverantören. Du måste även följa stegen för att slutföra inställningarna:
-   På sidan Parametrar för kundreskontra anger du parametrar för att använda kreditkortskontroller.
-   På sidan Betalningsvillkor ställer du in betalningsvillkor för kreditkort. I fältet Betalningstyp väljer du Kreditkort.
-   På sidan Kundkreditokort anger du kreditkortsinformation för kunder.

## <a name="adding-a-new-credit-card"></a>Lägg till ett nytt kreditkort
Du kan skapa nya kreditkortsposter på sidan Kunder, genom att använda Kund, Inställning, Kreditkort. Du kan också skapa kreditkortsposter när du registrerar försäljningsorder på sidan Försäljningsorder, genom att använda Hantera, Kund, Kreditkort, Register.
Lägg till ett kreditkort till en försäljningsorder
-------------------------------------

Du kan lägga till ett kreditkort till en försäljningsorder, genom att välja ett kreditkort i kreditkortuppslagningen på snabbfliken Pris och rabatter på sidan Försäljningsorder. Om du vill starta behörighetsprocessen, väljer du kreditkort och godkänna i åtgärdsfönstret på fliken Hantera.
Kreditkortskontroll
-------------------------

När ett kreditkort auktoriseras verifieras kortnumret och kortinnehavarens namn, och det tillgängliga kreditsaldot bekräftas. Du kan även verifiera cvv-kod och kortinnehavarens adress verifieras. Kundens tillgängliga kreditsaldo minskas med beloppet på fakturan. Betaltjänsten skickar information om att kreditkortet har godkänts eller avvisats. När en försäljningsorder faktureras, debiteras kreditkortet (samlats in) med fakturabeloppet.

### <a name="card-verification-value"></a>Kortverifieringsnummer

Du kan kräva cvv-kod, som ibland refereras till som kortets säkerhetkod. För American Express är detta ett fyrsiffrigt värde. För Discover, MasterCard och Visa är det ett ensiffrigt värde.

### <a name="address-verification"></a>Adressverifiering

Information om adressverifieringen skickas alltid till betalningsleverantören. Du kan bestämma hur mycket information som krävs för att en transaktion ska godkännas. Se till att kontrollera med din leverantör för att avgöra om denne godkänner denna information. Här följer alternativen för adressverifiering:
-   **Acceptera alltid transaktionen** - Acceptera transaktionen oavsett adressverifieringresultat.
-   **Kontohållare** – Jämför kortinnehavarens namn från transaktionen med kreditkortsföretagets information.
-   **Faktureringsadress** – Jämför kortinnehavarens namn och faktureringsadress från transaktionen med kreditkortsföretagets information.
-   **Postnummer för fakturering** – Jämför kortinnehavarens namn och faktureringsadress och postnummer från transaktionen med kreditkortsföretagets information.

## <a name="data-support"></a>Datasupport
För respektive kreditkortstyp som stöds kan du ange datasupportnivån. Denna nivå kontrollerar hur mycket information om en transaktion överförs till betalningtjänsten. Se till att kontrollera med leverantören för att avgöra om den kan ange den här informationen. Här följer alternativen för datasupportnivån:
-   **Nivå 1** – Överför transaktionsdatum, transaktionsbelopp och beskrivning.
-   **Nivå 2** – Överför all nivå 1-information, plus leverans- och handelsadresser och momsinformation.
-   **Nivå 3** – Överför nivå 2-information, plus information om orderrad.

## <a name="partial-payments"></a>Delbetalningar
Om du levererar en delorder kommer beloppet för denna del av ordern att regitreras; tillståndet, som gällde beloppet för hela ordern, stängs. Ett nytt tillstånd skickas sedan för det återstående beloppet för den order som inte har levererats.

## <a name="voiding-an-authorization"></a>Annullera en auktorisering 
Om du vill annullera en kreditkortskontroll kan du ändra betalningsmetoden till en annan metod som inte har någon typ av kreditkort.






