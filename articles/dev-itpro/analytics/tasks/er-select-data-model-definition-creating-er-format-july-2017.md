--- 
title: "Välj datamodelldefinitioner när du skapar format"
description: "För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren \"ER Skapa en konfigurationsleverantör och markera den som aktiv\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: dc357db8acbdb98741a694a8a9d3c0c0625c50e4
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Välj datamodelldefinitioner när du skapar format

[!include [task guide banner](../../includes/task-guide-banner.md)]

För att slutföra stegen i den här proceduren måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv". 

Den här proceduren visar hur en modells rotobjekt kan väljas som en datamodelldefinition för att infoga en ER-formatkonfiguration (elektronisk rapportering) som syftar till att skapa elektroniska dokument. I den här proceduren ska du skapa en ER-formatkonfiguration för exempelföretaget Litware, Inc. 

Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av valfri datauppsättning.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.  
2. Klicka på Reporting configurations.

## <a name="add-a-new-er-data-model-configuration"></a>Lägg till en ny konfiguration för ER-datamodell
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
    * Vi lägger till en ny ER-modellkonfiguration som innehåller en datamodell som ska användas som datakälla för generering av ER-rapporter.  
2. Skriv "Payment model (fictitious)" i namnfältet.
    * Betalningsmodell (fiktiv)  
3. Klicka på Skapa konfiguration.
4. Klicka på Designer.
    * Öppna ER-designern för att ange strukturen på datamodellen för den här konfigurationen.  
    * Anta att vi utformar datamodellen för betalningens företagsdomän till att stödja två betalningsmetoder – kreditöverföring och autogiro.  
5. Klicka på Nytt om du vill öppna dialogrutan.
6. Skriv "Payments – credit transfer" i namnfältet.
    * Betalningar - kreditöverföring  
7. Klicka på Lägg till.
8. Klicka på Nytt om du vill öppna dialogrutan.
9. Ange "Modellrot" i fältet "Ny nod som ett fält...".
10. Skriv "Payments – direct debit" i namnfältet.
    * Betalningar - autogirobetalningar  
11. Klicka på Lägg till.
12. Klicka på Spara.
13. Stäng sidan.
14. Klicka på Ändra status.
    * Slutför utkastversionen av modellen för att göra den tillgänglig i nya modellmappningar och format.  
15. Klicka på Slutför.
16. Klicka på OK.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Börja ange en ny ER-formatkonfiguration
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Ange "Format based on data model Payment model (fictitious)" i fältet Ny.
3. Ange eller välj ett värde i fältet Data model definition.
    * Observera att alla rotobjekt i den valda datamodellen kan väljas som datamodelldefinition. Du kan fortsätta att utforma formatet genom att använda de rotobjekt som behövs för datamodellen. Du kan fortsätta även om det saknas en modellmappning för valda rotobjektet.  
4. Stäng sidan.

## <a name="add-a-new-er-model-mapping-configuration"></a>Lägg till en ny konfiguration för ER-modellmappning
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Ange "Model Mapping based on data model Payment model (fictitious)" i fältet Ny.
3. Skriv "Payment model mappings (fictitious)" i namnfältet.
    * Betalningsmodellmappningar (fiktiv)  
4. Ange eller välj ett värde i fältet Data model definition.
5. Klicka på Skapa konfiguration.

## <a name="design-er-model-mappings"></a>Utforma ER-modellmappningar
1. Klicka på Designer.
    * Använd ER-designern om du vill ange modellmappningar för de nödvändiga rotobjekten.  
2. Klicka på Designer.
    * Simulera inställningen för den valda modellmappningen för den valda modellens rotobjekt.  
3. Välj Dynamics 365 for Dynamics 365 for Operations\Table records i trädet.
4. Klicka på Lägg till rot.
5. Skriv "Ledger" i namnfältet.
6. Skriv "LedgerJournalTrans" i fältet Tabell.
    * LedgerJournalTrans  
7. Klicka på OK.
8. Klicka på Spara.
9. Stäng sidan.
10. Stäng sidan.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Börja ange en till ny ER-formatkonfiguration
1. Välj "Payment model (fictitious)" i trädet.
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. Ange "Format based on data model Payment model (fictitious)" i fältet Ny.
4. Ange eller välj ett värde i fältet Data model definition.
    * Observera att det nu bara finns ett rotobjekt tillgängligt att mappa till programmets datakällor. När minst en modellmappning har tagits i bruk kan bara modellens rotobjekt som är mappade till programmet datakällor väljas som modelldefinition när ER-formatet läggs till.   
5. Stäng sidan.


