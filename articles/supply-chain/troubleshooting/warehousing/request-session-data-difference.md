---
title: Oväntade skillnader mellan begäran och sessionsdata under testning
description: En oväntad skillnad inträffar mellan begäran och sessionsdata i valideringsresultaten för lagerställets programuppgifter.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456947"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Oväntade skillnader mellan begäran och sessionsdata under testning

Felkod: WarehouseMobileDeroreRequestInputValidationError

## <a name="symptoms"></a>Symtom

När du använder [valideringsramverket för lagerställets programuppgift](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat) returnerar valideraren följande felmeddelande:

> Oväntade skillnader mellan begäran och sessionsdata. XML-protokoll för mobil enhet för lagerställe som överträds. REQUEST_XML_TAMPERING

## <a name="cause"></a>Orsak

Felet uppstår när resultatet från det sista steget som slutfördes i testkörningen inte matchar registrerade indata för nästa steg. Situationen kan uppstå eftersom uppgiftens validerare inte använder resultatet från ett tidigare steg som indata för ett efterföljande steg. Istället används registrerad XML som indata för respektive steg.

I de flesta fall inträffar felet när du kör en uppgift på nytt, men testet kräver vissa poster som ändrats eller tagits bort av en föregående körning av samma uppgift.

## <a name="resolution"></a>Lösning

Valideringstestet för lagerställeprogrammet är inte någon idempotent åtgärd, utan ändrar underliggande data. Innan du kör en uppgift på nytt kanske du därför måste återställa relevanta data.

1. Granska XML-utdata för det senaste lyckade teststeget för att fastställa var testkörningen avbröts.
1. Granska testet och kontrollera att alla nödvändiga försäljningsorder, överföringsorder, arbetsrubriker och andra poster fortfarande finns och i förväntat tillstånd.
1. Skapa om eller redigera saknade eller ändrade poster. Du kan även skapa nya testinställningar och designa testet så att giltiga befintliga poster används.
