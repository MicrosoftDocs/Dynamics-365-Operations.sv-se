---
title: "Arbetsyta för bankhantering"
description: "Det här ämnet innehåller information om Arbetsyta för bankhantering. Den här arbetsytan visar information som är relaterat till företagets bankkonton och omfattar en sammanfattningsvy och en sida för analys. Sammanfattningen innehåller sammanfattningsrutor, bankkontoinformation, saldodiagram och relaterad information. Sidan analys använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till bankkontosaldon."
author: saraschi
manager: AnnBe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 3abf4b151b177095b71d44e9a6c9fd8541eaa64e
ms.openlocfilehash: 759de82e9cd1c08f86c0a8eb55fa7bae5c4f740f
ms.contentlocale: sv-se
ms.lasthandoff: 06/14/2017

---
# Arbetsyta för bankhantering
<a id="bank-management-workspace" class="xliff"></a>

Arbetsytan **Bankhantering** visar information som hör till företagets bankkonton. Den här arbetsytan innehåller en **sammanfattningsvy** och en **analyssida**. **Sammanfattningsvyn** innehåller sammanfattningsrutor, bankkontoinformation, saldodiagram och relaterad information. Sidan **analys** använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till bankkontosaldon.

## Sammanfattningsvy
<a id="summary-view" class="xliff"></a>

### Sammanfattning
<a id="summary" class="xliff"></a>

Rutorna i avsnittet **sammanfattning** ger en översikt över dina bankkonton och ger snabb åtkomst till de sidor som du behöver använda oftast. Information för bankavstämning gäller funktionen avancerad bankavstämning. Informationen finns endast för de bankkonton som har alternativet inställt på **avancerad bankavstämning** till **Ja** på sidan **bankkonto**. Från avsnittet **sammanfattning** kan du importera elektroniska bankfilerna för bankkonton över alla juridiska personer.

### Bankkonton
<a id="bank-accounts" class="xliff"></a>

Varje bankkonto hos den juridiska personen representeras av ett kort i avsnittet **bankkonton**. Aktuellt saldo visas och du kan rulla ned till de transaktioner som utgör det sammanfattande balansbeloppet. Beloppet **interimstransaktioner** låter dig också rulla ner till de transaktioner som utgör detta sammanfattande balansbelopp. Interimstransaktioner är alla pågående transaktioner som har bokförts med hjälp av överbryggande funktioner, men som ännu inte har tagits emot. Beloppet **Väntar på saldo** är aktuellt saldo minus överbryggade eller pågående transaktioner.

Kortet visar även när bankkontot senast stämdes av. Den här informationen visas endast om avancerad bankavstämning aktiveras för bankkontot.

### Balans
<a id="balance" class="xliff"></a>

Diagrammet **Saldo** visar antingen historisk saldoinformation för det bankkonto som valts i avsnittet **bankkonton** eller en sammanfattning av information om alla bankkonton hos den juridiska personen historiska saldo. Denna information är tillgänglig för olika perioder: den aktuella veckan, innevarande månad, innevarande år, senaste fem åren och samtliga perioder (den fullständiga historiken över bankkontot). 

Om du förhandsgranskar diagrammet **Saldo** för ett enda bankkonto, visas historiska saldon i bankkontots valuta. Om du visar diagrammet för alla bankkonton i den juridiska personen, visas historiska saldon i redovisningsvaluta.

Information om när data senast uppdaterades visas högst upp i diagrammet. Du kan uppdatera data enligt behov.

### Relaterad information
<a id="related-information" class="xliff"></a>

Från avsnittet **relaterad information** kan du öppna sidan **redovisningsjournal** för att slutföra banköverföringar. Du kan snabbt öppna sidorna **banktransaktioner** och **interimstransaktioner**.

## Analysvy
<a id="analytics-view" class="xliff"></a>

Sidan **analys** ger viktiga mått om bankkonton i det aktuella företaget. Följande visualiseringar är tillgängliga på sidan.

-   Totalt banksaldo i systemvaluta
-   Saldo per juridisk person
-   Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta
-   Saldo per bankkonto
-   Saldo per valuta

Du kan visa bankanalys i alla företag från arbetsytan **kontantöversikt – alla företag**.

