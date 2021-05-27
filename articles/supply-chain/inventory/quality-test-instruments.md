---
title: Testinstrument för kvalitetshantering
description: I detta ämne beskrivs hur du skapar testinstrument som kan användas för tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021742"
---
# <a name="quality-management-test-instruments"></a>Testinstrument för kvalitetshantering

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du skapar testinstrument som kan användas för tester på kvalitetsorder i Microsoft Dynamics 365 Supply Chain Management.

På sidan **Testinstrument** kan du definiera och visa information om de enheter som används för att utföra tester på kvalitetsorder. Testinstrument är valfria. De kan emellertid hjälpa kvalitetsmedarbetare att veta vilken enhet eller vilket verktyg de bör använda för att utföra ett visst test.

## <a name="test-instrument-example"></a>Exempel på testinstrument

Du utför olika tester på elkomponenter. Vissa tester är avsedda för komponenternas utdata, ett test gäller deras temperatur och ett test gäller deras vikt. Olika verktyg, enheter eller utrustning används för att utföra respektive test. En spänningsmätare används för att mäta spänning, en termometer används för att mäta temperatur, och en våg används för att mäta vikt. Du kan konfigurera var och en av dessa enheter som ett testinstrument och ange måttenheten som testresultatet ska registreras i. Resultat från spänningsmätaren registreras till exempel i volt, resultat från termometern registreras i grader i Fahrenheit eller Celsius, och resultatet från vågen registreras i pund eller kilo.

## <a name="create-a-test-instrument"></a>Skapa ett testinstrument

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Testinstrument**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Testinstrument** – Ange ett unikt ID eller namn för testinstrumentet.
    - **Beskrivning** – Ange en detaljerad beskrivning av testinstrumentet.
    - **Enhet** – Välj den enhet som instrumentmåtten resulterar i. Fältet **Precision** ställs automatiskt in utifrån den enhet du väljer.

1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshanteringstest](quality-tests.md)
- [Testgrupper för kvalitetshantering](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
