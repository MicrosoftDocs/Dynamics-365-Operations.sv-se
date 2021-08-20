---
title: Skapa en inköpsreturorder
description: I den här proceduren visas hur du skapar en inköpsreturorder med hjälp av åtgärden Kreditfaktura om du vill kopiera rader från ett leverantörsfakturadokument till en ny inköpsorder.
author: kamaybac
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying, InventMarking, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a391b8dd122bbc9aed57741879fcbca91b9fc26f0caa561702a92e4aaa517bbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738207"
---
# <a name="create-a-purchase-return-order"></a>Skapa en inköpsreturorder

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar en inköpsreturorder med hjälp av åtgärden Kreditfaktura om du vill kopiera rader från ett leverantörsfakturadokument till en ny inköpsorder. Den visar också hur du bekräftar ordern och bearbetar leveransen av varorna tillbaka till leverantören. De exempel som visas i den här proceduren kan användas i demoföretaget USMF. Denna uppgift utförs vanligtvis av en inköpsagent.

## <a name="create-a-new-purchase-return-order"></a>Skapa en ny inköpsreturorder.
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsorder > Alla inköpsorder**. Första steget är att skapa en ny inköpsorder som ska användas som inköpsreturorder.  
2. Klicka på **Ny**.
3. In the **Leverantörskonto**, ange "US-102".
4. Klicka på **OK**.
5. I **Åtgärdsfönstret** klickar du på **Köp**.
6. Klicka på **Kreditfaktura**. Detta är sidan som du kan kopiera från en befintlig leverantörsfaktura till din returorder. Detta är samma sida som används för andra kopieringsåtgärder. Men eftersom du har öppnat den från åtgärden Kreditfaktura konfigureras sidan för att stödja skapandet av en returorder som motbokar leverantörsfakturor.  
7. Expandera avsnittet **Parametrar**.
    - Alternativet **Byt förtecken** väljs automatiskt och kan inte ändras. På så sätt ser du till att tecknet ändras för kvantiteterna och att orderrader som läggs till kommer att motboka leverantörsfakturan.  
    - Alternativet **Kopiera avgifter** väljs automatiskt och kan inte ändras. Det innebär att avgifter från leverantörsfakturan läggs till på inköpsreturordern för att motboka den ursprungliga avgiften. Det är möjligt att ändra ändringarna i sidhuvudet och raderna senare.  
    - Alternativet **Kopiera exakt** väljs automatiskt och kan inte ändras. På så sätt ser du till att en exakt kopia görs av värdena i fälten på leverantörsfakturahuvudet och raderna. Detta innebär att en inköpsreturorder skapas med värden som matchar alla termer som används med leverantörsfakturadokumentet. 
    - Alternativet **Radera inköpsrader** tar bort alla inköpsorderrader som redan finns på inköpsordern som du lägger till de nya raderna. I det här exemplet har vi ännu inte lagt till rader till inköpsreturordern så det ska inte vara någon effekt. Använd det här alternativet försiktigt eftersom det tar bort alla befintliga rader utan ytterligare varning.  
    * Alternativet **Kopiera orderrubrik** väljs automatiskt och kan inte ändras. På så sätt ser du till att informationen kopieras från leverantörsfakturan och tillämpas på orderrubriken för inköpsreturen. Detta är användbart eftersom det blir det enklare att se till att inköpsreturordern motbokar fakturan med hjälp av liknande villkor.  
8. Komprimera avsnittet **Parametrar**.
9. Expandera avsnittet **Fakturor**. Sidan har öppnats från åtgärden Kreditfaktura, så det enda tillgängliga alternativet är att kopiera information från leverantörsfakturor. Den här fliken visar alla tillgängliga fakturor för leverantörskontot som anges på inköpsreturordern som du skapade tidigare.   Fakturorna identifieras av fakturaverifikationen eller inköpsorder-ID.
10. Leta upp leverantörsfakturan som kan identifieras med fakturanumret AP-0006 och välj den raden genom att klicka på något av fälten i den raden.
11. Markera raden genom att klicka i kryssrutan för raden. Observera att raderna som är tillgängliga för leverantörsfakturan väljs automatiskt tillsammans med ordern. Den särskilda leverantörsfakturan har 2 orderrader. För det här exemplet ska du returnera en del av kvantiteten från den andra raden.
12. Välj den andra raden (den med artikel M0006) genom att klicka på något av fälten i den raden.
13. Ändra kvantiteten till 10 i fältet **Kvantitet**. Detta är den kvantiteten som vi sedan returnerar till leverantören. 
14. Markera den första raden (den med artikel M0005) genom att klicka på något av fälten i den raden.
15. Avmarkera kryssrutorna för raden. Endast raderna som du har valt kopieras till din order.
16. Komprimera avsnittet **Fakturor**.
17. Expandera avsnittet **Valda rader eller rubriker som ska kopieras**. Den här vyn visar en sammanfattning av alla dokument och rader som du har valt att kopiera till din order.  
18. Komprimera avsnittet **Valda rader eller rubriker som ska kopieras**.
19. Klicka på **OK**. Raden som du valde har nu kopierats till din inköpsreturorder. Fältet **Kvantitet** visar -10.   
20. I avsnittet **Inköpsorderrad**, klicka på **Lager**.
21. Klicka på **Markering**. Den orderrad som skapades är markerad mot lagertransaktionen från leverantörsfakturan. På så sätt ser du till att lagret som returneras till leverantören är samma som det lager som inlevererades från dem tidigare. Det finns vissa fall där markering inte uppstår, till exempel om lagret redan har markerats som Förbrukat, eller om produkten är en som inte använder markering.  

22. Klicka på **OK**.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Bekräfta och registrera leveransen av varor
1. Klicka på **åtgärder > bekräfta**.
2. I **åtgärdsfönstret**, klicka på **Ta emot**.
3. Klicka på **Produktinleverans**.
    - Den här sidan används till att registrera produktinleveransen för inköpsorder samt för att bearbeta returnerade varor tillbaka till leverantören. Orderrader med en negativ kvantitet innebär att varor ska returneras till leverantören och dokumentet som kan skapas från den här sidan kan användas som följesedel för detta ändamål.   
    - Välj Beställd kvantiteten för det här exemplet i fältet **Kvantitet**. På så sätt ser du till att sändningen bearbetas för hela beställda kvantiteten som orderrader skapades med.   
4. I fältet **Produktinleverans**, skriv ett värde. Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.  
5. Klicka på **OK**. Varorna har nu registrerats som skickade på inköpsreturordern och en produktinleveransjournal har skapats. Du kan använda åtgärden Produktinleverans om du vill granska journalerna som skapats med inköpsordern och se vad som har inlevererats eller returnerats och när.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]