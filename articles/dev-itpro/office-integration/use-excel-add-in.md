---
title: "Använd Excel-tillägget"
description: "Det här avsnittet beskriver hur du öppnar enhetsdata i Microsoft Excel och sedan visar, uppdaterar och redigerar data med Microsoft Dynamics Office-tillägget för Excel."
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 06fc9f8dda83fddea9ae331bb82c8874b15d76b9
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="use-the-excel-add-in"></a>Använd Excel-tillägget

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du öppnar enhetsdata i Microsoft Excel och sedan visar, uppdaterar och redigerar data med Microsoft Dynamics Office-tillägget för Excel. För att öppna enhetsdata kan du starta från Excel eller Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Genom att öppna enhetsdata i Microsoft Excel kan du snabbt och enkelt visa, uppdatera och redigera data med Microsoft Dynamics Office-tillägget för Excel. Det här tillägget kräver Microsoft Excel 2016. **Obs!** om din Microsoft Azure Active Directory (AD Azure)-innehavare har konfigurerats för att använda Active Directory Federation Services (ADFS), måste du se till att uppdateringen från maj 2016 har installerats, så att Excel-tilläggen logga in dig korrekt.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-finance-and-operations"></a>Öppna enhetsdata i Excel när du startar från Dynamics 365 for Finance and Operations
1.  På en sida i Microsoft Dynamics 365 for Finance and Operations klickar du på **Öppna i Microsoft Office**. Om rotdatakällan (register) för sidan är samma som rotdatakällan för alla enheter skapas standardalternativet **öppna i Excel** för sidan. Alternativet **Öppna i Excel** finns på ofta använda sidor, t.ex. **alla leverantörer** och **alla kunder**.
2.  Klicka på alternativet **öppnas i Excel** och öppna en arbetsbok som har skapats. Den här arbetsboken har bindningsinformation för enheten, en pekare till din miljö och en länk till Excel-tillägget.
3.  I Excel klickar du på **skrivskyddet** för att tillåta att Excel-tillägget körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4.  Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget**.
5.  Om du uppmanas att logga in klickar du på **Logga in** och loggar sedan in med samma inloggningsuppgifter som du använde för att logga in på Dynamics 365 for Finance and Operations. Excel-tillägget använder en tidigare inloggningskontext från Internet Explorer och loggar automatiskt in dig, om det kan. Kontrollera därför användarnamnet i det övre högra hörnet av Excel-tillägget.

Excel-tillägget läser automatiskt data för enheten som du har valt. Lägg märke till att det finns inga data i arbetsboken förrän Excel-tillägget läser in den.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Öppna enhetsdata i Excel när du startar från Excel
1.  I Excel på fliken **infoga** i gruppen **tillägg** klickar du på **butik** för att öppna Office Store.
2.  I Office Store.söker du efter nyckelordet "Dynamics" och klickar på **Lägg till** bredvid **Microsoft Dynamics Office-tillägget** (Excel-tillägget).
3.  Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget** för att tillåta att Excel-tillägget körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4.  Klicka på **lägga till information om server** för att öppna fönstret **alternativ**.
5.  Kopiera webbadressen från Dynamics 365 for Finance and Operations.-instansen, klistra in den i fältet **Server-URL** och ta bort allt efter värdnamnet. Den resulterande URL:en ska ha bara värdnamnet.
Exempelvis är URL:en https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage, delete everything except **https://xxx.dynamics.com**.
6.  Klicka på **OK**, och sedan på **Ja** för att bekräfta ändringarna. Excel-tillägget startar om och hämtar metadata. Knappen **Design** är nu tillgänglig. Om Excel-tillägget har knappen **Läs in appletar** är du troligen inte korrekt inloggad som användare. Mer information finns i "Knappen läs in appletar visas" i avsnittet "Felsökning" i det här avsnittet.
7.  Klicka på **Design**. Excel-tillägget hämtar enhetsmetadata.
8.  Klicka på **Lägg till register**. En lista över enheter visas. Enheterna anges i formatet "Namn – etikett".
9.  Välj en enhet i listan, till exempel **kund - kunder**, och klicka sedan på **nästa**.
10. Lägg till ett fält från listan **tillgängliga fält** till listan **markerade fält**, klicka på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet.
11. När du är klar med att lägga till fält till listan **markerade fält**, kontrollera att markören är på rätt plats i kalkylbladet (till exempel cell A1) och klicka sedan på **Klar**. Klicka på **Klart** för att stänga designverktyget.
12. Klicka på **uppdatera** för att dra in en uppsättning data.

## <a name="view-and-update-entity-data-in-excel"></a>Visa och uppdatera enhetsdata i Excel
När Excel-tillägget har läst in enhetsdata i arbetsboken, kan du uppdatera informationen när som helst genom att klicka på **uppdatera** i Excel-tillägget.

