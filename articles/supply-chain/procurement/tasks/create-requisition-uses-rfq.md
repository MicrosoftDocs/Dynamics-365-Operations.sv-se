---
title: Skapa en rekvisition som använder en anbudsförfrågan
description: I det här avsnittet visas hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88d50c24e84b94128aa3fd567562f3240832910
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578066"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Skapa en rekvisition som använder en anbudsförfrågan

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du lägger till pris- och leverantörsinformation till en inköpsrekvisition från en anbudsförfråganprocess. De exempel som visas i den här handboken kan användas i demoföretaget USMF och du måste vara inloggad som administratör för att utföra alla steg. Uppgifterna i den här handboken utförs normalt av anskaffningsproffs.


## <a name="create-a-requisition"></a>Skapaen rekvisition
1. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. Ange ett datum i fältet **Begärt datum**.
5. Ange ett datum i fältet **Redovisningsdatum**.
6. Välj **OK**.
7. Ange eller välj ett värde i fältet **Orsak**.
8. Välj **Markera rad**.
9. I fältet **Anskaffningskategori** väljer du en kategori i trädet och väljer **OK**.
10. Skriv ett värde i fältet **Produktnamn**.
11. Ange ett nummer i fältet **Kvantitet**.
12. Ange eller välj ett värde i fältet **Enhet**.
13. Välj **Spara**.
14. Klicka på **Arbetsflöde** för att öppna dialogrutan.
15. Välj **skicka**.
16. Stäng sidan.
17. Välj **skicka**.

## <a name="reassign-a-workflow-task"></a>Tilldela om en arbetsflödesuppgift
Nästa uppgift är att skapa en anbudsförfrågan för att få bud från leverantörer för produkten. I USMF-demonstrationdata ställs rekvisitionarbetsflödet in med en regel så att om en leverantör inte är markerad, eller om priset per enhet är 0 för en rad, tilldelas en uppgift till en särskild arbetare för att skapa en anbudsförfrågan. Om du vill fortsätta med den här guiden måste du tilldela om den uppgiften igen till en annan användare (dig själv). Du kan bara göra detta om du är inloggad som administratör.  

1. Klicka på **Arbetsflöde** för att öppna dialogrutan.
2. Välj **Visa historik**.
3. Uppdatera sidan.
4. Expandera avsnittet **Spårningsuppgifter**.
5. Välj raden som startar med ”Arbetsflödet för rad aktiverat på” i trädet.
6. Välj **Visa information om arbetsflöde**.
7. Expandera avsnittet **Arbetsuppgifter**.
8. Välj **Tilldela om**.
9. Välj **Administratör** i fältet **Användare**.
10. Välj **Tilldela om**.
11. Stäng de två sidorna.

## <a name="create-an-rfq"></a>Skapa en anbudsförfrågan

1. Uppdatera sidan.
2. Välj **Anbudsförfrågan**.
3. I fältet **Juridisk person för inköp** väljer du **USMF**. Du måste välja samma juridiska person som finns på rekvisitionraden.  
4. Markera vald rad i listan. Om du har flera rader i din inköpsrekvisition, markerar du alla rader som du vill lägga till i anbudsförfrågan.  
5. Välj **OK**.
6. Uppdatera sidan.
7. Öppna faktaboxen och expandera sedan avsnittet **Relaterade dokument**.
8. Välj länken i fältet **Anbudsförfrågan** för att öppna anbudsförfrågan som just har skapats.
9. Välj **Sidhuvud**.
10. Markera **Lägg till**.
11. I **leverantörskonto** fält, ange eller välj ett värde.
12. Markera **Lägg till**.
13. I **leverantörskonto** fält, ange eller välj ett värde.
14. Välj **Skicka**.
15. Välj **OK**.
16. Välj **Ange svar**.
17. Klicka på **Svar** i åtgärdsfönstret.
18. Välj **Kopiera data till svar**. Då kopieras data, till exempel kvantitet och datum, från anbudsförfrågan till svaret.  
19. Ange ett tal i fältet **Enhetspris**. Detta är priset som du har tagit emot från leverantören. Du kanske också vill ange ytterligare information från leverantören.  
20. Välj **Godkänn**.
21. Välj **OK**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Kontrollera att leverantören och priset har överförts till rekvisitionen
1. Stäng sidan.
2. Markera **rader**
3. Välj **Relaterad information**.
4. Välj **Inköpsrekvisition**.
5. Markera raden som har överförts till anbudsförfrågan. Kontrollera att priset och leverantören har kopierats till rekvisitionen.  
6. Klicka på **Arbetsflöde** för att öppna dialogrutan.
7. Välj Slutför.
8. Välj sidan.
9. Välj Slutför.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]