---
title: Skapa dokument som omfattar programdata
description: 'Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Generera dokument med uppdatering av programdata (Del 4: Ändra format)".'
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
ms.openlocfilehash: 90c6ebc456d3e137e43022fad7d59ce3ca2cdcab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "363900"
---
# <a name="generate-documents-that-have-application-data"></a>Skapa dokument som omfattar programdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Generera dokument med uppdatering av programdata (Del 4: Ändra format)".



Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att generera ett elektroniskt dokument och uppdatera programdata. I den här proceduren ska du köra ER-formatkonfigurationen för att generera Intrastat-rapporten och uppdatera programdata för arkivering av information om rapporteringen.



Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen DEMF. Innan du börjar ska du se till att landet för företaget DEMF är BEL (Belgien).


## <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar
1. Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.
2. Klicka på fliken Nummersekvenser.
    * För att kunna arkivera information om Intrastat-rapporteringen måste vi identifiera poster för varje arkiv vi skapar. För detta måste en särskild nummerserie konfigureras.  
3. Välj referensen Arkiv-ID - Intrastat.
4. Skriv ett värde i fältet Nummerseriekod.
    * Ange eller välj värdet Fore_2 i fältet Nummerseriekod.  
5. ResolveChanges nummerseriekoden.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="run-modified-er-format"></a>Kör det ändrade ER-formatet
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera Intrastat (model) i trädet.
3. Välj Intrastat Intrastat (model)\Intrastat (format) i trädet.
4. Klicka på Kör.
5. Skriv "intrastat2.xml" i fältet Ange filnamn.
    * intrastat2.xml  
6. Klicka på OK.

## <a name="review-er-format-executions-results"></a>Granska resultatet från körningen av ER-formatet
    * Granska den genererade XML-filen.  
1. Stäng sidan.
2. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
    * Öppna detta formulär som innehåller Intrastat-transaktionerna som har inkluderats i det genererade elektroniska dokumentet.  
3. Klicka på Intrastat-arkiv.
    * Eftersom det ER-formatet nu innehåller inställningarna för uppdatering av programdata, har informationen om den slutförda Intrastat-rapporteringen arkiverats. I det här formuläret visas rubrikposten för det skapade arkivet.  
4. Klicka på Detaljer.
    * I det här formuläret visas detaljerna för det skapade arkivet.  
5. Stäng sidan.
6. Stäng sidan.
7. Stäng sidan.

