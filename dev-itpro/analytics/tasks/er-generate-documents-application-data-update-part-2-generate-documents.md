--- 
title: "Generera dokument med programdatauppdatering för elektronisk rapportering (ER)"
description: "Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Generera dokument med uppdatering av programdata (Del 1: Importera konfigurationer)."
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f10faaaffeb7df5be0b37a9b8dbfa5db5c24d2a2
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Generera dokument med programdatauppdatering för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Generera dokument med uppdatering av programdata (Del 1: Importera konfigurationer).



Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att generera ett elektroniskt dokument. I den här proceduren ska du köra den importerade ER-formatkonfigurationen som har skapats för exempelföretaget Litware, Inc. för att skapa elektroniska dokument.



Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF. 



Innan du börjar ska du ändra land för DEMF-företaget från DEU (Tyskland) till BEL (Belgien). Klicka på Organisationsadministration > Organisationer > Juridiska personer för att uppdatera landskoden i den primära adressen för den juridiska personen DEMF. Starta om programmet.


## <a name="run-imported-er-format"></a>Kör det importerade ER-formatet
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera Intrastat (model) i trädet.
3. Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.
4. Klicka på Kör.
    * Kör utkastversionen av ER-formatkonfigurationen för att generera Intrastat-rapporten.  
5. Skriv "intrastat.xml" i fältet Ange filnamn.
    * Ange namnet på filen.  
6. Klicka på OK.
    * Granska den genererade XML-filen.  
7. Stäng sidan.
8. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
    * Öppna detta formulär när du vill visa Intrastat-transaktionerna som ingår i det genererade elektroniska dokumentet.  
9. Klicka på Intrastat-arkiv.
    * Eftersom det ER-format som körts inte innehåller några inställningar för uppdatering av programdata, arkiverades inte informationen om den slutförda Intrastat-rapporten.  
10. Stäng sidan.
11. Stäng sidan.


