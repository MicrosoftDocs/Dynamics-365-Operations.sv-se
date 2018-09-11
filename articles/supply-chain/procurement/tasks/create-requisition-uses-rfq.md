--- 
title: "Skapa en rekvisition som använder en anbudsförfrågan"
description: "Den här handboken visar hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Skapa en rekvisition som använder en anbudsförfrågan

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här handboken visar hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess. De exempel som visas i den här handboken kan användas i demoföretaget USMF och du måste vara inloggad som administratör för att utföra alla steg. Uppgifterna i den här handboken utförs normalt av anskaffningsproffs.


## <a name="create-a-requisition"></a>Skapaen rekvisition
1. Gå till Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett datum i fältet Begärt datum.
5. Ange ett datum i fältet Redovisningsdatum.
6. Klicka på OK.
7. Ange eller välj ett värde i fältet Orsak.
8. Klicka på Lägg till rad.
9. I fältet Anskaffningkategori väljer du kategori i trädet och klickar på OK.
10. Skriv ett värde i fältet Produktnamn.
11. Ange ett tal i fältet Kvantitet.
12. Ange eller välj ett värde i fältet Enhet.
13. Klicka på Spara.
14. Klicka på Arbetsflöde för att öppna dialogrutan.
15. Klicka på Skicka.
16. Stäng sidan.
17. Klicka på Skicka.

## <a name="reassign-a-workflow-task"></a>Tilldela om en arbetsflödesuppgift
    * Nästa uppgift är att skapa en anbudsförfrågan för att få bud från leverantörer för produkten. I USMF-demonstrationdata ställs rekvisitionarbetsflödet in med en regel så att om en leverantör inte är markerad, eller om priset per enhet är 0 för en rad, tilldelas en uppgift till en särskild arbetare för att skapa en anbudsförfrågan. Om du vill fortsätta med den här guiden måste du tilldela om den uppgiften igen till en annan användare (dig själv). Du kan bara göra detta om du är inloggad som administratör.  
1. Klicka på Arbetsflöde för att öppna dialogrutan.
2. Klicka på Visa historik.
3. Uppdatera sidan.
4. Expandera avsnittet Spårningsuppgifter.
5. Välj ”raden som startar med ”Arbetsflödet för rad aktiverat på” i trädet.
6. Klicka på Visa information om arbetsflöde.
7. Expandera avsnittet Arbetsuppgifter.
8. Klicka på Tilldela om.
9. Välj Administraör i fältet Användare.
10. Klicka på Tilldela om.
11. Stäng sidan.
12. Stäng sidan.

## <a name="create-an-rfq"></a>Skapa en anbudsförfrågan
1. Uppdatera sidan.
2. Klicka på Anbudsförfrågan.
3. Välj USMF i fältet Juridisk person för inköp.
    * Du måste välja samma juridiska person som finns på rekvisitionraden.  
4. Markera vald rad i listan.
    * Om du har flera rader i din inköpsrekvisition, markerar du alla rader som du vill lägga till i anbudsförfrågan.  
5. Klicka på OK.
6. Uppdatera sidan.
7. Öppna faktaboxen och expandera sedan avsnittet Relaterade dokument.
    * Du kanske redan har faktaboxen öppen. Sök efter ikonen med en pil till höger om växlingsknapparna rader/rubrik. Om pilen pekar till höger är faktaboxen redan öppen. Om pilen pekar åt vänster klickar du på den för att öppna faktaboxen.  
8. Klicka på länken i fältet Anbudsförfrågan för att öppna anbudsförfrågan som just har skapats.
9. Klicka på Rubrik.
10. Klicka på Lägg till.
11. Ange eller välj ett värde i fältet Leverantörskonto.
12. Klicka på Lägg till.
13. Ange eller välj ett värde i fältet Leverantörskonto.
14. Klicka på Skicka.
15. Klicka på OK.
16. Klicka på Ange svar.
17. Klicka på Svar i åtgärdsfönstret.
18. Klicka på Kopiera data för att svara.
    * Då kopieras data, till exempel kvantitet och datum, från anbudsförfrågan till svaret.  
19. Ange ett tal i fältet Enhetspris.
    * Detta är priset som du har tagit emot från leverantören. Du kanske också vill ange ytterligare information från leverantören.  
20. Klicka på Godkänn.
21. Klicka på OK.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Kontrollera att leverantören och priset har överförts till rekvisitionen
1. Stäng sidan.
2. Klicka på Rader.
3. Klicka på Relaterad information.
4. Klicka på Inköpsrekvisition.
5. Markera raden som har överförts till anbudsförfrågan.
    * Kontrollera att priset och leverantören har kopierats till rekvisitionen.  
6. Klicka på Arbetsflöde för att öppna dialogrutan.
7. Klicka på Slutför.
8. Stäng sidan.
9. Klicka på Slutför.


