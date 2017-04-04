---
title: "Följa upp i KASSAN med försäljningsgrupper provisioner"
description: "Det är vanligt att spåra försäljningen per associera som arbetade med kunden retail – ingripanden, ökad försäljning mellan försäljning och bearbetar transaktionen."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dfefdede8f3bc884b230109d6c915127a1361ecd
ms.lasthandoff: 03/31/2017


---

# <a name="track-commissions-in-pos-using-sales-groups"></a>Följa upp i KASSAN med försäljningsgrupper provisioner

Det är vanligt att spåra försäljningen per associera som arbetade med kunden retail – ingripanden, ökad försäljning mellan försäljning och bearbetar transaktionen.

Spåra försäljning per säljare är ett mått på intresseföretag säljer färdigheter, är ett mått på hastigheten och effektiviteten vid försäljning per kassör. Försäljning per säljare spåras används också ofta att beräkna provision eller andra ersättningar.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Konfigurera en arbetare att en försäljare i kassa
När en anställd har lagts till en försäljningsgrupp kan bli berättigad till kommissionen och kan identifieras i systemet som en säljare. Om personen inte finns i en försäljningsgrupp är inte berättigade till kommissionen och anges inte som en försäljare i punkten för försäljning (PO). I KASSAN hämtas lista över säljare från alla försäljningsgrupper som innehåller minst en arbetare som har tilldelats butiken. I listan visas som en kombination av grupp-ID och namn i POS (ID: namn). En standardgrupp för försäljning kan tilldelas arbetare ge stöd för scenarier där återförsäljaren väljer att bedrev säljaren POS raderna automatiskt. Användarna kan välja från Säljgrupp som anställde tillhör.

## <a name="functionality-profile-settings"></a>Funktionen profilinställningar
Det finns ett antal funktioner profilinställningarna för en butik som bestämmer flödet och process i kassa som berör säljare.

|                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Profile**                           | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Default to cashier when available** | Om det här alternativet aktiveras då POS fylls i automatiskt transaktionsrader med aktuella kassören standardgrupp för försäljning. Om en standard försäljningsgrupp angiven saknar en kassör kan värdet den inte. En användare kan manuellt ange försäljningsgruppen rutnätet för POS knappen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Prompt for sales representative**   | Det här alternativet har tre möjliga värden: ** nr **-om det här alternativet väljs användaren ombeds inte att välja en försäljningsgrupp. Värdet kan fortfarande anges med en kassör standardgrupp för försäljning eller genom att använda en POS knappen manuellt rutnät. **Transaktionens början** - om det här alternativet väljs och antingen den **som standard kassören** alternativet inte har aktiverats eller inte aktuella kassören har en standardgrupp för försäljning, uppmanas användaren att välja en försäljningsgrupp i början av varje transaktion. Välja en försäljningsgrupp varningen visar som standard alla valda försäljningsgruppen efterföljande rader. En användare kan manuellt ange försäljningsgruppen rutnätet för POS knappen. **För varje rad** - om det här alternativet väljs och antingen den **som standard kassören** alternativet inte har aktiverats eller inte aktuella kassören har en standardgrupp för försäljning, uppmanas användaren att välja en försäljningsgrupp efter tillägg av varje rad. En användare kan manuellt ange försäljningsgruppen rutnätet för POS knappen. |
| **Kräver**                           | Det här alternativet gäller endast om POS har konfigurerats för att fråga efter säljare. Om aktiverad uppmanas användaren att välja en försäljningsgrupp innan du fortsätter. Annars kan användaren blir ombedd men avbryta och fortsätta utan att göra ett val. När raden läggs en användare med tillräcklig behörighet kan dock ta bort försäljningsgruppen från raden. "Kräv säljare" används inte för tillfället.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Visa informationen för Försäljningsrepresentant på POS-skärmen transaktioner
POS transaktionen skärmlayout och innehåll kan konfigureras med hjälp av skärmen layout designer och tilldelade Skärmlayouter till butiker, kassor eller arbetare. Den **försäljningsrepresentant** fält kan läggas till på fliken rader i inleveransfönstret.  ID för den angivna gruppen försäljning för varje rad visas på skärmen för transaktionen.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Genom att lägga till knappen representativa operationer som POS rutnät
POS kan du konfigurera knappsatser som ingår i skärmar för att komma åt POS operationer. Knappar på knappsats som berör säljare kan tilldelas följande åtgärder i KASSAN.

|                                           |                                                                                                                                                                                                                                                                                              |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Operation**                             | **Description**                                                                                                                                                                                                                                                                              |
| Ange säljare på rad          | Åtgärden POS visar en lista över grupper berättigad försäljning (ID: namn) för butiken. Om du markerar en Säljgrupp i listan ställs värdet på den aktuella transaktionsraden.                                                                                                            |
| Rensa säljare på rad        | Åtgärden POS tar bort aktuell grupp försäljningsvärde från den aktuella transaktionsraden.                                                                                                                                                                                                  |
| Ange säljare på transaktion   | Åtgärden POS visar en lista över grupper berättigad försäljning (ID: namn) för butiken. Om du markerar en Säljgrupp i listan ställs standardvärdet på aktuell transaktion. Alla befintliga rader utan en försäljningsgrupp tilldelade blir uppsättningen samt alla rader som läggs till i efterhand. |
| Avmarkera försäljningsrepresentant på transaktion | Åtgärden POS tar bort aktuell försäljning grupp standardvärdet från den aktuella transaktionen. Det påverkar inte de rader som redan finns i transaktionen.                                                                                                                             |

## <a name="calculating-commissions"></a>Beräkning av provision
Provisionen beräknas för anställda inom angivna försäljningsgrupper vid tidpunkten för bokföring av försäljningsorder eller utdraget bokförs. Provisionsbeloppet bestäms utifrån arbetarens Provisionsandel, enligt försäljningsgruppen och tillhörande kommissionen beräkningsinställningar för kund- och produkter för transaktionen.


