---
title: Förbered programdata att användas i RCS
description: Stegen i det här avsnittet förklarar hur en användare kan skapa en ny konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för Finance and Operations-program för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS).
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1bd2298240fa789762a350e90888201c5a7ce45
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/04/2019
ms.locfileid: "1726993"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>Förbered programdata att användas i RCS
[!include [task guide banner](../../includes/task-guide-banner.md)]

Följande steg i det här avsnittet förklarar hur användare i rollen i systemadministratör eller utvecklare av ekonomiska rapporter kan skapa en ny konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för Microsoft Dynamics 365 for Finance and Operations-program för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS). Den här konfigurationen används för att utforma ett exempel på en konfiguration av ER-modellmappning för åtkomst till utländska handelstransaktioner. I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i något företag. För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)

## <a name="prerequisites"></a>Förutsättningar
1.  Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**. 
2.  Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md). 
3.  Klicka på **Metadatakonfiguration**. 
4.  Anta att RCS kommer att användas för att utforma en ER-lösning för ett Finance and Operation-program som genererar elektroniska dokument som innehåller information från affärsdomänen för utländsk handel. Om du vill ange mappningen mellan ER-datamodellen och källorna till de data som krävs måste du i RCS få till gång till metadata för Finance and Operation-programmet. Som en del av utformningen av ER-lösning konfigurerar du därför en ny konfiguration av ER-metadata som innehåller alla metadata som för närvarande krävs för att generera ER-rapporter för vald affärsdomän. 

## <a name="add-metadata-configuration"></a>Lägg till metadatakonfiguration 
1.  Klicka på **Skapa konfiguration** om du vill öppna dialogrutan. 
2.  Ange metadata för utländsk handel i fältet **Namn**. 
3.  Klicka på **Skapa konfiguration**. 
4.  Klicka på **Designer**. 
5.  Klicka på **Lägg till**. 
  
> [!NOTE]
> Du kan välja alla metadata för hela programmet eller valda modeller eller valda moduler. Tänk på att följande metadata kommer att läggas till automatiskt i det här fallet: register över poster, uppräkningar och utökade datatyper. Om det behövs ytterligare typer av metadata måste de läggas till manuellt. 
 
Det finns vissa externa handelstransaktioner relaterade till metadata genom att markera metadataelement manuellt. 
  
6.  Klicka på **Lägg till datakälla**. 
7.  Klicka på **Tabellregister**. 
8.  Använd snabbfiltret för att filtrera på fältet **Namn** med värdet Intrastat. 
9.  Väljtabellregister **Intrastat**. 
10. Klicka på **OK**.
  
Vi har lagt till metadatainformation om Intrastat-tabellen med poster. 
  
11. I trädet expanderar du **Tabellregister Intrastat**\>**Relationer**. 
12. I trädet väljer du **Tabellregistr Intrastat**\>**Relations\IntrastatCommodity (Tabellregister EcoResCategory)**.   
13. Klicka på **Lägg till metadata**. 
  
> [!NOTE]
> Du måste lägga till metadata för obligatoriska relationer för det valda register med poster manuellt. 
  
16. Klicka på **Lägg till datakälla**. 
17. Klicka **uppräkning**. 
18. Använd snabbfiltret för att filtrera på fältet **Namn** med värdet IntrastatDirection. 
19. Välj posten **IntrastatDirection enumeration**. 
20. Klicka på **OK**. 
21. Klicka på **Spara**.  
22. Stäng sidan. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>Fyll i utkastet av konfigurationen av metadata
1.  Klicka på **Ändra status**. 
2.  Klicka på **Slutför**. 
3.  Klicka på **OK**. 
4.  Väljden slutförda versionen **1**. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>Exportera den slutförda versionen av metadata-konfigurationen från programmet som XML-fil
1.  Klicka på **Byt**. 
2.  Klicka på **Exportera som XML-fil**. 
3.  Klicka på **OK**. 
    
Den skapade konfigurationen av ER-metadata har sparats som en XML-fil som kan importeras till RCS och användas som källa för information om metadata för den utländska handelsdomänen i Finance and Operations. Utifrån den här informationen kan vi ange mappningen mellan programdata och ER-datamodell.
