---
title: Skapa bokföringskonton för leasing
description: Det här ämnet visar de bokföringskonton som krävs för transaktioner för tillgångsleasing och förklarar hur du definierar bokföringskonton på sidan för Parametrar för bokföring av leasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6e3a0d8dd3bb3e58ca10b2efce0cc88a2f48d2de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859926"
---
# <a name="set-up-lease-posting-accounts"></a>Skapa bokföringskonton för leasing

[!include [banner](../includes/banner.md)]

Det här ämnet visar de bokföringskonton som krävs för transaktioner för tillgångsleasing och förklarar hur du definierar bokföringskonton på sidan **Parametrar för bokföring av leasing**.

För att följa Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16) kanske du behöver skapa konton i din kontoplan. De konton som du skapar för att uppfylla ASC- och IFRS-standarder är dock inte anläggningstillgångskonton. Enligt ASC 842 registreras en ROU-tillgång (Right-Of-Use, tillgång med nyttjanderätt) för både finansiella och operationella leasingar. Dessa leasingar skiljer sig från anläggningstillgångar. (Du kan fortfarande underhålla en ROU-tillgång genom att använda Anläggningstillgångar.)

Mer information om hur du skapar kontostrukturer finns i [Skapa kontostrukturer](../general-ledger/tasks/create-account-structures.md). Mer information om hur du skapar ett huvudkonto finns i [Skapa ett huvudkonto](../general-ledger/tasks/create-main-account.md).

I följande tabell visas exempel på konton som du måste skapa för transaktioner för leasade tillgångar, om de inte redan har skapats. Enligt IFRS 16 används fortfarande operationella leasingrelationer för lågvärdes- och korttidsleasingar.

| Nummer för huvudbokskonto | Kontotyp  | Kontonamn                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Tillgång         | Fordon ROU-tillgång                                     |
| 180160                | Tillgång         | Byggnad ROU-tillgång                                    |
| 180250                | Tillgång         | Ackumulerad avskrivning – fordon                   |
| 180260                | Tillgång         | Ackumulerad avskrivning – byggnader                  |
| 222300                | Skulder     | Kortsiktig skyldighet – finansiella leasingar                |
| 222310                | Balansräkning | Kortsiktig skyldighet – operationella leasingar              |
| 250200                | Skulder     | Egna accepter                                         |
| 250601                | Balansräkning | Långsiktig skyldighet – finansiella leasingar                 |
| 250602                | Balansräkning | Långsiktig skyldighet – operationella leasingar               |
| 250606                | Balansräkning | Uppskov av leasingavgift                                         |
| 300160                | Balansräkning | Balanserade vinstmedel                                     |
| 604500                | Expense       | Leasingkostnad                                         |
| 604501                | Expense       | Operationell leasingkostnad för fordon – räntetillväxt  |
| 604502                | Expense       | Operationell leasingkostnad för fordon – amortering        |
| 605200                | Expense       | Operationell leasingkostnad för byggnader – räntetillväxt |
| 605201                | Expense       | Operationell leasingkostnad för byggnader – amortering       |
| 607101                | Expense       | Amorteringsutgift för fordonsleasing                    |
| 607102                | Expense       | Amorteringsutgift för byggnadsleasing                   |
| 607103                | Expense       | Nedskrivningsutgift – finansiella leasingar                   |
| 607104                | Expense       | Nedskrivningsutgift – operationella leasingar                 |
| 618910                | Expense       | Leasingkostnad – finansiella leasingar                        |
| 618920                | Expense       | Variabla betalningar – finansiella leasingar                    |
| 618930                | Expense       | Variabla betalningar – operationella leasingar                  |
| 800600                | Expense       | Räntekostnad för fordonsleasing                        |
| 800601                | Expense       | Räntekostnad för byggnadsleasing                       |
| 801201                | Balansräkning | Vinst/förlust – leasingändring                      |

## <a name="configure-posting-accounts"></a>Konfigurera bokföringskonton

Om du vill tilldela konton till leasingböcker och grupper som har skapats måste du konfigurera parametrar för tillgångsleasing.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för bokföring av leasing**.
2. På fliken **Konton** öppnar du snabbfliken **Leasingkonton**. Bestäm huvudkonton för finansiell och operationell leasing med motsvarande **Bokföringstyp**. I tabellen ovan visas de konton som är relaterade till operationella och finansiella leasingar.

    > [!NOTE]
    > Det här steget kräver att du konfigurerar separata konton för både operationella och finansiella leasingar för varje bokföringstyp utom **Motbokning av leasingkostnad** och **Öka/minska leasing**. Företag som följer IFRS 16 redovisningsramverk måste lägga till ett huvudkonto för operationell leasing. Men systemet använder inte det här kontot trots att det är ett obligatoriskt fält, eftersom alla leasingar enligt IFRS 16 klassificeras som finansiella leasingar.
    >[!NOTE]
    > **Öka/minska leasing** används som bokföringstyp för ytterligare tillgångsbeaktanden, inklusive **direkta utgifter, leasingincitament, förskottsbetalningar av leasing och nedmonteringskostnader**, men bokförs till ROU-tillgångens huvudkonto vilket som standard är **Leasingtillgång**.        
    
3. Om du vill välja en specifik leasinggrupp som motsvarar huvudkontot, välj **Grupp** i fältet **Kontokod**. I fältet **Konto/gruppnummer** väljer du sedan den leasinggrupp som ska tilldelas huvudkontot.
4. Om du vill tilldela kontokoder till de administrativa kostnader som har konfigurerats i systemet väljer du en kostnad i fältet **Utgiftstyp** på snabbfliken **Verkställighetskostnad**. Tilldela sedan finansiella och operationella konton som ska användas för varje bok.

    > [!NOTE]
    > Det valda finansiella eller operationella kontot kommer att debiteras när fakturan för den planerade utgiften bokförs.
    > **Motbokning av leasingkostnad** används som bokföringstyp för verkställighetskostnadstransaktioner men bokförs på ett definierat **motkonto** på **raderna för betalningsplanen för verkställighetskostnad** i leasinginformationen eller i leasingbokformuläret.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
