---
title: Visa och uppdatera enhetsdata i Excel
description: Det här avsnittet beskriver hur du öppnar enhetsdata i Microsoft Excel och sedan visar, uppdaterar och redigerar data med Microsoft Dynamics Excel-tillägget.
author: jasongre
ms.date: 05/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5090674fc4f7c49c55a8a12aea8c567545d519f
ms.sourcegitcommit: 9f11ce4d24f546e96ab794a23479a43a89b742f0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762665"
---
# <a name="view-and-update-entity-data-with-excel"></a>Visa och uppdatera enhetsdata i Excel 

[!include [applies to](../includes/applies-to-commerce-finance-scm.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]


Det här avsnittet beskriver hur du öppnar enhetsdata i Microsoft Excel och sedan visar, uppdaterar och redigerar data med Microsoft Dynamics Excel-tillägget. För att öppna entitetsdata kan du starta från antingen Excel eller Ekonomi och Drift-appar.

Genom att öppna enhetsdata i Excel kan du snabbt och enkelt visa, uppdatera och redigera data med tillägget för Excel. Det här tillägget kräver Microsoft Excel 2016 eller senare.

> [!NOTE]
> Om din Microsoft Azure Active Directory (Azure AD) klientorganisation har konfigurerats för att använda Active Directory Federation Services (ADFS), måste du se till att uppdateringen för Office från maj 2016 har installerats, så att Excel-tilläggen logga in dig korrekt.

Om du vill veta mer om hur du använder Excel-tillägg, titta på den korta videon [Skapa en Excel-mall för rubriker och mönster](https://youtu.be/RTicLb-6dbI).

## <a name="open-entity-data-in-excel-when-you-start-from-a-finance-and-operations-app"></a>Öppna enhetsdata i Excel när du startar från Ekonomi och Drift-app
1. På en sida i Ekonomi och Drift-app väljer du **Öppna i Microsoft Office**.

    Om rotdatakällan (register) för sidan är samma som rotdatakällan för alla enheter skapas standardalternativet **öppna i Excel** för sidan. Alternativet **Öppna i Excel** finns på ofta använda sidor, t.ex. **alla leverantörer** och **alla kunder**.
 
2. Klicka på alternativet **öppnas i Excel** och öppna en arbetsbok som har skapats. Den här arbetsboken har bindningsinformation för enheten, en pekare till din miljö och en länk till Excel-tillägget.
3. I Excel klickar du på **skrivskyddet** för att tillåta att Excel-tillägget körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4. Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget**.
5. Om du uppmanas att logga in klickar du på **Logga in** och loggar sedan in med samma inloggningsuppgifter som du använde för att logga in på Ekonomi och Drift-app. Excel-tillägget använder en tidigare inloggningskontext från webbläsaren och loggar automatiskt in dig, om det kan. (Mer information om webbläsaren som används baserat på operativsystemet finns i [Webbläsare som används av Office-tillägg](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins). För att säkerställa att inloggningen lyckades, verifiera användarnamnet i det övre högra hörnet av Excel-tillägget. 

Excel-tillägget läser automatiskt data för enheten som du har valt. Lägg märke till att det finns inga data i arbetsboken förrän Excel-tillägget läser in den.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Öppna enhetsdata i Excel när du startar från Excel
1. I Excel på fliken **infoga** i gruppen **tillägg** klickar du på **butik** för att öppna Office Store.
2. I Office Store.söker du efter nyckelordet **Dynamics** och väljer sedan **Lägg till** bredvid **Microsoft Dynamics Office-tillägget** (Excel-tillägget).
3. Om du använder Excel-tillägg för första gången klickar du på **Lita på det här tillägget** för att tillåta att Excel-tillägget körs. Excel-tillägget körs i ett fönster till höger i Excel-fönstret.
4. Klicka på **lägga till information om server** för att öppna fönstret **alternativ**.
5. I webbläsaren kopierar du webbadressen från Ekonomi och Drift-appinstansen, klistra in den i fältet **Server-URL** och ta bort allt efter värdnamnet. Den resulterande URL:en ska ha bara värdnamnet.

    Om URL-adressen är till exempel `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, ta bort allt utom `https://xxx.dynamics.com`.

6. Klicka på **OK**, och sedan på **Ja** för att bekräfta ändringarna. Excel-tillägget startar om och hämtar metadata.

    Knappen **Design** är nu tillgänglig. Om Excel-tillägget har länk **Läs in appletar** är du troligen inte korrekt inloggad som användare. Mer information om hur du tar upp det här problemet finns i avsnittet [Läs in appletar](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane) felsökningsposten.

7. Välj **Design**. Excel-tillägget hämtar enhetsmetadata.
8. Välj **Lägg till registrer**. En lista över enheter visas. Enheterna anges i formatet "Namn – etikett".
9. Välj en enhet i listan, till exempel **kund - kunder**, och klicka sedan på **nästa**.
10. Lägg till ett fält från listan **tillgängliga fält** till listan **markerade fält**, klicka på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet i listan **tillgängliga fält**.
11. När du är klar med att lägga till fält till listan **markerade fält**, kontrollera att markören är på rätt plats i kalkylbladet (till exempel cell A1) och klicka sedan på **Klar**. Klicka på **Klart** för att stänga designverktyget.
12. Klicka på **uppdatera** för att dra in en uppsättning data.

## <a name="view-and-update-entity-data-in-excel"></a>Visa och uppdatera enhetsdata i Excel
När Excel-tillägget har läst in enhetsdata i arbetsboken, kan du uppdatera informationen när som helst genom att klicka på **uppdatera** i Excel-tillägget.

## <a name="edit-entity-data-in-excel"></a>Redigera enhetsdata i Excel
Du kan ändra enhetsdata som du vill och sedan publicera den igen i Ekonomi och Drift-appen genom att klicka på **publicera** i Excel-tillägget. Markera en cell i kalkylbladet om du vill redigera en post och ändra värdet i cellen. Om du vill lägga till en ny post, gör du något av följande:

- Klicka var som helst i registret för datakällor och klicka sedan på **Ny** i Excel-tillägg.
- Klicka i den sista raden i registret för datakällor och tryck på TAB tills markören flyttas från den sista kolumnen på samma rad och en ny rad skapas.
- Klicka i raden direkt under registret för datakällor och börja ange data i en cell. När du flyttar fokus från cellen utökas registret till att inkludera den nya raden.
- Klicka på någon av rubrikposternas fältbindningar, klicka på ett av fälten och klicka sedan på **Ny** i Excel-tillägget.

Observera att en ny post endast skapas om alla huvud- och obligatoriska fält är bundna i kalkylbladet eller om standardvärden fylldes i med filtervillkoret.

Om du vill ta bort en ny post, gör du något av följande:

- Högerklicka på radnummer bredvid kalkylbladsraden om du vill ta bort och klicka sedan på **Ta bort**.
- Högerklicka på radnummer bredvid kalkylbladsraden om du vill ta bort och klicka sedan på **Ta bort** &gt; **Registerrader**.

Om datakällor har lagts till som relaterade datakällor, publiceras inte rubriken före raderna. Om det finns beroenden mellan andra datakällor kan du behöva ändra standardpubliceringsordningen. Om du vill ändra publiceringsordning väljer du knappen **alternativ** (växelsymbol) i Excel-tillägget och sedan snabbfliken **dataanslutning** väljer du **konfigurera publiceringsorder**.

## <a name="add-or-remove-columns"></a>Lägg till eller ta bort kolumner
Du kan använda designern för att justera att kolumnerna läggs till automatiskt i kalkylbladet.

> [!NOTE]
> Om kaeppen **Design** inte visas under knappen **Filter** i Excel-tillägget, måste du aktivera datakällans designer. Välj knappen **alternativ** (växelsymbol) och markera sedan kryssrutan **aktivera design**.

1. Klicka på **Design** i Excel-tillägg. Alla datakällor visas.
2. Bredvid datakällan klickar du på knappen **redigera** (pennsymbolen).
3. I listan **markerade fält** justerar du listan över fält som du behöver:

    - Lägg till ett fält från listan **tillgängliga fält** till listan **markerade fält**, klicka på fältet och sedan på **Lägg till**. Du kan också dubbelklicka på fältet i listan **tillgängliga fält**.
    - Om du vill ta bort ett fält från listan **Valda fält** klickar du på fältet och sedan på **Ta bort**. Du kan också dubbelklicka på fältet.
    - Om du vill ändra ordningen på fälten klickar du på fältet i listan **markerade fält** och klickar sedan på **upp** eller **ned**.

4. Gör ändringarna till datakällan genom att klicka på **uppdatering**. Klicka på **Klart** för att stänga designverktyget.
5. Om du har lagt till ett fält (kolumn) klickar du på **uppdatera** för att ta emot en uppdaterad uppsättning data.

## <a name="change-the-publish-batch-size"></a>Ändra publicera batchstorlek
När användarna publicerar ändringar i dataposter med hjälp av Excel-tillägget skickas uppdateringarna i batchar. Standard (och maximal) publiceringsbatchstorlek är 100 rader; dock ger funktionen **Tillåt konfiguration av publiceringsbatchstorleken i Excel-tillägget** ger dig flexibilitet när det gäller att minska publiceringsbatchstorleken, särskilt om du ser tidsplanering när du försöker publicera uppdateringar från Excel.

Systemadministratörer kan ange en systemomfattande gräns för publicering av batchstorlek för "Öppna i Excel"-arbetsböcker genom att ange fältet **Publicera batchgräns** i avsnittet **Apparametrar** på sidan **Office-apparametrar**.

Publicera batchstorlek kan också ändras för en enskild arbetsbok genom att använda Excel-tillägget.

1. Öppna arbetsboken i Excel.
2. Vöälj knappen **Alternativ** (kugghjul) längst upp till höger i Excel-tillägget.
3. Ställ in fältet **Publicera batchstorlek** efter behov. Värdet du anger måste vara lägre än den systemövergripande publiceringsgränsen för batch.
4. Välj **OK**.
5. Spara arbetsboken. Om du inte sparar arbetsboken efter att du har gjort ändringar i inställningarna för tillägg, finns inte dessa ändringar kvar när arbetsboken öppnas igen.

Författare till Excel-arbetsboksmallar kan använda samma procedur för att ställa in publiceringen av batchstorlek för mallar innan de överför dem till systemet.

## <a name="copy-environment-data"></a>Kopiera miljödata

De data som läses in i arbetsboken från en miljö kan kopieras till en annan miljö. Du kan inte bara ändra anslutnings-URL eftersom datacachen i arbetsboken fortsätter att hantera informationen som befintliga data. I stället måste du använda funktionen Kopiera miljödata och publicera data till en ny miljö som nya data.

1. Välj knappen **alternativ** (växelsymbol) och sedan på snabbfliken **dataanslutning** väljer du **Kopiera miljödata**. 
2. Ange serverns URL för den nya miljön. 
3. Klicka på **OK**, och sedan på **Ja** för att bekräfta åtgärden. Excel-tillägget startas om och ansluts till den nya miljön. Befintliga data i arbetsboken behandlas som nya data.

    När Excel-tillägget startas om anger en meddelanderuta att arbetsboken är i läget Miljökopia.

4. För att kopiera data till den nya miljön som nya data väljer du **publicera**. Om du vill avbryta kopieringen och granska befintliga data i den nya miljön väljer du **uppdatera**.

## <a name="troubleshooting"></a>Felsökning
Det finns några problem som kan lösas genom några enkla steg.

- **Länken "Läs in appletar" visas** – För mer information om detta problem se [Läs in appletar](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane) felsökningsposten. 
- **Felmeddelandet "Förbjudet" visas** – Om felmeddelandet "Förbjudet" visas medan Excel-tillägget läser in metadata, har det konto som är inloggat i Excel-tillägget inte behörighet att använda den riktade tjänsten, instansen eller databasen. Kontrollera att rätt användarnamn visas i det övre högra hörnet av Excel-tillägget för att lösa problemet. Om ett felaktigt användarnamn visas, klickar du på den, loggar ut och loggar sedan in igen.
- **En tom webbsida visas över Excel** – Om en tom webbsida öppnas när du loggar in, kräver kontot AD FS, men versionen av Excel som kör Excel-tillägget är inte tillräcklig nytt för att läsa in dialogrutan för inloggning. Uppdatera versionen av Excel som du använder för att lösa problemet. Uppdatera Excel-versionen när du arbetar i ett företag på den uppskjutna kanalen med [Office distributionsverktyg](/deployoffice/overview-office-deployment-tool) för att [flytta från uppskjuten kanal till den aktuella kanalen](/deployoffice/overview-update-channels).
- **Du får en timeout medan du publicerar dataändringar** - Om du får timeout-meddelanden när du försöker publicera dataändringar till en enhet kan du överväga att minska publiceringsbatchstorleken för den berörda arbetsboken. Enheter som utlöser större mängder logik i poständringar kan kräva uppdateringar som skickas i mindre batchar för att förhindra timeout.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
