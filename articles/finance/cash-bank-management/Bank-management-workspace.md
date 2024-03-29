---
title: Arbetsyta för bankhantering
description: Det här ämnet innehåller information om Arbetsyta för bankhantering. Den här arbetsytan visar information som hör till företagets bankkonton.
author: angelad116
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f9880928281e704edcd24a75f99d4562761b7c82
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151564"
---
# <a name="bank-management-workspace"></a>Arbetsyta för bankhantering

[!include [banner](../includes/banner.md)]

Arbetsytan **Bankhantering** visar information som hör till företagets bankkonton. Den här arbetsytan innehåller en **sammanfattningsvy** och en **analyssida**. **Sammanfattningsvyn** innehåller sammanfattningsrutor, bankkontoinformation, saldodiagram och relaterad information. Sidan **analys** använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till bankkontosaldon.

## <a name="summary-view"></a>Sammanfattningsvy

### <a name="summary"></a>Sammanfattning

Rutorna i avsnittet **sammanfattning** ger en översikt över dina bankkonton och ger snabb åtkomst till de sidor som du behöver använda oftast. Information för bankavstämning gäller funktionen avancerad bankavstämning. Informationen finns endast för de bankkonton som har alternativet inställt på **avancerad bankavstämning** till **Ja** på sidan **bankkonto**. Från avsnittet **sammanfattning** kan du importera elektroniska bankfilerna för bankkonton över alla juridiska personer.

### <a name="bank-accounts"></a>Bankkonton

Varje bankkonto hos den juridiska personen representeras av ett kort i avsnittet **bankkonton**. Aktuellt saldo visas och du kan rulla ned till de transaktioner som utgör det sammanfattande balansbeloppet. Beloppet **interimstransaktioner** låter dig också rulla ner till de transaktioner som utgör detta sammanfattande balansbelopp. Interimstransaktioner är alla pågående transaktioner som har bokförts med hjälp av överbryggande funktioner, men som ännu inte har tagits emot. Beloppet **Väntar på saldo** är aktuellt saldo minus överbryggade eller pågående transaktioner.

Kortet visar även när bankkontot senast stämdes av. Den här informationen visas endast om avancerad bankavstämning aktiveras för bankkontot.

### <a name="balance"></a>Balans

Diagrammet **Saldo** visar antingen historisk saldoinformation för det bankkonto som valts i avsnittet **bankkonton** eller en sammanfattning av information om alla bankkonton hos den juridiska personen historiska saldo. Denna information är tillgänglig för olika perioder: den aktuella veckan, innevarande månad, innevarande år, senaste fem åren och samtliga perioder (den fullständiga historiken över bankkontot). 

Om du förhandsgranskar diagrammet **Saldo** för ett enda bankkonto, visas historiska saldon i bankkontots valuta. Om du visar diagrammet för alla bankkonton i den juridiska personen, visas historiska saldon i redovisningsvaluta.

Information om när data senast uppdaterades visas högst upp i diagrammet. Du kan uppdatera data enligt behov.

### <a name="related-information"></a>Relaterad information

Från avsnittet **relaterad information** kan du öppna sidan **redovisningsjournal** för att slutföra banköverföringar. Du kan snabbt öppna sidorna **banktransaktioner** och **interimstransaktioner**.

## <a name="analytics-view"></a>Analysvy

Sidan **analys** ger viktiga mått om bankkonton i det aktuella företaget. Följande visualiseringar är tillgängliga på sidan.

-   Totalt banksaldo i systemvaluta
-   Saldo per juridisk person
-   Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta
-   Saldo per bankkonto
-   Saldo per valuta

Du kan visa bankanalys i alla företag från arbetsytan **kontantöversikt – alla företag**. Mer information finns i [Kassaöversikt Power BI-innehåll](Cash-Overview-Power-BI-content.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
