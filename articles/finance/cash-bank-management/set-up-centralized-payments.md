---
title: Ställ in centraliserade leverantörsbetalningar
description: Följ dessa steg för att bearbeta betalningar för en juridisk person på uppdrag av andra juridiska personer inom din organisation.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: kfend
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16548572cd70129efcc7dacf0236f3eb4b252d88
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804058"
---
# <a name="set-up-centralized-payments"></a>Ställ in centraliserade leverantörsbetalningar

[!include [banner](../includes/banner.md)]

Följ dessa steg för att bearbeta betalningar för en juridisk person på uppdrag av andra juridiska personer inom din organisation. Innan du börjar måste följande konfiguration ha genomförts:

-   Skapa juridiska personer.
-   Konfigurera redovisningsparametrar och kontoplaner.
-   Konfigurera parametrar i leverantörsreskontra och kundreskontra (beroende på de moduler som använder centraliserade betalningar).
-   Ställ in koncernintern redovisning.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Ställ in en organisationshierarki för centraliserade betalningar
Du måste ställa in en organisationshierarki för centraliserade betalningar. Samma organisationshierarki används för att bearbeta centraliserade leverantörsbetalningar och centraliserade kundbetalningar. 

>[!Note] 
>Strukturen i hierarkin innebär spelar ingen roll för centraliserade betalningar. Alla juridiska personer i hierarkin ska kunna bearbeta betalningar på uppdrag av en annan juridisk person i hierarkin. På sidan **Organisationshierarkier** kan du skapa en ny organisationshierarki. I fältet **Syfte** måste du välja **Centraliserade betalningar**. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Ställ in koncernintern redovisning för centraliserade betalningar
När betalningstransaktioner för den aktuella juridiska personen kvittas mot fakturor i andra juridiska personer skapas transaktioner med lämpliga giltighetsdatum för varje juridisk person. Du måste ange den juridiska personen där eventuella tillämpliga kassarabatter och eventuella realiserade skulder eller förluster bokförs. Innan du börjar måste du fastställa vilken juridisk person du ska använda för betarbetning av kund- och leverantörsbetalningar. Om en juridisk person bearbetar leverantörsbetalningar, men en annan juridisk person bearbetar kundbetalningar måste du växla mellan dem. På sidan **Koncernintern redovisning** kan du välja en koncernintern relationspost för en juridisk person som du ska bearbeta betalningar för. 

På fliken **Centraliserade betalningar** och välj om kassarabatter ska bokföras i den juridiska personen för betalningen (eller någon annan transaktion som minskar saldot på leverantörskontot) eller i den juridiska personen för fakturan (eller någon annan transaktion som ökar saldot på leverantörskontot). Det här valet fungerar tillsammans fältet **Administration av kassarabatt** på sidorna **Parametrar för leverantörsreskontra** och **Parametrar för kundreskontra**. För överbetalnings- och öresdifferenstoleranser används inställningen i den juridiska personen för betalningen. För underbetalnings- och öresdifferenstoleranser används inställningen i den juridiska personen för fakturan.

## <a name="map-vendor-accounts-across-legal-entities"></a>Mappa leverantörskonton över flera juridiska personer
Om du betalar en leverantör från en juridisk person, och du vill välja fakturor för den leverantören i andra juridiska personer, måste du se till att alla motsvarande leverantörskonton i varje juridisk person använder samma adressboks-ID. Om du tar emot betalningar från en kund som betalar fakturor från fler än en juridisk person måste du se till att alla motsvarande kundkonton i samtliga juridiska personer använder samma adressboks-id.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Ställ in bokföringsprofiler för centraliserade betalningar
När du skapar en betalning i en juridisk person som kvittar fakturor i andra juridiska personer, måste båda juridiska personer ha samma bokföringsprofil-ID. Säkerställ att betalningarna skapas korrekt genom att i varje juridisk person för fakturan konfigurera en bokföringsprofil som motsvarar de bokföringsprofiler som används i den juridiska personen för betalningen. Växla till det första juridiska personen för fakturan, och sedan på sidan **Bokföringsprofiler för leverantörer** kan du skapa en ny bokföringsprofil eller redigera en existerande bokföringsprofil. De val du gör för bokföringsprofilen i fakturans juridiska person måste inte matcha bokföringsprofilinställningarna i betalningens juridiska person.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Ställ in betalsätt för centraliserade betalningar
När du skapar en betalning i en juridisk person som kvittar fakturor i andra juridiska personer, måste båda juridiska personer ha samma betalningsmetod-ID. Säkerställ att betalningarna skapas korrekt genom att i varje juridisk person för fakturan konfigurera ett betalsätt som motsvarar de betalsätt som används i den juridiska personen för betalningen. Växla till det första juridiska personen för fakturan, och sedan på sidan **Betalsätt** kan du skapa en ny betalningsmetod eller redigera en befintlig metod för betalning. De val du gör för betalsättet i den juridiska personen för faktureringen måste inte matcha betalningsmetodinställningarna i den juridiska personen för betalningen.

## <a name="set-up-default-descriptions"></a>Ställ in standardbeskrivningar
Du kan ange standardbeskrivningar för koncerninterna kvittningsverifikationer. Standardbeskrivningen inkluderas i transaktioner med giltighetsdatum under kvittningsprocessen mellan företag. På sidan **Standardbeskrivningar** kan du skapa nya beskrivningar för både **Koncernintern kundkvittning** och **Koncernintern leverantörkvittning** genom att välja ett språk och sedan ange text.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
