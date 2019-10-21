---
title: Utforma konfigurationer för att skapa dokument som omfattar programdata
description: 'Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Skapa dokument med uppdatering av programdata (Del 1: Importera konfigurationer).'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9aec1da7fe168b05af10470221ac745ec1c01f6b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182334"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Utforma konfigurationer för att skapa dokument som omfattar programdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren ER Skapa dokument med uppdatering av programdata (Del 1: Importera konfigurationer).



Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument. I den här proceduren ska du köra den importerade ER-formatkonfigurationen som har skapats för exempelföretaget Litware, Inc. för att skapa elektroniska dokument.



Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF. 



Innan du börjar ska du ändra land för DEMF-företaget från DEU (Tyskland) till BEL (Belgien). Klicka på Organisationsadministration > Organisationer > Juridiska personer för att uppdatera landskoden i den primära adressen för den juridiska personen DEMF. Starta om programmet.


## <a name="run-imported-er-format"></a>Kör det importerade ER-formatet
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera Intrastat (model) i trädet.
3. Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.
4. Klicka på Kör.
    * Kör utkastversionen av ER-formatkonfigurationen för att skapa Intrastat-rapporten.  
5. Skriv "intrastat.xml" i fältet Ange filnamn.
    * Ange namnet på filen.  
6. Klicka på OK.
    * Granska den skapade XML-filen.  
7. Stäng sidan.
8. Gå till Skatt > Deklarationer > Utländsk handel > Intrastat.
    * Öppna detta formulär när du vill visa Intrastat-transaktionerna som ingår i det skapade elektroniska dokumentet.  
9. Klicka på Intrastat-arkiv.
    * Eftersom det ER-format som körts inte innehåller några inställningar för uppdatering av programdata, arkiverades inte informationen om den slutförda Intrastat-rapporten.  
10. Stäng sidan.
11. Stäng sidan.

