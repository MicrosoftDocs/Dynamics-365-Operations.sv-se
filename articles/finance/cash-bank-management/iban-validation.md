---
title: Hantera validering av internationellt bankkontonummer (IBAN)
description: Den här artikeln förklarar hur du hanterar validering av internationellt bankkontonummer (IBAN).
author: angelad116
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 0e64c763cb74362503a3d6dfa184b26df77f30b3
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151803"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Hantera validering av internationellt bankkontonummer (IBAN)

[!include [banner](../includes/banner.md)]

Validering av internationellt bankkontonummer (IBAN) ökar mängden validering som görs när du lägger till ett IBAN till ett bankkonto.

Information om IBAN-strukturen lagras i Microsoft Dynamics 365 Finance och läses in automatiskt när du första gången använder IBAN på bankkonton. Den innehåller längden på IBAN, bankkontonumrets startposition och organisationsnumret och längden på kontonumret och organisationsnummer.

## <a name="set-up-iban-structures"></a>Ställ in IBAN-strukturer

1. Gå till **Kassa- och bankhantering \> Inställningar \> IBAN-strukturer**.
2. Observera att IBAN strukturerna för varje land eller region har ställts in automatiskt.
3. Välj knappen **Redigera** om strukturen måste uppdateras för ett specifikt land eller en specifik region.
4. Strukturdefinitionerna kommer att ingå i varje ny utgåva. Du kan använda menyn **Återställ strukturer** för att hämta de senaste definitionerna efter varje uppdatering.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Validera IBAN-strukturen på ett bankkonto

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Skapa ett bankkonto.
3. På snabbfliken **Ytterligare information**, ange ett IBAN.

    Om längden på IBAN inte motsvaras av längden som definieras för varje land eller region, visas ett varningsmeddelande. Du kan inte fortsätta om längden på IBAN inte motsvaras av längden som specificeras i IBAN-strukturen.

    Valideringen kontrollerar även att bankkontonumret stämmer överens med delen i IBAN-numret som representerar numret på bankkontot. Om bankkontonumret inte överensstämmer visas ett varningsmeddelande. Detta meddelande är bara en varning. Du kan fortsätta trots att bankkontonumret inte stämmer överens.

    Valideringen kontrollerar även att bankorganisationsnumret stämmer överens med delen i IBAN-numret som representerar bankorganisationsnumret. Organisationsnumret inkluderar ett banknummer och ofta ett ytterligare bankkontor. Om bankorganisationsnumret inte överensstämmer visas ett varningsmeddelande. Detta meddelande är bara en varning. Du kan fortsätta trots att bankorganisationsnumret inte stämmer överens.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
