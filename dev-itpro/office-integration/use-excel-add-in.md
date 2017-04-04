---
title: "Använd Excel-tillägg"
description: "Det här avsnittet beskrivs hur du öppnar entitetens data i Microsoft Excel och sedan visa, uppdatera och redigera data med Microsoft Dynamics Office-tillägget för Excel. Öppna entitetsdata börjar du med Excel- eller Microsoft Dynamics 365 för operationer."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Använd Excel-tillägg

Det här avsnittet beskrivs hur du öppnar entitetens data i Microsoft Excel och sedan visa, uppdatera och redigera data med Microsoft Dynamics Office-tillägget för Excel. Öppna entitetsdata börjar du med Excel- eller Microsoft Dynamics 365 för operationer.

Genom att öppna entitetens data i Microsoft Excel du snabbt och enkelt visa och redigera data med Microsoft Dynamics Office-tillägget för Excel. Det här tillägget kräver Microsoft Excel 2016. **Anmärkning:** om din Microsoft Azure Active Directory (AD Azure) innehavare har konfigurerats för att använda Active Directory Federation Services (ADFS), måste du se till att maj 2016 uppdateringen har installerats, så att Excel-tillägg kan ska logga in dig.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Öppna entitetsdata i Excel när du startar från Dynamics 365 för operationer
1.  Klicka på en sida i Microsoft Dynamics 365 för operationer **öppen i Microsoft Office**. Om rotdatakällan (register) för sidan är identisk för alla entiteter rotdatakällan standard **öppna i Excel** alternativ genereras för sidan. **Öppna i Excel** alternativ hittar du på vanliga sidor, t ex **alla leverantörer** och **alla kunder**.
2.  Klicka på en **öppnas i Excel** alternativet och öppna en arbetsbok som har skapats. Den här arbetsboken har bindningsinformation för entiteten, en pekare till din miljö och en länk till Excel-tillägg.
3.  I Excel klickar du på **skrivskyddet** att Excel-tillägg som körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4.  Om du använder Excel-tillägg för första gången klickar du på **förtroende tillägget**.
5.  Om du uppmanas att logga in klickar du på **inloggning**, och logga in med samma autentiseringsuppgifter som du använde för att logga in på Dynamics 365 för operationer. Excel-tillägget används en tidigare-modul kontext från Internet Explorer och logga in dig automatiskt, om det går. Därför Kontrollera användarnamnet i det övre högra hörnet av Excel-tillägg.