## <a name="edit-entity-data-in-excel"></a>Redigera enhetsdata i Excel
Du kan ändra enhetsdata som du vill och sedan publicera den igen genom att klicka på **publicera** i Excel-tillägget. Markera en cell i kalkylbladet om du vill redigera en post och ändra värdet i cellen. Om du vill lägga till en ny post, gör du något av följande:

-   Klicka var som helst i registret för datakällor och klicka sedan på **Ny** i Excel-tillägg.
-   Klicka i den sista raden i registret för datakällor och tryck på TAB tills markören flyttas från den sista kolumnen på samma rad och en ny rad skapas.
-   Klicka i raden direkt under registret för datakällor och börja ange data i en cell. När du flyttar fokus från cellen utökas registret till att inkludera den nya raden.
-   Klicka på någon av rubrikposternas fältbindningar, klicka på ett av fälten och klicka sedan på **Ny** i Excel-tillägget.

Observera att en ny post endast skapas om alla huvud- och obligatoriska fält är bundna i kalkylbladet eller om standardvärden fylldes i med filtervillkoret.
Om du vill ta bort en ny post, gör du något av följande:

-   Högerklicka på radnummer bredvid kalkylbladsraden om du vill ta bort och klicka sedan på **Ta bort**.
-   Högerklicka på radnummer bredvid kalkylbladsraden om du vill ta bort och klicka sedan på **Ta bort** &gt; **registerrader**.
Om datakällor har lagts till som relaterade publiceras inte rubriken före raderna. Om det finns beroenden mellan andra datakällor kan du behöva ändra standardpubliceringsordningen. Om du vill publicera klickar du på knappen **alternativ** (växelsymbol) i Excel-tillägget. Klicka sedan på snabbfliken **dataanslutning** och sedan på **konfigurera publiceringsordning**.

## <a name="add-or-remove-columns"></a>Lägg till eller ta bort kolumner
Du kan använda designern för att justera att kolumnerna läggs till automatiskt i kalkylbladet.

1.  Starta den datakälla som skapat Excel-tillägg genom att klicka på **alternativ**-knappen (växelsymbol) och sedan markera kryssrutan **aktiverar design**.
2.  Klicka på **Design** i Excel-tillägg. Alla datakällor visas.
3.  Bredvid datakällan klickar du på knappen **redigera** (pensymbolen).
4.  Justera listan i **markerade fält** som du behöver:
    -   Lägg till ett fält från listan **tillgängliga fält** till listan **markerade fält**, klicka på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet.
    -   Om du vill ta bort ett fält från listan **Valda fält** klickar du på fältet och sedan på **Ta bort**. Du kan också dubbelklicka på fältet.
    -   Om du vill ändra ordningen på fälten klickar du på fältet i listan **markerade fält** och klickar sedan på **upp** eller **ned**.

5. Gör ändringarna till datakällan genom att klicka på **uppdatering**. Klicka på **Klart** för att stänga designverktyget. 
6. Om du har lagt till ett fält (kolumn) klickar du på **uppdatera** för att ta emot en uppdaterad uppsättning data.

## <a name="troubleshooting"></a>Felsökning
Det finns några problem som kan lösas genom några enkla steg.

-   **Knappen Läs in appletar visas.** Om Excel-tillägget har knappen **Läs in appletar** efter inloggning är du troligen inte korrekt inloggad som användare. Kontrollera att rätt användarnamn visas i det övre högra hörnet av Excel-tillägget för att lösa problemet. Om ett felaktigt användarnamn visas, klickar du på den, loggar ut och loggar sedan in igen.
-   **Felmeddelandet "Förbjudet" visas.** Om felmeddelandet "Förbjudet" visas medan Excel-tillägget läser in metadata, har det konto som är inloggat i Excel-tillägget inte behörighet att använda den riktade tjänsten, instansen eller databasen. Kontrollera att rätt användarnamn visas i det övre högra hörnet av Excel-tillägget för att lösa problemet. Om ett felaktigt användarnamn visas, klickar du på den, loggar ut och loggar sedan in igen.
-   **En tom webbsida visas över Excel.** Om en tom webbsida visas när du loggar in på kontot kräver AD FS, men versionen av Excel som kör tillägget är inte tillräckligt nytt för att läsa in dialogrutan för inloggning Uppdatera versionen av Excel som du använder för att lösa problemet. Uppdatera Excel-versionen när du arbetar i ett företag på den uppskjutna kanalen med [Office distributionsverktyg](https://technet.microsoft.com/library/jj219422.aspx) för att [flytta från uppskjuten kanal till den aktuella kanalen](https://technet.microsoft.com/library/mt455210.aspx).




