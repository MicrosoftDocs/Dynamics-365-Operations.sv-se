--- 
title: "Designa konfigurationer för att generera rapporter i Microsoft Office-format med inbäddade bilder"
description: "I detta avsnitt finns information steg för steg om hur du skapar konfigurationer för elektronisk rapportering (ER) som genererar elektroniska dokument i Microsof Office-format (Excel och Word) och som innehåller inbäddade bilder."
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5e3ba5c76df3dcc5042074a565d102ceaeeadfb0
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="design-configurations-to-generate-reports-in-microsoft-office-formats-with-embedded-images"></a>Designa konfigurationer för att generera rapporter i Microsoft Office-format med inbäddade bilder

[!include [task guide banner](../../includes/task-guide-banner.md)]

För att slutföra stegen i den här proceduren ska du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv". Den här proceduren förklarar hur du skapar konfigurationer för elektronisk rapportering (ER) för att generera elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel eller Microsoft Word-dokument. I den här proceduren skapar du de nödvändiga ER-konfigurationerna för exempelföretaget Litware, Inc. Dessa steg kan slutföras med hjälp av USMF-datauppsättning. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Innan du börjar ska du hämta och spara filerna i hjälpavsnittet [bädda in bilder och former i affärsdokument som skapas med verktyget elektronisk rapportering](../electronic-reporting-embed-images-shapes.md). Filerna är: modell för checkar.xml, utskriftsformat för checkar.xml, företagslogotyp.png, signatur.png, signaturbild 2.png och checkmall för Word.docx.

## <a name="verify-prerequisites"></a>Verifiera förutsättningar  
 1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.  
 2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv".   
 3. Klicka på Reporting configurations.  
 
## <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell  
 1. Du kan läsa in konfigurationsfilen för ER-modell (modell för cheques.xml) som du sparat tidigare istället för att skapa en ny modell. Den här filen innehåller exempeldatamodellen för betalningscheckar och mappning av datamodellen till datakomponenterna i Dynamics 365 for Operations-programmet .   
 2. Klicka på Utbyte på snabbfliken Versioner.   
 3. Klicka på Läs in från XML-fil.  
 4. Klicka på Bläddra och välj Modell för cheques.xml.   
 5. Klicka på OK.  
 6. Den inlästa modellen ska användas som en datakälla för information för att skapa dokument som innehåller bilder i Excel och Word.  

## <a name="add-a-new-er-format-configuration"></a>Lägg till en ny konfiguration för ER-format  
 1. Du kan läsa in konfigurationsfilen för ER-format (Checkutskrift för format.xml) som du sparat tidigare istället för att skapa ett nytt format. Den här filen innehåller exempellayouten på formatet för att skriva ut checkar med det förtryckta formuläret och mappning av detta format till datamodellen ”modell för checkar”.   
 2. Klicka på Byt.  
 3. Klicka på Läs in från XML-fil.  
 4. Klicka på Bläddra och välj checkutskriftsformat (format).xml.   
 5. Klicka på OK.  
 6. Expandera "Modell för checkar" i trädet.  
 7. Välj Model for cheques\Cheques printing format i trädet.  
 8. Det inlästa formatet ska användas för att skapa dokument som innehåller bilder i Excel och Word.   

## <a name="configure-er-user-parameters"></a>Konfigurera ER-användarparametrar  
 1. Klicka på Configurations i åtgärdsfönstret.  
 2. Klicka på User parameters.  
 3. Välj Yes i fältet Run settings.  
  Aktivera flaggan ”kör utkast" för att starta utkastversionen av det markerade formatet i stället för den slutfördaslutfört.  
 4. Klicka på OK.  

## <a name="configure-cash--bank-management-parameters"></a>Konfigurera parametrar för kassa och bankhantering  
 1. Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.  
 2. Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".  
 3. Klicka på Ställ in i åtgärdsfönstret.  
 4. Klicka på Kontrollera.  
 5. Expandera avsnittet Inställningar.  
 6. Klicka på Redigera.  
 7. Välj Ja i fältet Företagslogo.  
 8. Klicka på Företagslogo.  
 9. Klicka på Ändra.  
 10. Klicka på Bläddra och välj filen som du hämtade förut, Company logo.png.   
 11. Klicka på Spara.  
 12. Stäng sidan.  
 13. Expandera avsnittet Signatur.  
 14. Välj Ja i fältet Skriv ut första signatur.  
 15. Klicka på Ändra.  
 16. Klicka på Bläddra och välj filen som du hämtade förut, Signature image.png.   
 17. Expandera avsnittet Kopior.  
 18. Markera ett alternativ i fältet Vattenstämpel.  
 19. Välj Ja i fältet Allmänt elektroniskt exportformat.  
 20. Välj konfigurationen "checkutskriftsformat".  
 21. Nu kommer det valda ER-formatet att användas för utskrift av checkar.  
 22. Klicka på Koppla.  
 23. Klicka på Ny.  
 24. Klicka på Arkiv.  
 25. Klicka på Bläddra och välj filen som du hämtade förut, Signature image 2.png.   
 26. Stäng sidan.  
 27. Stäng sidan.  
 28. Stäng sidan.  
 29. Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.  
 30. Välj Ja i fältet Tillåt att reservationer skapas för inaktiva bankkonton:  
 31. Klicka på Spara.  
 32. Stäng sidan.  

