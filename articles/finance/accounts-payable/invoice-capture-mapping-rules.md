---
title: Mappningsregler för lösningen Invoice Capture
description: Den här artikeln innehåller information om hur mappningsreglerna ställs in i lösningen Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691240"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Mappningsregler för lösningen Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Mappningsregler hämtar grundläggande huvuddata från Microsoft Dynamics 365 Finance eller ERP-systemet (Enterprise Resource Planning). När mappningsregler har ställts in härleds den information som krävs för att skapa leverantörsfakturor i Ekonomi. När mappningsregler används kontrollerar ansvarig för leverantörsreskontra (AP) status istället för att manuellt fylla i alla fältvärden som saknas.

Det finns fyra typer av mappningsregler:

- Juridisk person
- Leverantörskonto
- Objekt
- Utgiftstyp

## <a name="manage-mapping-rules-by-using-the-app"></a>Hantera mappningsregler med hjälp av programmet

Välj inställningar för att hantera mappningsregler med hjälp av **programmet**. Fliken **Inställning av mappningsregel** innehåller fyra alternativ:

- Juridisk person 
- Leverantörskonto 
- Artikelmappning 
- Utgiftstyp

Du kan till exempel välja alternativet **Mappningsregler för juridisk person**. Koden för den juridiska personen identifieras med hjälp av företagsnamnet, adressen och momsregistreringsnumret. För en regel som kallas **LE-USPM** är den juridiska personens kod som innehåller texten "Contoso Robotics USA" innehåller koden för juridisk person **USPM**.

På sidan visas alla aktiva mappningsregler. Om du vill se de inaktiva mappningsreglerna, välj **Regler för aktiv kartläggning av juridiska personer** och välj sedan **Inaktiv mappningsregler för juridisk person**.

Följande åtgärder är tillgängliga för mappningsregler.

### <a name="create-a-mapping-rule"></a>Skapa en mappningsregel

Du kan använda två metoder för att skapa en mappningsregel:

- Välj **Ny** för att skapa en ny mappningsregel. Ange sedan informationen för mappningsregeln. Värdet på **regelnamnet** bör vara unikt för varje typ av mappningsregel.
- Om du väljer en befintlig mappningsregel blir knappen **Kopiera** tillgänglig. Välj det och välj sedan **OK** i dialogrutan som visas. En mappningsregel skapas genom att duplicera den valda regeln.

### <a name="edit-a-mapping-rule"></a>Redigera en mappningsregel

Om du vill redigera en mappningsregel markerar du ett fält och ändrar värdet.

### <a name="activatedeactivate-mapping-rules"></a>Aktivera/inaktivera mappningsregler

Om du vill inaktivera en eller flera mappningsregler markerar du dem på sidan **Aktiva mappningsregler** och väljer sedan **Inaktivera**. Reglerna flyttas från sidan **Aktiva mappningsregler** till sidan **Inaktiva mappningsregler**.

Om du vill aktivera en eller flera mappningsregler markerar du dem på sidan **Inaktiva mappningsregler** och väljer sedan **Aktivera**.

### <a name="remove-mapping-rules"></a>Ta bort mappningregler

För att ta bort mappningsregler, markera dem och välj sedan **Ta bort**.

### <a name="check-for-conflicts"></a>Kontrollera om det finns konflikter

Om två mappningsregler har samma **Juridisk person** och **Leverantörskonto** men olika **Artikelnamn** kommer en konflikt att upptäckas och mappningsregeln kommer inte att skapas eller uppdateras.

## <a name="importexport-mapping-rules-from-excel"></a>Importera/exportera mappningsregler från Excel

Ett Excel-tillägg kan användas för att hantera regler i en batch. Följande alternativ är tillgängliga:

- Hämta Excel-mall.
- Exportera till Excel.
- Importera från Excel.

### <a name="download-an-excel-template"></a>Hämta Excel-mall

Välj **Hämta mall** om du vill hämta en Excel-mall. Välj sedan de fält som ska inkluderas i mallen.

### <a name="export-to-excel"></a>Exportera till Excel

Du kan exportera på två sätt:

- Välj **Öppna i Excel Online** om du vill öppna filen i Excel. Du kan sedan redigera fil online. Välj **Spara** när du är klar. Alla ändringar sparas på sidan **Mappningsregel**.
- Välj **Hämta kalkylblad** för att hämta en Excel-fil som innehåller mappningsregler. Du kan sedan redigera filen. När du är klar väljer du **Importera från Excel** för att överföra det uppdaterade kalkylbladet.

### <a name="import-from-excel"></a>Importera från Excel

1. Välj **Importera från Excel** för att importera data från en XLSX‑fil. Du kan också importera från kommaavgränsade värden (CSV) eller XML-filer. Innan du importerar bör du bestämma om dubbletter ska tillåtas.
2. Välj **Granska mappning** om du vill granska attributmappningen och avgöra om den är korrekt. Du kan ändra mappningsrelationen.
3. När du är klar väljer du **Avsluta import** för att starta importen.
4. Du kan välja **Spåra process** om du vill spåra förloppet för importprocessen.

    Importstatus uppdateras från **Slutför** till **Tolkning**, sedan till **Transformering** och slutligen till **Slutförd**.

När importprocessen är klar visas statistik över lyckade resultat, delfel, fel och totalt bearbetat.
