---
title: EUR-00002 Skapa en Intrastat-deklaration för EU
description: I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2aba5caaaf0fbee511e1a293b09fa8301bb6831
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408626"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a>EUR-00002 Skapa en Intrastat-deklaration för EU

[!include [banner](../../includes/banner.md)]

I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format. 

Innan du kan slutföra proceduren, måste du överföra transaktioner till Intrastat. 

Proceduren har skapats med demodataföretaget DEMF.


## <a name="import-configurations-with-settings"></a>Importera konfigurationer med inställningar
1. Gå till Arbetsytor > Elektronisk rapportering
2. Klicka på Ställ in aktiv.
3. Klicka på Databaser.
4. Klicka på Öppna.
5. Öppna kolumnfiltret för Konfigurationsnamn.
6. Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”DIntrastat (DE)", med hjälp av filteroperatorn ”börjar med”.
    * Du bör välja konfigurationnamnet som gäller för din juridiska persons land. I den här proceduren används den tyska juridiska personen (till exempel DEMF), därför ska ”Intrastat (DE)” väljas.  
    * Klicka på Importera och sedan på Ja.  
7. Öppna kolumnfiltret för Konfigurationsnamn.
8. Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”intrastat-rapport", med hjälp av filteroperatorn ”börjar med”.
    * Klicka på Importera och sedan på Ja.  

## <a name="set-up-foreign-trade-parameters"></a>Konfigurera utländska handelsparametrar
1. Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.
2. Expandera avsnittet Elektronisk rapportering.
3. Ange eller välj ett värde Intrastat (DE) i fältet Mappning av filformat.
4. Ange eller välj ett värde Intrastat-rapport i fältet Mappning av rapportformat.
5. Expandera avsnittet Avrundningsregler.
    * Du bör ställa in avrundningregler som kan användas i ditt land/din region för Intrastat-rapporteringen.  
6. Ange ett tal i fältet Avrundningsregel.
    * Ange avrundningsprecision, till exempel ”0,01 ".  
7. Ange ett nummer i fältet Antal decimaler för belopp.
    * Ange t.ex. "2".  
8. Markera ett alternativ i fältet Avrundning under 1 kg.
    * Välj t.ex. ”Avrundning till 1 kg”.  
9. Ange ett tal i fältet Avrundningsregel.
    * Ange t.ex. "1" för avrundning av vikt till heltal.  
10. Visa avsnittet Minimigräns.
11. Ange ett nummer i fältet Vikt.
    * Ange ”10” som minsta vikt.  
12. I fältet Belopp, ange ett tal.
    * Ange ”200” som minsta belopp.  
13. Ange eller välj ett värde i fältet Artikel.

## <a name="set-up-compression-of-intrastat"></a>Ställ in komprimering av Intrastat
1. Gå till Moms > Inställningar > Utländsk handel > Komprimering av Intrastat.
2. Klicka på Ta bort.
3. Hitta och markera önskad post i listan.
    * Du kan till exempel välja Artikel i avsnittet Tillgänglig.  
4. Klicka på Lägg till.

## <a name="generate-intrastat-declaration"></a>Generera en Intrastat-deklaration
1. Gå till Moms > Deklarationer > Utländsk handel > Intrastat
2. Klicka på Validera.
    * Valideringen görs i enlighet med fältet Kontrollera inställningar på sidan Utrikeshandelparameter.  
3. Klicka på OK.
4. Klicka på Uppdatera.
5. Klicka på Minimigräns.
6. Ange ett datum i fältet Startdatum.
    * Ange t.ex. januari 2015.  
7. Välj Ja i fältet Komprimera.
8. Ange ett datum i fältet Slutdatum.
    * Ange t.ex. 31 januari 2015.  
9. Klicka på OK.
10. Klicka på Uppdatera.
11. Klicka på Komprimera.
    * Denna komprimering sker enligt hur du ställer in komprimeringen av Intrastat-inställningar.  
12. Ange ett datum i fältet Startdatum.
    * Ange t.ex. januari 2015.  
13. Ange ett datum i fältet Slutdatum.
    * Ange t.ex. 31 januari 2015.  
14. Klicka på OK.
15. Klicka på Uppdatera.
16. Klicka på Generera om löpnummer.
17. Klicka på OK.
18. Klicka på Utdata.
19. Klicka på Rapport.
20. Ange det första datumet i rapporteringperioden i fältet Från-datum.
    * Ange t.ex. datum till 1 januari 2015.  
21. Ange ett datum i fältet Till datum.
    * Ange t.ex. 31 januari 2015.  
22. Välj Ja i fältet Generera fil.
23. Ange ett värde i fältet Filnamn.
24. Välj Ja i fältet Generera rapport.
25. Ange ett värde i fältet Rapportfilnamn.
26. Markera ett alternativ i fältet Riktning.
    * Välj till exempel "Utförsel".  
27. Klicka på OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]