Excel-tillägget läser automatiskt data för enheten som du har valt. Lägg märke till att det sker inga data i arbetsboken tills står i Excel-tillägg.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Öppna entitetsdata i Excel när du startar från Excel
1.  I Excel på den **infogar** fliken den **tillägg** grupp genom att klicka på **butiken** att öppna Office-arkivet.
2.  Söka efter nyckelordet "Dynamics" i arkivet för Office och klickar på **Lägg till** bredvid det **Microsoft Dynamics Office-tillägget** (Excel-tillägget).
3.  Om du använder Excel-tillägg för första gången klickar du på **förtroende tillägget** att Excel-tillägg som körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4.  Klicka på **lägga till information om server** så att den **alternativ** fönstret.
5.  Kopiera webbläsare Webbadressen från Dynamics 365 mål för operationer instans, klistra in det i den **serverns URL** fältet och ta bort allt efter värdnamnet (t ex bort **/? cmp = usmf & mi = CustTableListPage**). Den resulterande URL: en ska ha bara värdnamnet (t.ex, **https://xxx.dynamics.com**).
6.  Klicka på **OK**, och klicka sedan på **Ja** att bekräfta ändringen. Excel lägger till omstarter och hämtas metadata. Den **Design** knappen är nu tillgänglig. Om Excel-tillägg har en **ladda applets** knappen du troligen inte är inloggad som användare korrekt. Mer information finns i "knappen Läs in tillägg visas" i avsnittet "Felsökning" i det här avsnittet.
7.  Klicka på **Design**. Hämtar enhetsmetadata Excel-tillägg.
8.  Klicka på **Lägg till tabell**. En lista över entiteter visas. Enheterna anges i formatet "– etikett".
9.  Välj en entitet i listan, till exempel **kund - kunder**, och klicka sedan på **nästa**.
10. Lägg till ett fält från den **tillgängliga fält** listan till den **markerade fält**, klickar du på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet.
11. När du har lagt till önskade fält till den **markerade fält** listan, kontrollera att markören är på rätt plats i kalkylbladet (till exempel cell A1) och klicka sedan på **har gjort**. Klicka på **har gjort** vill stänga designern.
12. Klicka på **uppdatera** att dra i en uppsättning data.

## <a name="view-and-update-entity-data-in-excel"></a>Visa och uppdatera entitetsdata i Excel
När Excel-tillägget har läst entitetens data i arbetsboken, kan du uppdatera informationen när som helst genom att klicka på **uppdatera** i Excel-tillägg.

## <a name="edit-entity-data-in-excel"></a>Redigera entitetsdata i Excel
Du kan ändra entitetens data som du behöver och sedan publicera den igen genom att klicka **publicera** i Excel-tillägg. Markera en cell i kalkylbladet om du vill redigera en post och ändra värdet i cellen. Om du vill lägga till en ny post, gör du något av följande:

-   Klicka var som helst i kalkylbladet och klicka sedan på **New** i Excel-tillägg.
-   Klicka i den sista raden i kalkylbladet och tryck på TAB tills markören flyttas från den sista kolumnen på samma rad och en ny rad skapas.
-   Klicka i raden direkt under kalkylbladet och börjar ange data i en cell. När du flyttar fokus från cellen utökas kalkylbladet för att inkludera den nya raden.

Ta bort en post, gör du något av följande:

-   Högerklicka på radnummer bredvid raden kalkylblad om du vill ta bort och klicka sedan på **bort**.
-   Högerklicka på raden kalkylblad om du vill ta bort och klicka sedan på **bort**&gt;**rader**.

## <a name="add-or-remove-columns"></a>Lägg till eller ta bort kolumner
Du kan använda designer för att justera kolumnerna läggs automatiskt till i kalkylbladet.

1.  Starta den datakälla som skapat Excel-tillägg genom att klicka på den **alternativ** knappen (växel-symbol) och sedan välja den **aktiverar design** kryssrutan.
2.  Klicka på **Design** i Excel-tillägg. Alla datakällor visas.
3.  Klicka på bredvid datakällan i **redigera** knappen (symbolen penna).
4.  Justera listan i den **markerade fält** lista som du behöver:
    -   Lägg till ett fält från den **tillgängliga fält** listan till den **markerade fält**, klickar du på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet.
    -   Ta bort ett fält från den **markerade fält**, klickar du på fältet och sedan på **bort**. Du kan också dubbelklicka på fältet.
    -   Om du vill ändra ordningen på fälten klickar du på fältet i den **markerade fält** och klicka sedan på **in** eller **ned**.

5.  Gör ändringarna till datakällan genom att klicka på **uppdatering**. Klicka på **har gjort** vill stänga designern. Om du har lagt till ett fält (kolumn) klickar du på **uppdatera** att ta emot en uppdaterad uppsättning data.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Det finns några problem som kan lösas genom några enkla steg.

-   **Knappen Läs in tillägg visas.** Om Excel-tillägg har en **ladda applets** knappen efter inloggning du troligen inte är inloggad som användare korrekt. Kontrollera att rätt användarnamn visas i det övre högra hörnet av Excel-tillägg för att lösa problemet. Om ett felaktigt användarnamn visas, klickar du på den, logga ut och sedan logga in igen.
-   **Felmeddelandet "Nekad" visas.** Om felmeddelandet "Nekad" visas när Excel-tillägget läses metadata har inte behörighet att använda riktad service, instans eller databas det konto som du är inloggad i Excel-tillägg. Kontrollera att rätt användarnamn visas i det övre högra hörnet av Excel-tillägg för att lösa problemet. Om ett felaktigt användarnamn visas, klickar du på den, logga ut och sedan logga in igen.
-   **En tom webbsida visas under Excel.** Om en tom webbsida visas när du loggar in på kontot måste ADFS. vilken version av Excel med tillägget inte tidigare att läsa in dialogrutan för inloggning Uppdatera version av Excel som du använder för att lösa problemet. Uppdatera Excel-versionen när du arbetar i ett företag på uppskjutna kanalen med den [Office deployment tool](https://technet.microsoft.com/library/jj219422.aspx) till [flytta från uppskjuten kanal till den aktuella kanalen](https://technet.microsoft.com/library/mt455210.aspx).



