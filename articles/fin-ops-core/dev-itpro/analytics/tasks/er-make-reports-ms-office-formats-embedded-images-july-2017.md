---
title: Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder
description: Det här ämnet beskriver hur du skapar konfigurationer som genererar elektroniska dokument i Excel- och Word-format som innehåller inbäddade bilder.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03a514c5b616d761ef3eb6347e67e645b23eaa1794911775835e77cded4500ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719355"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Utforma konfigurationer för att generera rapporter i Office-format med inbäddade bilder

[!include [banner](../../includes/banner.md)]

För att slutföra stegen i den här proceduren ska du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv". Den här proceduren förklarar hur du skapar konfigurationer för elektronisk rapportering (ER) för att skapa elektroniska dokument som innehåller inbäddade bilder i Microsoft Excel eller Word-dokument. I den här proceduren skapar du de nödvändiga ER-konfigurationerna för exempelföretaget Litware, Inc. Dessa steg kan slutföras med hjälp av USMF-datauppsättning. Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Hämta och spara följande filer innan du börjar: 

| beskrivning                                          | Filnamn                   |
|------------------------------------------------------|-----------------------------|
| Exempel på konfiguration av ER-datamodell.                          | [Modell för checkar.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Konfiguration för ER-fomat                              | [Checkar utskriftsformat.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Bild av företagslogotypen                                   | [Företagslogotyp.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Signaturbild                                      | [Signaturbild.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Alternativ signaturbild                          | [Signaturbild 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word-mall för utskrift av betalningscheckar  | [Checkmall Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>Verifiera förutsättningar  
 1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.  
 2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.   
 3. Klicka på Reporting configurations.  
 
## <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell  
 1. Du kan läsa in konfigurationsfilen för ER-modell (modell för cheques.xml) som du sparat tidigare istället för att skapa en ny modell. Den här filen innehåller exempeldatamodellen för betalningscheckar och mappning av datamodellen till datakomponenterna i programmet Dynamics 365 for Operations.   
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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
