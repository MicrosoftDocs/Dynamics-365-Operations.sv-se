---
title: Skapa en anbudsförfrågan
description: Den här proceduren visar hur du skapar en anbudsförfrågan.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59202cb6678660ae035f9f76ebe4267bac01d78f
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019914"
---
# <a name="create-a-request-for-quotation"></a>Skapa en anbudsförfrågan

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du skapar en anbudsförfrågan. Detta görs normalt av en inköpsagent. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Du måste ha ställt in begäranstyper innan du börjar. När du har slutfört den här uppgiften och du har skapat och har skickat en anbudsförfrågan kan du sedan ange svarstyper per leverantör, jämföra dem och tilldela kontraktet.


## <a name="prepare-a-new-rfq"></a>Förbered en ny anbudsförfrågan
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Anbudsförfrågningar > Alla anbudsförfrågningar**.
2. Klicka på **Ny**.
    Följande inköpstyper finns: Inköpsorder (inställt som standard): ett dokument som bekräftar erbjudandet att köpa produkter eller godkännande av ett erbjudande att sälja produkter i utbyte mot betalning. Inköpsrekvisition: den här typen väljs automatiskt, om du skapar en anbudsförfrågan direkt från en inköpsrekvisition. Om du väljer det här alternativet manuellt får du ett felmeddelande. Inköpsavtal: ett avtal att köpa ett visst kvantitet eller värde av produkt över tid. Om du markerar det här alternativet måste du välja det datumintervall som gäller för inköpsavtalet.  
3. Skriv in ett värde i fältet **Dokumenttitel**.
4. Ange eller välj ett värde i fältet **Typ av begäran**.
    + Om en poängsättningsmetod associeras med typ av begäran kommer detta att bli standardpoängmetoden för den anbudsförfrågan som du skapar. Det går det att ändra poängmetod senare.  
    + I fältet **Leveransdatum**, ange ett datum.  
    + Välj det datum då du vill få artiklarna.  
    + I fältet **Utgångsdatum och tid** anger du datum och tid.  
    + Ange datum och tid då leverantörerna senast måste svara på anbudsförfrågan.  
5. Ange eller välj ett värde i fältet **Lagerställe**. Leveransadressen ska anpassas till lageradressen.  
6. Klicka på **OK**.

## <a name="add-lines"></a>Lägg till rader

När du har angett grundläggande information om anbudsförfrågan anger du de varor eller tjänster som du vill att leverantörerna ska bjuda på. Artikel är standardradtypen.

1. I fältet **artikelnummer** anger du eller väljer ett värde. Om du använder USMF kan du välja T0020.  
2. Ange ett nummer i fältet **Kvantitet**.
3. Klicka på **Lägg till rad**.
4. Välj "Kategori" i fältet **Radtyp**. Du kan använda kategoriradtypen om du vill skapa anbudsförfrågan för lagervaror eller tjänster som inte finns i lager. Sedan måste du välja vilken typ av varor eller tjänster från en hierarki med anskaffningkategorier.  
5. Ange eller välj ett värde i fältet **Anskaffningskategori**.
6. Skriv ett värde i fältet **Produktnamn**.
7. Ange ett nummer i fältet **Kvantitet**.
8. Ange eller välj ett värde i fältet **Enhet**.

## <a name="add-vendors"></a>Lägg till leverantörer
1. Klicka på **Rubrik** för att ändra från radvyn till rubrikvyn. 
2. Visa avsnittet **Leverantör**.
3. Klicka på **Lägg till säljare automatiskt**. Du kan lägga till leverantörer i en anbudsförfrågan automatiskt, baserat på anskaffningkategorin för de begärda artiklarna. Om det inte finns några leverantörer som har godkänts för de kategorier som ingår i raderna kan du lägga till leverantörer manuellt.  
4. Klicka på **Lägg till**.
5. I **leverantörskonto** fält, ange eller välj ett värde.
6. Klicka på **Lägg till**.
7. I **leverantörskonto** fält, ange eller välj ett värde. När du har valt en leverantör, skapas statusen. Detta innebär att leverantörsinformationen har sparats i anbudsförfrågan, men du har inte skickat anbudsförfrågan till leverantören. Du kan lägga till en leverantör i en anbudsförfrågan oavsett leverantörstatusen.  

## <a name="send-the-rfq-to-vendors"></a>Skicka anbudsförfrågan till leverantörer
1. Klicka på **Skicka** i **åtgärdsfönstret**. På sidan Skickar anbudsförfrågan kontrollerar du att leverantörerna i listan är de leverantörer som du vill få anbudsförfrågan från.  
2. Klicka på **Skriv ut**. Denna dialogruta låter dig skriva ut anbudsförfrågan. Om du väljer att skriva ut ett svarsblad, anges i innehållet i detta i Anskaffnings- och källparametrar. Om du väljer hur du skriver ut svarsblad, klickar du på Avancerade utskriftsalternativ när du har öppnat dialogrutan Skriv ut. En anbudsförfrågan ska skrivas ut för varje leverantör som innehåller de rader som har statusen Skapad eller Skickad. Annullerade rader och rader med registrerade svar skrivs inte ut.   
3. Klicka på **Avbryt**.
4. Klicka på **OK**.
5. Stäng sidan.
6. Stäng sidan.

## <a name="view-the-rfq-journal"></a>Visa anbudsförfråganjournalen
1. Gå till **Anskaffning och källa > Anbudsförfrågningar > Uppföljning av anbudsförfrågning > Journaler för anbudsförfrågan**.
2. Klicka på **Förhandsgranska/Skriv ut**.
3. Klicka på **Ursprunglig förhandsgranskning**.
4. Stäng sidan.
5. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]