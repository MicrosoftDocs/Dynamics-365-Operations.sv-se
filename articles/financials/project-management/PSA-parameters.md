---
title: Integrationsparametrarna Project Service Automation
description: "Du kan konfigurera hur data som ska användas som standar när du integrerar Project Service Automation med Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Integrationsparametrarna Project Service Automation

På sidan **Integrationsparametrarna Project Service Automation** kan du konfigurera hur data ska användas som standard när du integrerar Project Service Automation med Finance and Operations. Följande måste konfigureras för projekt för att synkroniserats från Project Service Automation i Finance and Operations.

> [!NOTE]
> Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.




| **Flik**                      | **Fält**                          | **Beskrivning**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Allmänt**                  | **Standardprojekttyp**               | Markera standard för **projekttyp**, dvs när projekt synkroniseras från Project Service Automation om du inte har angett ett standardvärde i integrationsmallen. Under synkroniseringen kommer nya projekt att ha **projekttyp** inställd på detta värde och kan uppdateras när projektkontraktsrader synkroniseras från Project Service Automation.               |
| **Allmänt**                  | **Tidskategori**                      | Markera standard för **Tidskategori** när timuppskattningar synkroniseras från Project Service Automation. Under synkroniseringen kommer nya timprognoser i projekt i Finance and Operations att ha **kategori** inställt på det här värdet när timuppskattningar och faktiska timmar synkroniseras från Project Service Automation.   |
| **Allmänt**                  | **Avgiftskategori**                       | Markera standard för **Avgiftskategori** när de faktiska avgifterna synkroniseras från Project Service Automation. Under synkroniseringen kommer nya avgiftstransaktioner i Finance and Operations att ha **kategori** inställt på den faktiska avgiften synkroniseras från Project Service Automation.          |
| **Standardvärden för projektgrupp**   | **Projekttyp** | Klicka på **Ny** för att lägga till en rad där du kan välja projekttyp som ska anges i standardgruppen för projektet. En viss projekttyp kan bara väljas en gång i konfigurationen.              
|                              | **Projektgrupp**          | Välj standardprojektgrupp för den angivna projekttypen. När nya projekt synkroniseras från Project Service Automation kommer **Projektgrupp** att vara standard baserat på projekttypen om du inte har angett ett standardvärde i integrationsmallen.  |
| **Standardvärden för typ av fakturering**    | **Faktureringstyp** | Klicka på **Ny** för att lägga till en rad där du kan välja faktureringstyp som ska anges i standardradegenskapen. En viss faktureringstyp kan bara väljas en gång i konfigurationen.          |
|                              | **Radegenskap**| Välj standardradegenskap för den angivna faktureringstypen. Vid nya timuppskattningar, nya utgiftsuppskattningar eller nya faktiska värden synkroniseras från Project Service Automation kommer **radegenskap** att vara standardvärdet baserat på faktureringstypen.          |
| **Funktionslåsning**    |                   | Välj funktionen som ska inaktiveras i Finance and Operations för projekt och kontrakt som härrör från Project Service Automation. Exempelvis kan du välja att inaktivera möjligheten att redigera kontrakt och projekt, skapa arbetsfördelningsstrukturer och ange tidrapporter i Finance and Operations. Redovisningsrelaterade fält fortsätter att vara aktiverade, även om de inte blir tillgängliga genom parameterinställningen. Alla funktioner aktiveras som standard.           |

